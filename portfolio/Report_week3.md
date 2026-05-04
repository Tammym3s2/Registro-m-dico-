Sistema de Gestión Veterinaria "Mundo Animal"
Semana:(Abril 13 - 17)

**Rol de The data modeler (Alejandra Porras).
Durante esta semana, el enfoque principal fue la arquitectura y el diseño técnico 
de la base de datos en MongoDB. Se establecieron los cimientos necesarios para que 
el sistema de la veterinaria sea escalable y profesional:


•Modelado de Entidades: Se definieron y estructuraron las tres colecciones fundamentales: 
pets para el registro de pacientes, medications para el control de inventario y sales para 
la gestión transaccional.
•Gestión de Inventario: Se configuró la colección de medicamentos con identificadores únicos
(IDs), precios unitarios y categorías médicas estandarizadas.
•Sistema de Transacciones Profesionales: Se diseñó una estructura de ventas que permite vincular 
servicios profesionales (como consultas y baños) con productos de farmacia en un solo movimiento contable.

🧠 2. Desafíos y Soluciones
Durante el proceso de diseño surgieron retos importantes. Inicialmente, el esquema de ventas presentaba una 
inconsistencia en el idioma, mezclando términos en español e inglés, lo cual se resolvió mediante una reestructuración 
completa para unificar todo el sistema bajo estándares globales.
Otro desafío fue la lógica de negocio en la colección de ventas; al principio, los registros solo consideraban productos de 
farmacia, omitiendo los servicios un profesionales que son la base de una veterinaria. Para solucionar esto, se rediseñó el JSON
de ventas para incluir un arreglo de ítems capaz de soportar múltiples servicios y productos simultáneamente. Por último, se 
trabajó minuciosamente en garantizar que cada transacción estuviera perfectamente vinculada a los dueños registrados en el sistema,
asegurando que la información sea coherente y no existan registros huérfanos.

** Rol de Query Developer (Tammy Nashely)

En mi calidad de Constructor MQL (MongoDB Query Language), asumí la responsabilidad de diseñar, implementar y optimizar la capa de recuperación 
de datos del sistema. Mi enfoque principal fue garantizar que la comunicación entre el servidor Node.js y el clúster de MongoDB Atlas fuera eficiente,
permitiendo al equipo administrativo acceder a información crítica de los pacientes de manera instantánea.

•Implementaciones Técnicas
Desarrollé una arquitectura de consultas orientada a la flexibilidad del usuario, destacando los siguientes hitos técnicos:
* Segmentación por Especie: Implementé filtros lógicos para clasificar la población de pacientes (caninos, felinos, etc.), permitiendo una visualización 
organizada de la carga de trabajo clínica.
* Análisis Cronológico Avanzado: Diseñé consultas utilizando expresiones regulares (Regex) para filtrar registros médicos por mes y año específicos, facilitando
  la generación de reportes de visitas periódicas.
* Indexación de Contacto: Estructuré búsquedas directas por número telefónico del propietario, optimizando los tiempos de respuesta en situaciones de urgencia o seguimiento.

Todas las consultas fueron probadas para manejar de forma dinámica los nuevos atributos de la base de datos, incluyendo rasgos físicos específicos y fechas de 
nacimiento de las mascotas, asegurando un sistema escalable y preciso.

**Rol de Integration Specialist (Brayan Hernandez)

Descripción de la actividad.
Durante esta semana se trabajó con operadores de comparación en MongoDB, específicamente:
$gt, $lt, $in, $ne, enfocados en consultas avanzadas y filtrado de datos dentro de la base de datos.

El objetivo era aplicar estos operadores en queries para obtener información específica a partir de colecciones, particularmente en escenarios de filtrado numérico y listas.

Actividades realizadas.
Analicé la estructura de consultas en MongoDB (MQL).
Revisé ejemplos de filtrado avanzado en queries/02_filters.
Comprendí el uso de operadores de comparación:

$gt (greater than)
$lt (less than)
$in (in list)
$ne (not equal)

Preparé la lógica de consulta solicitada en el ejercicio.
Limitaciones encontradas
Actualmente no se me permite ejecutar directamente consultas en la base de datos, por lo que:
No pude validar en tiempo real los resultados del query.
Tuve que trabajar únicamente con la estructura teórica.
Quedé a la espera de que se habilite o actualice el acceso a la base de datos para continuar con pruebas prácticas.

Ejercicio solicitado
Problema:
"I need to find products with price greater than 50 AND stock less than 10." 

Solución (MQL Query)

db.products.find({
  price: { $gt: 50 },
  stock: { $lt: 10 }
})

Explicación de los operadores
$gt (greater than)
Filtra los documentos donde el campo price sea mayor a 50.
$lt (less than)
Filtra los documentos donde el campo stock sea menor a 10.
Ambas condiciones se combinan implícitamente con un AND, ya que están dentro del mismo objeto.
Resultados esperados
Se espera obtener todos los productos que:
Tengan un precio superior a 50
Y un stock menor a 10 unidades.

**Rol de The data seeler/QA(Ximena Rosas)
* Generación de Datos Sintéticos:
Investigar cómo crear millones de registros que parezcan reales pero que cubran todas las variaciones posibles
(nombres largos, direcciones inexistentes, correos con formatos extraños).
* Edge Case Analysis (Casos de Borde):
Identificar los limites del sistema. Si un campo acepta números del 1 al 100, tu investigación se centra en qué pasa si metes 0, 101, -1 0 ABC.
2. Herramientas Clave que debes
dominar
Para ser un experto en este rol, tu investigación debe cubrir estas tecnologías:
A. Mockaroo (Tu arma principal)
Es la herramienta estándar para generar datos.
Debes investigar:
* Custom Logic: Cómo usar formulas para que un campo dependa de otro (ej: si el país es "México", que el código postal tenga 5 digitos).
* Datasets Relacionados: Cómo generar archivos JSON que estén vinculados entre si (que el product_id
Datasets Relacionados: Cómo generar archivos JSON que estén vinculados entre si (que el product_id en la colección de "Ventas" realmente exista en la colección de "Productos").
B. MongoDB Shell & Compass
Como Data Seeder, necesitas mover datos rápido:
* mongoimport / mongoexport :
Comandos de terminal para cargar archivos JSON/CSV masivamente.

**Rol de scrum master (Annel Ricaño)
Durante la semana fui gestionando los bloques que habían, facilitar la estandarización.
Mi objetivo fue hacer una retrospectiva breve del bloqueo que hubo durante .
*Promover el acuerdo: Moderar una sesión rápida (Daily o Refinement) para decidir que el estándar oficial sería el inglés.
*Garantizar la coherencia: Asegurarte de que supieran que los campos cambiaron (ej: de mascotas a pets) para que sus queries no fallaran.
A.Identificar el "Blocker": Registrar en el tablero (Jira/Trello/GitHub) que el rol de Integration está detenido.
B.Escalación: Hablar con el administrador del clúster de MongoDB Atlas o el IT Manager para conseguirle las credenciales.
C.Mitigación: Si el acceso tardaba, proponerle que use MongoDB Playground o un contenedor local de Docker para validar su lógica teórica.


