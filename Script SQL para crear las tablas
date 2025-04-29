-- Crear base de datos (opcional)
CREATE DATABASE IF NOT EXISTS gestion_inventarios;
USE gestion_inventarios;

-- Tabla: categorias
CREATE TABLE categorias (
    categoria_id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(50) NOT NULL,
    descripcion VARCHAR(255)
);

-- Tabla: proveedores
CREATE TABLE proveedores (
    proveedor_id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    contacto VARCHAR(100),
    telefono VARCHAR(20),
    email VARCHAR(100)
);

-- Tabla: productos
CREATE TABLE productos (
    producto_id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    descripcion VARCHAR(255),
    precio DECIMAL(10,2) NOT NULL,
    stock INT NOT NULL,
    categoria_id INT,
    proveedor_id INT,
    FOREIGN KEY (categoria_id) REFERENCES categorias(categoria_id),
    FOREIGN KEY (proveedor_id) REFERENCES proveedores(proveedor_id)
);

-- Tabla: movimientos_inventario
CREATE TABLE movimientos_inventario (
    movimiento_id INT PRIMARY KEY AUTO_INCREMENT,
    producto_id INT,
    fecha DATE NOT NULL,
    tipo VARCHAR(10) NOT NULL, -- 'entrada' o 'salida'
    cantidad INT NOT NULL,
    proveedor_id INT,
    motivo VARCHAR(100),
    FOREIGN KEY (producto_id) REFERENCES productos(producto_id),
    FOREIGN KEY (proveedor_id) REFERENCES proveedores(proveedor_id)
);
