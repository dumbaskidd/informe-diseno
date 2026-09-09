[⬅ Volver al índice](../README.md)

# Capítulo II: Requirements Elicitation & Analysis

## 2.1. Competidores

El mercado de gestión energética para establecimientos comerciales en el Perú combina tres tipos
de oferta: fabricantes de medidores y hardware de monitoreo, empresas de servicios de eficiencia
energética que realizan auditorías puntuales, y plataformas internacionales de energy management
orientadas a grandes industrias. Ninguna de las tres resuelve por completo el problema de un
local comercial de mediana superficie.

**Schneider Electric (EcoStruxure Power)** es el referente global en gestión de energía. Ofrece
medición avanzada, análisis de calidad de energía y control de demanda, con integración a
sistemas de automatización de edificios. Su fortaleza es la profundidad técnica y la fiabilidad
del hardware. Su limitación para nuestro segmento es el costo y la complejidad: está diseñado
para plantas industriales y edificios corporativos, requiere integrador certificado y su modelo
comercial no se ajusta a un local de 500 m².

**Sistemas de gestión de las distribuidoras (Enel Perú, Luz del Sur)** ofrecen a sus clientes
comerciales portales de consulta de consumo y, en algunos casos, información de demanda máxima
facturada. Su fortaleza evidente es que la fuente del dato es la propia empresa que factura. Su
limitación es que el dato es diferido y agregado por suministro: sirve para consultar lo ocurrido,
no para actuar durante el mes, y no desglosa por zona ni por equipo.

**Empresas de eficiencia energética y auditoría (consultoras locales)** realizan diagnósticos
puntuales, miden durante un periodo acotado y entregan un informe con recomendaciones. Su
fortaleza es el criterio experto aplicado al caso concreto. Su limitación es que el resultado es
una fotografía: no hay seguimiento continuo, y meses después el local vuelve a no tener
visibilidad. Además el costo por intervención es elevado para un establecimiento independiente.

**Refoss / Shelly / medidores inteligentes de consumo** son dispositivos accesibles que permiten
ver el consumo en tiempo real desde una aplicación móvil. Su fortaleza es el precio y la
facilidad de instalación. Su limitación es determinante para este segmento: reportan energía a
un precio único por kWh, sin modelar franja horaria ni cargo por potencia, que es donde se
origina el sobrecosto comercial.

### 2.1.1. Análisis competitivo

| Competitive Analysis Landscape | | **Energix — SEMS** | **Schneider EcoStruxure** | **Portal de la distribuidora** | **Medidores tipo Refoss / Shelly** |
| :-- | :-- | :-- | :-- | :-- | :-- |
| **¿Por qué llevar a cabo este análisis?** | | Determinar qué necesidad del segmento de establecimientos comerciales no está siendo atendida por la oferta actual, y sobre qué base construir la ventaja competitiva de SEMS. | | | |
| **Perfil** | Overview | Plataforma web de gestión energética para establecimientos comerciales. Mide por local y por zona, calcula con la tarifa comercial peruana y avisa antes de superar la potencia contratada. | Suite empresarial de gestión de energía y automatización para industria y edificios corporativos. | Portal de consulta de consumo y facturación que la distribuidora ofrece a sus clientes. | Dispositivos de medición de consumo con aplicación móvil, orientados al mercado doméstico. |
| | Ventaja competitiva | Modela la estructura tarifaria comercial peruana completa (punta, fuera de punta y demanda máxima) y alerta con margen antes del exceso. | Profundidad técnica, calidad de energía, integración con control industrial y respaldo de marca global. | El dato proviene de la misma empresa que emite la factura. | Precio bajo e instalación sencilla. |
| **Perfil de Marketing** | Mercado objetivo | Establecimientos comerciales de 200 a 2.000 m² y cadenas de retail pequeñas y medianas. | Industria, minería, edificios corporativos y grandes superficies. | Todos los clientes de la concesionaria. | Consumidor doméstico y pequeño negocio. |
| | Estrategias de marketing | Venta directa a cadenas, alianzas con gremios de comerciantes y prueba piloto gratuita en un local. | Red de integradores certificados y venta consultiva de alto ticket. | Canal propio incluido en el servicio. | Comercio electrónico y retail de tecnología. |
| **Perfil de Producto** | Productos y servicios | Landing page, aplicación web, API RESTful y aplicación móvil. Alertas de demanda, factura estimada desglosada, consumo por zona y comparación entre locales. | Medidores, software de supervisión, servicios de ingeniería y analítica avanzada. | Consulta de recibos, histórico de consumo y demanda facturada. | Medidor con aplicación de consumo y automatizaciones básicas. |
| | Precios y costos | Suscripción mensual escalonada por número de locales. Plan de entrada gratuito para un local. | Licenciamiento e implementación de alto costo, con proyecto de integración. | Sin costo adicional, incluido en el servicio eléctrico. | Pago único por dispositivo. |
| | Canales de distribución | Web y móvil. | Integradores y fuerza de ventas directa. | Web y aplicación de la distribuidora. | Comercio electrónico. |
| **Análisis SWOT** | Fortalezas | Modela la tarifa comercial peruana; alerta preventiva de demanda; desglose por zona; equipo con conocimiento del contexto regulatorio local. | Marca consolidada, robustez técnica, catálogo completo de hardware y software. | Acceso directo al dato oficial de facturación. | Costo bajo, gran base instalada y facilidad de uso. |
| | Debilidades | Startup sin trayectoria ni base instalada; depende de hardware de medición de terceros; sin histórico de casos de éxito. | Costo y complejidad desproporcionados para el segmento; ciclo de venta largo. | Dato diferido y agregado; sin desglose por zona; sin capacidad de alerta preventiva. | No modela franja horaria ni demanda máxima; orientado al hogar; sin gestión multi-local. |
| | Oportunidades | Segmento desatendido entre el medidor doméstico y la suite industrial; presión creciente sobre los costos operativos del retail. | Expansión hacia edificios comerciales medianos. | Ampliar los servicios digitales al cliente comercial. | Adaptar su producto al segmento comercial. |
| | Amenazas | Que la distribuidora o un fabricante de medidores incorporen alertas de demanda en su propia oferta. | Competidores especializados más ágiles en nichos concretos. | Regulación y competencia en la comercialización eléctrica. | Saturación del mercado y competencia por precio. |

