# Proyecto: Rediseño web eCompass SAS
- Empresa colombiana de geomática: LiDAR, fotogrametría, mobile mapping (Trimble MX50), Gaussian Splatting, BIM, SIG (Esri Partner), topografía, catastro, drones (eBee X, eBee VISION, eBee TAC, eBee TAC Seguridad Pública, Matrice 350 RTK — distribuidor autorizado AgEagle en Colombia), venta de equipos.
- 13 años (cumplidos en 2026), 170+ proyectos, 100+ clientes.

## Identidad visual (NUNCA cambiar sin autorización)
Alineada al manual de marca oficial recibido.
- Fondo: negro #000000 (nota: el sitio actual usa fondo blanco/claro con bandas oscuras en hero/footer — heredado de un cambio de tema anterior, ver `## Estructura de archivos`)
- Naranja oficial: **Orange Pumpkin #ff7514** (Pantone 1585 C) — hover/oscuro: #d95c0a
- Paleta complementaria oficial:
  - `--gris-claro: #e9e9e9` — secciones claras alternas (fondo de sección, no de tarjetas)
  - `--arsenic: #363c4a` — color de texto principal sobre fondos claros (reemplaza al gris oscuro anterior)
  - `--oxford: #070f5f` — disponible en la paleta, aún sin aplicar en ningún elemento
- Tipografía:
  - Títulos: **Refoke** (tipografía oficial de marca) — pendiente de recibir los archivos de fuente; mientras tanto se usa **Barlow Condensed** como sustituto temporal
  - Cuerpo de texto: **Barlow** (Google Fonts)
- Motivo gráfico: triángulos y cortes diagonales (`clip-path` en botones, marcador `▲` en eyebrows)
- Formas complementarias oficiales de las letras del isotipo (referencia para futuros elementos gráficos):
  - Triángulos de la "A"
  - Brújula de la "O" (ya usada como isotipo/favicon del sitio)
  - Chevrones de la "M"
  - Diagonal de la aguja (la flecha naranja de la brújula)
- Idioma de todo el contenido: español (Colombia)

### Reglas del logo
- Usar siempre la versión horizontal como prioritaria (`img/logo-ecompass.png` oscuro / `img/logo-ecompass-blanco.png` claro)
- Tamaño mínimo en digital: 200px de ancho
- Área de reserva mínima alrededor del logo: igual a la altura de la letra "e" minúscula del logotipo
- Prohibido: deformar, rotar, agregar efectos (sombras, brillos, degradados) o contornos al logo

## Estructura de archivos
Sitio multipágina, casi todo plano en la raíz, con UNA subcarpeta (`drones/`) para las landings de producto:
- `index.html` — inicio; conserva la sección `id="contacto"` (CTA final de WhatsApp), pero el enlace "Contacto" del menú ahora lleva a `contacto.html`
- `servicios.html` — página única de servicios (no hay una landing por cada línea de servicio); las 11 tarjetas usan iconos SVG inline propios (ver `## Iconos de servicios`)
- `sectores.html`, `blog.html`, `multimedia.html`, `recursos.html`, `webinars.html`
- `contacto.html` — página de contacto: hero compacto con canvas LiDAR, información de contacto (WhatsApp, teléfono, correo, ubicación, badges Esri Partner/AgEagle, redes) y formulario con validación (fallback a WhatsApp si no hay backend configurado)
- `gaussian-splatting.html` — landing de Gaussian Splatting con galería "Proyectos 3D" (visores SuperSplat de carga diferida)
- `mobile-mapping.html` — landing de Mobile Mapping
- `drones/` — landings de producto de la línea AgEagle (menú "Drones" desplegable en el header de TODAS las páginas):
  - `drones/ebee-x.html`, `drones/ebee-vision.html`, `drones/ebee-tac.html`, `drones/ebee-tac-seguridad.html`
  - Cada una: sub-nav fija con anclas (Descripción, Características, ¿Por qué?, Especificaciones, Cámaras), hero oscuro con canvas de puntos, grid de cifras, sección de argumentos, tabla de especificaciones (con scroll horizontal en móvil), cámaras compatibles, CTA final con interlinking a los otros 3 drones
  - Rutas relativas ajustadas (`../index.html`, `../img/...`, etc.) — son las únicas páginas fuera de la raíz
- `index.html.html` — archivo huérfano de la versión anterior de una sola página; no está enlazado desde ninguna otra página

## Menú "Drones" (desplegable)
Presente en el header de las 14 páginas del sitio. En escritorio se revela con `:hover`/`:focus-within` (panel oscuro, hover naranja); en móvil funciona como acordeón dentro del menú hamburguesa (JS con `data-dropdown="drones"` / `#drones-menu`, clase `is-open` — evitar reusar el nombre de clase `open` porque colisiona en especificidad con `.nav ul.open` del menú móvil).

## Iconos de servicios
Las 11 tarjetas de `servicios.html` (y las 3 del adelanto en `index.html`) usan SVG inline dibujados a mano (viewBox 48x48, `stroke="currentColor"`, `stroke-width:2.5`, `stroke-linecap:square`, sin fill, cortes a 45°). Nada de emojis ni librerías de iconos externas — mantener ese estilo si se agregan más servicios.

## Reglas
- **[MÁXIMA PRIORIDAD] OBLIGATORIO: el sitio debe verse y funcionar perfectamente en celulares.** Todo cambio (secciones nuevas, banners, visores, formularios) debe verificarse en viewport móvil (375px y 414px de ancho) antes de dar por terminada la tarea: sin texto cortado ni desbordado, botones táctiles de mínimo 44px, imágenes y videos adaptados, menú móvil funcional, y sin scroll horizontal en ninguna página.
- El archivo principal es index.html (todo en un solo archivo por ahora)
- Mantener responsive (móvil primero)
- No usar frameworks sin preguntarme primero
- Explícame los cambios en lenguaje sencillo, no soy programador
