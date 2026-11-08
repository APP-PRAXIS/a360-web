# Informe de correcciones · asesores360.com

| | |
| --- | --- |
| **Proyecto** | A360 Ibiza Asesores, web A360 Asesoría + A360 Marketing (HTML estático) |
| **Producción** | https://www.asesores360.com (no se ha tocado) |
| **Enlace de pruebas** | https://app-praxis.github.io/a360-web/ |
| **Repositorio** | https://github.com/APP-PRAXIS/a360-web (público, por decisión del cliente) |
| **Rama con las correcciones** | `fix/auditoria-2026-11-08` (último commit de código: `bafe38a`) |
| **Rama del enlace de pruebas** | `preview/auditoria-2026-11-08` (= fix + ajustes solo de pruebas) |
| **Rama `main`** | Copia exacta de producción a 2026-11-08 (punto de partida) |
| **Fecha** | 8 de noviembre de 2026 |
| **Autor** | Praxis Branding |

---

## 1. Resumen ejecutivo

Se revisaron las 11 páginas de la web en 12 tamaños de pantalla, desde móviles pequeños hasta monitores grandes. También se revisaron los formularios, la seguridad del servidor, la accesibilidad, el SEO técnico y el rendimiento. La web ya era rápida y estaba bien construida, pero tenía fallos que hacían perder contactos y afeaban la versión móvil.

Lo que se ha mejorado:

- **Formularios de contacto.** Ahora tienen un campo para escribir la consulta (antes no existía). Los correos llegan con un asunto que distingue Asesoría de Marketing y se puede responder directamente al cliente.
- **Móvil.** La página «Quiénes somos» de Asesoría ya no se desplaza de lado ni corta el menú y el botón de WhatsApp.
- **Contenido siempre visible**, aunque el navegador bloquee o tarde en cargar el JavaScript. Los buscadores y las IA ven ahora también el subtítulo principal.
- **Accesibilidad.** Los textos y botones con poco contraste (incluidos los de WhatsApp) cumplen la norma WCAG AA.
- **Privacidad y seguridad.** El mapa de Google ya no se carga sin que el usuario lo pida, y el servidor envía las cabeceras de seguridad recomendadas.
- **SEO.** Los datos estructurados son válidos, las descripciones tienen una longitud correcta, el HTML no tiene errores W3C y las direcciones duplicadas redirigen a la buena.

### Cifras

| Severidad | Detectados | Corregidos y verificados | Corregidos, pendientes de verificar en producción o dispositivo real | Requieren acción del cliente | Descartados |
| --- | --- | --- | --- | --- | --- |
| Crítico | 0 | 0 | 0 | 0 | 0 |
| Alto | 6 | 5 | 1 (A-05) | 0 | 0 |
| Medio | 12 | 9 | 2 (M-03, M-06) | 1 (M-02) | 0 |
| Bajo | 10 | 9 | 1 (B-10) | 0 | 0 |
| **Total** | **28** | **23** | **4** | **1** | **0** |

### Lighthouse: antes y después

Antes = producción (www.asesores360.com). Después = enlace de pruebas (GitHub Pages). Una ejecución por URL, Lighthouse 12.8: móvil con 4G lenta emulada y CPU ×4.