### 2.1.2. Estrategias y tácticas frente a competidores

**Frente a la debilidad de los medidores domésticos (no modelan la tarifa comercial)**

Nuestra estrategia es hacer de la tarifa el núcleo del producto y no un añadido. La táctica
concreta es mostrar en el panel la factura estimada **desglosada** en energía de punta, energía
fuera de punta y cargo por potencia, de modo que el usuario vea con sus propios números qué
proporción de su recibo depende del pico y no del consumo. Ese desglose es la demostración más
directa de por qué un medidor doméstico no le sirve.

**Frente a la fortaleza de las suites industriales (profundidad técnica y marca)**

No competimos en profundidad técnica. Nuestra estrategia es competir en **tiempo hasta el primer
valor**: mientras una implementación industrial requiere un proyecto de integración, SEMS permite
dar de alta una organización, un local y un medidor en minutos, y empezar a recibir alertas de
demanda el mismo día. La táctica es un plan de entrada gratuito para un local, pensado para que
el responsable pruebe sin autorización de compra.

**Frente a la ventaja del portal de la distribuidora (dato oficial)**

No disputamos la fuente del dato de facturación. Nuestra estrategia es posicionarnos en el
**momento** en que el dato es útil: el portal informa de lo ocurrido, SEMS avisa mientras todavía
se puede evitar. La táctica es explicitar en la comunicación que el cargo por potencia se fija por
un pico de minutos y que ninguna consulta mensual permite prevenirlo.

**Frente a la amenaza de que un competidor incorpore alertas de demanda**

Nuestra estrategia es construir el diferencial en la capa que es más difícil de copiar: el
modelado por **zona** y la comparación entre locales de una cadena, que requieren estructura de
dominio y no solo un umbral sobre una señal. La táctica es priorizar en el backlog las
funcionalidades multi-local desde los primeros sprints.

**Aprovechando nuestra oportunidad (segmento desatendido)**

La estrategia es concentrarnos en un nicho concreto y ganarlo antes de ampliar: establecimientos
con refrigeración continua, donde el problema del pico de demanda es más agudo y más fácil de
demostrar. La táctica es construir el caso de negocio con un local piloto y usar sus cifras
reales como argumento de venta ante cadenas del mismo rubro.

## 2.2. Entrevistas

### 2.2.1. Diseño de entrevistas

Las entrevistas buscan validar las hipótesis del *Lean UX Process* y recoger la información
necesaria para construir los arquetipos: características demográficas, contexto operativo del
local, comportamiento frente al recibo, canales digitales de interacción y disposición a adoptar
la solución.

