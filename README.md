# Menú Digital Interactivo — Los Arcos de Doña Julia

Menú digital interactivo para el restaurante **Los Arcos de Doña Julia**, ubicado en Jardín Hidalgo No. 11, Villa de Pozos, San Luis Potosí. Cocina tradicional mexicana con el lema *"Sazón que viene del corazón"*.

---

## Archivo principal

```
index.html
```

Archivo HTML único y autónomo (app completa: bienvenida, menú y panel administrador). No requiere servidor, framework ni dependencias externas. Se abre directamente en cualquier navegador. Todas las imágenes (logos y fotos de platillos) van embebidas en base64, por lo que el archivo pesa ~15 MB.

> `menu.html` es una versión previa/alterna que contiene únicamente la pantalla de menú con su propio panel administrador independiente (misma contraseña, mismo esquema de 5 taps). Se conserva como respaldo, pero `index.html` es el archivo vigente.

---

## Cómo usar

### Cliente (comensal)

1. Escanear el código QR en la mesa.
2. El menú se abre en el navegador del celular.
3. Navegar por categorías usando las pestañas superiores o usar el buscador (ícono de lupa en la barra superior).
4. Contactar directamente por WhatsApp con el botón flotante (mensaje prellenado).

### Administrador

1. Tocar el escudo/logo **5 veces consecutivas** (en menos de 2 segundos) desde la pantalla de bienvenida.
2. Ingresar la contraseña: `admin1234arcos`
3. Desde el panel se puede:
   - Ver estadísticas rápidas (platillos activos, inactivos, de fin de semana).
   - Activar/desactivar cada platillo directamente desde la lista (toggle), sin entrar al modal de edición.
   - Editar nombre, descripción y precio de cualquier platillo.
   - Asignar o quitar insignias.
   - Cambiar o quitar la foto del platillo (se comprime automáticamente antes de guardarse).

> Los cambios del administrador se guardan en `localStorage` del navegador del dispositivo. Es recomendable usar siempre el mismo dispositivo para administrar el menú.

---

## Estructura del menú

71 platillos organizados en 6 categorías:

| Sección              | Platillos | Contenido                                                      |
|----------------------|:---------:|-----------------------------------------------------------------|
| **Desayunos**        | 19        | Huevos, chilaquiles, quesadillas, lechuzas                       |
| **Gorditas y Sopes**  | 4         | Gorditas normales y especiales, sopes                            |
| **Comidas**          | 25        | Enmoladas, enchiladas, flautas, carnes, antojitos                |
| **Especialidades**   | 6         | Menudo, barbacoa de borrego, mole, guacamole, platillo del día   |
| **Infantil**         | 5         | Salchipulpos, nuggets, hamburguesa, papas, hot cakes             |
| **Bebidas**          | 12        | Refrescos, café de olla, aguas, licuados, cervezas, micheladas   |

Algunos platillos (Menudo, Caldo de Menudo, Barbacoa de Borrego, Aguas frescas, Limonada/Naranjada Mineral) usan **precios por variante** (chico/mediano/grande, por kilo, por taco, etc.) en vez de un precio único. "Platillo del Día" es un ítem especial sin precio fijo que invita a preguntar al mesero.

---

## Insignias de platillo

| Insignia            | Significado                              |
|---------------------|------------------------------------------|
| Al momento          | Se prepara al momento (tiempo de espera) |
| Especialidad        | Platillo icónico de la casa              |
| Rápido              | Listo en pocos minutos                   |
| Cocción lenta       | Requiere mayor tiempo de preparación     |
| Picante             | Contiene chile o salsa picante           |
| Para niños          | Pertenece al menú infantil               |
| Vegetariano         | Sin carne                                |
| Fin de semana       | Disponible solo sábado y domingo         |

---

## Imágenes de platillos

70 de los 71 platillos tienen foto (objeto `ITEM_IMAGES` en `index.html`), embebidas en base64 directamente en el HTML. El único platillo sin imagen fija es "Platillo del Día" (cambia diario, no aplica foto).