| Página | Dispositivo | Rendimiento | Accesibilidad | Buenas prácticas | SEO | LCP (s) |
| --- | --- | --- | --- | --- | --- | --- |
| / | Móvil | 100 | 100 | 100 | 100 → 100* | 1,8 s → 1,6 s |
| / | Escritorio | 100 | 100 | 100 | 100 → 100* | 0,4 s → 0,6 s |
| /asesoria/ | Móvil | 100 → 99 | 100 | 100 | 100 → 100* | 1,5 s → 2,0 s |
| /asesoria/ | Escritorio | 100 | 96 → 100 | 100 | 100 → 100* | 0,3 s → 0,4 s |
| /asesoria/servicios.html | Móvil | 99 | 100 | 100 | 100 → 100* | 2,1 s → 2,2 s |
| /asesoria/servicios.html | Escritorio | 100 | 100 | 100 | 100 → 100* | 0,4 s |
| /asesoria/nosotros.html | Móvil | 98 → 99 | 100 | 100 | 100 → 100* | 2,4 s → 2,0 s |
| /asesoria/nosotros.html | Escritorio | 100 | 96 → 100 | 100 | 100 → 100* | 0,6 s → 0,5 s |
| /asesoria/contacto.html | Móvil | 100 → 99 | 100 | 100 | 100 → 100* | 1,4 s → 1,7 s |
| /asesoria/contacto.html | Escritorio | 100 | 96 → 100 | 100 | 100 → 100* | 0,5 s → 0,4 s |
| /marketing/ | Móvil | 100 → 99 | 100 | 100 | 100 → 100* | 1,6 s → 1,8 s |
| /marketing/ | Escritorio | 100 | 100 | 100 | 100 → 100* | 0,5 s → 0,4 s |
| /marketing/servicios.html | Móvil | 100 | 96 → 100 | 100 | 100 → 100* | 1,4 s → 1,5 s |
| /marketing/servicios.html | Escritorio | 100 | 96 → 100 | 100 | 100 → 100* | 0,3 s → 0,4 s |
| /marketing/nosotros.html | Móvil | 98 → 99 | 100 | 100 | 100 → 100* | 2,4 s → 1,8 s |
| /marketing/nosotros.html | Escritorio | 100 | 100 | 100 | 100 → 100* | 0,4 s → 0,5 s |
| /marketing/contacto.html | Móvil | 100 | 100 | 100 | 100 → 100* | 1,5 s → 1,6 s |
| /marketing/contacto.html | Escritorio | 100 | 96 → 100 | 100 | 100 → 100* | 0,4 s |
| /legal.html | Móvil | 100 | 95 → 100 | 100 | 100 → 100* | 1,1 s → 0,9 s |
| /legal.html | Escritorio | 100 | 95 → 100 | 100 | 100 → 100* | 0,3 s |

\* En el enlace de pruebas Lighthouse da 63–66 en SEO **solo** por la auditoría *is-crawlable*, porque el `noindex` está puesto a propósito; el resto de auditorías SEO pasan. En producción, sin ese `noindex`, queda en 100.

Resultado: la **accesibilidad sube de 95–96 a 100** en las 9 combinaciones que fallaban. El rendimiento se mantiene en 98–100 (las variaciones de ±1 punto y ±0,3 s son ruido entre servidores). El **LCP móvil de las dos páginas «Nosotros» mejora de 2,4 s a 1,8–2,0 s**.

### Lo que notará el cliente

- **Más contactos útiles.** Cada consulta llega con el mensaje del cliente y se responde con un clic.
- **Móvil.** No hay páginas que bailen de lado. El chat de WhatsApp no hace zoom en iPhone y los botones de WhatsApp se leen bien.
- **Velocidad.** Las imágenes más pesadas de Marketing pasan de 557 KB a 219 KB, y los logos pesan la mitad.
- **Seguridad y privacidad.** HTTPS forzado (HSTS), política de seguridad de contenidos (CSP) y Google Maps solo bajo demanda.
- **SEO.** HTML válido, datos estructurados correctos y sin URL duplicadas.

---

## 2. Cómo testear la web

**Enlace:** https://app-praxis.github.io/a360-web/ (sin contraseña)

> **Es un entorno de pruebas.** No se indexa (`noindex, nofollow` en todas las páginas y `robots.txt` con `Disallow: /`). **Los formularios no envían nada:** al enviar muestran «MODO PRUEBA» y no contactan con Web3Forms ni con ningún correo. Los enlaces de canonical y de redes sociales siguen apuntando a producción, que es lo correcto.

