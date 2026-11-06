
# 📚 Clase 12:SQL (Structured Query Language o Lenguaje de Consulta Estructurada

---

## 📌 Resumen de la Clase


Este documento contiene un resumen práctico sobre conceptos fundamentales de bases de datos (**SQL**), **Diagramas de Procesos** y el **Modelo Entidad-Relación (DER)**, incluyendo la simbología, los tipos de conexiones gráficos habituales, un *cheat sheet* de sintaxis y herramientas de benchmarking.

---

## 🗄️ 1. Lenguaje SQL (Structured Query Language)

El lenguaje **SQL** es el estándar utilizado para interactuar con bases de datos relacionales. Se divide principalmente en dos grandes subconjuntos:

### 🔹 DDL (*Data Definition Language*) – Definición de Estructura
Define, modifica y elimina las estructuras de la base de datos (tablas, vistas, índices).
* `CREATE`: Crea nuevas bases de datos o tablas.
* `ALTER`: Modifica la estructura de una tabla existente.
* `DROP`: Elimina objetos (tablas o bases de datos) de forma permanente.

### 🔹 DML (*Data Manipulation Language*) – Manipulación de Datos
Gestiona los datos o registros almacenados dentro de las tablas.
* `SELECT`: Consulta y recupera información almacenada.
* `INSERT`: Agrega nuevos registros a una tabla.
* `UPDATE`: Modifica registros ya existentes.
* `DELETE`: Elimina registros específicos.

---

## ⚡ 2. SQL Cheat Sheet (Comandos y Sintaxis Más Comunes)

### 📌 Consultas Básicas (Queries)
```sql
-- Seleccionar todas las columnas
SELECT * FROM usuarios;

-- Seleccionar columnas específicas con alias y filtro básico
SELECT nombre AS nombre_usuario, email 
FROM usuarios 
WHERE edad >= 18;

-- Eliminar duplicados
SELECT DISTINCT pais FROM clientes;

-- Ordenar resultados (ASC para ascendente, DESC para descendente)
SELECT * FROM productos 
ORDER BY precio DESC;

-- Limitar cantidad de resultados
SELECT * FROM empleados 
LIMIT 10;
```

### 📌 Filtros y Operadores Lógicos (`WHERE`)
```sql
-- Filtros múltiples
SELECT * FROM pedidos 
WHERE estado = 'Enviado' AND total > 100;

-- Coincidencia con patrones (LIKE)
SELECT * FROM clientes WHERE nombre LIKE 'A%';   -- Empieza con 'A'
SELECT * FROM clientes WHERE email LIKE '%@gmail.com'; -- Termina en '@gmail.com'

-- Rangos e Inclusión
SELECT * FROM productos WHERE precio BETWEEN 10 AND 50;
SELECT * FROM usuarios WHERE ciudad IN ('Madrid', 'Barcelona', 'Valencia');

-- Valores Nulos
SELECT * FROM usuarios WHERE telefono IS NULL;
```

### 📌 Manipulación de Datos (DML)
```sql
-- Insertar datos
INSERT INTO usuarios (nombre, email, edad) 
VALUES ('Laura Gómez', 'laura@email.com', 25);

-- Actualizar datos (¡SIEMPRE usar WHERE!)
UPDATE usuarios 
SET edad = 26, ciudad = 'Sevilla' 
WHERE id = 5;

-- Eliminar datos (¡SIEMPRE usar WHERE!)
DELETE FROM usuarios 
WHERE id = 10;
```

### 📌 Uniones de Tablas (`JOINs`)
```sql
-- INNER JOIN: Devuelve coincidencias en ambas tablas
SELECT usuarios.nombre, pedidos.total 
FROM usuarios 
INNER JOIN pedidos ON usuarios.id = pedidos.usuario_id;

-- LEFT JOIN: Todo de la tabla izquierda y lo coincidente de la derecha
SELECT clientes.nombre, facturas.monto 
FROM clientes 
LEFT JOIN facturas ON clientes.id = facturas.cliente_id;
```

