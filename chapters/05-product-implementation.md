[⬅ Volver al índice](../README.md)

# Capítulo V: Product Implementation

## 5.1. Software Configuration Management

### 5.1.1. Software Development Environment Configuration

| Propósito | Herramienta | Versión | Enlace |
| :-- | :-- | :-- | :-- |
| Control de versiones | Git | 2.4x | <https://git-scm.com> |
| Alojamiento y colaboración | GitHub | — | <https://github.com> |
| Gestión del producto | `<Pivotal Tracker / Jira / Trello>` | — | `<URL del tablero>` |
| Editor de código | Visual Studio Code | 1.9x | <https://code.visualstudio.com> |
| Entorno del backend | .NET SDK | 8.0 | <https://dotnet.microsoft.com> |
| Entorno de la web | Node.js | 20 LTS | <https://nodejs.org> |
| Empaquetador de la web | Vite | 7 | <https://vite.dev> |
| Base de datos local | PostgreSQL | 16 | <https://www.postgresql.org> |
| Cliente de base de datos | pgAdmin / DBeaver | — | — |
| Pruebas de la API | Swagger UI, cURL | — | — |
| Diagramas C4 | Structurizr | — | <https://structurizr.com> |
| Diagramas UML y ER | LucidChart | — | <https://lucidchart.com> |
| Artefactos UX | UXPressia | — | <https://uxpressia.com> |
| Diseño de interfaz | Figma | — | <https://figma.com> |

**Puesta en marcha del backend**

```bash
git clone https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Backend.git
cd SEMS-Backend
cp .env.example .env      # completar DATABASE_URL, JWT_SECRET y el resto
dotnet restore
dotnet test               # 68 pruebas
dotnet run --project src/Sems.Api
```

**Puesta en marcha de la aplicación web**

```bash
git clone https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Web-Application.git
cd SEMS-Web-Application/semswebapp
npm install
npm run dev
```

> El proyecto vive en la subcarpeta `semswebapp/`. Todos los comandos de `npm` se ejecutan ahí.

**Puesta en marcha del Landing Page**

No requiere instalación ni compilación: se abre `index.html` en el navegador, o se sirve la
carpeta con cualquier servidor estático.

**Variables de entorno.** Ninguna credencial se versiona. Cada repositorio incluye un
`.env.example` con todas las claves y sus valores vacíos, y `.env` está en `.gitignore`. Las
variables con prefijo `VITE_` quedan incrustadas en el paquete que descarga el navegador, de modo
que **nunca contienen secretos**: solo la URL pública de la API y la clave publicable de la
pasarela de pagos.

### 5.1.2. Source Code Management

El proyecto usa **GitFlow**.

| Rama | Propósito | Origen | Destino |
| :-- | :-- | :-- | :-- |
| `main` | Código en producción | `develop` | — |
| `develop` | Integración del trabajo en curso | `main` | `main` |
| `feature/<nombre>` | Una funcionalidad o tarea | `develop` | `develop` |
| `release/<versión>` | Preparación de una entrega | `develop` | `main` y `develop` |
| `hotfix/<nombre>` | Corrección urgente en producción | `main` | `main` y `develop` |

Nunca se hace *push* directo a `main` ni a `develop`: todo entra por *Pull Request*.

**Repositorios de la organización**

| Repositorio | Contenido |
| :-- | :-- |
| [SEMS-Backend](https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Backend) | API REST en ASP.NET Core |
| [SEMS-Web-Application](https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Web-Application) | Aplicación web en Vue 3 |
| [SEMS-Landing-Page](https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Landing-Page) | Sitio estático en HTML5, CSS3 y JavaScript |
| [SEMS-Mobile-App](https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Mobile-App) | Aplicación móvil nativa |
| [SEMS-Report](https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Report) | Este informe |

**Convención de commits.** Se aplica **Conventional Commits**, con el formato
`<tipo>(<alcance>): <descripción en imperativo>`.

| Prefijo | Cuándo se usa |
| :-- | :-- |
| `feat:` | Funcionalidad nueva visible para el usuario |
| `fix:` | Corrección de un defecto |
| `test:` | Pruebas nuevas o modificadas |
| `ci:` | Cambios en pipelines o automatización |
| `refactor:` | Reorganización sin cambio de comportamiento |
| `docs:` | Documentación |
| `chore:` | Mantenimiento y configuración |
| `style:` | Formato, sin efecto sobre el comportamiento |

