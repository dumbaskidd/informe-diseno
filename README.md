<div align="center">

# UNIVERSIDAD PERUANA DE CIENCIAS APLICADAS

`<Insertar imagen del logo de la UPC>`

**CARRERA:** Ingeniería de Software

**CURSO:** 1ASI0732 — Diseño de Experimentos de Ingeniería de Software

**CICLO:** 2026-20

**SECCIÓN:** `<NRC>`

**PROFESOR:** `<NOMBRE DEL PROFESOR>`

## Informe de Trabajo Final

**Startup:** Energix
**Producto:** SEMS — Smart Energy Management System

### Integrantes

| Nombre completo | Código | Rol |
| :-- | :-- | :-- |
| `<Apellidos, Nombres>` | `<Código>` | **Team Leader** |
| `<Apellidos, Nombres>` | `<Código>` | Integrante |
| `<Apellidos, Nombres>` | `<Código>` | Integrante |

**Septiembre 2026**

</div>

---

## Registro de Versiones del Informe

| Versión | Fecha | Autor | Descripción de modificación |
| :-- | :-- | :-- | :-- |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Creación del repositorio del informe y de la estructura de capítulos en Markdown. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Redacción del Startup Profile y de los perfiles de los integrantes del equipo. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Redacción de Antecedentes y Problemática aplicando la técnica 5W2H. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Ejecución del Lean UX Process: Problem Statements, Assumptions, Hypothesis Statements y Canvas. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Descripción de los segmentos objetivo con sustento estadístico del MINEM. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Análisis competitivo y definición de estrategias y tácticas frente a competidores. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Diseño de las entrevistas para los dos segmentos objetivo. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Registro y análisis de entrevistas. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Needfinding: User Personas, User Task Matrix, User Journey Maps, Empathy Maps y As-Is Scenario Mapping. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Ubiquitous Language. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Requirements Specification: To-Be Scenario Mapping, User Stories, Product Backlog e Impact Mapping. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Style Guidelines e Information Architecture. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Landing Page UI Design: wireframes y mock-ups. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Web Applications UX/UI Design y prototipado. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Domain-Driven Software Architecture: diagramas C4 de contexto, contenedores y componentes. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Software Object-Oriented Design: diagramas de clases y diccionario. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Database Design: diagrama entidad-relación. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Software Configuration Management y configuración de despliegue. |
| 1.0 | `<dd/mm/aaaa>` | `<Integrante>` | Evidencias de implementación del Landing Page, la aplicación web y la API. |

> El cuadro se amplía en cada entrega. Cada fila debe corresponder con un commit verificable en
> este repositorio, según se detalla en *Project Report Collaboration Insights*.

---

## Project Report Collaboration Insights

**Repositorio del informe:** <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Report>

El informe se elabora de forma colaborativa en este repositorio, en formato Markdown, aplicando
**GitFlow Workflow** y **Conventional Commits**. Cada integrante trabaja sobre una rama
`feature/<sección>` que nace de `develop` y regresa por *Pull Request*; `main` solo recibe las
versiones entregadas.

Se trabaja en Markdown y no en un procesador de textos por una razón que el curso evalúa: cada
párrafo queda asociado a un commit con autor y fecha, de modo que la contribución de cada
integrante es verificable y no depende de lo que se declare en una tabla.

> `<Insertar la gráfica de contribuciones del repositorio del informe (Insights → Contributors).>`

---

## Contenido

