# Eric_MySql

# tablas

```sql
CREATE DATABASE vtaszfs;
USE vtaszfs;

-- Tabla Clientes

CREATE TABLE Clientes (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
    email VARCHAR(100) UNIQUE
);

-- Tabla UbicacionCliente

CREATE TABLE UbicacionCliente (
    id INT PRIMARY KEY AUTO_INCREMENT,
    cliente_id INT,
    direccion VARCHAR(255),
    ciudad VARCHAR(100),
    estado VARCHAR(50),
    codigo_postal VARCHAR(10),
    pais VARCHAR(50),
    FOREIGN KEY (cliente_id) REFERENCES Clientes(id)
);


-- Tabla Empleados

CREATE TABLE Empleados (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
);
--tabla datosEmpleados

CREATE TABLE datosEmpleados (
id INT PRIMARY KEY AUTO_INCREMENT,
nombre VARCHAR(100),
fechaContratacion DATE
);

--tabla puestos

CREATE TABLE puestos (
id INT PRIMARY KEY AUTO_INCREMENT,
salario INT
);

-- Tabla Proveedores

CREATE TABLE Proveedores (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
    contacto VARCHAR(100),
    telefono VARCHAR(20),
    direccion VARCHAR(255)
);

--TABLA ingresos

CREATE TABLE ingresos (
id INT PRIMARY KEY AUTO_INCREMENT,
Empleados_fk INT,
Productos_fk INT,
CONSTRAINT fk_ingresos_Empleados FOREIGN KEY(Empleados_fk) REFERENCES Empleados(Id_Empleados),
CONSTRAINT fk_ingresos _Productos FOREIGN KEY(Productos_fk) REFERENCES Productos(Id_Productos)
);

-- Tabla TiposProductos

CREATE TABLE TiposProductos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    tipo_nombre VARCHAR(100),
    descripcion TEXT
);

-- Tabla Productos
CREATE TABLE Productos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100),
    precio DECIMAL(10, 2),
    proveedor_id INT,
    tipo_id INT,
    FOREIGN KEY (proveedor_id) REFERENCES Proveedores(id),
    FOREIGN KEY (tipo_id) REFERENCES TiposProductos(id)
);

-- tabla categorias
CREATE TABLE categorias (
	id INT PRIMARY KEY AUTO_INCREMENT,
    aseo VARCHAR(100),
    carnes VARCHAR(100),
    lacteos VARCHAR(100),
    aseo VARCHAR(100)
)

-- Tabla Pedidos
CREATE TABLE Pedidos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    cliente_id INT,
    fecha DATE,
    total DECIMAL(10, 2),
    FOREIGN KEY (cliente_id) REFERENCES Clientes(id)
);

-- Tabla DetallesPedido
CREATE TABLE DetallesPedido (
    id INT PRIMARY KEY AUTO_INCREMENT,
    pedido_id INT,
    producto_id INT,
    cantidad INT,
    precio DECIMAL(10, 2),
    FOREIGN KEY (pedido_id) REFERENCES Pedidos(id),
    FOREIGN KEY (producto_id) REFERENCES Productos(id)
);

-- tabla historialPedidos 

CREATE TABLE historialPedidos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    cambios 

)
```