**Versionado.** Se sigue **Semantic Versioning** (`MAJOR.MINOR.PATCH`) con etiquetas anotadas en
`main` por cada entrega.

### 5.1.3. Source Code Style Guide & Conventions

| Artefacto | Guía | Herramienta |
| :-- | :-- | :-- |
| Backend (C#) | Convenciones de nomenclatura de .NET | Analizadores de .NET, `dotnet format` |
| Aplicación web (JavaScript, Vue) | Guía de estilo de Vue 3 | ESLint con `eslint-plugin-vue` |
| Landing Page (HTML, CSS, JS) | HTML5 semántico, BEM ligero en CSS | Revisión en *Pull Request* |
| Markdown | — | Revisión en *Pull Request* |

**Convenciones del backend**

- `PascalCase` para clases, registros, propiedades y métodos públicos; `_camelCase` para campos
  privados; `camelCase` para variables locales y parámetros.
- Un archivo por agregado o por conjunto cohesionado de tipos del mismo módulo.
- Los tipos del dominio no llevan anotaciones de persistencia ni de serialización: el mapeo vive
  en la capa de infraestructura y el contrato JSON en la capa de interfaces.
- Los comentarios explican **por qué**, no **qué**. La documentación XML de cada acción del
  controlador se publica en la interfaz de documentación de la API.

**Convenciones de la aplicación web**

- Componentes en `PascalCase`, uno por archivo, con `<script setup>`.
- Vistas en `views/`, componentes reutilizables en `components/`, llamadas a la API en `services/`.
- El estado del servidor se gestiona con TanStack Query; el estado propio de la interfaz, con Pinia.

**Contrato de la API.** El estilo de nomenclatura del JSON no es uniforme entre módulos, y esto es
deliberado: los módulos migrados desde el servicio original conservan el estilo que ya consumían
los clientes existentes, para no romperlos. La regla se documenta aquí para que sea una decisión
registrada y no una inconsistencia accidental.

| Módulo | Estilo del JSON |
| :-- | :-- |
| Identity & Access Management, Device Management | `camelCase` |
| Energy, Analytics, Alerts, Organizations, Payments | `snake_case` |
| Subscriptions | Peticiones en `snake_case`, respuestas en `PascalCase` |

**Idioma.** El idioma por defecto de los mensajes, de la interfaz y de la documentación de todos
los productos es el **inglés**, con español latinoamericano disponible en los artefactos de cara
al usuario.

### 5.1.4. Software Deployment Configuration

| Artefacto | Plataforma | Estrategia |
| :-- | :-- | :-- |
| Landing Page | GitHub Pages | Publicación del repositorio tal cual, sin compilación, al hacer *push* a `main` |
| Aplicación web | Vercel | Compilación con Vite y publicación automática por rama |
| API REST | Render | Servicio web con despliegue automático desde `main` |
| Base de datos | PostgreSQL gestionado | Instancia única con migraciones aplicadas al arrancar |

**Configuración del backend en el proveedor**

| Variable | Contenido |
| :-- | :-- |
| `DATABASE_URL` | Cadena de conexión completa de Npgsql, en **una sola** variable |
| `PORT` | Lo inyecta la plataforma; la aplicación lo lee y escucha en él |
| `ALLOWED_ORIGINS` | Los orígenes de la aplicación web y del entorno local, separados por comas |
| `JWT_SECRET` | Mínimo 32 caracteres, generado aleatoriamente |
| `MAIL_*` | Servidor de correo saliente |
| `STRIPE_SECRET_KEY`, `STRIPE_WEBHOOK_SECRET` | Credenciales de la pasarela |

**Comprobaciones de salud.** La API expone dos rutas distintas, y la diferencia importa:

| Ruta | Qué responde | Para qué sirve |
| :-- | :-- | :-- |
| `/health` | Que el proceso está vivo | Comprobación de vida de la plataforma |
| `/health/ready` | Que además la base de datos acepta consultas | Comprobación de disponibilidad real |

Separarlas evita el fallo más común de esta clase de despliegues: un servicio que responde
«correcto» mientras su base de datos está caída.

## 5.2. Product Implementation & Deployment

### 5.2.1. Sprint Backlogs

**Sprint 1**

| Sprint | Objetivo | Fecha inicio | Fecha fin |
| :-- | :-- | :-- | :-- |
| 1 | Publicar el Landing Page y la API con el registro, la gestión de organizaciones y locales, y el cálculo de la factura comercial | `<dd/mm/aaaa>` | `<dd/mm/aaaa>` |

| ID | User Story | Tarea | Responsable | Estimación (h) | Estado |
| :-- | :-- | :-- | :-- | --: | :-- |
| US01 | Sección hero del Landing Page | Maquetar el *hero* con la propuesta de valor | `<Integrante>` | 4 | `<Estado>` |
| US03 | Sección de planes | Maquetar los tres planes con sus límites | `<Integrante>` | 4 | `<Estado>` |
| US04 | Navegación del Landing Page | Barra superior, menú móvil y anclas | `<Integrante>` | 3 | `<Estado>` |
| US05 | Selección de idioma | Diccionarios en-US y es-419, y conmutador | `<Integrante>` | 5 | `<Estado>` |
| — | Infraestructura | Publicación automática en GitHub Pages | `<Integrante>` | 2 | `<Estado>` |
| — | Infraestructura | Despliegue de la API y de la base de datos | `<Integrante>` | 4 | `<Estado>` |

> Se amplía con un cuadro por sprint en cada entrega.

### 5.2.2. Implemented Landing Page Evidence

| Dato | Valor |
| :-- | :-- |
| Repositorio | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Landing-Page> |
| Desplegado en | <https://sems-diseno-de-experimentos.github.io/SEMS-Landing-Page/> |
| Tecnología | HTML5, CSS3 y JavaScript, sin framework ni paso de compilación |
| Páginas | `index.html` y `terms.html` |

**Características implementadas**

- Diseño Material Design 3 con tema claro y oscuro.
- Internacionalización en inglés (por defecto) y español latinoamericano, con 211 claves y
  persistencia de la elección.
- Accesibilidad: enlace de salto, puntos de referencia semánticos, atributos ARIA en todos los
  controles sin texto visible, acordeón operable por teclado y contraste verificado en ambos temas.
- Llamados a la acción por segmento que redirigen a las vistas correspondientes de la aplicación web.
- Sección de Términos y Condiciones con la política de privacidad y el acuerdo de nivel de servicio.

> `<Insertar capturas del Landing Page desplegado, en escritorio y en móvil, y en ambos idiomas.>`

### 5.2.3. Implemented Frontend-Web Application Evidence

| Dato | Valor |
| :-- | :-- |
| Repositorio | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Web-Application> |
| Desplegado en | `<URL de Vercel>` |
| Tecnología | Vue 3, Vite, PrimeVue con *preset* Material, Pinia, TanStack Query |

**Vistas implementadas:** autenticación (inicio de sesión, registro, verificación, recuperación),
resumen, dispositivos, monitoreo, analítica, alertas, reportes, suscripción y pagos, y
configuración.

> `<Insertar capturas de las vistas principales de la aplicación web.>`

### 5.2.4. Implemented Native-Mobile Application Evidence

> `<Evidencia de la aplicación móvil.>`

### 5.2.5. Implemented RESTful API Evidence

| Dato | Valor |
| :-- | :-- |
| Repositorio | <https://github.com/SEMS-Diseno-de-Experimentos/SEMS-Backend> |
| Desplegado en | `<URL del servicio>` |
| Tecnología | ASP.NET Core 8, C#, Entity Framework Core, PostgreSQL |
| Endpoints | 111 |
| Módulos | 8 |
| Tablas | 33 |
| Pruebas | 68, todas en verde |

**Estado de la implementación por módulo**

| Módulo | Estado | Endpoints |
| :-- | :-- | --: |
| Identity & Access Management | Implementado | 8 |
| Organizations | Implementado | 16 |
| Device Management | Implementado | 18 |
| Energy Monitoring | Implementado | 23 |
| Analytics | Implementado | 13 |
| Alerts | Implementado | 14 |
| Subscriptions | Implementado | 7 |
| Payments | Implementado | 12 |
| **Total** | | **111** |

**Seguridad implementada**

- Autenticación por JWT con token de acceso de vida corta y token de refresco de vida larga.
- Política de autorización global: toda ruta exige autenticación salvo las declaradas públicas.
- Contraseñas almacenadas con BCrypt; los tokens se guardan como resumen SHA-256, nunca en claro.
- CORS restringido a la lista de orígenes configurada.
- El *webhook* de la pasarela se autentica por la firma del cuerpo, no por JWT, y controla
  duplicados para no procesar dos veces el mismo cobro.
- `forgot-password` responde exactamente lo mismo exista o no la cuenta, para no convertirse en un
  verificador de correos registrados.
- Los datos de la tarjeta nunca llegan al servidor: se introducen en la página de la pasarela y la
  aplicación solo recibe un identificador del medio de pago.

> `<Insertar capturas de peticiones y respuestas contra la API desplegada.>`

### 5.2.6. RESTful API Documentation

La API se documenta con **OpenAPI 3**, generada con Swashbuckle a partir de la documentación XML
del propio código, de modo que documentación e implementación no pueden divergir.

| Dato | Valor |
| :-- | :-- |
| Interfaz de documentación | `<URL del servicio>/swagger` |
| Documento OpenAPI | `<URL del servicio>/swagger/v1/swagger.json` |
| Título | SEMS API |
| Descripción | Smart Energy Management System. Modular monolith: one bounded context per module. |
| Idioma | Inglés |
| Autenticación | Esquema `Bearer` declarado; el token se pega en el diálogo *Authorize* |

**Ejemplo — estimación de la factura de un local**

```http
POST /api/v1/energy/bill-estimate
Authorization: Bearer <token>
Content-Type: application/json

{
  "tariff_category": "MT2",
  "contracted_power_kw": 250,
  "kwh_peak": 12000,
  "kwh_off_peak": 48000,
  "max_demand_kw": 280
}
```

```json
{
  "kwh_peak": 12000,
  "kwh_off_peak": 48000,
  "max_demand_kw": 280,
  "contracted_power_kw": 250,
  "subtotal": 32108.80,
  "igv": 5779.58,
  "total": 37888.38
}
```

> `<Insertar capturas de la interfaz de documentación desplegada.>`

### 5.2.7. Team Collaboration Insights

| Dato | Valor |
| :-- | :-- |
| Organización | <https://github.com/SEMS-Diseno-de-Experimentos> |
| Flujo de trabajo | GitFlow |
| Convención de commits | Conventional Commits |

> `<Insertar la gráfica de contribuciones de cada repositorio (pestaña Insights → Contributors) y
> una tabla que relacione cada integrante con sus commits y Pull Requests del sprint.>`

| Integrante | Commits | Pull Requests | Revisiones | Artefactos principales |
| :-- | --: | --: | --: | :-- |
| `<Integrante>` | `<n>` | `<n>` | `<n>` | `<Artefactos>` |
| `<Integrante>` | `<n>` | `<n>` | `<n>` | `<Artefactos>` |
| `<Integrante>` | `<n>` | `<n>` | `<n>` | `<Artefactos>` |

## 5.3. Video About-the-Product

| Dato | Valor |
| :-- | :-- |
| Enlace | `<URL privado de Microsoft Stream>` |
| Duración | `<mm:ss>` |

## 5.4. Deuda técnica identificada

Se registra de forma explícita lo que hoy no cumple con el diseño descrito, para que el estado del
producto quede documentado con honestidad y sea verificable en la siguiente entrega.

| # | Deuda | Dónde | Impacto | Prevista para |
| :-- | :-- | :-- | :-- | :-- |
| DT01 | La aplicación web conserva la vista `/household` («Mi hogar») del segmento anterior de viviendas | Aplicación web | Incoherencia con el dominio comercial | Sprint 2 |
| DT02 | El formulario de alta de dispositivo no envía `siteId`, que la API exige como obligatorio | Aplicación web | El alta de dispositivos falla contra la API actual | Sprint 2 |
| DT03 | La aplicación web muestra la interfaz en español por defecto | Aplicación web | Incumple la restricción de idioma por defecto en inglés | Sprint 2 |
| DT04 | No existe suite de pruebas automatizadas en la aplicación web | Aplicación web | Sin red de seguridad ante regresiones | Sprint 2 |
| DT05 | No existe pipeline de integración continua | Los tres repositorios | Las pruebas del backend se ejecutan a mano | Sprint 2 |
| DT06 | La aplicación móvil no está iniciada | SEMS-Mobile-App | Alcance pendiente | `<Sprint>` |

---

[⬅ Capítulo IV](04-product-design.md) · [Volver al índice](../README.md) · [Conclusiones ➡](99-conclusiones.md)