### 📌 Agrupación y Funciones de Agregación (`GROUP BY`)
```sql
-- Funciones comunes: COUNT(), SUM(), AVG(), MIN(), MAX()
SELECT categoria_id, COUNT(*) AS total_productos, AVG(precio) AS precio_promedio 
FROM productos 
GROUP BY categoria_id 
HAVING COUNT(*) > 5; -- HAVING filtra sobre el grupo (después de GROUP BY)
```

---

## 🔄 3. Diagramas de Procesos (Flujogramas)

Un **diagrama de procesos** representa de forma gráfica los pasos secuenciales de un flujo de trabajo o algoritmo.

### Simbología Estándar

| Símbolo | Elemento | Descripción |
| :---: | --- | --- |
| `(  )` | **Inicio / Fin** | Representa los puntos de entrada o salida del proceso. |
| `[  ]` | **Proceso / Acción** | Indica una tarea, cálculo o acción a ejecutar. |
| `<  >` | **Decisión** | Evalúa una condición y divide el flujo (ej: *Sí / No*). |
| `/  /` | **Entrada / Salida** | Representa operaciones de lectura o impresión de datos. |

---

## 🔀 4. Diagrama Entidad-Relación (DER)

El **DER** es una herramienta conceptual utilizada para diseñar bases de datos relacionales.

### Componentes Principales

```text
 [ ENTIDAD ]  <--- ( Relación ) --->  [ ENTIDAD ]
      |
 (Atributo)
```

1. **Entidades `[ Rectángulo ]`:** Representan objetos o conceptos del mundo real sobre los cuales se almacena información (ej: `Cliente`, `Producto`).
2. **Atributos `( Óvalo )`:** Propiedades o características que describen a una entidad (ej: `Nombre`, `Precio`).
3. **Relaciones `< Rombo >`:** Muestran la interacción lógica entre dos o más entidades (ej: `Cliente` *realiza* `Compra`).

---

## ➡️ 5. Tipos de Flechas y Líneas de Conexión

Las líneas y flechas comunican la secuencia temporal, jerarquías y dependencias entre elementos.

### Flowchart / Procesos
* **Línea continua con flecha (`--->`):** Flujo principal y secuencia obligatoria paso a paso.
* **Línea discontinuada (`- - ->`):** Flujo condicional, alternativo o paso de datos secundario.

### Cardinalidad en DER (Relaciones entre Entidades)
* **1:1 (Uno a Uno):** Un elemento de la entidad A se asocia con un único elemento de la entidad B.
* **1:N (Uno a Muchos):** Un elemento de A puede vincularse con múltiples elementos en B.
* **N:M (Muchos a Muchos):** Múltiples elementos en A se asocian con múltiples elementos en B.

---

## ⏱️ 6. Software de Benchmarking y Pruebas de Rendimiento en SQL

El **software de benchmarking de bases de datos** se utiliza para medir el rendimiento, la velocidad de procesamiento, la concurrencia y la escalabilidad de un motor SQL bajo cargas de trabajo simuladas o masivas.

* **Utilidad principal:**
  * Evaluar tiempos de respuesta ante transacciones por segundo (TPS).
  * Detectar cuellos de botella en consultas complejas, bloqueos (*locks*) o indexación deficiente.
  * Comparar el rendimiento de distintas plataformas de bases de datos (PostgreSQL, MySQL, SQL Server, Oracle).

* **Herramientas populares de la industria:**
  * **HammerDB:** Estándar de código abierto muy utilizado para pruebas de carga (*load testing*) y estrés en bases de datos relacionales. Soporta múltiples motores y scripts de CI/CD.
  * **Sysbench:** Herramienta modular orientada a evaluar el rendimiento de MySQL/MariaDB y del sistema operativo (operaciones de lectura/escritura).
  * **BenchBase:** Framework enfocado en OLTP (*Online Transaction Processing*) diseñado para comparar arquitecturas de bases de datos mediante cargas transaccionales estandarizadas.
