[⬅ Volver al índice](../README.md)

# Capítulo I: Introducción

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

**Energix** es una startup formada por estudiantes de Ingeniería de Software de la Universidad
Peruana de Ciencias Aplicadas. Desarrollamos **SEMS (Smart Energy Management System)**, una
plataforma de gestión energética dirigida a **establecimientos comerciales de mediana y gran
superficie**: supermercados, tiendas por departamento, minimarkets, restaurantes y almacenes.

En este tipo de local la factura eléctrica no se explica solo por cuánta energía se consume.
Bajo las categorías tarifarias comerciales del pliego peruano, el recibo suma tres conceptos
distintos: la energía consumida en hora punta, la consumida fuera de punta y un **cargo por
potencia** calculado sobre la **demanda máxima** registrada en el mes. Ese tercer concepto es el
que suele pasar desapercibido y el que puede representar cerca de la mitad del costo variable
del recibo.

SEMS mide el consumo por local y por zona, calcula la factura estimada con la tarifa comercial
que corresponde a cada suministro, y avisa **antes** de que la demanda supere la potencia
contratada, cuando todavía se puede evitar el recargo.

**Misión**

Dar a los establecimientos comerciales visibilidad y control sobre su consumo y su demanda
eléctrica, para que reduzcan su costo energético con decisiones basadas en datos y no en
suposiciones.

**Visión**

Ser la plataforma de referencia en gestión energética para el retail y los servicios en el Perú,
capaz de acompañar tanto a un local independiente como a una cadena con decenas de sedes.

**Logo de la Startup**

`<Insertar imagen del logo de Energix>`

### 1.1.2. Perfiles de integrantes del equipo

| Integrante | Código | Carrera | Perfil |
| :-- | :-- | :-- | :-- |
| `<Apellidos, Nombres>` **(Team Leader)** | `<Código>` | Ingeniería de Software | `<Foto. Párrafo de resumen con los principales conocimientos técnicos y habilidades que aporta al equipo.>` |
| `<Apellidos, Nombres>` | `<Código>` | Ingeniería de Software | `<Foto. Párrafo de resumen con los principales conocimientos técnicos y habilidades que aporta al equipo.>` |
| `<Apellidos, Nombres>` | `<Código>` | Ingeniería de Software | `<Foto. Párrafo de resumen con los principales conocimientos técnicos y habilidades que aporta al equipo.>` |
| `<Apellidos, Nombres>` | `<Código>` | Ingeniería de Software | `<Foto. Párrafo de resumen con los principales conocimientos técnicos y habilidades que aporta al equipo.>` |
| `<Apellidos, Nombres>` | `<Código>` | Ingeniería de Software | `<Foto. Párrafo de resumen con los principales conocimientos técnicos y habilidades que aporta al equipo.>` |

## 1.2. Solution Profile

### 1.2.1. Antecedentes y problemática

El sector comercial y de servicios es uno de los mayores consumidores de electricidad del país,
y dentro de él los establecimientos con refrigeración continua —supermercados, minimarkets,
restaurantes— presentan la particularidad de operar cargas que no se apagan nunca. A esto se
suma que, a partir de cierto nivel de consumo, el suministro deja de facturarse bajo una tarifa
residencial de precio único y pasa a categorías comerciales (BT3, BT4, MT2, MT3) que introducen
dos conceptos ausentes en una vivienda: la **diferenciación por franja horaria** y el **cargo por
potencia sobre la demanda máxima**.

**Estructura tarifaria (fuente verificada).** El Anexo B de la Resolución de OSINERGMIN define
literalmente el horario de punta:

> *"Se entenderá por horas de punta (HP) el período comprendido entre las 18:00 horas y 23:00 horas
> de cada día de todos los meses del año, exceptuándose a solicitud del cliente, los días domingos,
> días de descanso que correspondan a feriados y feriados que coincidan con días de descanso."*
>
> — OSINERGMIN, *Anexo B: Opciones Tarifarias y Condiciones de Aplicación de las Tarifas*.
> Disponible en https://www.osinergmin.gob.pe/Resoluciones/pdf/ANEXO_B_Resolucion_1908.pdf