| # | Página | Dispositivo | Qué hacer | Resultado esperado |
| --- | --- | --- | --- | --- |
| 1 | /asesoria/nosotros.html | Móvil | Intentar desplazar la página hacia los lados | No se mueve. El menú (arriba) y el botón verde de WhatsApp (abajo) se ven enteros. |
| 2 | /asesoria/contacto.html y /marketing/contacto.html | Móvil y escritorio | Pulsar «Enviar consulta» sin rellenar nada | Aparecen 6 mensajes de error, incluido el de la casilla de privacidad. Hay un campo nuevo, «Mensaje». |
| 3 | Mismo formulario | Cualquiera | Rellenarlo todo y enviar | El botón dice «Enviando…» y luego aparece «MODO PRUEBA: …». No llega ningún correo. |
| 4 | Contacto (los dos) | Cualquiera | Bajar hasta «Cómo llegar» | Se ve una caja gris con «Ver el mapa». El mapa de Google solo aparece al pulsarlo. |
| 5 | /asesoria/contacto.html | Escritorio | Mirar el botón «Escríbenos por WhatsApp» | El fondo es verde, como antes, y el texto es oscuro y se lee bien. |
| 6 | /asesoria/ | Escritorio | Pulsar la lupa, escribir «calendario», tabular hasta «Cerrar» y pulsar Enter | El buscador se cierra; no navega a ninguna página. |
| 7 | /asesoria/ y /marketing/ | Cualquiera | Desactivar JavaScript en el navegador y recargar | Todo el texto se ve, incluido el subtítulo bajo el título principal. |
| 8 | /legal.html | Móvil | Pulsar «Cookies» en el índice superior | El título «Política de cookies» queda visible, no tapado por la cabecera. |
| 9 | Chat de WhatsApp (cualquier página) | iPhone | Abrir el botón verde y tocar el campo de texto | La página no hace zoom. |
| 10 | Todas | Escritorio | Abrir la consola de DevTools (F12) y navegar | Sin errores rojos. La única excepción es una URL inexistente, que da el 404 esperado. |

> El enlace de pruebas está en GitHub Pages, que no aplica el `.htaccess`. Por eso, ahí no se pueden comprobar las cabeceras de seguridad (HSTS, CSP), la redirección de `index.html` ni la caché versionada. Están verificadas en un Apache local con el mismo `.htaccess` y deben revisarse en producción después de subir (sección 5).

---

## 3. Detalle de correcciones (técnico)

Verificación hecha con Chrome y Playwright, en local sobre Apache con HTTPS y el mismo `.htaccess` de producción, en 12 viewports: 320, 360, 375, 390, 414, 768, 1024, 1280, 1440, 1920, 667×375 en horizontal y 1024×1366.

### Responsive

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-01 | Alto | /asesoria/nosotros.html | Scroll horizontal en móvil (390 → 421 px); nav y WhatsApp cortados | El halo `.split-asimetrico__foto::before` con `inset:-16%` sobresalía 55 px. Su zona exterior ya era transparente. (La auditoría señalaba también el logo del hero: era un falso positivo, porque ese logo lo recorta `overflow:clip`.) | El halo solo se extiende en vertical (`inset:-16% 0`) y la elipse se reescribe en % (`66% 50%`), con el mismo dibujo | `assets/css/asesoria.css` | 9574a2b | `scrollWidth` = viewport en los 12 anchos; diferencia de 0–1 px con producción a 390 y 1280 |

