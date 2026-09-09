[⬅ Volver al índice](../README.md)

# Capítulo III: Requirements Specification

En este capítulo se especifican los requisitos de los productos digitales de la solución a partir
del análisis realizado en el capítulo anterior. Se inicia con el To-Be Scenario Mapping, que
describe cómo cambia la experiencia del usuario al incorporar SEMS, y continúa con las User
Stories, el Impact Mapping y el Product Backlog priorizado.

## 3.1. To-Be Scenario Mapping

> Se elabora en **LucidChart o Miro**, uno por User Persona, una vez construidos los As-Is de la
> sección 2.3.4.

El proceso seguido por el equipo comprende las etapas de preparación, lluvia de ideas individual,
revisión conjunta, identificación de fases como columnas, denominación de las fases y comparación
con el As-Is correspondiente para hacer explícitos los cambios que introduce la solución.

**To-Be Scenario Map — User Persona #1: Responsable de operaciones de cadena**

`<Insertar imagen con las filas Phases, Doing, Thinking y Feeling>`

`<Explicación del mapa y comparación con el As-Is: qué fases desaparecen, cuáles se acortan y en
qué punto del recorrido el usuario pasa de reaccionar a anticipar.>`

**To-Be Scenario Map — User Persona #2: Propietario de establecimiento independiente**

`<Insertar imagen>`

`<Explicación y comparación con el As-Is.>`

## 3.2. User Stories

Las User Stories se redactan bajo el formato *Como \<rol\>, deseo \<objetivo\> para \<beneficio\>*,
con criterios de aceptación en estructura Gherkin (Given–When–Then). Los criterios se expresan en
tiempo presente y tercera persona, son comprobables y no hacen referencia a detalles de interfaz.

Se incluyen tres tipos de historia:

- **De usuario final**, para la aplicación web y móvil, con los roles derivados de los User Personas.
- **De visitante**, para el Landing Page, con el rol *visitante* o su subconjunto por segmento.
- **Technical Stories**, para los componentes sin interacción directa con el usuario final —los
  RESTful APIs—, redactadas con el rol *Developer* y con criterios expresados como escenarios de
  request/response.

### Epics

| Epic ID | Título | Descripción |
| :-- | :-- | :-- |
| **EP01** | Landing Page | Como visitante, deseo conocer la propuesta de valor de SEMS y acceder a la aplicación, para evaluar si resuelve el problema de costo energético de mi establecimiento. |
| **EP02** | Identidad y control de acceso | Como responsable de una organización, deseo gestionar quién accede a qué locales, para que cada persona vea únicamente lo que le corresponde. |
| **EP03** | Gestión de la organización y sus locales | Como administrador, deseo registrar mi cadena y sus locales con sus datos de suministro, para que el sistema calcule sobre la tarifa correcta de cada uno. |
| **EP04** | Gestión de zonas y medidores | Como supervisor, deseo organizar mi local en zonas y asignar medidores, para saber en qué parte del local se consume la energía. |
| **EP05** | Monitoreo de consumo | Como supervisor, deseo consultar el consumo de mi local en el tiempo, para detectar variaciones y entender el comportamiento de mis equipos. |
| **EP06** | Control de demanda y alertas | Como responsable, deseo ser avisado antes de superar la potencia contratada, para reducir carga a tiempo y evitar el recargo. |
| **EP07** | Analítica y proyección de factura | Como responsable, deseo conocer la factura estimada del periodo desglosada, para saber qué concepto pesa más y dónde actuar. |
| **EP08** | Suscripciones y pagos | Como administrador, deseo contratar y gestionar el plan que corresponde al tamaño de mi cadena, para acceder a las funcionalidades que necesito. |
| **EP09** | Plataforma y servicios (Technical) | Como developer, deseo disponer de un API RESTful documentado y seguro, para integrar los productos digitales de la solución. |

### User Stories

