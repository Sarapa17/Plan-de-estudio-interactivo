# Plan de Estudio Interactivo

Constructor y visualizador interactivo de planes de estudio con grafo de dependencias. Una herramienta estática (HTML/CSS/JS) para organizar tus materias, definir correlativas y hacer seguimiento de tu progreso académico.

## Características

- ✨ **Validación visual en tiempo real** - Ve instantáneamente si un nombre de materia ya existe
- 📋 **Constructor intuitivo** - Agrega materias con cuatrimestre y estado inicial
- 🔗 **Correlativas** - Define dependencias entre materias
- 📊 **Grafo interactivo** - Visualiza las relaciones entre materias
- ✅ **Seguimiento de progreso** - Marca materias como Pendiente, Regular o Aprobada
- 💾 **Persistencia local** - Tu plan se guarda automáticamente en el navegador
- 🌓 **Tema claro/oscuro** - Cambia de tema según tu preferencia
- 📱 **Responsivo** - Funciona en desktop y mobile
- 📤 **Exporta a JSON** - Guarda tu plan para compatirlo o respaldar

## Cómo usar

### 1. Abrir la aplicación

Simplemente abre `index.html` en tu navegador (Chrome, Firefox, Safari recomendado).

### 2. Constructor: Agregar materias

En la sección "Cargá tus materias":

- **Nombre**: Escribe el nombre de la materia
    - ✓ Si está disponible, verás un mensaje verde
    - ⚠️ Si ya existe, verás una advertencia roja
- **Cuatrimestre**: Número del cuatrimestre donde va (1, 2, 3, etc.)
- **Estado inicial global**: Aplica un estado a todas las materias de una vez

Luego haz clic en **"Agregar"** (o presiona Enter)

### 3. Definir correlativas

En la sección "Definí correlativas":

- Selecciona una materia objetivo
- Marca las correlativas que necesita
- Haz clic en "Guardar Correlativas"

### 4. Visualizar el plan

Haz clic en **"Construir y Mostrar Plan"** para ver el grafo interactivo.

## Estados de materias

- **Pendiente** (gris): No cursada
- **Regular** (amarillo): Cursaste pero no aprobaste
- **Aprobada** (verde): Completada

En el grafo, haz clic en cualquier materia para cambiar su estado. Las materias se habilitan automáticamente cuando todas sus correlativas están aprobadas.

## Formatos de entrada

### Formato simple (modo avanzado)

```
Programación I;1;0
Programación II;2;0
Base de Datos;3;0
```

Formato: `NombreMateria;Cuatrimestre;Estado`

- Estado: 0=Pendiente, 1=Regular, 2=Aprobada

### Correlativas (modo avanzado)

```
Programación II -> Programación I
Base de Datos -> Programación II, Cálculo
```

Formato: `MateriaDependiente -> Prerequisito1, Prerequisito2`

## Lectura del grafo

- **Nodos**: Cada rectángulo es una materia
- **Flechas**: Indican dependencias (A → B significa que A debe aprobarse antes de B)
- **Colores**:
    - Gris: Pendiente
    - Amarillo: Regular
    - Verde: Aprobada
    - Azul claro: Habilitada para cursar
- **Distribución**: Organizadas por cuatrimestre (izquierda a derecha)

## GitHub Pages

Para publicar en GitHub Pages:

1. Sube este repositorio a GitHub
2. Ve a Settings → Pages
3. Selecciona "main" como rama
4. La aplicación estará disponible en: `https://<tu-usuario>.github.io/<tu-repo>/`

## Subir a GitHub

```sh
git init
git add .
git commit -m "Initial commit - Plan de estudios interactivo"
git remote add origin https://github.com/<tu-usuario>/<tu-repo>.git
git push -u origin main
```

## Requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Conexión a internet (para cargar la librería vis-network desde CDN)

## Archivos

- `index.html` — Aplicación completa embebida (HTML + CSS + JavaScript)
- `README.md` — Este archivo
- `.gitignore` — Configuración de Git

## Licencia

Libre para usar y modificar.
