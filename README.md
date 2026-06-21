# Menú Digital Interactivo — Los Arcos de Doña Julia

Menú digital interactivo para el restaurante **Los Arcos de Doña Julia**, ubicado en Jardín Hidalgo No. 11, Villa de Pozos, San Luis Potosí. Cocina tradicional mexicana con el lema *"Sazón que viene del corazón"*.

---

## Archivo principal

```
Menu Los Arcos de Dona Julia.html
```

Archivo HTML único y autónomo. No requiere servidor, framework ni dependencias externas (excepto Google Fonts). Se abre directamente en cualquier navegador.

---

## Cómo usar

### Cliente (comensal)

1. Escanear el código QR en la mesa.
2. El menú se abre en el navegador del celular.
3. Navegar por categorías usando las pestañas superiores o usar el buscador.

### Administrador

1. Tocar el escudo/logo **5 veces consecutivas** (en menos de 2 segundos) desde la pantalla de bienvenida.
2. Ingresar la contraseña: `admin1234arcos`
3. Desde el panel se puede:
   - Editar nombre, descripción y precio de cualquier platillo.
   - Activar/desactivar platillos (por ejemplo, marcar como "agotado").
   - Asignar o quitar insignias.

> Los cambios del administrador se guardan en `localStorage` del navegador del dispositivo. Es recomendable usar siempre el mismo dispositivo para administrar el menú.

---

## Estructura del menú

| Sección          | Contenido                                                      |
|------------------|----------------------------------------------------------------|
| **Desayunos**    | Huevos, chilaquiles, quesadillas, lechuzas                    |
| **Gorditas y Sopes** | Gorditas normales y especiales, sopes                     |
| **Comidas**      | Enmoladas, enchiladas, flautas, carnes, antojitos              |
| **Especialidades** | Menudo, barbacoa de borrego, mole, guacamole, platillo del día |
| **Infantil**     | Salchipulpos, nuggets, hamburguesa, papas, hot cakes           |
| **Bebidas**      | Refrescos, café de olla, aguas, licuados, cervezas, micheladas |

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

El menú incluye 10 fotografías generadas por IA (Higgsfield) embebidas directamente en el HTML como base64. Cada imagen está optimizada a 300x300px JPEG (~30 KB cada una) para carga rápida en móvil.

| Imagen                       | Platillo                  | Sección         |
|------------------------------|---------------------------|-----------------|
| Chilaquiles con pollo        | Chilaquiles con pollo     | Desayunos       |
| Huevos Rancheros             | Huevos Rancheros          | Desayunos       |
| Enchiladas Potosinas         | Enchiladas potosinas      | Comidas         |
| Barbacoa de Borrego          | Barbacoa de Borrego       | Especialidades  |
| Menudo                       | Menudo                    | Especialidades  |
| Mole con pollo               | Mole con pollo / cerdo    | Especialidades  |
| Gorditas                     | Gordita y Gordita Especial| Gorditas y Sopes|
| Arrachera                    | Arrachera                 | Comidas         |
| Café de olla                 | Café de olla              | Bebidas         |
| Agua de jamaica              | Agua de sabor             | Bebidas         |

Los platillos sin imagen muestran un placeholder con patrón diagonal.

Las imágenes originales en alta resolución (2048x2048) se encuentran en la carpeta `Imágenes/`.

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

| Componente      | Detalle                                          |
|-----------------|--------------------------------------------------|
| Estructura      | HTML5 semántico                                  |
| Estilos         | CSS3 con variables inline (sin frameworks)       |
| Lógica          | JavaScript vanilla (sin dependencias)            |
| Persistencia    | `localStorage` para cambios del administrador    |
| Fuentes         | Google Fonts (Playfair Display, DM Sans)         |
| Imágenes        | Base64 embebido (archivo 100% autónomo)          |
| Diseño          | Mobile-first, optimizado para 360px–430px        |

---

## Pantallas

1. **Bienvenida** — Logo, lema, botón "Ver Menú" y datos de contacto.
2. **Menú** — Pestañas por categoría, buscador, tarjetas de platillos con imagen, insignias y precio.
3. **Login Admin** — Pantalla de contraseña (acceso oculto vía 5 taps en el logo).
4. **Panel Admin** — Lista de platillos con toggles de activación y botones de edición.
5. **Modal de Edición** — Formulario para editar nombre, descripción, precio e insignias.

---

## Archivos del proyecto

```
Los Arcos de Doña Julia/
├── Menu Los Arcos de Dona Julia.html   ← Menú digital (archivo principal)
├── menu.html                           ← Versión anterior del menú
├── menu.md                             ← Contenido del menú en Markdown
├── menu26.pdf                          ← Menú original en PDF
├── Brief_Menu_Interactivo.md           ← Brief del proyecto
├── Los_Arcos_de_Dona_Julia.md          ← Notas del proyecto
├── Logo1.png                           ← Logo fondo naranja
├── Logo1 Trans.png                     ← Logo fondo transparente
├── Logo2.png                           ← Logo alternativo
├── Logo3.png                           ← Logo escudo ilustrado
├── Imágenes/
│   ├── Imagen Muestra.png              ← Referencia visual (plato de barro)
│   ├── 01_Chilaquiles_con_Pollo.jpeg   ← 2048x2048
│   ├── 02_Huevos_Rancheros.jpeg
│   ├── 03_Enchiladas_Potosinas.jpeg
│   ├── 04_Barbacoa_de_Borrego.jpeg
│   ├── 05_Menudo.jpeg
│   ├── 06_Mole_con_Pollo.jpeg
│   ├── 07_Gorditas.jpeg
│   ├── 08_Arrachera.jpeg
│   ├── 09_Cafe_de_Olla.jpeg
│   └── 10_Agua_de_Jamaica.jpeg
└── README.md                           ← Este archivo
```

---

## Contacto del restaurante

- **Dirección:** Jardín Hidalgo No. 11, Villa de Pozos, S.L.P.
- **Teléfonos:** (444) 824 0561 · (444) 300 9318
- **Redes:** @losarcosdejulia (Facebook)
- **Avalado por:** Turismo Municipal de Villa de Pozos