### Funcionalidad

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-02 | Alto | Contacto ×2 | Formulario sin campo de mensaje | No existía en el HTML | `textarea name="mensaje"` obligatorio, `maxlength=3000` | `asesoria/contacto.html`, `marketing/contacto.html` | e9c529e | Envío interceptado: llega `mensaje`; vacío da error; 4000 caracteres quedan en 3000 |
| A-05 | Alto | Contacto ×2 | Correos sin Reply-To del cliente y con asunto genérico | El correo iba en `correo` (Web3Forms toma el Reply-To de `email`) y faltaban `subject` y `from_name` | `name="email"`, más `subject` y `from_name` ocultos, distintos para Asesoría y Marketing | ídem | e9c529e | Payload correcto. **Pendiente:** un envío real |
| A-03 | Alto | 8 páginas | Sin JS (o si app.js falla) todo el contenido quedaba invisible; subtítulo vacío para los bots | `.reveal{opacity:0}` sin depender de JS; el texto del subtítulo solo estaba en `data-texto-maquina` | Clase `.js` en el `<head>`, que se retira en `load` si app.js no arranca; `.js .reveal`; texto del subtítulo en el HTML | `assets/css/base.css`, `assets/js/app.js`, 8 HTML | 564aa65 | Sin JS: 0/22 invisibles. app.js con 404: todo visible. app.js lento: sin parpadeo |
| B-06 | Bajo | /asesoria/, /marketing/ | Con scroll rápido quedaban bloques invisibles | El observer solo revelaba lo que entraba en pantalla | También revela lo que ya quedó por encima | `assets/js/app.js` | 564aa65 | Scroll rápido y salto a ancla: 0 invisibles por encima |
| M-05 | Medio | Buscador | Enter sobre «Cerrar» navegaba al primer resultado | El `keydown` del panel capturaba Enter con cualquier foco | Solo actúa si el foco está en el input | `assets/js/app.js` | cf8a236 | Enter en «Cerrar» cierra sin navegar |
| M-12 | Medio | /legal.html | El título quedaba tapado al llegar por ancla | Faltaba `scroll-margin-top` | `scroll-margin-top:104px` en las secciones | `legal.html` | c973806 | `#cookies`: título a 153 px, con la cabecera en 89 px |
| B-01 | Bajo | Contacto ×2 | Sin estado «Enviando…»; un 500 se mostraba como «sin conexión» | `.json()` sin comprobar `ok` ni el tipo | Estado de envío, limpieza del mensaje anterior, `respuesta.ok` y content-type | `assets/js/app.js` | fed78fa | 500 con HTML → «No hemos podido…»; sin red → «No hay conexión…» |
| B-02 | Bajo | Contacto ×2 | Sin `maxlength` | — | `maxlength` en nombre, email, teléfono y mensaje (el teléfono sigue siendo obligatorio: es decisión de negocio) | 2 contactos | e9c529e | Atributos presentes |

### Rendimiento

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-06 | Alto | Todas | Riesgo de CSS/JS viejos tras desplegar (caché de 7 días) | URL sin versión | `?v=20261108` en las 32 referencias | 11 HTML | c4d27af | Las URL versionadas responden 200 |
| M-07 | Medio | Heros | Bucle `requestAnimationFrame` infinito, también en táctiles | Sin comprobar el puntero ni condición de parada | Sale sin ratón; el bucle se detiene al converger | `assets/js/app.js` | cfa4140 | Consola limpia; TBT de 0 ms |
| M-08 | Medio | /marketing/nosotros.html | Imagen LCP con `loading=lazy` y 2752 px | — | Sin lazy, `fetchpriority=high`, srcset 1376w/2752w | HTML + `fondo-mision-vision-mk-1376.webp` | 371a260 | Auditoría lcp-lazy-loaded OK |
| M-09 | Medio | Todas | Logos de 973 px mostrados a 44–60 px; fotos de más de 1000 px mostradas a 352 px | Sin variantes por tamaño | Logos de 180 px; fotos WebP de 704 px | 9 HTML + 7 imágenes nuevas | 371a260 | Diferencia visual de 0–0,3 % a 2x. **Parcial:** los fondos `fondo-*-mk.webp` y las fotos de equipo y oficina siguen sin `srcset` |