| Epic / User Story ID | Título | Descripción | Criterios de aceptación | Relacionado con (Epic ID) |
| :-- | :-- | :-- | :-- | :-- |
| **US01** | Sección hero del Landing Page | Como visitante, deseo comprender en la primera pantalla qué problema resuelve SEMS, para decidir en segundos si me interesa. | **Escenario:** el visitante llega al Landing Page.<br>**Given** el visitante accede a la página principal,<br>**When** la página termina de cargar,<br>**Then** se muestra la propuesta de valor centrada en el control del costo energético de establecimientos comerciales<br>**And** se muestra un call-to-action visible hacia el registro. | EP01 |
| **US02** | Explicación del cargo por potencia | Como visitante del segmento de establecimientos, deseo entender por qué un pico de minutos encarece mi recibo del mes, para reconocer el problema como propio. | **Given** el visitante se desplaza a la sección de problemática,<br>**When** visualiza el contenido,<br>**Then** se presenta con un ejemplo numérico la diferencia entre el costo de energía y el cargo por potencia. | EP01 |
| **US03** | Sección de planes en el Landing Page | Como visitante, deseo conocer los planes y sus límites, para estimar cuál corresponde a mi caso antes de registrarme. | **Given** el visitante accede a la sección de planes,<br>**When** visualiza el contenido,<br>**Then** se muestran los planes disponibles con su precio y su límite de locales<br>**And** cada plan presenta un call-to-action que redirige al registro de la aplicación web. | EP01 |
| **US04** | Navegación del Landing Page | Como visitante, deseo desplazarme entre las secciones del Landing Page, para revisar la información en el orden que me interesa. | **Given** el visitante se encuentra en cualquier sección,<br>**When** selecciona un elemento del menú de navegación,<br>**Then** la vista se desplaza a la sección correspondiente. | EP01 |
| **US05** | Selección de idioma en el Landing Page | Como visitante, deseo cambiar el idioma del Landing Page, para leer el contenido en el idioma que domino. | **Given** el visitante se encuentra en el Landing Page,<br>**When** selecciona un idioma disponible,<br>**Then** el contenido textual se presenta en el idioma seleccionado<br>**And** la selección persiste al navegar entre secciones. | EP01 |
| **US06** | Registro de cuenta | Como visitante, deseo crear una cuenta con mi correo y contraseña, para acceder a la aplicación. | **Escenario 1:** registro correcto.<br>**Given** el visitante proporciona un correo no registrado y una contraseña válida,<br>**When** confirma el registro,<br>**Then** la cuenta se crea y se emite un token de sesión.<br><br>**Escenario 2:** correo ya registrado.<br>**Given** el visitante proporciona un correo existente,<br>**When** confirma el registro,<br>**Then** el sistema informa que el correo ya está en uso y no crea una cuenta duplicada. | EP02 |
| **US07** | Inicio de sesión | Como usuario registrado, deseo iniciar sesión, para acceder a la información de mis locales. | **Escenario 1:** credenciales correctas.<br>**Given** el usuario proporciona credenciales válidas,<br>**When** confirma el inicio de sesión,<br>**Then** se emite un token de sesión y accede a la aplicación.<br><br>**Escenario 2:** credenciales incorrectas.<br>**Given** el usuario proporciona una contraseña incorrecta,<br>**When** confirma el inicio de sesión,<br>**Then** el acceso se rechaza sin revelar si el correo existe. | EP02 |
| **US08** | Recuperación de contraseña | Como usuario registrado, deseo restablecer mi contraseña, para recuperar el acceso si la olvido. | **Given** el usuario solicita el restablecimiento indicando su correo,<br>**When** confirma la solicitud,<br>**Then** el sistema responde de forma idéntica exista o no la cuenta<br>**And** si la cuenta existe, se envía un enlace de restablecimiento de un solo uso. | EP02 |
| **US09** | Cierre de sesión | Como usuario autenticado, deseo cerrar sesión, para impedir el acceso desde un equipo compartido del local. | **Given** el usuario tiene una sesión activa,<br>**When** cierra la sesión,<br>**Then** el token deja de ser válido para peticiones posteriores. | EP02 |
| **US10** | Asignación de acceso a una persona | Como administrador de la organización, deseo dar acceso a una persona indicando su papel y su alcance, para que gestione únicamente lo que le corresponde. | **Escenario 1:** supervisor con local asignado.<br>**Given** el administrador indica el papel *supervisor* y un local de su organización,<br>**When** confirma la asignación,<br>**Then** el vínculo se crea y la persona accede solo a ese local.<br><br>**Escenario 2:** supervisor sin local.<br>**Given** el administrador indica el papel *supervisor* sin local,<br>**When** confirma la asignación,<br>**Then** la operación se rechaza indicando que un supervisor requiere un local asignado. | EP02 |
| **US11** | Revocación de acceso | Como administrador, deseo revocar el acceso de una persona, para retirar permisos cuando deja el puesto. | **Escenario 1:** revocación válida.<br>**Given** existe más de un administrador en la organización,<br>**When** el administrador revoca un vínculo,<br>**Then** la persona pierde el acceso.<br><br>**Escenario 2:** último administrador.<br>**Given** queda un único administrador,<br>**When** se intenta revocar su vínculo,<br>**Then** la operación se rechaza para no dejar la organización sin gestión posible. | EP02 |
| **US12** | Registro de la organización | Como administrador, deseo registrar mi empresa con su RUC y tipo de negocio, para agrupar bajo ella todos mis locales. | **Escenario 1:** RUC válido.<br>**Given** el administrador proporciona una razón social y un RUC de once dígitos no registrado,<br>**When** confirma el registro,<br>**Then** la organización se crea y queda como administrador de ella.<br><br>**Escenario 2:** RUC con formato inválido.<br>**Given** el RUC no tiene once dígitos numéricos,<br>**When** confirma el registro,<br>**Then** la operación se rechaza indicando el formato esperado.<br><br>**Escenario 3:** RUC duplicado.<br>**Given** el RUC ya pertenece a otra organización,<br>**When** confirma el registro,<br>**Then** la operación se rechaza. | EP03 |
| **US13** | Registro de un local | Como administrador, deseo registrar un local con su potencia contratada y su categoría tarifaria, para que el sistema calcule sobre la tarifa que realmente le aplica. | **Escenario 1:** alta correcta.<br>**Given** el administrador proporciona código, nombre, potencia contratada mayor que cero y categoría tarifaria válida,<br>**When** confirma el alta,<br>**Then** el local queda registrado en la organización.<br><br>**Escenario 2:** código duplicado.<br>**Given** el código de local ya existe en esa organización,<br>**When** confirma el alta,<br>**Then** la operación se rechaza.<br><br>**Escenario 3:** potencia no válida.<br>**Given** la potencia contratada es cero o negativa,<br>**When** confirma el alta,<br>**Then** la operación se rechaza. | EP03 |
| **US14** | Consulta de los locales de la organización | Como responsable de operaciones, deseo ver la lista de mis locales vigentes, para acceder a cada uno desde un punto único. | **Given** el usuario está autenticado y pertenece a la organización,<br>**When** consulta los locales,<br>**Then** se listan los locales vigentes<br>**And** los locales archivados no aparecen en el listado. | EP03 |
| **US15** | Actualización de los datos de un local | Como supervisor, deseo actualizar los datos de mi local, para reflejar un cambio de potencia contratada o de categoría tarifaria. | **Given** el supervisor modifica la potencia contratada de su local por un valor mayor que cero,<br>**When** confirma el cambio,<br>**Then** los cálculos posteriores de factura estimada utilizan el nuevo valor. | EP03 |
| **US16** | Archivado de un local | Como administrador, deseo archivar un local que ha cerrado, para que deje de aparecer sin perder su histórico. | **Given** el administrador archiva un local,<br>**When** consulta el listado de locales,<br>**Then** el local no aparece<br>**And** su información histórica permanece almacenada. | EP03 |
| **US17** | Consulta de mis organizaciones | Como usuario, deseo ver a qué organizaciones pertenezco y con qué papel, para cambiar de contexto cuando trabajo para más de una. | **Given** el usuario tiene vínculos vigentes con una o más organizaciones,<br>**When** consulta sus organizaciones,<br>**Then** se listan con el papel y el alcance que tiene en cada una. | EP03 |
| **US18** | Registro de zonas de un local | Como supervisor, deseo dividir mi local en zonas, para saber en qué parte se consume la energía. | **Escenario 1:** alta de zona.<br>**Given** el supervisor indica un nombre y un tipo de zona válido,<br>**When** confirma el alta,<br>**Then** la zona queda registrada en el local.<br><br>**Escenario 2:** deducción del funcionamiento fuera de horario.<br>**Given** el supervisor registra una zona de tipo cámara frigorífica sin especificar si opera fuera del horario,<br>**When** confirma el alta,<br>**Then** la zona se marca como operativa fuera del horario de atención. | EP04 |
| **US19** | Registro de un medidor en un local | Como supervisor, deseo registrar un medidor indicando su local y su zona, para atribuir su consumo al suministro y al área correctos. | **Escenario 1:** alta correcta.<br>**Given** el supervisor indica un local vigente y una zona perteneciente a ese local,<br>**When** confirma el alta,<br>**Then** el medidor queda asociado a ese local y a esa zona.<br><br>**Escenario 2:** zona de otro local.<br>**Given** la zona indicada pertenece a un local distinto,<br>**When** confirma el alta,<br>**Then** la operación se rechaza.<br><br>**Escenario 3:** código de medidor duplicado.<br>**Given** el código externo del medidor ya está registrado,<br>**When** confirma el alta,<br>**Then** la operación se rechaza. | EP04 |
| **US20** | Consulta de medidores por local | Como supervisor, deseo ver los medidores instalados en mi local, para verificar la cobertura de la medición. | **Given** el supervisor consulta los medidores de su local,<br>**When** se obtiene el listado,<br>**Then** se muestran los medidores vigentes del local<br>**And** los medidores dados de baja no aparecen. | EP04 |
| **US21** | Consulta de medidores por zona | Como supervisor, deseo ver los medidores de una zona concreta, para revisar el consumo de esa área. | **Given** el supervisor consulta los medidores de una zona,<br>**When** se obtiene el listado,<br>**Then** se muestran únicamente los medidores asignados a esa zona. | EP04 |
| **US22** | Traslado de un medidor entre zonas | Como supervisor, deseo reasignar un medidor a otra zona del mismo local, para reflejar un traslado de equipo. | **Escenario 1:** zona del mismo local.<br>**Given** la zona destino pertenece al local del medidor,<br>**When** el supervisor confirma el cambio,<br>**Then** el medidor queda asignado a la nueva zona.<br><br>**Escenario 2:** zona de otro local.<br>**Given** la zona destino pertenece a otro local,<br>**When** el supervisor confirma el cambio,<br>**Then** la operación se rechaza. | EP04 |
| **US23** | Baja de un medidor | Como supervisor, deseo dar de baja un medidor retirado, para que deje de contar en mi cupo y en los listados. | **Given** el supervisor da de baja un medidor,<br>**When** consulta nuevamente los medidores del local,<br>**Then** el medidor no aparece<br>**And** el cupo de medidores del plan se libera<br>**And** las lecturas históricas del medidor se conservan. | EP04 |
| **US24** | Consulta del consumo actual | Como supervisor, deseo ver el consumo actual de mi local, para saber cómo está operando en este momento. | **Given** el local tiene al menos un medidor con lecturas,<br>**When** el supervisor consulta el consumo actual,<br>**Then** se presenta la última lectura registrada con su marca de tiempo. | EP05 |
| **US25** | Consulta del histórico de consumo | Como supervisor, deseo consultar el consumo histórico de un medidor, para comparar periodos. | **Given** el supervisor indica un medidor y un rango,<br>**When** consulta el histórico,<br>**Then** se presentan las lecturas del periodo ordenadas cronológicamente. | EP05 |
| **US26** | Consumo desglosado por zona | Como supervisor, deseo ver el consumo agrupado por zona, para identificar qué área concentra el gasto. | **Given** el local tiene zonas con medidores asignados,<br>**When** el supervisor consulta el consumo por zona,<br>**Then** se presenta el consumo agregado de cada zona en el periodo. | EP05 |
| **US27** | Consulta de la tarifa vigente | Como supervisor, deseo consultar la tarifa aplicable a mi local, para conocer los precios de energía y el cargo por potencia. | **Given** el local tiene una categoría tarifaria asignada,<br>**When** el supervisor consulta la tarifa,<br>**Then** se presentan el precio de energía en punta, el precio fuera de punta, el cargo por potencia y el horario de punta vigente. | EP05 |
| **US28** | Creación de una regla de demanda | Como responsable, deseo definir a qué porcentaje de mi potencia contratada quiero ser avisado, para tener margen de reacción. | **Escenario 1:** regla válida.<br>**Given** el responsable indica una potencia contratada mayor que cero y un porcentaje de aviso entre 1 y 100,<br>**When** confirma la creación,<br>**Then** la regla queda activa para el local.<br><br>**Escenario 2:** porcentaje fuera de rango.<br>**Given** el porcentaje indicado es cero o mayor que 100,<br>**When** confirma la creación,<br>**Then** la operación se rechaza. | EP06 |
| **US29** | Aviso de demanda con margen | Como responsable, deseo recibir un aviso cuando la demanda de mi local se acerca a la potencia contratada, para reducir carga antes del recargo. | **Given** existe una regla de demanda activa con umbral de aviso,<br>**When** la demanda registrada alcanza o supera el umbral sin superar la potencia contratada,<br>**Then** se genera una alerta de severidad *warning*<br>**And** la alerta indica cuántos kW de margen quedan. | EP06 |
| **US30** | Aviso de exceso de potencia | Como responsable, deseo saber cuándo he superado la potencia contratada, para dimensionar el recargo del periodo y evitar que se repita. | **Given** existe una regla de demanda activa,<br>**When** la demanda registrada supera la potencia contratada,<br>**Then** se genera una alerta de severidad *critical*<br>**And** la alerta indica cuántos kW se ha excedido. | EP06 |
| **US31** | Ausencia de aviso por debajo del umbral | Como responsable, deseo no recibir avisos cuando la operación es normal, para que la alerta conserve su valor. | **Given** existe una regla de demanda activa,<br>**When** la demanda registrada es inferior al umbral de aviso,<br>**Then** no se genera ninguna alerta. | EP06 |
| **US32** | Umbrales de consumo por dispositivo | Como supervisor, deseo definir umbrales de consumo para un equipo, para detectar comportamientos anómalos. | **Given** el supervisor define un umbral con un operador y un valor para un dispositivo,<br>**When** una lectura del dispositivo cumple la condición del umbral,<br>**Then** se genera una alerta de consumo asociada al dispositivo. | EP06 |
| **US33** | Consulta y resolución de alertas | Como supervisor, deseo revisar y marcar como resueltas las alertas de mi local, para llevar control de las atendidas. | **Given** existen alertas generadas para el usuario,<br>**When** consulta el listado,<br>**Then** se presentan con su severidad, mensaje y estado<br>**And** al marcar una alerta como resuelta, su estado cambia y deja de figurar como pendiente. | EP06 |
| **US34** | Preferencias de notificación | Como responsable, deseo configurar por qué canal y con qué severidad mínima recibo avisos, para no ser interrumpido por alertas menores. | **Given** el responsable define una severidad mínima y un canal,<br>**When** se genera una alerta de severidad inferior a la configurada,<br>**Then** la alerta se registra pero no se notifica por ese canal. | EP06 |
| **US35** | Proyección de factura del periodo | Como responsable, deseo conocer la factura estimada de mi local desglosada, para saber qué concepto pesa más. | **Given** el responsable indica el consumo previsto en punta y fuera de punta, la demanda máxima y la potencia contratada del local,<br>**When** solicita la proyección,<br>**Then** se presentan el costo de energía, el costo de potencia, el cargo fijo, el IGV y el total<br>**And** se indica si existe exceso sobre la potencia contratada. | EP07 |
| **US36** | Peso del cargo por potencia | Como responsable, deseo ver qué proporción de mi factura corresponde al cargo por potencia, para decidir si conviene actuar sobre el pico o sobre el consumo. | **Given** existe una proyección de factura calculada,<br>**When** el responsable la consulta,<br>**Then** se presenta la proporción del subtotal que corresponde al cargo por potencia. | EP07 |
| **US37** | Recomendaciones de ahorro | Como responsable, deseo recibir recomendaciones concretas para reducir mi costo, para saber por dónde empezar. | **Given** existen datos de consumo del local por franja horaria,<br>**When** el responsable consulta las recomendaciones,<br>**Then** se presentan recomendaciones con el ahorro estimado asociado a cada una. | EP07 |
| **US38** | Detección de anomalías de consumo | Como supervisor, deseo que el sistema señale consumos atípicos, para investigar posibles fallas o desperdicios. | **Given** existe un histórico de consumo del local,<br>**When** una lectura se desvía significativamente del patrón del periodo,<br>**Then** se registra una anomalía consultable por el usuario. | EP07 |
| **US39** | Comparación entre locales | Como responsable de operaciones, deseo comparar el desempeño energético de mis locales, para identificar los que están peor. | **Given** la organización tiene dos o más locales con datos de consumo,<br>**When** el responsable consulta la comparación,<br>**Then** se presentan los locales ordenados por un indicador comparable entre ellos. | EP07 |
| **US40** | Consulta de planes disponibles | Como administrador, deseo ver los planes con sus límites y precios, para elegir el que corresponde a mi cadena. | **Given** el administrador está autenticado,<br>**When** consulta los planes,<br>**Then** se listan los planes con su precio, su límite de locales y su límite de medidores por local. | EP08 |
| **US41** | Contratación de un plan | Como administrador, deseo contratar un plan, para habilitar las funcionalidades que necesita mi organización. | **Given** el administrador selecciona un plan y un método de pago válido,<br>**When** confirma la contratación,<br>**Then** la suscripción queda activa para la organización<br>**And** se habilitan los límites correspondientes al plan. | EP08 |
| **US42** | Límite de locales según el plan | Como administrador, deseo que el sistema respete el límite de locales de mi plan, para conocer cuándo necesito ampliarlo. | **Given** la organización alcanzó el límite de locales de su plan,<br>**When** intenta registrar un local adicional,<br>**Then** la operación se rechaza indicando el límite del plan vigente. | EP08 |
| **US43** | Registro de método de pago | Como administrador, deseo registrar un método de pago, para automatizar la renovación de la suscripción. | **Given** el administrador proporciona los datos de la tarjeta en el formulario de la pasarela,<br>**When** confirma el registro,<br>**Then** el método de pago queda asociado a la organización<br>**And** los datos de la tarjeta no son almacenados por la aplicación. | EP08 |
| **US44** | Consulta de comprobantes | Como administrador, deseo consultar mis comprobantes de pago, para llevar el control contable de la suscripción. | **Given** existen pagos registrados para la organización,<br>**When** el administrador consulta los comprobantes,<br>**Then** se listan con su fecha, importe y estado. | EP08 |
| **TS01** | API de autenticación | Como developer, deseo un endpoint de autenticación que emita tokens, para proteger el acceso a los recursos del API. | **Escenario 1:** credenciales válidas.<br>**Given** una petición `POST /api/v1/auth/login` con credenciales válidas,<br>**When** el servicio procesa la petición,<br>**Then** responde `200 OK` con un token de sesión.<br><br>**Escenario 2:** credenciales inválidas.<br>**Given** una petición con contraseña incorrecta,<br>**When** el servicio procesa la petición,<br>**Then** responde `401 Unauthorized` sin indicar si el correo existe. | EP09 |
| **TS02** | Protección por defecto de los endpoints | Como developer, deseo que todo endpoint exija sesión salvo los explícitamente públicos, para que un descuido no deje un recurso abierto. | **Escenario 1:** sin token.<br>**Given** una petición a un endpoint protegido sin cabecera de autorización,<br>**When** el servicio la procesa,<br>**Then** responde `401 Unauthorized`.<br><br>**Escenario 2:** token inválido.<br>**Given** una petición con un token mal formado,<br>**When** el servicio la procesa,<br>**Then** responde `401 Unauthorized`. | EP09 |
| **TS03** | API de organizaciones y locales | Como developer, deseo endpoints para gestionar organizaciones, locales y zonas, para que las aplicaciones cliente construyan la jerarquía del negocio. | **Escenario 1:** alta correcta.<br>**Given** una petición `POST /api/v1/organizations` con cuerpo válido y token,<br>**When** el servicio la procesa,<br>**Then** responde `201 Created` con el recurso creado.<br><br>**Escenario 2:** recurso inexistente.<br>**Given** una petición `GET /api/v1/organizations/{id}` con un identificador no registrado,<br>**When** el servicio la procesa,<br>**Then** responde `404 Not Found`.<br><br>**Escenario 3:** identificador mal formado.<br>**Given** una petición con un identificador que no es un UUID,<br>**When** el servicio la procesa,<br>**Then** responde `400 Bad Request`. | EP09 |
| **TS04** | API de cálculo de factura | Como developer, deseo un endpoint que calcule la factura estimada a partir del consumo y la demanda, para que las aplicaciones no repliquen la lógica tarifaria. | **Given** una petición `POST /api/v1/energy/bill-estimate` con categoría tarifaria, potencia contratada, consumo por franja y demanda máxima,<br>**When** el servicio la procesa,<br>**Then** responde `200 OK` con el desglose de energía, potencia, cargo fijo, IGV y total. | EP09 |
| **TS05** | API de evaluación de demanda | Como developer, deseo un endpoint que evalúe una demanda medida contra las reglas del local, para generar las alertas correspondientes. | **Given** una petición `POST /api/v1/sites/{siteId}/demand-evaluations` con la demanda medida,<br>**When** el servicio la procesa,<br>**Then** responde `200 OK` con las alertas generadas<br>**And** devuelve una lista vacía si ninguna regla resulta incumplida. | EP09 |
| **TS06** | Documentación OpenAPI | Como developer, deseo la especificación OpenAPI publicada, para conocer el contrato sin leer el código fuente. | **Given** una petición `GET /swagger/v1/swagger.json` o `GET /v3/api-docs`,<br>**When** el servicio la procesa,<br>**Then** responde `200 OK` con la especificación válida de todos los endpoints expuestos. | EP09 |
| **TS07** | Endpoints de salud del servicio | Como developer, deseo endpoints de salud diferenciados, para que el proveedor de hosting distinga un proceso caído de una base de datos inaccesible. | **Escenario 1:** proceso vivo.<br>**Given** una petición al endpoint de *liveness*,<br>**When** el proceso está en ejecución,<br>**Then** responde `200 OK` aunque la base de datos no esté disponible.<br><br>**Escenario 2:** dependencia caída.<br>**Given** una petición al endpoint de *readiness* con la base de datos inaccesible,<br>**When** el servicio la procesa,<br>**Then** responde `503 Service Unavailable`. | EP09 |
| **TS08** | Webhook de la pasarela de pagos | Como developer, deseo un endpoint de webhook autenticado por firma, para confirmar los pagos sin exponer un recurso abierto. | **Escenario 1:** firma ausente.<br>**Given** una petición al webhook sin cabecera de firma,<br>**When** el servicio la procesa,<br>**Then** responde `400 Bad Request`.<br><br>**Escenario 2:** firma válida.<br>**Given** una petición con firma válida,<br>**When** el servicio la procesa,<br>**Then** responde `200 OK` y actualiza el estado del pago. | EP09 |
| **TS09** | Configuración de CORS | Como developer, deseo restringir los orígenes que pueden consumir el API desde un navegador, para impedir el uso desde sitios no autorizados. | **Escenario 1:** origen permitido.<br>**Given** una petición de comprobación previa desde un origen registrado,<br>**When** el servicio la procesa,<br>**Then** responde con la cabecera de origen permitido.<br><br>**Escenario 2:** origen no permitido.<br>**Given** una petición desde un origen no registrado,<br>**When** el servicio la procesa,<br>**Then** la respuesta no incluye cabecera de origen permitido. | EP09 |