Se realizarán entre **3 y 5 entrevistas por segmento**, registradas en video. Cada entrevista se
inicia explicando el propósito de la investigación y solicitando consentimiento para la grabación.

> **Nota metodológica.** Las preguntas están formuladas de manera abierta y evitan sugerir la
> respuesta. En particular, las preguntas sobre el cargo por potencia se plantean **sin nombrarlo**
> al inicio (preguntas 6 y 7 del segmento 1), para comprobar si el entrevistado lo identifica por
> sí mismo. Si se le explica primero, la respuesta pierde valor como evidencia.

#### Entrevista — Segmento #1: Responsables de operaciones y mantenimiento de cadenas de retail

**Bloque A. Perfil y contexto**

1. ¿Podría contarnos su cargo, cuánto tiempo lleva en él y cuántos locales están bajo su responsabilidad?
2. ¿Qué tipo de establecimientos son y qué superficie aproximada tienen?
3. ¿Quién decide en su organización una inversión en equipamiento o software para los locales, y qué necesita usted para sustentarla?

**Bloque B. Situación actual del costo energético**

4. ¿Qué lugar ocupa el costo eléctrico dentro de los costos operativos que usted gestiona?
5. ¿Cómo se entera hoy de cuánto consumió cada local y con qué frecuencia lo revisa?
6. Cuando el recibo de un local sube respecto del mes anterior, ¿cómo averigua a qué se debió?
7. ¿Qué conceptos aparecen en el recibo de sus locales? ¿Cuál de ellos le resulta más difícil de explicar o de controlar?
8. ¿Ha tenido alguna vez un recibo que le sorprendiera? ¿Qué hizo al respecto?

**Bloque C. Operación y equipos**

9. ¿Qué equipos considera que consumen más en sus locales y en qué momento del día?
10. ¿Existe algún procedimiento cuando se produce un corte y los equipos vuelven a arrancar todos a la vez?
11. ¿Puede identificar qué zona de un local (sala de ventas, cámaras, almacén, oficinas) consume más? ¿Cómo lo sabría?
12. ¿Tiene forma de comparar el desempeño energético entre locales similares de la cadena?

**Bloque D. Solución y adopción**

13. Si pudiera recibir un aviso mientras el consumo de un local se está disparando, ¿qué haría con ese aviso? ¿Quién debería recibirlo?
14. ¿Quién en cada local debería poder ver esta información y quién debería poder modificar la configuración?
15. ¿Qué tendría que demostrarle una herramienta de este tipo para que usted la lleve a su gerencia?
16. ¿Qué le haría desconfiar o abandonar una herramienta así?

**Bloque E. Perfil digital**

17. ¿Desde qué dispositivo revisaría esta información: computadora de oficina, teléfono, ambos?
18. ¿Qué herramientas digitales usa hoy para gestionar la operación de los locales?
19. ¿Cómo prefiere recibir una alerta urgente: correo, mensajería, notificación en la aplicación?

#### Entrevista — Segmento #2: Propietarios y administradores de establecimientos independientes

**Bloque A. Perfil y contexto**

1. ¿Podría contarnos qué tipo de negocio tiene, hace cuánto y qué superficie aproximada ocupa?
2. ¿Cuál es su rol en el día a día del local?
3. ¿Cuántas personas trabajan en el local y quién se ocupa de temas como el mantenimiento o los servicios?

**Bloque B. Situación actual del costo energético**

4. ¿Cuánto representa el recibo de luz dentro de sus gastos fijos mensuales?
5. ¿Cómo revisa su recibo? ¿Mira solo el total o entra en el detalle?
6. ¿Ha notado variaciones entre meses que no supiera explicar? ¿Qué hizo?
7. ¿Sabe qué potencia tiene contratada para su local? ¿Sabe qué pasa si la supera?
8. ¿Alguna vez le han ofrecido una revisión o auditoría eléctrica? ¿Qué resultado tuvo?

**Bloque C. Operación y equipos**

9. ¿Qué equipos de su local funcionan las 24 horas y cuáles solo durante la atención?
10. ¿En qué momento del día siente que el local consume más?
11. Si tuviera que reducir consumo mañana, ¿sabría por dónde empezar?

**Bloque D. Solución y adopción**

