# Patitas-Potosinas
# 🐾 Patitas Potosinas

Plataforma web de adopción de perros en San Luis Potosí, México.  
Conecta perritos rescatados de refugios locales con familias responsables.

> **Adopta, no compres.** Ninguna adopción tiene costo económico.

---

## 📋 ¿De qué trata?

Patitas Potosinas es un sitio web que digitaliza el proceso de adopción canina en San Luis Potosí. Permite a los usuarios:

- Explorar un catálogo de perros disponibles en refugios aliados.
- Ver la ficha completa de cada peludito (raza, edad, salud, refugio).
- Buscar y filtrar mascotas según sus preferencias.
- Registrarse como adoptante y enviar solicitudes de adopción.
- Conocer el proceso paso a paso y los requisitos.

El objetivo es dar visibilidad a los perros rescatados, reducir el abandono y facilitar adopciones responsables con seguimiento real.

---

## 🚀 Cómo ejecutarlo

El proyecto usa **módulos ES6 nativos**, por lo que necesita servirse desde un servidor local (no funciona abriendo `index.html` directo con doble clic).

### Opción 1 — Python (la más simple)

```bash
cd patitas-potosinas
python -m http.server 8000
```

Abre en el navegador: **http://localhost:8000**

### Opción 2 — Node.js

```bash
cd patitas-potosinas
npx serve
```

### Opción 3 — VS Code

1. Instala la extensión **Live Server**.
2. Clic derecho en `index.html` → **"Open with Live Server"**.

### Requisitos

- Un navegador moderno (Chrome, Firefox, Edge o Safari).
- Python 3 o Node.js instalados (solo para levantar el servidor).

---

## ✨ Características

### Vistas disponibles
- **Inicio** — Hero con mensaje de adopción, estadísticas, cómo funciona y mascotas destacadas.
- **Mascotas** — Catálogo con búsqueda y filtros por sexo, edad, tamaño y estado.
- **Detalle de mascota** — Galería, ficha completa, estado de salud, refugio responsable y botón para solicitar adopción.
- **Registro** — Formulario con validaciones y medidor de contraseña.
- **Login** — Inicio de sesión con opción de mostrar/ocultar contraseña.
- **Cómo adoptar** — Guía de 6 pasos y lista de requisitos.
- **Nosotros** — Misión del proyecto y refugios aliados.
- **404** — Página de error personalizada.

### Funcionalidades clave
- Navegación tipo SPA (sin recargas de página).
- Filtros combinables y ordenamiento en el catálogo.
- Modal de solicitud de adopción con validación de campos.
- Toasts (notificaciones) animados.
- Validación de correo, teléfono y contraseña.
- Diseño 100% responsivo (móvil, tablet y escritorio).
- Fallback automático si una imagen no carga.

---

## ⚠️ Cosas importantes que debes saber

### 1. Los datos son de prueba (mock)
Actualmente las mascotas y refugios viven en `js/data.js` como datos estáticos.  
Cuando conectes los microservicios reales, solo hay que reemplazar esas lecturas por llamadas `fetch()`. Busca los comentarios `// TODO:` en el código.

### 2. No funciona abriendo el HTML directo
Debes usar un servidor local. Si abres `index.html` con doble clic, verás errores de CORS en la consola por los módulos ES6.

### 3. El CSS debe estar en su archivo
Todo el diseño va en `css/styles.css`. Si lo pegas ahí tal cual, la página se ve exactamente como debe.

### 4. Rutas con hash
La app usa URLs tipo `#/mascotas` y `#/mascota/1`. Esto permite compartir enlaces directos sin configurar el servidor.

### 5. Sin dependencias ni build
No requiere `npm install`, Webpack, Vite ni nada parecido. Solo HTML, CSS y JavaScript puro.

### 6. Preparado para microservicios
La arquitectura está pensada para conectarse a servicios separados: usuarios, mascotas, adopciones, refugios y notificaciones. Cada `init()` de las vistas es el punto natural de integración.

### 7. Adopción gratuita por diseño
El sistema no contempla pagos entre adoptante y refugio. Solo se firma un compromiso de adopción responsable.

---

## 📁 Estructura del proyecto

```
patitas-potosinas/
├── index.html              # Entrada + navbar + footer
├── README.md               # Este archivo
├── css/
│   └── styles.css          # Todos los estilos
└── js/
    ├── app.js              # Bootstrap y eventos globales
    ├── router.js           # Enrutador SPA
    ├── data.js             # Datos mock (mascotas y refugios)
    ├── utils.js            # Helpers, validaciones, toasts
    ├── components/
    │   └── petCard.js      # Tarjeta reutilizable de mascota
    ├── modals/
    │   └── adopcion.js     # Modal de solicitud
    └── views/
        ├── home.js         # Inicio
        ├── mascotas.js     # Catálogo
        ├── detalle.js      # Ficha de mascota
        ├── registro.js     # Registro
        ├── login.js        # Login
        ├── comoAdoptar.js  # Guía de adopción
        ├── nosotros.js     # Sobre el proyecto
        └── notFound.js     # Página 404
```

---

## 🗺 Rutas de la aplicación

| Ruta | Vista |
|------|-------|
| `#/` | Inicio |
| `#/mascotas` | Catálogo |
| `#/mascota/:id` | Detalle (ej: `#/mascota/1`) |
| `#/registro` | Crear cuenta |
| `#/login` | Iniciar sesión |
| `#/como-adoptar` | Guía paso a paso |
| `#/nosotros` | Sobre el proyecto |
| Otra | Página 404 |

---

## 🛠 Tecnologías usadas

- **HTML5** — Estructura semántica.
- **CSS3** — Variables, Grid, Flexbox, animaciones.
- **JavaScript ES6+** — Módulos nativos, router, componentes.
- **Google Fonts** — Fraunces + Nunito Sans.

Sin frameworks, sin dependencias, sin build step.

---

## 🐾 Sobre el proyecto

Patitas Potosinas nació en 2023 como una iniciativa ciudadana sin fines de lucro.  
Trabaja de la mano con refugios locales, veterinarias y voluntarios para garantizar adopciones responsables, con seguimiento y acompañamiento real.

**Hecho con 🧡 en San Luis Potosí, México.**