Dos consecuencias de esta definición condicionan el modelo de la solución. La primera es que la
hora punta rige **todos los días**, domingos incluidos: la exclusión de domingos y feriados existe,
pero es una opción que el cliente debe solicitar a la distribuidora, no una regla general. Para un
supermercado la diferencia es relevante, porque el domingo es uno de sus días de mayor afluencia.
La segunda es que la opción tarifaria MT2 —y sus equivalentes BT2, BT3 y BT4— es una tarifa con
medición doble de energía y contratación o medición de dos potencias, lo que significa que la
factura incorpora un cargo por potencia independiente de la energía consumida.

**Dimensión del segmento (fuente verificada).** El *Anuario Estadístico de Electricidad 2024* del
MINEM registra una venta de energía eléctrica a cliente final a nivel nacional de **53 288,7 GWh**,
repartida por sector económico de la siguiente manera:

| Sector económico | Energía vendida (GWh) | Participación |
| :-- | --: | --: |
| Industrial | 31 834,9 | 59,74 % |
| Residencial | 11 112,7 | 20,85 % |
| **Comercial** | **9 157,3** | **17,18 %** |
| Alumbrado público | 1 183,9 | 2,22 % |
| **Total** | **53 288,7** | **100,00 %** |

> MINEM, *Anuario Estadístico de Electricidad 2024*, Capítulo 5 «Distribución de energía eléctrica»,
> cuadro 5.3.3.1 «Venta mensual de energía eléctrica por sector económico (GWh)». Disponible en
> <https://www.gob.pe/institucion/minem/informes-publicaciones/7324144-anuario-estadistico-de-electricidad-2024>

El sector comercial es, por tanto, un mercado de **9 157 GWh anuales**: menor que el industrial en
volumen, pero con una diferencia estructural que resulta determinante para el producto. El consumo
industrial se concentra en un número reducido de clientes de gran tamaño, muchos de ellos del
mercado libre, que cuentan con personal e instrumentación propios para la gestión energética. El
consumo comercial, en cambio, se reparte entre miles de establecimientos —supermercados, tiendas
por departamento, farmacias, cadenas de conveniencia— que enfrentan la misma estructura tarifaria
con cargo por potencia y hora punta, pero sin un área de energía que la administre. Ese desajuste
entre la complejidad de la tarifa y la capacidad instalada del cliente es el espacio que ocupa SEMS.

El problema operativo es concreto. La demanda máxima que fija el cargo por potencia del mes se
determina por el **pico más alto registrado**, aunque ese pico haya durado quince minutos. En un
supermercado, el arranque simultáneo de los compresores de las cámaras frigoríficas tras un
corte, una jornada de alta afluencia o la puesta en marcha del aire acondicionado a primera hora
bastan para producirlo. El administrador del local no dispone de ninguna señal en el momento en
que ocurre: se entera treinta días después, cuando llega el recibo, y para entonces el recargo ya
está aplicado a todo el periodo.

A esa ceguera se añade una segunda: el recibo llega agregado por suministro. No indica qué zona
del local ni qué equipo originó el consumo, de modo que aunque el responsable quiera actuar, no
sabe **dónde** actuar. En una cadena con varias sedes el problema se multiplica, porque tampoco
existe forma sencilla de comparar el desempeño energético entre locales de tamaño y tipo
similares.

**Análisis de la problemática — 5W2H**

