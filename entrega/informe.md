# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller X - [Nombre completo del taller]_

## 👥 Integrantes del equipo
- Julián Mauricio Zafra
- Santiago Araque
- Juan José Forero

## 🧠 Descripción general del trabajo
En el presente trabajo se llevo acabo un proceso de analisis y modelado de las actividades del dia a dia de THEGEEKHUB, un emprendimiento dedicado a la comercializacion minorista de articulos coleccionables de series y videojuegos, quienes manejan su negocio a traves de las redes sociales y tienen dificultades para alcanzar las ventas esperadas y organizar sus procesos. A partir del dialogo con uno de los dueños del negocio se extrajeron las ideas y procesos clave del negocio para llegar a un modelado limpio y estructurado que garantice la consistencia en los datos de ventas, asi como registros adecuados de los datos de clientes e información financiera de las ventas.

## 🔧 Proceso de desarrollo
Explique cómo realizaron el trabajo: qué decisiones tomaron, qué herramientas utilizaron, qué aspectos modelaron primero y cómo lo fueron ajustando.

Nuestro proceso de desarrollo se realizo en 3 fases principales: Indagación, estructuración de los procesos actuales y finalmente el modelado. A continuación se describe cada una de las etapas.

Indagación: Se tuvo una reunión con uno de los dueños del negocio para realizar un perfilamiento/caracterización del mismo, ayudandonos a determinar que es lo que le duele de su negocio y que objetivos tiene a corto y largo plazo para el mismo. El objetivo de esto es realizar un sondeo de que aspectos pueden tener una mejoria inmediata, bien sea en procesos facilmente optimizable o incluso en la organización de sus actividades.

Estructuración de los procesos actuales: Se tomo en cuenta los flujos de procesos del negocio para encontrar aspectos clave que pueden brindar una mejoria al proceso que llevan a cabo, para ello se hizo uso de un diagrama de contexto que exponia a nivel general como opera THEGEEKHUB. Gracias a ello logramos determinar que la organización de los datos de ventas se lleva a cabo por medio de hojas de excel que almacenan la información de cada año de ventas y compras desde finales de 2023. Sin embargo no se documenta adecuadamente al excluir datos fundamentales para posible atención al cliente, por ejemplo las fechas de ventas o otorgarle de forma estandar un SKU a cada referencia de los productos. El siguiente paso era llegar a una conclución de como podiamos mejorar este procesos, la respuesta fue clara de inmediato para algunos de los aspectos, mientras que otros requirieron de una mayor indagación y supuestos sobre el futuro de THEGEEKHUB.

Modelado: En esta etapa hicimos el modelado entidad - relación del negocio teniendo en cuenta las mejorias que se le sugeririan a THEGEEKHUB y el supuesto de que es un negocio que al ser 100% virtual eventualmente buscara expandirse a un sistema mas profesional y seguro para guardar su informacion y la de sus clientes. Para ello modelaron 6 entidades: Transacción, Referencia, Ventas, cambioFuente, Comprador y Fuente. Comprador pasó sin muchos cambios de como se maneja actualmente esta información, mas allá de haber pasado por una organización estructurada en lugar de información que solo almacenan hasta el momento de la entrega del producto. Referencia y ventas por otro lado fueron reestructuradas casi en su totalidad para que toda la información de valor de estos 2 aspectos sea mas facilmente migrable a la futura expansión de THEGEEKHUB en el E-commerce así como a la posibilidad de tener un local fisico.

## 🧩 Análisis del modelo propuesto
Incluya un análisis sobre:
- Cómo se estructura el modelo entregado
- Cómo representa las necesidades del cliente
- Qué supuestos se tomaron

El modelo entidad–relación propuesto para THEGEEKHUB se estructura mediante las 6 entidades previamente mencionadas. La estructura separa claramente tres dimensiones fundamentales del negocio:
Dimensión comercial: Ventas y referencia, dimensión del cliente: comprador y la dimensión financiera: transacción, fuente y cambioFuente. La entidad Ventas funciona como núcleo del modelo, ya que conecta el producto vendido (Referencia), el cliente (Comprador) y la plataforma financiera utilizada (Fuente). Por otro lado, la entidad Transacción permite registrar los movimientos de dinero asociados a cada venta, mientras que CambioFuente modela las transferencias internas entre plataformas financieras (por ejemplo, de MercadoPago a Nequi o cuenta bancaria). La separación de estas entidades evita redundancia de información y facilita la trazabilidad tanto comercial como financiera.

