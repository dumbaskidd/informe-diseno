[⬅ Volver al índice](../README.md)

# Conclusiones, Bibliografía y Anexos

## Conclusiones

**Sobre el segmento y el problema.** El sector comercial concentra 9 157,3 GWh anuales, el 17,18 %
de la venta nacional de energía eléctrica a cliente final. A diferencia del residencial, enfrenta
una tarifa con cargo por potencia calculado sobre la demanda máxima del mes: un único pico de
quince minutos fija el cargo de todo el periodo. Ese desajuste entre la complejidad de la tarifa y
la capacidad instalada del cliente —miles de establecimientos sin área de energía propia— es lo
que justifica el producto.

**Sobre el diseño del producto.** Adoptar Material Design como lenguaje común permitió que el
*Landing Page*, construido a mano con HTML5, CSS3 y JavaScript, y la aplicación web, construida
con PrimeVue, presenten la misma gramática visual sin mantener dos sistemas de diseño. La
accesibilidad y la internacionalización se incorporaron desde el primer sprint, no como una capa
posterior.

**Sobre la arquitectura.** El monolito modular con ocho módulos, tablas prefijadas y puertos
explícitos ofrece la separación conceptual del diseño dirigido por el dominio sin el costo
operativo de una arquitectura distribuida. Las tres dependencias entre módulos se resuelven por
interfaces reducidas, de modo que la frontera es verificable y no una convención.

**Sobre el proceso.** El valor del curso está en la evidencia de que el producto se construye con
un proceso riguroso. En este primer hito se establecieron el control de versiones con GitFlow, la
convención de commits, la separación de entornos por variables sin credenciales versionadas, las
comprobaciones de vida y de disponibilidad diferenciadas y una suite de 68 pruebas del núcleo del
dominio. Queda registrada de forma explícita la deuda pendiente: la automatización del pipeline,
las pruebas de la aplicación web y las correcciones heredadas del segmento anterior.

**Sobre las decisiones que exigieron un juicio informado.** Dos merecen mención. La primera, haber
corregido la regla de hora punta al contrastarla con el pliego tarifario oficial, aun cuando el
error producía facturas estimadas favorables al cliente y nadie lo habría notado. La segunda,
haber verificado en la fuente primaria la cifra de participación del sector comercial en lugar de
aceptar un dato de circulación frecuente que resultó no coincidir con el anuario oficial.

> Las conclusiones se amplían en cada entrega.

## Recomendaciones

- Cerrar la deuda técnica DT01 a DT05 antes del segundo hito, empezando por el envío de `siteId`
  desde la aplicación web, que hoy impide dar de alta dispositivos contra la API.
- Automatizar la ejecución de las 68 pruebas en cada *Pull Request*.
- Incorporar pruebas de la aplicación web, hoy inexistentes.
- Instrumentar el producto para poder medir los objetivos declarados en el capítulo III.

## Bibliografía

> Referencias en formato APA. Se amplía en cada entrega.

- Bass, L., Clements, P., & Kazman, R. (2021). *Software architecture in practice* (4th ed.). Addison-Wesley.
- Evans, E. (2003). *Domain-driven design: Tackling complexity in the heart of software*. Addison-Wesley.
- Vernon, V. (2013). *Implementing domain-driven design*. Addison-Wesley.
- Brown, S. (2023). *The C4 model for visualising software architecture*. https://c4model.com
- Gothelf, J., & Seiden, J. (2021). *Lean UX: Designing great products with agile teams* (3rd ed.). O'Reilly Media.
- Google. (2024). *Material Design 3*. https://m3.material.io
- World Wide Web Consortium. (2018). *Web Content Accessibility Guidelines (WCAG) 2.1*. https://www.w3.org/TR/WCAG21/
- Driessen, V. (2010). *A successful Git branching model*. https://nvie.com/posts/a-successful-git-branching-model/
- Conventional Commits. (2023). *Conventional Commits 1.0.0*. https://www.conventionalcommits.org
- Ministerio de Energía y Minas. (2025). *Anuario estadístico de electricidad 2024. Capítulo 5: Distribución de energía eléctrica* [cuadro 5.3.3.1, venta mensual de energía eléctrica por sector económico]. MINEM. https://www.gob.pe/institucion/minem/informes-publicaciones/7324144-anuario-estadistico-de-electricidad-2024
- Organismo Supervisor de la Inversión en Energía y Minería. (s. f.). *Anexo B: Opciones tarifarias y condiciones de aplicación de las tarifas a usuario final*. OSINERGMIN. https://www.osinergmin.gob.pe/Resoluciones/pdf/ANEXO_B_Resolucion_1908.pdf
- Organismo Supervisor de la Inversión en Energía y Minería. (s. f.). *Pliegos tarifarios aplicables al cliente final*. OSINERGMIN. https://www.osinergmin.gob.pe/seccion/institucional/regulacion-tarifaria/pliegos-tarifarios/electricidad/pliegos-tarifiarios-cliente-final

## Anexos

**Anexo A. Estructura para la sección Objetivo del Estudiante (Student Outcome)**

Ver [Student Outcome](00-student-outcome.md).

**Anexo B. Informe de participación**

El *Final Project Individual Member Performance Report* lo elabora el Team Leader en un documento
aparte, con el nombre de archivo
`upc-pre-202620-1asi0732-<NRC>-energix-performance-<avn/tbn>` en `.docx` y `.pdf`, y se adjunta en
cada entrega.

| Ítem | Estudiante | Responsabilidades | Cumplimiento | Calificación |
| :-- | :-- | :-- | :-- | :-- |
| 1 | `<Apellidos, Nombres>` | `<Responsabilidades>` | `<A tiempo / A destiempo / Parcialmente / No cumplió>` | `<20/16/13/07/00>` |
| 2 | `<Apellidos, Nombres>` | `<Responsabilidades>` | `<...>` | `<...>` |
| 3 | `<Apellidos, Nombres>` | `<Responsabilidades>` | `<...>` | `<...>` |

**Anexo C. Videos**

| Entrega | Video | URL | Duración |
| :-- | :-- | :-- | :-- |
| TB1 | Exposición | `<URL privado de Microsoft Stream>` | `<mm:ss>` |
| TB1 | About-the-Product | `<URL>` | `<mm:ss>` |
| TB1 | About-the-Team | `<URL>` | `<mm:ss>` |
| TB1 | Evidencia de entrevistas | `<URL>` | `<mm:ss>` |

**Anexo D. Enlaces del proyecto**

| Recurso | URL |
| :-- | :-- |
| Organización | <https://github.com/SEMS-Diseno-de-Experimentos> |
| Repositorio del informe | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Report> |
| Repositorio del Landing Page | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Landing-Page> |
| Repositorio de la aplicación web | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Web-Application> |
| Repositorio de la API | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Backend> |
| Repositorio de la aplicación móvil | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Mobile-App> |
| Landing Page desplegado | <https://sems-diseno-de-experimentos.github.io/SEMS-Landing-Page/> |
| Aplicación web desplegada | `<URL de Vercel>` |
| API desplegada | `<URL del servicio>` |
| Documentación de la API | `<URL del servicio>/swagger` |
| Tablero de gestión | `<URL del tablero>` |

---

[⬅ Capítulo V](05-product-implementation.md) · [Volver al índice](../README.md)