### Accesibilidad

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A-04 | Alto | Contacto ×2, FAQ | Botón de WhatsApp con contraste 1,98:1 | Texto blanco sobre #25D366 | Mismo verde, texto e icono #0B3B2E (6,3:1). **Cambio visual:** el texto deja de ser blanco | `asesoria.css`, `marketing.css`, `base.css` | c457b5a | Lighthouse color-contrast OK |
| M-10 | Medio | Legal, nosotros, nav, marketing/servicios | Naranja y azul de marca por debajo de 4,5:1 en texto pequeño | Colores de marca usados en texto pequeño | Token existente `--naranja-texto`, nuevo `--azul-acero-texto`, pie de legal y chips 02/03/05 oscurecidos lo justo | CSS + `legal.html` | c457b5a | Lighthouse Accessibility de 95–96 a 100 |
| M-11 | Medio | Contacto ×2 | La casilla de privacidad no mostraba error; sin ARIA | Faltaba `.campo__error` | Mensaje propio, `aria-invalid` y `aria-describedby` | 2 contactos, `app.js`, `base.css` | fed78fa | Cada campo enlazado a su error |
| B-05 | Bajo | 8 páginas | Sin landmark `<header>`; chat sin rol | — | `<header>` en la nav flotante; `role="dialog"` en el chat | 8 HTML, `app.js` | afb7ef8 | header:1; diferencia visual del nav de 0–0,02 % |

### SEO

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| M-04 | Medio | /marketing/, contacto | Schema `MarketingAgency` inexistente | Tipo inventado | `ProfessionalService` | 2 HTML | 183a07f, 6e0bc53 | JSON-LD válido |
| B-03 | Bajo | 8 páginas | Error W3C: `role=combobox` en `type=search` | — | `type="text" enterkeyhint="search"` | 8 HTML | a61f851 | W3C: 0 errores en las 11 páginas |
| B-04 | Bajo | Contacto ×2 | Error W3C: `width/height="100%"` en el iframe | — | El iframe se crea por JS y se dimensiona por CSS | ver M-01 | 0dd9ad0 | W3C: 0 errores |
| B-07 | Bajo | 5 páginas | `meta description` de 170–185 caracteres | — | Recortadas a 127–159 sin reescribirlas | 5 HTML | 534cbc8 | Longitudes medidas |
| B-08 | Bajo | Todas | Faltaban metas `og:image:*`; `/index.html` duplicaba la URL | — | Width, height y alt de la imagen OG; 301 de `index.html` a la URL con barra | 10 HTML, `.htaccess` | 88080e0 | curl: 301 conservando la query |

### Seguridad

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| M-03 | Medio | Todo el sitio | Sin HSTS, CSP ni Permissions-Policy | No configuradas | Las tres cabeceras en `.htaccess`; la CSP sin `unsafe-inline` en scripts (usa el hash del único script inline) | `.htaccess` | 6f33590 | 0 violaciones de CSP en 11 páginas × 2 anchos con todas las interacciones. **Pendiente:** confirmarlo en el hosting |
| B-09 | Bajo | Todas | `target=_blank` sin `noreferrer` | — | `rel="noopener noreferrer"` en 41 enlaces y en `window.open` | 11 HTML, `app.js` | 9b42971 | 0 enlaces sin `noreferrer` |

### Legal

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| M-01 | Medio | Contacto ×2 | Google Maps se cargaba sin interacción (envía la IP a Google) | iframe incrustado directamente | Aviso con «Ver el mapa» (clic para cargar) y enlace «Abrir en Google Maps». **Cambio visual:** caja gris hasta pulsar | 2 contactos, `app.js`, CSS | 0dd9ad0 | 0 peticiones a Google antes del clic |
| M-02 | Medio | /legal.html | No se informa de la transferencia internacional (Web3Forms) | Texto legal | **Acción del cliente** (sección 5) | — | — | — |

### Compatibilidad

| ID | Sev. | Página | Problema detectado | Causa raíz | Solución aplicada | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| M-06 | Medio | Chat de WhatsApp | Zoom de iOS al escribir | `font-size` de 15 px | 16 px | `base.css` | 4136874 | 0 inputs de menos de 16 px. **Pendiente:** iPhone real |
| B-10 | Bajo | Todas | El modo oscuro forzado podía invertir colores | Sin `color-scheme` | `<meta name="color-scheme" content="light">` | 11 HTML | e7b202f | Presente. **Pendiente:** Samsung Internet |