## 3.3. Product Backlog

El orden del Product Backlog lo determina el valor para el negocio. Se sitúan primero las
historias del Landing Page, por ser el punto de entrada del modelo de negocio y por requerirse
desde el primer sprint, seguidas de la construcción de la jerarquía de organización, local y zona,
que es la que habilita todo lo demás. Las historias de control de demanda —el diferencial del
producto— se priorizan por delante de la analítica avanzada y de los pagos.

**Herramienta:** `<Pivotal Tracker / Jira / Trello>`
**URL pública del Product Backlog:** `<...>`
`<Insertar captura del Product Backlog en la herramienta>`

| # Orden | User Story Id | Título | Descripción | Story Points |
| :-- | :-- | :-- | :-- | :-- |
| 1 | US01 | Sección hero del Landing Page | Como visitante, deseo comprender en la primera pantalla qué problema resuelve SEMS, para decidir en segundos si me interesa. | 3 |
| 2 | US02 | Explicación del cargo por potencia | Como visitante del segmento de establecimientos, deseo entender por qué un pico de minutos encarece mi recibo del mes, para reconocer el problema como propio. | 3 |
| 3 | US04 | Navegación del Landing Page | Como visitante, deseo desplazarme entre las secciones del Landing Page, para revisar la información en el orden que me interesa. | 2 |
| 4 | US03 | Sección de planes en el Landing Page | Como visitante, deseo conocer los planes y sus límites, para estimar cuál corresponde a mi caso antes de registrarme. | 3 |
| 5 | TS06 | Documentación OpenAPI | Como developer, deseo la especificación OpenAPI publicada, para conocer el contrato sin leer el código fuente. | 2 |
| 6 | US06 | Registro de cuenta | Como visitante, deseo crear una cuenta con mi correo y contraseña, para acceder a la aplicación. | 3 |
| 7 | US07 | Inicio de sesión | Como usuario registrado, deseo iniciar sesión, para acceder a la información de mis locales. | 3 |
| 8 | TS01 | API de autenticación | Como developer, deseo un endpoint de autenticación que emita tokens, para proteger el acceso a los recursos del API. | 3 |
| 9 | TS02 | Protección por defecto de los endpoints | Como developer, deseo que todo endpoint exija sesión salvo los explícitamente públicos, para que un descuido no deje un recurso abierto. | 3 |
| 10 | US12 | Registro de la organización | Como administrador, deseo registrar mi empresa con su RUC y tipo de negocio, para agrupar bajo ella todos mis locales. | 5 |
| 11 | US13 | Registro de un local | Como administrador, deseo registrar un local con su potencia contratada y su categoría tarifaria, para que el sistema calcule sobre la tarifa que realmente le aplica. | 5 |
| 12 | US14 | Consulta de los locales de la organización | Como responsable de operaciones, deseo ver la lista de mis locales vigentes, para acceder a cada uno desde un punto único. | 3 |
| 13 | TS03 | API de organizaciones y locales | Como developer, deseo endpoints para gestionar organizaciones, locales y zonas, para que las aplicaciones cliente construyan la jerarquía del negocio. | 5 |
| 14 | US18 | Registro de zonas de un local | Como supervisor, deseo dividir mi local en zonas, para saber en qué parte se consume la energía. | 3 |
| 15 | US19 | Registro de un medidor en un local | Como supervisor, deseo registrar un medidor indicando su local y su zona, para atribuir su consumo al suministro y al área correctos. | 5 |
| 16 | US20 | Consulta de medidores por local | Como supervisor, deseo ver los medidores instalados en mi local, para verificar la cobertura de la medición. | 2 |
| 17 | US27 | Consulta de la tarifa vigente | Como supervisor, deseo consultar la tarifa aplicable a mi local, para conocer los precios de energía y el cargo por potencia. | 3 |
| 18 | US24 | Consulta del consumo actual | Como supervisor, deseo ver el consumo actual de mi local, para saber cómo está operando en este momento. | 3 |
| 19 | US28 | Creación de una regla de demanda | Como responsable, deseo definir a qué porcentaje de mi potencia contratada quiero ser avisado, para tener margen de reacción. | 5 |
| 20 | US29 | Aviso de demanda con margen | Como responsable, deseo recibir un aviso cuando la demanda de mi local se acerca a la potencia contratada, para reducir carga antes del recargo. | 8 |
| 21 | US30 | Aviso de exceso de potencia | Como responsable, deseo saber cuándo he superado la potencia contratada, para dimensionar el recargo del periodo y evitar que se repita. | 3 |
| 22 | US31 | Ausencia de aviso por debajo del umbral | Como responsable, deseo no recibir avisos cuando la operación es normal, para que la alerta conserve su valor. | 2 |
| 23 | TS05 | API de evaluación de demanda | Como developer, deseo un endpoint que evalúe una demanda medida contra las reglas del local, para generar las alertas correspondientes. | 5 |
| 24 | US35 | Proyección de factura del periodo | Como responsable, deseo conocer la factura estimada de mi local desglosada, para saber qué concepto pesa más. | 8 |
| 25 | US36 | Peso del cargo por potencia | Como responsable, deseo ver qué proporción de mi factura corresponde al cargo por potencia, para decidir si conviene actuar sobre el pico o sobre el consumo. | 3 |
| 26 | TS04 | API de cálculo de factura | Como developer, deseo un endpoint que calcule la factura estimada a partir del consumo y la demanda, para que las aplicaciones no repliquen la lógica tarifaria. | 5 |
| 27 | US25 | Consulta del histórico de consumo | Como supervisor, deseo consultar el consumo histórico de un medidor, para comparar periodos. | 3 |
| 28 | US26 | Consumo desglosado por zona | Como supervisor, deseo ver el consumo agrupado por zona, para identificar qué área concentra el gasto. | 5 |
| 29 | US21 | Consulta de medidores por zona | Como supervisor, deseo ver los medidores de una zona concreta, para revisar el consumo de esa área. | 2 |
| 30 | US10 | Asignación de acceso a una persona | Como administrador de la organización, deseo dar acceso a una persona indicando su papel y su alcance, para que gestione únicamente lo que le corresponde. | 5 |
| 31 | US11 | Revocación de acceso | Como administrador, deseo revocar el acceso de una persona, para retirar permisos cuando deja el puesto. | 3 |
| 32 | US17 | Consulta de mis organizaciones | Como usuario, deseo ver a qué organizaciones pertenezco y con qué papel, para cambiar de contexto cuando trabajo para más de una. | 3 |
| 33 | US33 | Consulta y resolución de alertas | Como supervisor, deseo revisar y marcar como resueltas las alertas de mi local, para llevar control de las atendidas. | 3 |
| 34 | US32 | Umbrales de consumo por dispositivo | Como supervisor, deseo definir umbrales de consumo para un equipo, para detectar comportamientos anómalos. | 5 |
| 35 | US34 | Preferencias de notificación | Como responsable, deseo configurar por qué canal y con qué severidad mínima recibo avisos, para no ser interrumpido por alertas menores. | 3 |
| 36 | US15 | Actualización de los datos de un local | Como supervisor, deseo actualizar los datos de mi local, para reflejar un cambio de potencia contratada o de categoría tarifaria. | 2 |
| 37 | US22 | Traslado de un medidor entre zonas | Como supervisor, deseo reasignar un medidor a otra zona del mismo local, para reflejar un traslado de equipo. | 3 |
| 38 | US23 | Baja de un medidor | Como supervisor, deseo dar de baja un medidor retirado, para que deje de contar en mi cupo y en los listados. | 3 |
| 39 | US16 | Archivado de un local | Como administrador, deseo archivar un local que ha cerrado, para que deje de aparecer sin perder su histórico. | 2 |
| 40 | US39 | Comparación entre locales | Como responsable de operaciones, deseo comparar el desempeño energético de mis locales, para identificar los que están peor. | 8 |
| 41 | US37 | Recomendaciones de ahorro | Como responsable, deseo recibir recomendaciones concretas para reducir mi costo, para saber por dónde empezar. | 5 |
| 42 | US38 | Detección de anomalías de consumo | Como supervisor, deseo que el sistema señale consumos atípicos, para investigar posibles fallas o desperdicios. | 8 |
| 43 | US40 | Consulta de planes disponibles | Como administrador, deseo ver los planes con sus límites y precios, para elegir el que corresponde a mi cadena. | 2 |
| 44 | US42 | Límite de locales según el plan | Como administrador, deseo que el sistema respete el límite de locales de mi plan, para conocer cuándo necesito ampliarlo. | 3 |
| 45 | US43 | Registro de método de pago | Como administrador, deseo registrar un método de pago, para automatizar la renovación de la suscripción. | 5 |
| 46 | US41 | Contratación de un plan | Como administrador, deseo contratar un plan, para habilitar las funcionalidades que necesita mi organización. | 8 |
| 47 | TS08 | Webhook de la pasarela de pagos | Como developer, deseo un endpoint de webhook autenticado por firma, para confirmar los pagos sin exponer un recurso abierto. | 5 |
| 48 | US44 | Consulta de comprobantes | Como administrador, deseo consultar mis comprobantes de pago, para llevar el control contable de la suscripción. | 3 |
| 49 | US08 | Recuperación de contraseña | Como usuario registrado, deseo restablecer mi contraseña, para recuperar el acceso si la olvido. | 3 |
| 50 | US09 | Cierre de sesión | Como usuario autenticado, deseo cerrar sesión, para impedir el acceso desde un equipo compartido del local. | 2 |
| 51 | US05 | Selección de idioma en el Landing Page | Como visitante, deseo cambiar el idioma del Landing Page, para leer el contenido en el idioma que domino. | 3 |
| 52 | TS07 | Endpoints de salud del servicio | Como developer, deseo endpoints de salud diferenciados, para que el proveedor de hosting distinga un proceso caído de una base de datos inaccesible. | 2 |
| 53 | TS09 | Configuración de CORS | Como developer, deseo restringir los orígenes que pueden consumir el API desde un navegador, para impedir el uso desde sitios no autorizados. | 2 |

