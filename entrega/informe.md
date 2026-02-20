# 📄 Informe Técnico del Taller

## 🔖 Nombre del Taller
_Taller X - [Nombre completo del taller]_

## 👥 Integrantes del equipo
- Julián Mauricio Zafra
- Santiago Araque
- Juan José Forero

## 🧠 Descripción general del trabajo
Describa brevemente el objetivo del taller y cómo se desarrolló la actividad.

## 🔧 Proceso de desarrollo
Explique cómo realizaron el trabajo: qué decisiones tomaron, qué herramientas utilizaron, qué aspectos modelaron primero y cómo lo fueron ajustando.

## 🧩 Análisis del modelo propuesto
Incluya un análisis sobre:
- Cómo se estructura el modelo entregado
- Cómo representa las necesidades del cliente
- Qué supuestos se tomaron

## 📈 Diagrama final entregado
> (Inserte aquí una imagen o enlace al modelo-final.drawio / .asta / PDF)

## 📋 Tabla de actores, entidades o componentes (si aplica)

| Nombre del elemento | Tipo | Descripción | Responsable |
|---------------------|------|-------------|-------------|
| Ej: Paciente        | Actor | Usuario que agenda una cita médica | Cliente |

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