---

## 4. Pendientes y acciones fuera del código

| Punto | Por qué está pendiente | Qué hacer exactamente |
| --- | --- | --- |
| A-05 · Envío real | El entorno de pruebas no envía correos, a propósito | Tras subir a producción, enviar «TEST AUDITORÍA – no responder» desde cada contacto. Comprobar el asunto («Nueva consulta desde la web · A360 Asesoría / Marketing»), que aparece `mensaje` y que «Responder» va al correo de prueba. El dato del correo llega ahora como `email`. |
| Web3Forms | Depende de la cuenta del cliente | En el panel: Allowed domains = `asesores360.com`, y activar el filtro de spam o hCaptcha. La clave es pública por diseño y está en el repositorio. |
| M-03 · Cabeceras | GitHub Pages no aplica `.htaccess` | Tras subir: `curl -sI https://www.asesores360.com/` debe mostrar `strict-transport-security`, `content-security-policy` y `permissions-policy`. Si no aparecen, pedir al hosting que active `mod_headers` o que ponga las tres cabeceras con los valores del `.htaccess`. |
| HSTS ampliado (opcional) | Puede haber subdominios sin HTTPS | Si todos usan HTTPS: `max-age=31536000; includeSubDomains`. |
| M-02 · Privacidad | Texto legal | Añadir en «Destinatarios»: «Web3Forms puede tratar los datos fuera del EEE; esta transferencia se ampara en [Marco de Privacidad de Datos UE-EE. UU. / cláusulas contractuales tipo]», tras confirmar la garantía con Web3Forms. Valorar una primera capa bajo la casilla del formulario (responsable, finalidad, derechos y enlace). |
| Política de cookies (M-01) | Texto legal | Sustituir el párrafo del mapa por: «La página de contacto ofrece un mapa de Google Maps que solo se carga si pulsas “Ver el mapa”. En ese momento Google recibe tu dirección IP y puede usar sus propias cookies». |
| M-06, B-10 y navegadores | Sin dispositivos reales | iPhone (Safari): nosotros y chat. Samsung Internet con modo oscuro. Firefox y Edge: recorrer las 4 plantillas. VoiceOver: formulario, menú, búsqueda y chat. |

---

## 5. Notas de despliegue (interno)

**Qué se sube a producción:** solo el contenido de la rama `fix/auditoria-2026-11-08` (o el zip `A360-subir-fix-auditoria-2026-11-08.zip`), excepto este informe.

- **Modificados (17):** `.htaccess`, `htaccess.txt`, `index.html`, `404.html`, `legal.html`, `asesoria/{index,servicios,nosotros,contacto}.html`, `marketing/{index,servicios,nosotros,contacto}.html`, `assets/css/{base,asesoria,marketing}.css` y `assets/js/app.js`.
- **Nuevos (8):** `assets/img/logo-a360-180.png`, `logo-a360-blanco-180.png`, `logo-marketing-azul-180.png`, `logo-marketing-blanco-180.png`, `fondo-mision-vision-mk-1376.webp` y `assets/img/fotos/{ingenia-grid-redes,26_07_01_PORTADA,trabajo-mk-diseno-web}-704.webp`.
- **No hay** base de datos ni configuración de CMS que replicar.

**Lo que NO debe pasar a producción:**

- La rama `preview/auditoria-2026-11-08` entera. Lleva `meta robots noindex, nofollow`, un `robots.txt` con `Disallow: /`, rutas con prefijo `/a360-web/`, el formulario en «MODO PRUEBA» y `.nojekyll`.
- `INFORME-CORRECCIONES.md` (además, el `.htaccess` bloquea los `.md` con un 403).

**Pasos:**

