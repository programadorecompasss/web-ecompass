# Proyecto: Rediseño web eCompass SAS
- Empresa colombiana de geomática: LiDAR, fotogrametría, mobile mapping (Trimble MX50), Gaussian Splatting, BIM, SIG (Esri Partner), topografía, catastro, drones (eBee TAC, eBee VISION, Matrice 350 RTK), venta de equipos.
- 12+ años, 170+ proyectos, 100+ clientes.

## Identidad visual (NUNCA cambiar sin autorización)
- Fondo: negro #000000
- Acento: naranja #FF6B00
- Tipografía: Barlow y Barlow Condensed (Google Fonts)
- Motivo gráfico: triángulos y cortes diagonales
- Idioma de todo el contenido: español (Colombia)

## Estructura de archivos
Sitio multipágina plano, sin subcarpetas (no existe `site/` ni `servicios/` con landings individuales):
- `index.html` — inicio; conserva la sección `id="contacto"` (CTA final de WhatsApp), pero el enlace "Contacto" del menú ahora lleva a `contacto.html`
- `servicios.html` — página única de servicios (no hay una landing por cada línea de servicio)
- `sectores.html`, `blog.html`, `multimedia.html`, `recursos.html`, `webinars.html`
- `contacto.html` — página de contacto: hero compacto con canvas LiDAR, información de contacto (WhatsApp, teléfono, correo, ubicación, badges Esri Partner/AgEagle, redes) y formulario con validación (fallback a WhatsApp si no hay backend configurado)
- `index.html.html` — archivo huérfano de la versión anterior de una sola página; no está enlazado desde ninguna otra página

## Reglas
- El archivo principal es index.html (todo en un solo archivo por ahora)
- Mantener responsive (móvil primero)
- No usar frameworks sin preguntarme primero
- Explícame los cambios en lenguaje sencillo, no soy programador
