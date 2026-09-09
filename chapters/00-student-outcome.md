[⬅ Volver al índice](../README.md)

# Student Outcome

El curso 1ASI0732 contribuye al cumplimiento del **ABET – EAC – Student Outcome 4**.

> **Criterio:** La capacidad de reconocer responsabilidades éticas y profesionales en situaciones
> de ingeniería y hacer juicios informados, que deben considerar el impacto de las soluciones de
> ingeniería en contextos globales, económicos, ambientales y sociales.

En el siguiente cuadro se describe las acciones realizadas y enunciados de conclusiones por parte
del grupo, que permiten sustentar el haber alcanzado el logro del ABET – EAC - Student Outcome 4.

> El párrafo introductorio que antecede al cuadro en el *Anexo A* del enunciado debe reproducirse
> aquí de forma idéntica antes de la tabla.

| Criterio específico | Acciones realizadas | Conclusiones |
| :-- | :-- | :-- |
| **4.c.1** Reconoce responsabilidad ética y profesional en situaciones de ingeniería de software. | **`<Apellidos, Nombres>`**<br>**TB1:** `<Acción concreta relacionada con una decisión de responsabilidad ética o profesional: por ejemplo, haber corregido la regla de hora punta al comprobar en el pliego tarifario oficial que la implementación cobraba de menos, en lugar de dejar el error por conveniencia.>`<br><br>**`<Apellidos, Nombres>`**<br>**TB1:** `<Acción concreta.>`<br><br>**`<Apellidos, Nombres>`**<br>**TB1:** `<Acción concreta.>` | `<Conclusión grupal sobre cómo el trabajo realizado desarrolló esta dimensión. Se amplía en cada entrega.>` |
| **4.c.2** Emite juicios informados considerando el impacto de las soluciones de ingeniería de software en contextos globales, económicos, ambientales y sociales. | **`<Apellidos, Nombres>`**<br>**TB1:** `<Acción concreta relacionada con un juicio informado sobre el impacto: por ejemplo, haber sustentado el dimensionamiento del segmento con la cifra oficial del MINEM en lugar de una estimación propia.>`<br><br>**`<Apellidos, Nombres>`**<br>**TB1:** `<Acción concreta.>`<br><br>**`<Apellidos, Nombres>`**<br>**TB1:** `<Acción concreta.>` | `<Conclusión grupal sobre esta dimensión. Se amplía en cada entrega.>` |

## Situaciones del proyecto que sustentan el outcome

Se listan aquí las situaciones concretas ocurridas durante el desarrollo que sirven de materia
prima para redactar las celdas anteriores. Cada integrante debe escoger aquellas en las que
participó y describirlas en primera persona.

**Dimensión 4.c.1 — Responsabilidad ética y profesional**

| Situación | Por qué es una cuestión de responsabilidad |
| :-- | :-- |
| Corrección de la regla de hora punta | La implementación excluía los domingos por defecto. Al contrastarla con el Anexo B del pliego tarifario se comprobó que la exclusión solo procede a solicitud del cliente. Mantener el error habría producido facturas estimadas por debajo de lo real, precisamente para los locales que más abren en domingo |
| Tratamiento de las credenciales | Ninguna credencial se versiona; las contraseñas se guardan como resumen irreversible y los datos de tarjeta nunca llegan al servidor. Son decisiones que protegen al cliente aunque nadie las audite |
| Respuesta uniforme en la recuperación de contraseña | El endpoint responde lo mismo exista o no la cuenta. Responder distinto sería más cómodo de depurar, pero convertiría el servicio en un verificador de correos registrados |
| Registro explícito de la deuda técnica | La sección 5.4 declara lo que hoy no cumple con el diseño, en lugar de omitirlo |
| Cita de fuentes verificadas | Las cifras del informe se tomaron de la fuente primaria y se descartó un dato de circulación frecuente en internet que no coincidía con el anuario oficial |

**Dimensión 4.c.2 — Juicios informados sobre el impacto**

| Situación | Contexto del impacto |
| :-- | :-- |
| Cambio de segmento de viviendas a establecimientos comerciales | **Económico.** El sector comercial concentra 9 157 GWh anuales y enfrenta una tarifa con cargo por potencia que el segmento residencial no tiene. La decisión se sustentó en la estadística oficial, no en una intuición |
| Precio por locales y no por dispositivos | **Económico y social.** Un límite por dispositivos habría penalizado a los establecimientos grandes sin distinguir su capacidad de pago. El plan gratuito para un solo local mantiene la herramienta al alcance del comercio independiente |
| Aviso de demanda con margen previo | **Ambiental y económico.** Desplazar carga fuera de la hora punta reduce la presión sobre el sistema eléctrico en el tramo de mayor demanda nacional, además de bajar el costo del cliente |
| Monolito modular en vez de microservicios | **Económico.** Una arquitectura distribuida habría multiplicado el costo de operación sin beneficio observable a la escala prevista |
| Landing Page sin framework ni compilación | **Global.** Un sitio estático de 160 KB carga en conexiones lentas y funciona sin JavaScript para el contenido esencial, lo que importa en un país con cobertura desigual |
| Accesibilidad e internacionalización | **Social.** Contraste verificado, navegación por teclado, atributos ARIA y dos idiomas amplían quién puede usar el producto |

> **Coherencia exigida.** Cada acción declarada debe corresponder con una fila del *Registro de
> Versiones del Informe* y con commits verificables en los repositorios de la organización. Las
> acciones se acumulan entrega tras entrega; no se reemplazan.

---

[⬅ Volver al índice](../README.md) · [Capítulo I ➡](01-introduccion.md)
