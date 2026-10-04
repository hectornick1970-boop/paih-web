# PAIH — Plataforma de Analítica e Inteligencia Hospitalaria

**Sitio en vivo:** [paih.net](https://paih.net)

PAIH es una plataforma comercial de analítica en Power BI para hospitales y clínicas en Colombia. Se conecta directamente a los sistemas de información hospitalaria (facturación, cartera, citas, hospitalización, contratación) para convertir esos datos en tableros de decisión, sin depender de hojas de cálculo intermedias.

Este repositorio contiene el sitio web comercial de PAIH: una landing page de una sola página (un único `index.html` más sus imágenes en `img/`), publicada en GitHub Pages.

## Contenido del sitio

- **Novedades** (`#novedades`): el menú de navegación unificado, los tooltips explicativos y los lienzos nuevos, cada uno con acceso directo.
- **Historias por módulo**: barra de círculos sobre el menú que reproduce tarjetas y capturas de cada módulo como historias, con pausa/continuar (botón o barra espaciadora). Incluye las historias *Nuevo menú* y *Tooltips*.
- **Menú interactivo de lienzos** (`#productos`): cada módulo activo se despliega en una tarjeta con sus lienzos. Al hacer clic en un lienzo se abre un modal con una captura del tablero real, una pestaña **Con tooltip** (cuando el lienzo los tiene) y una explicación de qué significan sus cifras.
- **Roadmap** (`#proximamente`): módulos en construcción, listados con su estado.
- **Sección de clientes** (`#clientes`) y **formulario de contacto** (`#contacto`), con envío funcional vía FormSubmit.
- **Botón flotante de WhatsApp**, **contador de visitas** (vía Abacus) y animaciones con soporte de `prefers-reduced-motion`.

## Módulos activos y lienzos

| Módulo | Lienzos |
|---|---|
| Citas | Citas Médicas, Comparativo Citas, Oportunidad Citas, Oportunidad Deseada, Capacidad Instalada |
| Ingresos · Hospitalización | Análisis Ingresos, **Ingresos Ejecutivo**, Estancia, Egresos |
| Facturación | Facturación, Snapshot Facturación, **Facturación Ejecutiva** |
| Radicación | Envío, Radicación, **Oportunidad Radicación** |
| Glosas | Semáforo Glosas, Glosas, Trámites Cosecha, Gestión Trámites |
| Cartera | Cartera por Edades, **Cartera Ejecutiva**, Anticipos, **Anticipos Ejecutivo** |
| Contratos | Contratos IPS, PBS |

En total: **7 módulos y 25 lienzos** publicados (en negrita, los 5 lienzos nuevos). 20 de ellos incluyen **tooltips explicativos (i)**: cada gráfico indica su Objetivo y cómo hacer su Lectura. La estructura sigue el nuevo menú de navegación del reporte (`Home`).

### En roadmap (aún no publicados en el sitio)

- Producción por Áreas de Servicio

## Privacidad de las capturas

Todas las capturas de tableros que aparecen en el sitio están anonimizadas antes de publicarse:

- Nombre del hospital → `HOSPITAL PAIH`
- Nombres de sede/centro de atención → `SEDE PAIH UNO`, `SEDE PAIH DOS`, …
- Nombres de médicos → `MEDICO PAIH UNO`, `MEDICO PAIH DOS`, …
- Prefijos de número de factura (p. ej. `FHUS`, `HUSM`) → `PAIH`
- Datos de pacientes (nombre, documento) → reemplazados por aviso de confidencialidad, conforme a la Ley 1581 de 2012
- Los textos de los tooltips y de las narrativas automáticas también se revisan: si mencionan sedes u otros nombres propios, se reescriben con los alias `SEDE PAIH …`

## Stack técnico

- HTML + CSS + JavaScript vanilla en un solo `index.html`, sin build step
- Tipografía: IBM Plex Sans / IBM Plex Mono
- Formulario de contacto: [FormSubmit](https://formsubmit.co)
- Contador de visitas: [Abacus](https://abacus.jasoncameron.dev)
- Hosting: GitHub Pages (dominio `paih.net` vía `CNAME`)
- Fuente de los datos mostrados: Power BI Service, conectado a Dinámica Gerencial Hospitalaria vía gateway on-premises

## Estructura del repositorio

```
paih-web/
├── index.html    # Sitio completo (HTML + CSS + JS)
├── img/
│   ├── lienzos/      # Capturas anonimizadas de cada lienzo (<nombre>.jpg y <nombre>_tooltip.jpg) y del menú (home.jpg)
│   └── historias/    # Imágenes de las historias; nuevas/ contiene las tarjetas de los lienzos nuevos
├── CNAME         # Dominio personalizado para GitHub Pages
└── README.md
```

## Ver el sitio en local

El sitio es estático. Como las imágenes viven en `img/`, conviene servirlo con un servidor simple, por ejemplo:

```bash
python -m http.server 8000
```

y luego visitar `http://localhost:8000`.

## Publicar cambios

El sitio es un `index.html` con sus imágenes en `img/`. Para actualizarlo:

1. Editar `index.html` y/o agregar las imágenes anonimizadas en `img/` de este repositorio. **No** reemplazar `index.html` por una copia suelta: podría pisar cambios más recientes.
2. Confirmar el cambio (`commit`) y enviarlo a la rama `main`.
3. GitHub Pages republica automáticamente en `paih.net` en uno o dos minutos.

## Contacto

- Correo: hector_nick@hotmail.com
- WhatsApp: +57 313 401 6630