| Elemento | Descripción |
| :-- | :-- |
| **Who** (Quién) | Responsables de operaciones y de mantenimiento de cadenas de retail, y propietarios o administradores de establecimientos comerciales independientes de mediana superficie. Ambos responden por el costo energético del local pero carecen de información oportuna para gestionarlo. |
| **What** (Qué) | Sobrecosto eléctrico originado por dos causas que el recibo mensual no permite atacar: picos de demanda que disparan el cargo por potencia, y consumo concentrado en hora punta que podría desplazarse a franjas más baratas. A ello se suma la imposibilidad de atribuir el consumo a una zona o equipo concreto. |
| **Where** (Dónde) | Perú, en establecimientos comerciales urbanos con suministro en categorías tarifarias que incluyen cargo por potencia (BT3, BT4, MT2, MT3), principalmente en Lima Metropolitana y capitales de provincia. |
| **When** (Cuándo) | De forma continua durante la operación del local. El pico de demanda se produce típicamente en el arranque de la jornada y en las horas de mayor afluencia, que además coinciden con la hora punta del sistema (18:00–23:00 de todos los días, salvo que la distribuidora haya concedido la exclusión de domingos a solicitud del cliente). |
| **Why** (Por qué) | Porque la medición disponible es agregada y diferida: un único medidor por suministro y una única lectura mensual. No existe visibilidad por zona, ni distinción por franja horaria, ni ninguna alerta que llegue mientras el problema todavía se puede corregir. |
| **How** (Cómo) | Mediante medición por zona dentro de cada local, cálculo de la factura estimada con la tarifa comercial correspondiente al suministro, y alertas de demanda que se disparan al aproximarse a la potencia contratada, antes de superarla. |
| **How Much** (Cuánto) | El cargo por potencia puede representar cerca de la mitad del costo variable de un recibo comercial. Evitar un único pico mensual de exceso, o desplazar parte del consumo fuera de hora punta, produce ahorros directos y recurrentes. `<Sustentar con el cálculo del caso de estudio del equipo y con el pliego tarifario vigente.>` |

### 1.2.2. Lean UX Process

#### 1.2.2.1. Lean UX Problem Statements

**Domain**

Gestión del consumo y de la demanda eléctrica en establecimientos comerciales sujetos a
tarifas con cargo por potencia.

**Customer Segments**

Responsables de operaciones y mantenimiento de cadenas de retail, y propietarios o
administradores de establecimientos comerciales independientes.

**Pain Points**

- La factura eléctrica llega agregada y con un mes de retraso, cuando ya no se puede actuar.
- El cargo por potencia se fija por un pico puntual que nadie observa en el momento en que ocurre.
- No se puede atribuir el consumo a una zona concreta del local, así que no se sabe dónde intervenir.
- En una cadena no hay forma de comparar el desempeño entre locales para identificar cuáles están mal.
- Las soluciones existentes están diseñadas para el hogar y no modelan potencia contratada ni franjas horarias.

**Gap**

Existen medidores y plataformas de monitoreo energético, pero orientados al consumo doméstico:
reportan kilovatios-hora a un precio único. Ninguno de los que analizamos modela la estructura
tarifaria comercial peruana —hora punta, fuera de punta y demanda máxima— que es precisamente
donde se origina el sobrecosto del segmento.

**Vision / Strategy**

Convertir la factura eléctrica de un establecimiento en algo observable y accionable: medir por
zona, calcular con la tarifa real del suministro y avisar mientras todavía queda margen para
reaccionar.

**Initial Segment**

Establecimientos comerciales de Lima Metropolitana con superficie entre 200 y 2.000 m² y
suministro en categoría tarifaria con cargo por potencia.

**Enunciado del problema**

> Los establecimientos comerciales pagan un sobrecosto eléctrico que no pueden explicar ni
> anticipar, porque su única fuente de información es un recibo mensual agregado que llega
> cuando el cargo por potencia del periodo ya está determinado.
>
> Hemos observado que las plataformas de monitoreo energético disponibles fueron diseñadas para
> el consumo doméstico y reportan energía a precio único, lo que deja fuera los dos conceptos que
> más pesan en una factura comercial: la franja horaria y la demanda máxima.
>
> **¿Cómo podríamos** dar a los responsables de un establecimiento visibilidad por zona y avisos
> oportunos sobre su demanda, de modo que puedan evitar el recargo por potencia y desplazar
> consumo fuera de hora punta, sin exigirles conocimientos de ingeniería eléctrica?

#### 1.2.2.2. Lean UX Assumptions

**Business Assumptions**

