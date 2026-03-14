# 🧩 React Kanban Board — Drag & Drop con dnd-kit

Aplicación web que implementa un **tablero Kanban interactivo** con funcionalidad de **Drag & Drop** para mover tareas entre columnas.

El proyecto está construido con **React** y utiliza **dnd-kit**, una librería moderna de alto rendimiento para sistemas de arrastrar y soltar.

Este proyecto fue desarrollado como práctica para comprender cómo implementar **arquitecturas de drag & drop escalables en React**.

---

# 🚀 Demo del proyecto

https://kanbansetup.netlify.app/

---

# 📌 Características principales

* Drag & Drop entre columnas
* Reordenamiento dinámico de tareas
* Arquitectura basada en componentes reutilizables
* Manejo de estado con React Hooks
* Estilos escalables con SCSS (metodología BEM)
* Uso de **dnd-kit** en lugar de librerías deprecadas como `react-beautiful-dnd`

---

# 🛠 Tecnologías utilizadas

Frontend:

* React
* JavaScript (ES6+)
* SCSS

Drag & Drop:

* @dnd-kit/core
* @dnd-kit/sortable
* @dnd-kit/utilities

Herramientas:

* Node.js
* npm
* Git

---

# 🧠 Arquitectura del sistema

El sistema está dividido en componentes especializados:

```
src
│
├── components
│   ├── kanban
│   │   ├── Kanban.jsx
│   │   └── Kanban.scss
│   │
│   └── card
│       └── Card.jsx
│
├── mockData.js
│
└── App.jsx
```

### Componentes principales

**Kanban**

* Componente raíz del tablero
* Controla el estado global
* Maneja los eventos de Drag & Drop

**DroppableSection**

* Representa cada columna del Kanban
* Define zonas donde las tareas pueden soltarse

**SortableItem**

* Representa cada tarjeta de tarea
* Implementa el comportamiento draggable usando `useSortable`

**Card**

* Componente visual reutilizable para representar tareas

---

# ⚙️ Funcionamiento del Drag & Drop

El sistema utiliza **dnd-kit** para manejar el ciclo completo de arrastre.

Flujo:

1️⃣ Cada tarjeta usa `useSortable()`
2️⃣ Cada columna usa `useDroppable()`
3️⃣ `DndContext` controla los eventos globales
4️⃣ `onDragEnd` actualiza el estado del tablero

Ejemplo simplificado:

```javascript
const onDragEnd = (event) => {
  const { active, over } = event

  if (!over) return

  const source = active.data.current
  const destination = over.data.current

  if (source.droppableId !== destination.droppableId) {
    // mover tarea entre columnas
  }
}
```

Este enfoque permite construir **interfaces drag & drop altamente personalizables**.

---

# 🎨 Sistema de estilos

El proyecto utiliza **SCSS con metodología BEM** para mantener una arquitectura de estilos clara y escalable.

Ejemplo:

```
kanban
kanban__section
kanban__section__title
kanban__section__content
```

Esto facilita:

* mantenimiento del código
* escalabilidad
* reutilización de componentes

---

# 📦 Instalación

Clonar el repositorio:

```
git clone https://github.com/JBedoyaSalazar/react-kanban-dnd.git
```

Entrar al proyecto:

```
cd react-kanban-dnd
```

Instalar dependencias:

```
npm install
```

---

# ▶️ Ejecutar el proyecto

Iniciar el servidor de desarrollo:

```
npm run dev
```

o

```
npm start
```

Abrir en el navegador:

```
http://localhost:3000
```

---

# 🔮 Roadmap de mejoras

Futuras funcionalidades que podrían agregarse:

* Crear nuevas tareas
* Eliminar tareas
* Editar contenido de las tarjetas
* Persistencia con LocalStorage o Base de datos
* Animaciones avanzadas de Drag & Drop
* Backend API (Node.js / Express)
* Autenticación de usuarios
* Sincronización en tiempo real

---

# 📚 Aprendizajes del proyecto

Durante el desarrollo se exploraron conceptos clave como:

* arquitectura de componentes en React
* implementación moderna de drag & drop
* manipulación dinámica de estado
* patrones de organización de estilos con SCSS
* manejo de estructuras de datos para interfaces interactivas

---

# 🤝 Contribuciones

Las contribuciones son bienvenidas.

Si deseas mejorar el proyecto:

1. Haz un fork
2. Crea una nueva rama
3. Realiza tus cambios
4. Envía un Pull Request

---

# 📄 Licencia

Este proyecto está bajo la licencia MIT.

---

# 👨‍💻 Autor

**Jefred Bedoya**

Estudiante de Ingeniería de Software interesado en el desarrollo de sistemas escalables, arquitectura de software y tecnologías modernas de frontend.

GitHub:
https://github.com/JBedoyaSalazar