1. Copia de seguridad del servidor, sobre todo del `.htaccess`.
2. Subir las imágenes nuevas y `assets/css`, `assets/js`.
3. Subir los 11 HTML.
4. Subir `.htaccess` (con «mostrar archivos ocultos» activado en el FTP).
5. Caché: el HTML va con `max-age=0` y CSS/JS cambian de URL, así que no hay que purgar nada salvo que haya un CDN o proxy delante.
6. En futuros cambios de CSS o JS, actualizar `?v=` en los 11 HTML. Si cambia el script inline del `<head>`, recalcular el hash de la CSP (el comando está en `.htaccess`).

**Smoke test después de subir:**

- [ ] `curl -sI https://www.asesores360.com/` muestra HSTS, CSP y Permissions-Policy.
- [ ] `/index.html` → 301 a `/`; `/asesoria/index.html` → 301 a `/asesoria/`.
- [ ] Home, /asesoria/, /marketing/ y legal: consola sin errores ni avisos de CSP.
- [ ] /asesoria/nosotros.html en móvil: sin desplazamiento lateral.
- [ ] Los dos contactos: campo Mensaje, 6 errores al enviar vacío y envío real con asunto y Reply-To correctos.
- [ ] El mapa solo carga tras pulsar «Ver el mapa».
- [ ] Los botones de WhatsApp se leen bien; el chat no hace zoom en iPhone.
- [ ] Compartir /marketing/ en WhatsApp muestra la vista previa.

---

## 6. Recomendaciones (fuera de la auditoría)

- **Unificar la dirección.** «12 bajos, local F · Santa Eulalia del Río» en la web y «planta 0, local F · Santa Eulària des Riu» en el aviso legal.
- **Centrar el logo en las imágenes OG.** WhatsApp recorta en cuadrado por el centro.
- **Logo en SVG.** Algunos logos grandes se amplían por encima de su tamaño real y se ven algo borrosos en retina.
- **`srcset` en los fondos** `fondo-*-mk.webp` y en las fotos de equipo y oficina (completa M-09).
- **Mover los `style="…"` del HTML a CSS** para quitar `unsafe-inline` de la CSP de estilos.
- **Accesibilidad del subtítulo «máquina de escribir»:** `aria-label` con el texto completo.
- **Casilla de privacidad de 20 px o más** para tocarla mejor en móvil.
- **`sitemap.xml`:** actualizar `lastmod` el día del despliegue.
- **Repositorios públicos.** Este repo y `juanrome09/a360-rediseno` son públicos. No contienen secretos más allá de la clave de Web3Forms, que ya es visible en la web, pero conviene restringirla por dominio (sección 4).

---

## 7. Ajustes posteriores a la auditoría (2026-11-08)

| Cambio | Problema | Causa raíz | Solución | Archivos | Commit | Verificación |
| --- | --- | --- | --- | --- | --- | --- |
| Footer de Asesoría | Bloque de cierre + footer demasiado alto, con un gran espacio vacío | `.cierre-pie` forzado a `min-height:100dvh` con `justify-content:space-between`: hueco de 99 px (768), 245 px (1920×1200), 418 px (1024×1366) y 485 px (2560) | Se quita la altura mínima y el bloque mide lo que su contenido, como el de Marketing | `assets/css/asesoria.css` | b06ebb6 | Hueco de 0 px en todos los anchos; bloque de 925–955 px (Marketing: 978–1005) |
| Carrusel «Nuestro trabajo» (/marketing/, móvil) | Al deslizar en vertical sobre las fotos se movía el carrusel por dentro y no la página | El halo `.trabajo-mk__pieza::before` (`inset:-29%`) desbordaba cada pieza; con `overflow-x:auto` el eje Y pasa a `auto` y el carrusel tenía scroll vertical propio (además de 41–75 px de scroll horizontal sobrante) | Mismo arreglo que en Servicios (`.servicio-panel-mk`): `overflow:hidden` en cada pieza dentro del carrusel móvil; `.reveal` pasa del contenedor a cada pieza | `assets/css/marketing.css`, `marketing/index.html` | 5b6e161 | Gesto vertical de 200 px: la página se mueve 201 px y el carrusel 0 (antes 0 y 65); swipe horizontal con snap correcto; escritorio sin cambios (0,1–0,9 %) |