1. Creemos que nuestros clientes necesitan visibilidad de su demanda eléctrica en el momento en que se produce, y no un mes después.
2. Estas necesidades se pueden resolver con una plataforma que mida por zona y calcule con la tarifa comercial del suministro.
3. Nuestros clientes iniciales son responsables de operaciones y propietarios de establecimientos comerciales con cargo por potencia.
4. El valor número uno que un cliente quiere de nuestro servicio es **evitar el recargo por exceso de demanda**.
5. El cliente también puede obtener beneficios adicionales como el desglose de consumo por zona y la comparación entre locales de la cadena.
6. Vamos a adquirir la mayoría de nuestros clientes mediante venta directa a cadenas y a través de gremios de comerciantes.
7. Generaremos ingresos mediante una suscripción mensual escalonada por número de locales gestionados.
8. Nuestra principal competencia en el mercado serán los proveedores de medidores inteligentes y las empresas de eficiencia energética que ofrecen auditorías puntuales.
9. Los venceremos porque entregamos monitoreo continuo y modelamos la tarifa comercial peruana, en lugar de un informe estático o un reporte de kWh.
10. Nuestro mayor riesgo es que la instalación del hardware de medición por zona resulte demasiado costosa o invasiva para el local.
11. Resolveremos esto permitiendo empezar con un solo medidor por local y añadir zonas de forma incremental.

**User Assumptions**

| Pregunta | Supuesto |
| :-- | :-- |
| ¿Quién es el usuario? | El responsable de operaciones o mantenimiento de una cadena, y el propietario o administrador de un local independiente. |
| ¿Dónde encaja nuestro producto en su trabajo o vida? | En la revisión operativa diaria del local y en el cierre mensual de costos. |
| ¿Qué problemas tiene nuestro producto que resolver? | La imposibilidad de anticipar el cargo por potencia y de atribuir el consumo a una zona. |
| ¿Cuándo y cómo es usado nuestro producto? | Consulta diaria breve desde el panel web, y reacción inmediata cuando llega una alerta de demanda. |
| ¿Qué características son importantes? | Alerta de demanda con margen, factura estimada desglosada, consumo por zona y comparación entre locales. |
| ¿Cómo debe verse y comportarse nuestro producto? | Directo y legible por personal no técnico: la alerta debe decir qué está pasando y cuánto margen queda, no mostrar una curva que haya que interpretar. |

#### 1.2.2.3. Lean UX Hypothesis Statements

**Hipótesis 1**

> **Creemos que** al notificar al responsable del local cuando la demanda alcanza el 85% de la
> potencia contratada
> **lograremos** que reduzca carga a tiempo y evite el recargo por exceso.
> **Sabremos que** hemos tenido éxito **cuando** al menos el 60% de las alertas de nivel *warning*
> vayan seguidas de un descenso de la demanda por debajo del umbral en los siguientes 30 minutos.

**Hipótesis 2**

> **Creemos que** al mostrar la factura estimada desglosada en energía, potencia y cargo fijo
> **lograremos** que el responsable identifique el peso real del cargo por potencia.
> **Sabremos que** hemos tenido éxito **cuando** más del 70% de los usuarios entrevistados sepa
> indicar, tras usar el panel, qué concepto pesa más en su recibo.

**Hipótesis 3**

> **Creemos que** al desglosar el consumo por zona dentro del local
> **lograremos** que las acciones de ahorro se dirijan a las zonas de mayor gasto.
> **Sabremos que** hemos tenido éxito **cuando** al menos el 50% de los locales con más de una
> zona registrada consulte la vista por zona al menos una vez por semana.

**Hipótesis 4**

> **Creemos que** al permitir comparar el consumo entre locales de una misma cadena
> **lograremos** que el responsable de operaciones detecte los locales con peor desempeño.
> **Sabremos que** hemos tenido éxito **cuando** las cuentas con tres o más locales usen la
> comparación al menos una vez al mes.

**Hipótesis 5**

> **Creemos que** al informar qué proporción del consumo cae en hora punta
> **lograremos** que el local desplace cargas desplazables a franjas más baratas.
> **Sabremos que** hemos tenido éxito **cuando** los locales que reciben la recomendación reduzcan
> su proporción de consumo en punta en al menos 5 puntos porcentuales en dos meses.

#### 1.2.2.4. Lean UX Canvas

`<Insertar imagen del Lean UX Canvas elaborado por el equipo, con los ocho cuadrantes:
1. Business Problem · 2. Business Outcomes · 3. Users · 4. User Outcomes & Benefits ·
5. Solutions · 6. Hypotheses · 7. What's the most important thing we need to learn first? ·
8. What's the least amount of work we need to do to learn the next most important thing?>`