- [Carátula](#universidad-peruana-de-ciencias-aplicadas)
- [Registro de Versiones del Informe](#registro-de-versiones-del-informe)
- [Project Report Collaboration Insights](#project-report-collaboration-insights)
- [Student Outcome](chapters/00-student-outcome.md)

### [Capítulo I: Introducción](chapters/01-introduccion.md)

- [1.1. Startup Profile](chapters/01-introduccion.md#11-startup-profile)
  - [1.1.1. Descripción de la Startup](chapters/01-introduccion.md#111-descripción-de-la-startup)
  - [1.1.2. Perfiles de integrantes del equipo](chapters/01-introduccion.md#112-perfiles-de-integrantes-del-equipo)
- [1.2. Solution Profile](chapters/01-introduccion.md#12-solution-profile)
  - [1.2.1. Antecedentes y problemática](chapters/01-introduccion.md#121-antecedentes-y-problemática)
  - [1.2.2. Lean UX Process](chapters/01-introduccion.md#122-lean-ux-process)
    - [1.2.2.1. Lean UX Problem Statements](chapters/01-introduccion.md#1221-lean-ux-problem-statements)
    - [1.2.2.2. Lean UX Assumptions](chapters/01-introduccion.md#1222-lean-ux-assumptions)
    - [1.2.2.3. Lean UX Hypothesis Statements](chapters/01-introduccion.md#1223-lean-ux-hypothesis-statements)
    - [1.2.2.4. Lean UX Canvas](chapters/01-introduccion.md#1224-lean-ux-canvas)
- [1.3. Segmentos objetivo](chapters/01-introduccion.md#13-segmentos-objetivo)

### [Capítulo II: Requirements Elicitation & Analysis](chapters/02-requirements-elicitation.md)

- [2.1. Competidores](chapters/02-requirements-elicitation.md#21-competidores)
  - [2.1.1. Análisis competitivo](chapters/02-requirements-elicitation.md#211-análisis-competitivo)
  - [2.1.2. Estrategias y tácticas frente a competidores](chapters/02-requirements-elicitation.md#212-estrategias-y-tácticas-frente-a-competidores)
- [2.2. Entrevistas](chapters/02-requirements-elicitation.md#22-entrevistas)
  - [2.2.1. Diseño de entrevistas](chapters/02-requirements-elicitation.md#221-diseño-de-entrevistas)
  - [2.2.2. Registro de entrevistas](chapters/02-requirements-elicitation.md#222-registro-de-entrevistas)
  - [2.2.3. Análisis de entrevistas](chapters/02-requirements-elicitation.md#223-análisis-de-entrevistas)
- [2.3. Needfinding](chapters/02-requirements-elicitation.md#23-needfinding)
  - [2.3.1. User Personas](chapters/02-requirements-elicitation.md#231-user-personas)
  - [2.3.2. User Task Matrix](chapters/02-requirements-elicitation.md#232-user-task-matrix)
  - [2.3.3. User Journey Mapping](chapters/02-requirements-elicitation.md#233-user-journey-mapping)
  - [2.3.4. Empathy Mapping](chapters/02-requirements-elicitation.md#234-empathy-mapping)
  - [2.3.5. As-is Scenario Mapping](chapters/02-requirements-elicitation.md#235-as-is-scenario-mapping)
- [2.4. Ubiquitous Language](chapters/02-requirements-elicitation.md#24-ubiquitous-language)

### [Capítulo III: Requirements Specification](chapters/03-requirements-specification.md)

- [3.1. To-Be Scenario Mapping](chapters/03-requirements-specification.md#31-to-be-scenario-mapping)
- [3.2. User Stories](chapters/03-requirements-specification.md#32-user-stories)
- [3.3. Product Backlog](chapters/03-requirements-specification.md#33-product-backlog)
- [3.4. Impact Mapping](chapters/03-requirements-specification.md#34-impact-mapping)

### [Capítulo IV: Product Design](chapters/04-product-design.md)

- [4.1. Style Guidelines](chapters/04-product-design.md#41-style-guidelines)
  - [4.1.1. General Style Guidelines](chapters/04-product-design.md#411-general-style-guidelines)
  - [4.1.2. Web Style Guidelines](chapters/04-product-design.md#412-web-style-guidelines)
  - [4.1.3. Mobile Style Guidelines](chapters/04-product-design.md#413-mobile-style-guidelines)
- [4.2. Information Architecture](chapters/04-product-design.md#42-information-architecture)
  - [4.2.1. Organization Systems](chapters/04-product-design.md#421-organization-systems)
  - [4.2.2. Labeling Systems](chapters/04-product-design.md#422-labeling-systems)
  - [4.2.3. SEO Tags and Meta Tags](chapters/04-product-design.md#423-seo-tags-and-meta-tags)
  - [4.2.4. Searching Systems](chapters/04-product-design.md#424-searching-systems)
  - [4.2.5. Navigation Systems](chapters/04-product-design.md#425-navigation-systems)
- [4.3. Landing Page UI Design](chapters/04-product-design.md#43-landing-page-ui-design)
  - [4.3.1. Landing Page Wireframe](chapters/04-product-design.md#431-landing-page-wireframe)
  - [4.3.2. Landing Page Mock-up](chapters/04-product-design.md#432-landing-page-mock-up)
- [4.4. Mobile Applications UX/UI Design](chapters/04-product-design.md#44-mobile-applications-uxui-design)
- [4.5. Mobile Applications Prototyping](chapters/04-product-design.md#45-mobile-applications-prototyping)
- [4.6. Web Applications UX/UI Design](chapters/04-product-design.md#46-web-applications-uxui-design)
- [4.7. Web Applications Prototyping](chapters/04-product-design.md#47-web-applications-prototyping)
- [4.8. Domain-Driven Software Architecture](chapters/04-product-design.md#48-domain-driven-software-architecture)
  - [4.8.1. Software Architecture Context Diagram](chapters/04-product-design.md#481-software-architecture-context-diagram)
  - [4.8.2. Software Architecture Container Diagrams](chapters/04-product-design.md#482-software-architecture-container-diagrams)
  - [4.8.3. Software Architecture Components Diagrams](chapters/04-product-design.md#483-software-architecture-components-diagrams)
- [4.9. Software Object-Oriented Design](chapters/04-product-design.md#49-software-object-oriented-design)
  - [4.9.1. Class Diagrams](chapters/04-product-design.md#491-class-diagrams)
  - [4.9.2. Class Dictionary](chapters/04-product-design.md#492-class-dictionary)
- [4.10. Database Design](chapters/04-product-design.md#410-database-design)

### [Capítulo V: Product Implementation](chapters/05-product-implementation.md)

- [5.1. Software Configuration Management](chapters/05-product-implementation.md#51-software-configuration-management)
  - [5.1.1. Software Development Environment Configuration](chapters/05-product-implementation.md#511-software-development-environment-configuration)
  - [5.1.2. Source Code Management](chapters/05-product-implementation.md#512-source-code-management)
  - [5.1.3. Source Code Style Guide & Conventions](chapters/05-product-implementation.md#513-source-code-style-guide--conventions)
  - [5.1.4. Software Deployment Configuration](chapters/05-product-implementation.md#514-software-deployment-configuration)
- [5.2. Product Implementation & Deployment](chapters/05-product-implementation.md#52-product-implementation--deployment)
  - [5.2.1. Sprint Backlogs](chapters/05-product-implementation.md#521-sprint-backlogs)
  - [5.2.2. Implemented Landing Page Evidence](chapters/05-product-implementation.md#522-implemented-landing-page-evidence)
  - [5.2.3. Implemented Frontend-Web Application Evidence](chapters/05-product-implementation.md#523-implemented-frontend-web-application-evidence)
  - [5.2.4. Implemented Native-Mobile Application Evidence](chapters/05-product-implementation.md#524-implemented-native-mobile-application-evidence)
  - [5.2.5. Implemented RESTful API Evidence](chapters/05-product-implementation.md#525-implemented-restful-api-evidence)
  - [5.2.6. RESTful API Documentation](chapters/05-product-implementation.md#526-restful-api-documentation)
  - [5.2.7. Team Collaboration Insights](chapters/05-product-implementation.md#527-team-collaboration-insights)
- [5.3. Video About-the-Product](chapters/05-product-implementation.md#53-video-about-the-product)
- [5.4. Deuda técnica identificada](chapters/05-product-implementation.md#54-deuda-técnica-identificada)

### [Conclusiones, Bibliografía y Anexos](chapters/99-conclusiones.md)
