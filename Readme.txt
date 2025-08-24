 Configuracion de MySQL
Contraseña:Proolol78@
Puerto:3306

 Creacion de la base de datos manualmente aunque el programa se diseño para que spring boot cree rapidamente las tablas asi evitando errores humanos
 (solo es necesario crear la base de datos y posteriormente ejecutar el programa)

 Crear base de datos
CREATE DATABASE IF NOT EXISTS pruebafullstackdb;
USE pruebafullstackdb;

 Tabla de usuarios
CREATE TABLE usuarios (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    nombre_usuario VARCHAR(50) NOT NULL UNIQUE,
    contrasena VARCHAR(100) NOT NULL
);

 Tabla de tareas
CREATE TABLE tareas (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL,
    descripcion TEXT,
    fecha_limite DATE,
    estado ENUM('pendiente', 'completada') DEFAULT 'pendiente',
    usuario_id BIGINT,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id) ON DELETE CASCADE
);

 Insertar usuarios de prueba
INSERT INTO usuarios (nombre_usuario, contrasena) 
VALUES ('cristian', '1234'),
       ('andres', 'abcd');



 Conexion A la base
url=jdbc:mysql://localhost:3306/PruebaFullStack_db?useSSL=false&serverTimezone=UTC
username=root
password=Proolol78@

 Configuracion inicial del entorno con spring tools en eclipse
Spring Starter Project - Maven - Java_17
Dependencias:
Spring Web (para exponer endpoints REST).
Spring Data JPA (para trabajar con MySQL usando repositorios).
MySQL Driver (para conectar con la base de datos).
Spring Boot DevTools (para recargar más rápido en desarrollo).