## 3.4. Impact Mapping

> Se elabora en **UXPressia**, a partir de las fichas de los User Personas de la sección 2.3.1.

**Business Goals (SMART)**

| ID | Business Goal |
| :-- | :-- |
| BG01 | Alcanzar 120 locales activos con suscripción de pago en un plazo de 12 meses desde el lanzamiento. |
| BG02 | Lograr que el 60% de las alertas de demanda de nivel *warning* vayan seguidas de una reducción de carga dentro de los 30 minutos siguientes, medido durante el segundo trimestre de operación. |
| BG03 | Alcanzar una tasa de renovación mensual del 85% entre las organizaciones suscritas, medida al sexto mes. |
| BG04 | Conseguir que 15 organizaciones con más de cinco locales adopten el plan *Enterprise* en los primeros 12 meses. |

**Estructura del Impact Map**

| Goal | Actor | Impact | Deliverable | User Stories |
| :-- | :-- | :-- | :-- | :-- |
| BG02 | Responsable de operaciones de cadena | Que reaccione ante el aviso reduciendo carga en lugar de ignorarlo | Alerta de demanda con margen expresado en kW y canal de notificación configurable | US28, US29, US30, US34 |
| BG02 | Propietario de establecimiento independiente | Que comprenda qué significa el aviso sin formación eléctrica | Mensaje de alerta redactado en términos de margen y de costo, no de magnitudes eléctricas | US29, US30 |
| BG01 | Propietario de establecimiento independiente | Que registre su local y su medidor sin apoyo técnico | Flujo de alta guiado de organización, local, zona y medidor | US12, US13, US18, US19 |
| BG01 | Visitante del Landing Page | Que reconozca el problema del cargo por potencia como propio | Sección del Landing Page con ejemplo numérico del impacto de un pico | US02, US03 |
| BG03 | Responsable de operaciones de cadena | Que use la plataforma de forma sostenida y no solo al inicio | Proyección de factura desglosada y comparación entre locales | US35, US36, US39 |
| BG04 | Responsable de operaciones de cadena | Que incorpore locales adicionales a la plataforma | Gestión multi-local con permisos por sede y límites por plan | US10, US14, US40, US42 |

`<Insertar imagen del Impact Map elaborado en UXPressia>`

---

[⬅ Capítulo II](02-requirements-elicitation.md) · [Volver al índice](../README.md) · [Capítulo IV ➡](04-product-design.md)
