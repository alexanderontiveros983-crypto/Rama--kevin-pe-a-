

### Bitácora Individual de Trabajo

**Nombre del Alumno:** Kevin Alexander Peña Ontiveros  
**Control Escolar:** 24660113  
**Institución:** Instituto Tecnológico de Matehuala  
**Materia / Curso:** Fundamentos de Ingeniería de Software (SCC-1007)  
**Célula:** Célula 5 - Quantum Code  
**Rol Asignado:** Backend  
**Proyecto:** GroStop (E-Commerce Grocery Store)  

---

#### Actividades Realizadas:

* **Clonación y Sincronización del Repositorio:** Comencé el flujo de trabajo conectándome al repositorio oficial del equipo mediante comandos de Git. Procedí a clonar el repositorio en mi entorno local para obtener la estructura base del proyecto, asegurándome de tener la última versión del código y los entregables compartidos por el equipo.
* **Revisión de Requerimientos y Archivos del Líder:** Analicé las directrices enviadas por el líder de la célula y revisé la estructura de archivos del proyecto de comercio electrónico (GroStop) para identificar los scripts de base de datos y la arquitectura del sistema asignada al rol de backend.
* **Configuración del Entorno de Base de Datos (XAMPP & MySQL):** Inicié el servidor local mediante el panel de control de XAMPP, activando los servicios de Apache y MySQL para habilitar el motor de base de datos relacional y el acceso a la plataforma de administración web (phpMyAdmin).
* **Creación y Depuración de la Base de Datos:** Creé la base de datos principal nombrada `quantum-code-grostop` en phpMyAdmin para albergar el esquema relacional del sistema e integrarlo con los componentes del backend.   
* **Importación y Mapeo de Tablas de E-Commerce:** Gestioné la importación masiva del archivo de respaldo SQL, logrando estructurar e inicializar todas las entidades relacionales del sistema, tales como: `admin`, `customer`, `product`, `orders`, `cart`, `category`, `delivery_boy`, `offer`, `product_feedback`, `rates_order_delivery`, `selects`, `seller`, `sells`, y tablas asociativas como `associated_with`, además de vistas y registros de prueba estructurados.   

---
<img width="512" height="272" alt="image" src="https://github.com/user-attachments/assets/cb547d1d-e503-48ea-8d56-a9a7eff4cd13" />






#### Pruebas y Hallazgos en el Sistema:

* Realicé pruebas de integridad y consultas de validación en la interfaz de phpMyAdmin para comprobar que el script se ejecutara correctamente y que las relaciones de claves foráneas (*Foreign Keys*) e índices estuvieran bien vinculadas.   
* Descubrí que la base de datos almacena catálogos completos de productos de supermercado, carritos de compra de usuarios, historial de transacciones, órdenes de entrega y registros de administradores, lo cual facilitará enormemente las pruebas de conexión e integración de las rutas y endpoints del backend.
* Exploré y evalué el uso de herramientas complementarias como editores de texto plano (Bloc de notas) para la manipulación y pre-procesamiento de archivos de texto estructurado de gran volumen antes de su ejecución en el servidor local de base de datos.

---

#### Errores Encontrados y Soluciones Aplicadas:

* **Problema 1 (Incompatibilidad de Collation):** Al intentar importar el archivo `.sql` proporcionado por el equipo en phpMyAdmin, el motor de base de datos arrojó un error crítico de sintaxis y compatibilidad: `MySQL ha dicho: #1273 - Collation desconocida: 'utf8mb4_0900_ai_ci'`. Esto sucedió debido a una discrepancia de versiones entre el servidor MySQL de origen (más reciente) y la versión local en ejecución dentro de nuestro entorno de pruebas de XAMPP.   
* **Solución 1:** Se abrió el archivo de respaldo `.sql` mediante un editor de texto avanzado y se aplicó una búsqueda y reemplazo masiva de todas las ocurrencias del cotejamiento incompatible (`utf8mb4_0900_ai_ci`) sustituyéndolas por el estándar compatible `utf8mb4_general_ci`. Posteriormente, se reintentó la importación del script modificado, logrando que el intérprete de MySQL procesara todas las consultas de forma exitosa y sin interrupciones.   
* **Problema 2 (Manejo de Nombres de Bases de Datos con Caracteres Especiales):** Al inicializar la base de datos con el nombre provisto por la célula (`quantum-code-grostop`), se identificó la presencia de guiones medios (`-`), los cuales pueden generar conflictos de interpretación en consultas SQL directas si no se delimitan apropiadamente.
* **Solución 2:** Se estandarizó el uso de comillas invertidas (backticks: `` `quantum-code-grostop` ``) en los scripts y operaciones de consola para asegurar que el motor de base de datos identificara correctamente el esquema sin arrojar errores de sintaxis.

---

#### Dudas o Aspectos por Aclarar:

* Validar en el próximo checkpoint con el equipo de frontend y los demás integrantes de la célula si los nombres de las tablas y los campos de las llaves foráneas coinciden exactamente con los modelos definidos en el código del servidor para evitar fallos de mapeo al momento de realizar las peticiones HTTP y consultas CRUD.
* Confirmar si se realizarán inserciones masivas adicionales de datos de prueba o si trabajaremos directamente sobre los registros actuales para las pruebas funcionales de la plataforma GroStop.

*(Nota: Agrega un nuevo bloque "Registro Diario de Actividades" al final de este archivo por cada día que trabajes en el proyecto)*