12. Si recibiera un aviso en el momento en que su local se acerca a un consumo que le va a costar caro, ¿qué haría?
13. ¿Qué información le gustaría ver para saber en qué parte del local se le está yendo la energía?
14. ¿Cuánto estaría dispuesto a pagar mensualmente por una herramienta que le ahorre una parte de su recibo? ¿Qué ahorro tendría que demostrarle para que valga la pena?
15. ¿Qué tan dispuesto estaría a que le instalen un equipo de medición en su tablero eléctrico? ¿Qué le preocuparía de eso?
16. ¿Qué le haría abandonar una herramienta así después de probarla?

**Bloque E. Perfil digital**

17. ¿Qué dispositivo usa habitualmente para temas del negocio?
18. ¿Usa alguna aplicación para llevar cuentas, inventario o ventas? ¿Cuál y por qué esa?
19. ¿Cómo prefiere que le llegue un aviso urgente del local?

### 2.2.2. Registro de entrevistas

> **Pendiente de ejecución por el equipo.** Esta sección se completa con las entrevistas reales.
> Por cada entrevista se debe registrar: nombres y apellidos, edad, distrito, cargo, un screenshot
> del cuadro de video, el URL del video subido a Microsoft Stream con el *timing* de inicio y la
> duración, y un resumen descriptivo de las principales respuestas.
>
> **El resumen debe incluir todas las características objetivas y subjetivas** (personalidad,
> marcas e influencias, tecnología, canales de interacción, navegador y dispositivos), porque cada
> característica de los arquetipos de la sección 2.3 debe poder rastrearse hasta un dato recogido
> aquí.

#### Segmento #1 — Entrevista 1

| Campo | Dato |
| :-- | :-- |
| Nombres y apellidos | `<...>` |
| Edad | `<...>` |
| Distrito | `<...>` |
| Cargo / tipo de establecimiento | `<...>` |
| Número de locales a cargo | `<...>` |
| URL del video | `<...>` |
| Timing de inicio | `<mm:ss>` |
| Duración | `<mm:ss>` |
| Screenshot | `<Insertar captura del cuadro de video>` |

**Resumen de la entrevista**

`<Resumen descriptivo de las respuestas del entrevistado a las preguntas realizadas, incluyendo
características objetivas y subjetivas.>`

> Repetir esta ficha para cada entrevista: **3 a 5 por segmento**.

### 2.2.3. Análisis de entrevistas

> **Pendiente de ejecución por el equipo.** Se completa una vez registradas las entrevistas.

El análisis se realiza **por segmento**, identificando con sustento estadístico (porcentajes) las
características objetivas y subjetivas más comunes, que son las que sostienen la construcción de
los arquetipos. Cada porcentaje debe poder verificarse contra los resúmenes de la sección 2.2.2.

**Estructura del análisis por segmento**

| Característica | Hallazgo | Porcentaje | Entrevistas que lo sustentan |
| :-- | :-- | :-- | :-- |
| Rango de edad predominante | `<...>` | `<X %>` | `<E1, E2, E4>` |
| Dispositivo principal de consulta | `<...>` | `<X %>` | `<...>` |
| Canal preferido para alertas | `<...>` | `<X %>` | `<...>` |
| Conoce su potencia contratada | `<...>` | `<X %>` | `<...>` |
| Identifica el cargo por potencia sin ayuda | `<...>` | `<X %>` | `<...>` |
| Ha tenido un recibo inexplicable | `<...>` | `<X %>` | `<...>` |
| Puede atribuir consumo a una zona | `<...>` | `<X %>` | `<...>` |
| Frustración más mencionada | `<...>` | `<X %>` | `<...>` |
| Disposición a pagar una suscripción | `<...>` | `<X %>` | `<...>` |

## 2.3. Needfinding

> Los artefactos de esta sección **derivan de las entrevistas** y deben elaborarse una vez
> registradas y analizadas. Se incluye aquí la estructura y las herramientas indicadas por el
> enunciado. Construirlos antes de entrevistar invalidaría el proceso: los arquetipos dejarían de
> representar a personas reales y pasarían a ser suposiciones del equipo.

### 2.3.1. User Personas

Elaborados en **UXPressia**, uno por segmento objetivo. Cada User Persona debe incluir datos
demográficos, rasgos de personalidad, motivaciones, frustraciones, objetivos, marcas e
influencias, canales digitales y dispositivos, **todos derivados del análisis de la sección 2.2.3**.

**User Persona — Segmento #1: Responsable de operaciones de cadena**