El modelo responde directamente a los problemas identificados durante la fase de indagación: ID único, fecha (en Transacción), SKU de referencia, comprador asociado y fuente de pago como respuesta a la falta de organización en las ventas. Una separacion de las ventas en: Venta (acto comercial), Transacción (movimiento de dinero) y CambioFuente (transferencias internas) para generar un control finanaciero mas claro y finalmente: Uso de SKU y una separación estricta de entidades para permitir una migración sencilla hacia sistemas como un posible ERP o simplemente una base de datos sencilla.

Como supuesto para este modelado se tomó:
- Cada venta corresponde a una única referencia (no se modeló carrito de múltiples productos).
- Cada venta utiliza una fuente principal de pago.
- Una venta puede generar múltiples transacciones (ej: pago, devolución).
- Las transferencias entre plataformas financieras deben registrarse independientemente de la venta.
- THEGEEKHUB crecerá y requerirá un sistema formal de base de datos relacional.
- Los datos del comprador deben conservarse incluso después de la venta para análisis futuro y fidelización.


## 📈 Diagrama final entregado
<img width="641" height="651" alt="modelo-final-er drawio" src="https://github.com/user-attachments/assets/4cf831e8-b89c-4f78-926e-b92f8d9c7d81" />

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento | Tipo | Descripción |
|---------------------|------|-------------|
| Ventas              | Entidad | Venta de una referencia a un comprador       |
| Comprador           | Entidad | Usuario que compra una referencia            |
| Referencia          | Entidad | Identificador de un articulo específico      |
| Transaccion         | Entidad | Accion que involucra el movimiento de dinero | 
| CambioFuente        | Entidad | Movimiento de dinero entre fuentes           |
| Fuente              | Entidad | Plataforma de servicio financiero            | 

## 🔍 Investigación complementaria
### Tema investigado:

#### Buenas prácticas en el modelado Entidad–Relación (ERD)

El modelo entidad–relación es una técnica utilizada para representar de forma conceptual la estructura de los datos de un sistema, mostrando entidades, atributos y relaciones entre ellas. Según Fundamentals of Database Systems [1], un buen modelo ER debe evitar la redundancia de información, definir correctamente las claves primarias y foráneas y reflejar las reglas del negocio.

En el modelo propuesto para THEGEEKHUB se identifican entidades como Ventas, Comprador, Fuente, Transacción y CambioFuente, lo cual permite separar la información comercial, los datos del cliente y los movimientos de dinero. Esta separación mejora la trazabilidad de las ventas, ya que permite conocer desde qué canal se realizó la compra y hacia qué plataforma se transfirió el dinero. Además, el uso de relaciones mediante llaves foráneas mantiene la integridad de los datos y facilita la generación de reportes.

#### Diagramas de contexto en arquitectura empresarial

El diagrama de contexto permite mostrar el sistema como una caja negra y visualizar su interacción con actores y sistemas externos mediante flujos de información. Este tipo de diagrama es utilizado en marcos de arquitectura como TOGAF y en el modelo C4, donde se busca identificar los límites del sistema y sus integraciones [2] [3].

En este caso práctico, el sistema de ventas de THEGEEEKHUB está conectado a plataformas externas como MercadoLibre, MercadoPago, Nequi, Instagram/Facebook y Excel. El flujo de información abarca confirmaciones de ventas, devoluciones, atención al cliente, actividades promocionales y registro de datos. Esto ayuda a comprender cómo fluye la información dentro de la empresa, identificar dependencias tecnológicas y descubrir posibles áreas de mejora o automatización.

### Resumen:
Los conceptos explorados en este taller están directamente relacionados con sus objetivos. El Modelo Entidad-Relación (Modelo ER) define la información que procesa una empresa y sus relaciones con otra información, mientras que el diagrama de contexto ilustra cómo los participantes y los sistemas interactúan con esta información.

Gracias a este enfoque, el modelo operativo de THEGEEEKHUB se reveló con mayor claridad, destacando las ventas multicanal, el procesamiento de pagos multiplataforma y la gestión de la información de socios. Esto nos permitió pasar de comprender los procesos de negocio a construir estructuras de datos ordenadas, facilitando así la futura integración tecnológica y mejorando el control operativo.

## 📚 Referencias
- [1] R. Elmasri y S. Navathe, *Fundamentals of Database Systems*, 7th ed. Pearson, 2016.  
- [2] The Open Group, *TOGAF® Standard, Version 9.2*, 2018. [En línea]. Disponible en: https://www.opengroup.org/togaf  
- [3] S. Brown, *The C4 Model for Visualising Software Architecture*. [En línea]. Disponible en: https://c4model.com  

---

_Este documento hace parte de la entrega del taller X del curso AREM (Arquitectura Empresarial) - Universidad de La Sabana._
