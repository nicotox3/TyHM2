
# 📚 Clase 12:SQL (Structured Query Language o Lenguaje de Consulta Estructurada

---

## 📌 Resumen de la Clase

Este documento contiene un resumen práctico sobre conceptos fundamentales de bases de datos (**SQL**), **Diagramas de Procesos** y el **Modelo Entidad-Relación (DER)**, incluyendo la simbología y los tipos de conexiones gráficos habituales.

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

## 🔄 2. Diagramas de Procesos (Flujogramas)

Un **diagrama de procesos** representa de forma gráfica los pasos secuenciales de un flujo de trabajo o algoritmo.

### Simbología Estándar

| Simbolo | Elemento | Descripción |
| :---: | :--- | :--- |
| `(  )` | **Inicio / Fin** | Representa los puntos de entrada o salida del proceso. |
| `[  ]` | **Proceso / Acción** | Indica una tarea, cálculo o acción a ejecutar. |
| `<  >` | **Decisión** | Evalúa una condición y divide el flujo (ej: *Sí / No*). |
| `/  /` | **Entrada / Salida** | Representa operaciones de lectura o impresión de datos. |

---

## 🔀 3. Diagrama Entidad-Relación (DER)

El **DER** es una herramienta conceptual utilizada para diseñar bases de datos relacionales.

### Componentes Principales

```
 [ ENTIDAD ]  <--- ( Relación ) --->  [ ENTIDAD ]
      |
 (Atributo)
```

1. **Entidades `[ Rectángulo ]`:** Representan objetos o conceptos del mundo real sobre los cuales se almacena información (ej: `Cliente`, `Producto`).
2. **Atributos `( Óvalo )`:** Propiedades o características que describen a una entidad (ej: `Nombre`, `Precio`).
3. **Relaciones `< Rombo >`:** Muestran la interacción lógica entre dos o más entidades (ej: `Cliente` *realiza* `Compra`).

---

## ➡️ 4. Tipos de Flechas y Líneas de Conexión

Las líneas y flechas comunican la secuencia temporal, jerarquías y dependencias entre elementos.

### Flowchart / Procesos
* **Línea continua con flecha (`--->`):** Flujo principal y secuencia obligatoria paso a paso.
* **Línea discontinuada (`- - ->`):** Flujo condicional, alternativo o paso de datos secundario.

### Cardinalidad en DER (Relaciones entre Entidades)
* **1:1 (Uno a Uno):** Un elemento de la entidad A se asocia con un único elemento de la entidad B.
* **1:N (Uno a Muchos):** Un elemento de A puede vincularse con múltiples elementos en B.
* **N:M (Muchos a Muchos):** Múltiples elementos en A se asocian con múltiples elementos en B.