`<Insertar imagen del User Persona elaborado en UXPressia>`

`<Párrafo explicativo del arquetipo, indicando de qué hallazgos de las entrevistas proviene cada
característica.>`

**User Persona — Segmento #2: Propietario de establecimiento independiente**

`<Insertar imagen del User Persona elaborado en UXPressia>`

`<Párrafo explicativo.>`

### 2.3.2. User Task Matrix

Matriz de tareas por User Persona, indicando frecuencia e importancia de cada tarea.

| Tarea | Persona #1 — Frecuencia | Persona #1 — Importancia | Persona #2 — Frecuencia | Persona #2 — Importancia |
| :-- | :-- | :-- | :-- | :-- |
| Revisar el consumo del día | `<Alta/Media/Baja>` | `<Alta/Media/Baja>` | `<...>` | `<...>` |
| Revisar el recibo mensual | | | | |
| Identificar la causa de una variación en el recibo | | | | |
| Atender un aviso de consumo anómalo | | | | |
| Comparar el desempeño entre locales | | | | |
| Configurar umbrales y avisos | | | | |
| Dar acceso a personal del local | | | | |
| Registrar un equipo o medidor nuevo | | | | |
| Descargar un reporte para la gerencia | | | | |

### 2.3.3. User Journey Mapping

El *User Journey Map* recorre la experiencia completa de cada User Persona a lo largo de un ciclo
de facturación, desde que empieza el mes hasta que recibe el recibo. A diferencia del *As-Is
Scenario Map*, que describe la secuencia de acciones, el *Journey Map* añade la dimensión
emocional y el nivel de conocimiento que la persona tiene en cada fase, que es lo que explica por
qué el problema persiste.

> `<Insertar los User Journey Maps elaborados en UXPressia, uno por cada User Persona.>`

**User Journey Map — User Persona #1 (responsable de operaciones de cadena)**

| Fase | Acción | Punto de contacto | Qué piensa | Emoción | Oportunidad |
| :-- | :-- | :-- | :-- | :-- | :-- |
| Inicio del mes | Recibe el presupuesto energético del trimestre | Hoja de cálculo interna | «Tengo que cerrar por debajo de lo presupuestado» | Confianza | Fijar un objetivo por local y medirlo desde el día 1 |
| Operación diaria | Delega la operación en cada jefe de tienda | Llamadas y mensajería | «Confío en que avisen si algo pasa» | Neutral | Dar a cada sede su propia vista con permisos acotados |
| Ocurre el pico | Nadie lo percibe: la operación continúa con normalidad | Ninguno | — | Ignorancia | **Alerta con margen antes de superar la potencia contratada** |
| Llega el recibo | Detecta un cargo por potencia superior al previsto | Recibo de la distribuidora | «¿De dónde salió esto?» | Frustración | Desglose por local y por zona del periodo facturado |
| Investigación | Pide explicaciones a la sede y no obtiene evidencia | Correo, reuniones | «Nadie sabe qué pasó» | Impotencia | Historial de demanda con marca temporal del pico |
| Cierre | Justifica la desviación ante gerencia sin causa raíz | Informe mensual | «El mes que viene puede repetirse» | Resignación | Comparación entre locales para aislar la sede desviada |

**User Journey Map — User Persona #2 (propietario de establecimiento independiente)**

| Fase | Acción | Punto de contacto | Qué piensa | Emoción | Oportunidad |
| :-- | :-- | :-- | :-- | :-- | :-- |
| Inicio del mes | Opera el local sin ninguna referencia de consumo | Local | «La luz es lo que es» | Indiferencia | Panel simple con el consumo del día en soles |
| Operación diaria | Enciende todo al abrir y apaga al cerrar | Tablero eléctrico | «Siempre lo hemos hecho así» | Rutina | Señalar el arranque simultáneo como causa de pico |
| Ocurre el pico | No lo percibe | Ninguno | — | Ignorancia | **Aviso inmediato en el móvil con qué hacer** |
| Llega el recibo | Ve un importe mayor sin explicación | Recibo | «¿Por qué subió si trabajé igual?» | Ansiedad | Comparación contra los tres meses anteriores |
| Reacción | Apaga equipos al azar para ahorrar | Local | «Algo tengo que hacer» | Angustia | Recomendación concreta priorizada por impacto |
| Cierre | Asume el costo como inevitable | — | «Es parte del negocio» | Resignación | Evidencia del ahorro conseguido mes a mes |