Desde el panel administrador se puede reemplazar o quitar la foto de cualquier platillo individualmente: la nueva imagen se comprime automáticamente en el navegador (canvas + `toDataURL`) antes de guardarse en `localStorage`, sin necesidad de subir archivos a un servidor.

Las imágenes originales en alta resolución (2048x2048) se encuentran en la carpeta `Imágenes/` como respaldo/fuente.

---

## Pantalla de bienvenida

Entre el botón "Ver Menú" y la dirección del local se muestran tres leyendas informativas:

- Aceptamos tarjeta de débito/crédito 💳
- Generamos factura 🧾
- Tenemos todo para tu evento. Cotiza 🎉

Se ubican en `index.html` (bloque justo debajo del botón `btn-ver-menu`). El logotipo "Los Arcos de Doña Julia" de esta pantalla usa una versión recortada (sin el margen transparente que traía el PNG original) para evitar espacio en blanco excesivo entre el escudo, el nombre y el botón.

---

## Identidad visual

| Elemento           | Valor                                    |
|--------------------|------------------------------------------|
| Color principal    | Naranja `#E07222`                        |
| Color secundario   | Crema/beige `#FAF0E6`                   |
| Color de acento    | Azul turquesa `#5BB8D4`                  |
| Color texto        | Café oscuro `#4A2C0A`                    |
| Tipografía display | Playfair Display (serif)                 |
| Tipografía cuerpo  | DM Sans (sans-serif)                     |
| Estilo             | Tradicional mexicano, artesanal, cálido  |

---

## Tecnología

| Componente      | Detalle                                                                 |
|-----------------|--------------------------------------------------------------------------|
| Estructura      | HTML5, un solo archivo con 3 pantallas (`.screen`) alternadas por JS     |
| Estilos         | CSS inline por elemento (sin frameworks, sin hoja de estilos separada)   |
| Lógica          | JavaScript vanilla (IIFE, sin dependencias ni build step)                |
| Persistencia    | `localStorage`: `arcos_menu_v1` (platillos) y `arcos_images_v1` (fotos)  |
| Fuentes         | Playfair Display y DM Sans referenciadas por nombre; no se cargan desde ningún CDN, así que el navegador usa su fuente del sistema como respaldo |
| Imágenes        | Base64 embebido (archivo 100% autónomo, ~15 MB)                         |
| Diseño          | Mobile-first, optimizado para 360px–430px                               |

---

## Pantallas

1. **Bienvenida** — Logo, lema, botón "Ver Menú", leyendas de pago/factura/eventos y datos de contacto.
2. **Menú** — Pestañas por categoría, buscador, tarjetas de platillos con imagen, insignias y precio.
3. **Login Admin** — Pantalla de contraseña (acceso oculto vía 5 taps en el logo).
4. **Panel Admin** — Estadísticas rápidas y lista de platillos con toggles de activación y botones de edición.
5. **Modal de Edición** — Formulario para editar nombre, descripción, precio, insignias y foto del platillo.

---

## Archivos del proyecto

```
Los Arcos de Doña Julia/
├── index.html                          ← App completa (archivo principal)
├── menu.html                           ← Versión anterior, solo menú + panel admin propio
├── menu.md                             ← Contenido del menú en Markdown
├── menu26.pdf                          ← Menú original en PDF
├── Brief_Menu_Interactivo.md           ← Brief del proyecto
├── Los_Arcos_de_Dona_Julia.md          ← Notas del proyecto
├── Logo1.png                           ← Logo fondo naranja
├── Logo1 Trans.png                     ← Logo fondo transparente
├── Logo2.png                           ← Logo alternativo
├── Logo3.png                           ← Logo escudo ilustrado
├── Imágenes/                           ← 71 fotos de platillos en alta resolución (fuente de los base64 embebidos)
└── README.md                           ← Este archivo
```

---

## Contacto del restaurante

Datos tal como aparecen en el pie de página de `index.html`:

- **Dirección:** Jardín Hidalgo No. 11, Villa de Pozos, S.L.P. · C.P. 78421
- **WhatsApp:** 444 300 9318
- **Horario:** 7:00 – 17:00 hrs
- **Avalado por:** Turismo Municipal de Villa de Pozos
