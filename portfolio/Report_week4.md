Sistema de Gestión Veterinaria "Mundo Animal"
Semana:(Abril 20 - 29)

**Rol de The data modeler (Alejandra Porras).

Durante esta semana, el trabajo se centró en la depuración de la colección pets dentro del clúster de MongoDB Atlas. El objetivo principal fue realizar el mantenimiento de los registros de propietarios y mascotas, asegurando que la información de contacto y salud estuviera debidamente vinculada.
2. Bitácora de Dudas y Desafíos Técnicos
Durante el proceso, surgieron obstáculos clave que requirieron un análisis profundo de la arquitectura de la base de datos:

Lunes 20 - Martes 21: Confusión de Interfaz (Query vs. Command)

Duda: ¿Por qué la plataforma marcaba errores de sintaxis (bordes rojos) al intentar ejecutar instrucciones de actualización?
Hallazgo: Se identificó que se estaba trabajando sobre la barra de Filtros (Query Bar), la cual está limitada exclusivamente a la lectura. Para realizar cambios estructurales o de datos mediante código, es indispensable el uso del Mongosh o herramientas de administración externas.

Miércoles 22 - Jueves 23: Identificación de Rutas de Campo (Dot Notation)

Duda: Los filtros de búsqueda no arrojaban resultados incluso ingresando el ID correcto.
Hallazgo: Tras revisar los documentos JSON, se confirmó que la información no es "plana". Los datos están organizados en objetos anidados. Por ejemplo, el ID del dueño no reside en la raíz, sino dentro de un sub-objeto llamado owner. Esto obligó a replantear la forma en que se accede a la información.

Viernes 24: Errores de Sintaxis en Terminal

Duda: El sistema rechazaba comandos a pesar de tener la lógica correcta.
Hallazgo: Se detectó sensibilidad extrema a caracteres invisibles (espacios al final de la línea) y errores en la separación de bloques mediante comas. Se estableció un protocolo de escritura en una sola línea para evitar interrupciones en la ejecución de la terminal.

3. Solución Aplicada
Para resolver los problemas de visibilidad de la terminal en el navegador y cumplir con los requerimientos técnicos, se optó por:
Validar la jerarquía de campos: Asegurando que cada ruta coincida con el esquema (objeto.campo).
Uso de MongoDB Compass: Se recomendó el uso de la aplicación de escritorio para garantizar el acceso estable a la consola de comandos cuando la interfaz web presentara limitaciones de visualización.

4. Estado Final de la Semana
La base de datos se encuentra correctamente estructurada. Se ha logrado una comprensión profunda de cómo navegar por documentos complejos y se han resuelto las barreras de comunicación con el motor de búsqueda de MongoDB

** Rol de Query Developer (Tammy Nashely)

1. Resumen de Actividades
Esta semana el enfoque principal fue la implementación de operadores lógicos avanzados para refinar la búsqueda de información y mejorar la precisión de los reportes de salud animal. Se optimizaron las consultas para permitir filtros múltiples y exclusiones específicas.
2. Implementación de Operadores Lógicos
A continuación, se detallan las consultas desarrolladas utilizando la sintaxis de MongoDB Query Language (MQL):
A. Uso del Operador $or
Este operador se utilizó para identificar registros que cumplen con al menos una de las condiciones especificadas. Es ideal para buscar múltiples especies o síntomas simultáneamente.
• Caso de uso: Filtrar pacientes que son aves o reptiles.
• Consulta: 
db.pacientes.find({
  $or: [
    { especie: "Canario" },
    { especie: "Tortuga" }
  ]
})

B. Uso del Operador $and
Se implementó para consultas que requieren que todas las condiciones se cumplan estrictamente. Aunque MongoDB aplica un $and implícito en muchos casos, su uso explícito es necesario cuando se repite la misma clave con diferentes operadores.
• Caso de uso: Filtrar mascotas de una especie específica que fueron atendidas en un rango de fechas determinado.
• Consulta:
db.consultas.find({
  $and: [
    { especie: "Hámster" },
    { fecha_visita: { $regex: /2026-04/ } }
  ]
})
db.consultas.find({
  $and: [
    { especie: "Hámster" },
    { fecha_visita: { $regex: /2026-04/ } }
  ]
})

C. Uso del Operador $not
Este operador se aplicó para invertir el efecto de otros operadores, permitiendo excluir resultados específicos que no cumplen con un criterio técnico o de salud.
• Caso de uso: Identificar pacientes que no han sido marcados como "estables".
• Consulta:
db.pacientes.find({
  estado_salud: { $not: { $eq: "Estable" } }
})
3. Resultados y Validaciones
• Precisión de Filtros: Se logró una segmentación más profunda de la colección registro_medico.
• Optimización: Las consultas fueron probadas en MongoDB Compass para asegurar que los tiempos de respuesta sean óptimos antes de integrarlas al backend en Node.js.
• Consistencia: Se verificó que los resultados coincidan con los requerimientos de análisis de datos solicitados por el equipo.

**Rol de The data seeler/QA(Ximena Rosas)
Generación de "Semillas" (Datasets)
Has creado tres colecciones interconectadas con lógica de Caos:
Colección pets: No solo pusiste nombres de perros. Investigaste y generaste datos con variabilidad:
Caos aplicado: Insertaste mascotas con edades extremas (0 o 25 años) y especies poco comunes para probar los filtros de búsqueda.
Colección medicine: Aquí es donde entra la precisión.
Caos aplicado: Medicamentos con fechas de vencimiento pasadas, stocks en cero y precios con decimales complejos para probar el operador $lt (menor que) y $lte.
Colección sales: El historial de transacciones.
Caos aplicado: Ventas sin ID de mascota asociado o con montos negativos, para ver si el sistema de QA detecta la falta de integridad

**Rol de Integration Specialist (Brayan Hernandez)

Reporte de Actividades – Conexión a mongoDB
Actividad realizada:
El día de hoy realicé la conexión a la base de datos MongoDB utilizando la terminal, apoyándome en Figma como herramienta de diseño para visualizar la estructura del proyecto.

Descripción del proceso:
Primero, utilicé Figma, que es una aplicación de diseño, para organizar y estructurar visualmente el proyecto. A partir de este diseño, trabajé todo dentro de una sola carpeta, lo que permitió mantener ordenados los archivos y facilitar la integración entre el diseño y la parte técnica.
Posteriormente, trabajé en la terminal para establecer la conexión con MongoDB. Configuré los parámetros necesarios y ejecuté los comandos correspondientes para lograr la comunicación entre la aplicación y la base de datos, permitiendo que la terminal enviara correctamente los datos hacia MongoDB.

Dificultades encontradas:
Durante el proceso surgieron algunos problemas al momento de realizar la conexión, probablemente relacionados con la configuración o ejecución de comandos en la terminal. Sin embargo, estos inconvenientes fueron resueltos rápidamente tras revisar los errores y ajustar la configuración.

Resultado final:
Se logró establecer correctamente la conexión con MongoDB, permitiendo el envío de datos desde la terminal hacia la base de datos. El uso de Figma facilitó la organización previa del proyecto y el manejo de todo en una sola carpeta ayudó a mantener un mejor control del desarrollo.
 
**Rol de scrum master (Annel Ricaño)
 Se optimizaron las consultas para permitir filtros múltiples y exclusiones específicas.
A. Implementación de Operadores Lógicos
A continuación, se detallan las consultas desarrolladas utilizando la sintaxis de MongoDB Query Language (MQL):
al momento se crea una carpeta de documentacion para incrementar los filtros