### 2.3.4. Empathy Mapping

Elaborados en **UXPressia**, uno por User Persona, con los cuadrantes *Thinks and Feels*, *Sees*,
*Says and Does*, *Hears*, *Pains* y *Gains*.

`<Insertar imagen del Empathy Map del User Persona #1 y su explicación>`

`<Insertar imagen del Empathy Map del User Persona #2 y su explicación>`

### 2.3.5. As-is Scenario Mapping

Elaborados en **LucidChart o Miro**, uno por User Persona, con las filas *Phases*, *Doing*,
*Thinking* y *Feeling*, describiendo cómo el usuario afronta hoy la gestión del costo energético
de su establecimiento **sin** la solución.

`<Insertar imagen del As-is Scenario Map del User Persona #1 y su explicación>`

`<Insertar imagen del As-is Scenario Map del User Persona #2 y su explicación>`

## 2.4. Ubiquitous Language

Lenguaje común del dominio, compartido entre el equipo técnico y los expertos del negocio. Los
términos que se listan a continuación son los que se emplean de forma consistente en los
artefactos de diseño, en el código fuente y en la interfaz de los productos.

> **Nota sobre el idioma.** Según el enunciado del curso, el idioma por defecto de la interfaz de
> usuario, de los mensajes y de la documentación de todos los productos de la solución es el
> **inglés**. Por eso cada término se registra con su denominación en inglés, que es la que aparece
> en el código y en la API, junto con su equivalente en español empleado en este informe.

| Término (EN) | Término (ES) | Definición |
| :-- | :-- | :-- |
| **Organization** | Organización | Empresa que contrata el servicio, identificada por su RUC. Puede agrupar uno o varios locales. Es el nivel al que se asocia la suscripción. |
| **Site** | Local | Establecimiento físico con su propio suministro eléctrico, su medidor, su contrato con la distribuidora y su factura. Es la unidad sobre la que se predice el gasto y se comparan desempeños. |
| **Zone** | Zona | Subdivisión funcional de un local: sala de ventas, cámaras frigoríficas, almacén, cocina, oficinas. Determina si el consumo fuera del horario de atención es esperado o anómalo. |
| **Device / Meter** | Dispositivo / Medidor | Equipo de medición instalado en un local y, opcionalmente, asignado a una zona. Reporta lecturas de consumo. |
| **Membership** | Vínculo de acceso | Relación entre una persona y una organización, con un papel y un alcance. Determina qué locales puede ver o modificar. |
| **Contracted Power** | Potencia contratada | Potencia en kW pactada con la distribuidora para un local. Superarla no interrumpe el suministro: se factura como exceso. |
| **Maximum Demand** | Demanda máxima | Mayor potencia registrada en el periodo de facturación. Determina el cargo por potencia de todo el mes, aunque el pico haya durado minutos. |
| **Peak Hours** | Hora punta | Franja de 18:00 a 23:00 de cada día del año, con precio de energía más alto. |
| **Off-Peak Hours** | Fuera de punta | Resto de las horas, con precio de energía más bajo. |
| **Excludes Sundays From Peak** | Exclusión de domingos | Opción que un suministro puede tener concedida, a solicitud del cliente, para que sus domingos y feriados se facturen fuera de punta. No es la regla general. |
| **Tariff Category** | Categoría tarifaria | Clasificación del suministro según el pliego (BT5B, BT3, BT4, MT2, MT3). Determina si el suministro paga cargo por potencia. |
| **Power Charge** | Cargo por potencia | Concepto de la factura calculado sobre la demanda máxima, independiente de la energía consumida. |
| **Excess Power** | Exceso de potencia | Diferencia entre la demanda máxima y la potencia contratada, facturada con recargo. |
| **Demand Rule** | Regla de demanda | Regla de vigilancia asociada a un local que define a qué porcentaje de la potencia contratada se emite un aviso. |
| **Bill Estimate** | Factura estimada | Proyección del recibo del periodo, desglosada en energía de punta, energía fuera de punta, cargo por potencia y cargo fijo. |
| **Consumption Alert** | Alerta de consumo | Aviso generado cuando una lectura supera un umbral configurado para un dispositivo. |
| **Subscription Plan** | Plan de suscripción | Nivel de servicio contratado por la organización, definido por el número de locales y de medidores por local. |

---

[⬅ Capítulo I](01-introduccion.md) · [Volver al índice](../README.md) · [Capítulo III ➡](03-requirements-specification.md)
