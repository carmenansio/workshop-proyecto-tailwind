### Estructura del Proyecto

```
tailwind-workshop/
├── .gitignore
├── index.html
├── input.css
├── output.css
├── package-lock.json
├── package.json
├── README.md
└── tailwind.config.js
```

### Contenido de los Archivos

#### .gitignore

```markdown
node_modules
```

#### 1. index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tailwind Workshop</title>
  <link href="output.css" rel="stylesheet">
</head>
<body class="bg-gray-100 p-6">

  <h1 class="text-4xl font-bold mb-4">Tailwind CSS Workshop</h1>

  <!-- Botón personalizado -->
  <button class="btn-custom">
    Custom Button
  </button>

  <!-- Contenedor responsive -->
  <div class="bg-blue-500 p-4 sm:bg-green-500 md:bg-red-500 lg:bg-yellow-500 xl:bg-purple-500 mt-6">
    Responsive Box
  </div>

  <!-- Input con focus -->
  <input class="border-2 border-gray-300 focus:border-blue-500 focus:outline-none mt-6 p-2" type="text" placeholder="Focus me">

  <!-- Footer -->
  <footer class="mt-12 bg-gray-800 text-white p-6 sm:flex sm:justify-between">
    <div>
      <h3 class="text-xl font-bold mb-2">Nuestra Compañía</h3>
      <ul class="links-footer">
        <li><a href="#">Acerca de nosotros</a></li>
        <li><a href="#">Testimonios</a></li>
        <li><a href="#">Nuestros socios</a></li>
        <li><a href="#">Proyectos</a></li>
      </ul>
    </div>
    <div class="mt-6 sm:mt-0">
      <h3 class="text-xl font-bold mb-2">Contáctanos</h3>
      <p>Avenida América 1400, Málaga, España</p>
      <p>Tel: 00-000-0000</p>
      <p>Email: correo@ejemplo.com</p>
    </div>
  </footer>

</body>
</html>
```

#### 2. input.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

/* Clases personalizadas */
.btn-custom {
  @apply bg-primary text-white py-2 px-4 rounded-lg shadow-lg;
}

/* Estilos personalizados */
.links-footer {
  @apply list-none p-0 m-0;
}

.links-footer li {
  @apply mb-2;
}

.links-footer a {
  @apply text-white hover:text-gray-300 transition-colors duration-300;
}
```

#### 3. tailwind.config.js

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#ff6363',
        secondary: '#1c1c1e',
      },
      spacing: {
        '72': '18rem',
        '84': '21rem',
        '96': '24rem',
      },
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('@tailwindcss/typography'),
  ],
}
```

#### 4. package.json

```json
{
  "name": "tailwind-workshop",
  "version": "1.0.0",
  "scripts": {
    "build": "postcss input.css -o output.css",
    "watch": "postcss input.css -o output.css --watch"
  },
  "dependencies": {
    "autoprefixer": "^10.2.6",
    "postcss": "^8.3.5",
    "tailwindcss": "^2.2.7"
  },
  "devDependencies": {
    "@tailwindcss/forms": "^0.3.3",
    "@tailwindcss/typography": "^0.4.1"
  }
}
```

#### 5. postcss.config.js

```javascript
module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer'),
  ]
}
```

#### 6. README.md


# Tailwind CSS Workshop

Este proyecto es un ejemplo práctico para el workshop de Tailwind CSS. Incluye ejemplos de cómo utilizar Tailwind para crear estilos personalizados, manejar diseño responsive y aplicar animaciones y transiciones.

## Estructura del Proyecto

- `index.html`: Contiene la estructura HTML del proyecto.
- `input.css`: Archivo CSS donde se importan las directivas de Tailwind y se definen las clases personalizadas.
- `tailwind.config.js`: Archivo de configuración de Tailwind donde se pueden extender temas y añadir plugins.
- `package.json`: Archivo de configuración de npm que incluye los scripts necesarios para construir el proyecto.
- `postcss.config.js`: Archivo de configuración de PostCSS.
- `README.md`: Este archivo, que explica la estructura y cómo ejecutar el proyecto.

## Cómo ejecutar el proyecto

1. Instala las dependencias:

   ```bash
   npm install -D tailwindcss
   npx tailwindcss init
   ```

2. Construye el CSS de Tailwind:

   ```bash
   npm run build
   ```

3. Abre `index.html` en tu navegador para ver el proyecto.

4. Para observar cambios en tiempo real mientras editas `input.css`, ejecuta:

   ```bash
   npm run watch
   ```

## Recursos

- [Documentación de Tailwind CSS](https://tailwindcss.com/docs)
- [Documentación de PostCSS](https://postcss.org/)


## Instrucciones para Ejecutar el Proyecto

1. **Clonar el repositorio (o crear la estructura manualmente):**
   ```bash
   git clone https://github.com/tu-repositorio/tailwind-workshop.git
   cd tailwind-workshop
   ```

2. **Instalar las dependencias:**
   ```bash
   npm install
   ```

3. **Construir el archivo CSS de Tailwind:**
   ```bash
   npm run build
   ```

4. **Abrir `index.html` en tu navegador para ver el proyecto:**
   Simplemente abre el archivo `index.html` en tu navegador preferido.

5. **Observar cambios en tiempo real (opcional):**
   Para observar cambios en tiempo real mientras editas `input.css`, ejecuta:
   ```bash
   npm run watch
   ```