| Cuadrante | Contenido |
| :-- | :-- |
| 1. Business Problem | Los establecimientos comerciales pagan un sobrecosto eléctrico que no pueden anticipar, porque el recibo mensual agregado llega cuando el cargo por potencia del periodo ya está fijado. |
| 2. Business Outcomes | Suscripciones activas de locales, tasa de renovación mensual, número de alertas de demanda atendidas a tiempo. |
| 3. Users | Responsable de operaciones o mantenimiento de cadena; propietario o administrador de local independiente. |
| 4. User Outcomes & Benefits | Evitar el recargo por exceso de demanda; saber en qué zona se va la energía; reducir el consumo en hora punta; comparar locales. |
| 5. Solutions | Medición por local y por zona; alerta de demanda con umbral configurable; factura estimada con tarifa comercial desglosada; comparación entre locales. |
| 6. Hypotheses | Las cinco hipótesis enunciadas en la sección 1.2.2.3. |
| 7. Lo más importante que necesitamos aprender primero | Si el aviso anticipado de demanda efectivamente provoca una acción de reducción de carga en el local, o si el responsable lo ignora por falta de margen operativo. |
| 8. Trabajo mínimo para aprenderlo | Instrumentar un local piloto con un único medidor, configurar la regla de demanda y registrar durante un mes qué ocurre tras cada alerta. |

## 1.3. Segmentos objetivo

Se han definido dos segmentos objetivo. Ambos responden por el costo energético de un
establecimiento comercial, pero se diferencian en la escala que gestionan, en el margen de
decisión que tienen y en el tipo de evidencia que necesitan para adoptar la solución.

### Segmento objetivo #1: Responsables de operaciones y mantenimiento de cadenas de retail

**Aspectos demográficos**

- Sexo: hombres y mujeres.
- Edad: entre 30 y 55 años.
- Formación: técnica o universitaria, con frecuencia en ingeniería industrial, electromecánica o administración.
- Cargo: jefe de operaciones, jefe de mantenimiento, coordinador de facilities o gerente de tienda regional.

**Aspectos geográficos**

- Nacionalidad: principalmente peruanos.
- Zona: urbana. Lima Metropolitana y capitales de provincia.
- Ámbito de responsabilidad: entre 2 y 40 locales.

**Aspectos psicográficos**

Responden ante una gerencia por indicadores de costo operativo y deben justificar cada inversión
con retorno demostrable. Valoran la evidencia por encima del argumento comercial: prefieren una
prueba en un local antes que una propuesta para toda la cadena. Están habituados a trabajar con
tableros e indicadores y toleran cierta complejidad si el dato es fiable.

**Aspectos conductuales**

Revisan indicadores de forma periódica, no continua. Reaccionan ante desviaciones, no ante
tendencias. Necesitan poder delegar la operación diaria en el personal de cada local, lo que
implica que la herramienta debe admitir varios usuarios con permisos distintos por sede.

### Segmento objetivo #2: Propietarios y administradores de establecimientos independientes

**Aspectos demográficos**

- Sexo: hombres y mujeres.
- Edad: entre 28 y 60 años.
- Formación: variable, frecuentemente sin especialización técnica en energía.
- Situación: propietario, socio o administrador de un único local de entre 200 y 800 m².

**Aspectos geográficos**

- Nacionalidad: principalmente peruanos.
- Zona: urbana, en distritos con actividad comercial densa.

**Aspectos psicográficos**

El recibo eléctrico es uno de sus costos fijos más altos y una fuente recurrente de
incertidumbre. No tienen formación eléctrica y desconfían de las propuestas que no puedan
verificar. Su criterio de adopción es el retorno inmediato y comprensible.

**Aspectos conductuales**

Descubren el problema cuando el recibo sube y no saben por qué. Tienen poca disponibilidad para
configurar herramientas y baja tolerancia a instalaciones invasivas que interrumpan la operación
del local. Necesitan que la herramienta les diga qué hacer, no que les entregue datos para que
ellos los interpreten.

---

[⬅ Volver al índice](../README.md) · [Capítulo II ➡](02-requirements-elicitation.md)
