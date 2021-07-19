# ApiCorePagos

FUENTES:
-	Descargue el archivo CorePagos.Api.rar y descomprímalo en donde desea alojar su Api.
-	Descargue el BackUp de la BD dbComercioElectronico.bak y restáurelo en su SQLServer.

CONFIGURACION BD EN EL API:
-	Al abrir su proyecto CorePagos.Api encontrara un archivo de configuración llamado appsettings.json donde encontrar el String de Conexión a la BD por favor modifique la conexión actual por la conexión de su BD.

Métodos Expuesto:
El método para realizar la factura es  api/Facturar/GenerarFactura de tipo POST el cual recibe un JSON con la siguiente estructura: 
{
    "DocumentoCliente":"1037609719", //Id de la tabla Usuarios
    "Productos": "OF_003,OF-001,PC-002" //Listado de id Productos separados por ‘,’
}

Este método se encarga de realizar la suma del pedido del cliente, crea el pedido en la tabla Pedios y envía un Email de confirmación al correo del usuario que tenga registrado en BD.

Existen varios métodos para la consulta de las diferentes tablas de la BD los cuales son:
-	Consultar métodos de pago y su estado:
•	api/MetodosPagoes Devuelve un listado con todos los métodos de pagos disponible con su estado actual.

-	 Consultar Pedidos:
•	api/Pedidoes Devuelve un listado con todos los pedidos Existentes.

-	Consultar Productos:
•	api/Productos Devuelve un listado con todos los productos Existentes.

-	Consultar Usuarios:
          api/Productos Devuelve un listado con todos los productos Existentes.



Para el desarrollo del API se utilizo:
System.Net.Mail: Contiene clases que se utilizan para enviar correo electrónico a un servidor de Protocolo simple de transferencia de correo (SMTP) para su entrega.
CorePagos.Api.BL: Clases donde se encuentra lo lógica interna o lógica del negocio.
CorePagos.Api.Data: Clases donde se encuentra la lógica que correspondiente a la interacción con la base de datos.
System.Collections.Generic: Contiene interfaces y clases que definen colecciones genéricas, que permiten a los usuarios crear colecciones fuertemente tipadas que brindan una mejor seguridad y rendimiento de tipos que las colecciones no genéricas fuertemente tipadas. 
Se utiliza en el desarrollo para la creación de listas.

Microsoft.EntityFrameworkCore: Utilizado para crear un modelo del BD en el ambiente .Net y poder utilizar las tablas como entidades propias de .Net

System.Linq: Proporciona clases e interfaces que admiten consultas que utilizan Language-Integrated Query.  Utilizado para realizar Query con las entidades creadas con el EntityFramework de la BD.


# Consideraciones:

En proyecto se esta presentado un error al realizar el Guardado del pedido en la BD ya que indica que el Objeto de nombre Producto no es valido, como se puede observar en el código arriba de donde se encuentra el comentario //Creacion del Pedido en BD Se puede apreciar como se instancia una variable de tipo Producto y se le setean los valores para posteriormente ser enviada en el .Add para su guardado en BD.





