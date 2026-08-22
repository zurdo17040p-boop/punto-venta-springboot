# Punto de Venta - instrucciones rápidas

Este ZIP contiene la versión actual del proyecto entregado y el script
necesario para crear la base de datos con datos de ejemplo.

## Requisitos

- Java 21
- MySQL 8
- MySQL Workbench
- Visual Studio Code con Extension Pack for Java y Spring Boot Extension Pack

## 1. Crear la base de datos

1. Abrir MySQL Workbench.
2. Abrir `database/punto_venta.sql`.
3. Ejecutar todo el archivo con el icono del rayo.
4. Actualizar la sección Schemas y comprobar que aparezca `punto_venta`.

## 2. Configurar la contraseña sin editar el proyecto

Abrir PowerShell dentro de la carpeta del proyecto y ejecutar:

```powershell
$env:DB_PASSWORD="AQUI_ESCRIBA_SU_CONTRASEÑA_DE_MYSQL"
```

La contraseña solo queda activa en esa terminal. No debe compartirse ni
subirse a GitHub.

## 3. Ejecutar Spring Boot

En la misma terminal ejecutar:

```powershell
.\mvnw.cmd spring-boot:run
```

El proyecto está listo cuando aparezca:

```text
Tomcat started on port 8080
Started EjemploApplication
```

## 4. Probar las rutas GET

- `http://localhost:8080/clientes`
- `http://localhost:8080/categorias`
- `http://localhost:8080/productos`
- `http://localhost:8080/pedidos`
- `http://localhost:8080/pedidos-detalles`

Los métodos POST pueden probarse desde Postman. Las capturas de la tarea no se
incluyen en este ZIP.

## Nota pendiente

Esta es la versión actual entregada. Quedó pendiente adaptar los POST de
Categoría, Producto, Pedido y PedidoDetalle al patrón exacto de Cliente con
`ResponseEntity<MessageResponse>` y validación de duplicados, según la clase
del 15 de agosto.
