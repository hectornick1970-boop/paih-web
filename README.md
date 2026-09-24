# PAIH — Plataforma de Analítica e Inteligencia Hospitalaria

**Sitio en vivo:** [paih.net](https://paih.net)

PAIH es una plataforma comercial de analítica en Power BI para hospitales y clínicas en Colombia. Se conecta directamente a los sistemas de información hospitalaria (facturación, cartera, citas, hospitalización, contratación) para convertir esos datos en tableros de decisión, sin depender de hojas de cálculo intermedias.

Este repositorio contiene el sitio web comercial de PAIH: una landing page de una sola página, autocontenida en un único archivo HTML, publicada en GitHub Pages.

## Contenido del sitio

- **Historias por módulo**: barra de círculos sobre el menú que reproduce las capturas de cada módulo como historias.
- **Menú interactivo de lienzos** (`#productos`): cada módulo activo se despliega en una tarjeta con sus lienzos. Al hacer clic en un lienzo se abre un modal con una captura del tablero real y una explicación de qué significan sus cifras.
- **Roadmap** (`#proximamente`): módulos en construcción, listados con su estado.
- **Sección de clientes** (`#clientes`) y **formulario de contacto** (`#contacto`), con envío funcional vía FormSubmit.
- **Botón flotante de WhatsApp**, **contador de visitas** (vía CountAPI) y animaciones con soporte de `prefers-reduced-motion`.

## Módulos activos y lienzos

| Módulo | Lienzos |
|---|---|
| Citas Médicas | Gestión de Citas, Comparativo de Citas, Oportunidad de Citas, Oportunidad Deseada, Capacidad Instalada |
| Admisiones | Análisis de Ingresos |
| Facturación | Facturación, Snapshot Facturación |
| Radicación | Envío, RecibidoEps |
| Glosas y Trámites | Semáforo de Glosas, Glosas, Trámites, Gestión Trámites |
| Hospitalización | Estancia, Egresos |
| Contratos IPS | Contratos IPS, PBS |
| Cartera a Fecha de Corte | Cartera Bruta y Neta, Cartera por Edades |

En total: **8 módulos y 20 lienzos** publicados.

### En roadmap (aún no publicados en el sitio)

- Cartera — Anticipos
- Producción por Áreas de Servicio

## Privacidad de las capturas

Todas las capturas de tableros que aparecen en el sitio están anonimizadas antes de publicarse:

- Nombre del hospital → `HOSPITAL PAIH`
- Nombres de sede/centro de atención → `SEDE PAIH UNO`, `SEDE PAIH DOS`, …
- Nombres de médicos → `MEDICO PAIH UNO`, `MEDICO PAIH DOS`, …
- Prefijos de número de factura (p. ej. `FHUS`, `HUSM`) → `PAIH`
- Datos de pacientes (nombre, documento) → reemplazados por aviso de confidencialidad, conforme a la Ley 1581 de 2012

## Stack técnico

- HTML + CSS + JavaScript vanilla, un solo archivo (`index.html`), sin build step
- Tipografía: IBM Plex Sans / IBM Plex Mono
- Formulario de contacto: [FormSubmit](https://formsubmit.co)
- Contador de visitas: [CountAPI](https://countapi.xyz)
- Hosting: GitHub Pages (dominio `paih.net` vía `CNAME`)
- Fuente de los datos mostrados: Power BI Service, conectado a Dinámica Gerencial Hospitalaria vía gateway on-premises

## Estructura del repositorio

```
paih-web/
├── index.html    # Sitio completo (HTML + CSS + JS, imágenes embebidas)
├── img/          # Capturas de lienzos usadas en los modales
├── CNAME         # Dominio personalizado para GitHub Pages
└── README.md
```

## Ver el sitio en local

Al ser un archivo estático, solo abre `index.html` en tu navegador. También puedes servir la carpeta con cualquier servidor simple, por ejemplo:

```bash
python -m http.server 8000
```

y luego visitar `http://localhost:8000`.

## Publicar cambios

El sitio es un único archivo `index.html` autocontenido (imágenes incrustadas en base64). Para actualizarlo:

1. Editar `index.html` en este repositorio (o reemplazarlo por una versión nueva).
2. Confirmar el cambio (`commit`) y enviarlo a la rama `main`.
3. GitHub Pages republica automáticamente en `paih.net` en uno o dos minutos.

## Contacto

- Correo: hector_nick@hotmail.com
- WhatsApp: +57 313 401 6630