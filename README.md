# 🚀 Prueba Técnica - Clon de eTicket.co con React y Firebase

Bienvenida 👋  
Este es un reto práctico para comenzar tu integración al equipo de desarrollo. El objetivo es replicar la estructura y funcionalidad visual básica del sitio [eticket.co](https://www.eticket.co) usando **React** para el frontend y **Firebase** para el backend (base de datos y hosting).

---

## 🎯 Objetivos

- Practicar desarrollo con **React**.
- Aprender cómo integrar y usar **Firebase**:
  - Firebase Hosting
  - Firestore (Base de datos)
- Aplicar buenas prácticas de organización de archivos y componentes en React.

---

## 📋 Requisitos

### Tecnologías

- React + Vite
- Firebase (Hosting + Firestore)
- Git y GitHub
- [Node.js](https://nodejs.org/) (versión 16+ recomendada)
- Editor de código (VS Code sugerido)

---

## 🧩 Qué debe incluir el clon

> No es necesario replicar toda la funcionalidad dinámica. En esta etapa es una maqueta visual con integración básica a Firestore.

### 1. Estructura visual

- Barra de navegación superior
- Carrusel/banner principal
- Sección de eventos (puede ser estática o dinámica desde Firestore)
- Footer

### 2. Firebase

- Conectar el proyecto a Firebase
- Crear una colección en Firestore llamada `eventos`
- Mostrar los datos de `eventos` en la página principal (título, fecha, ciudad, imagen, etc.)

### 3. Hosting

- Deploy del sitio usando Firebase Hosting
- Compartir la URL al finalizar

---

## 🛠️ Instrucciones

### 1. Clona este repositorio

```bash
git clone https://github.com/TU_USUARIO/eticket-clone.git
cd eticket-clone
2. Crea el proyecto en Firebase
Ve a https://console.firebase.google.com

Crea un nuevo proyecto

Habilita Firestore Database

Habilita Firebase Hosting

3. Configura el entorno local
bash
Copiar
Editar
npm install
Crea un archivo .env en la raíz y añade las variables de tu Firebase config:

env
Copiar
Editar
VITE_FIREBASE_API_KEY=your_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=sender_id
VITE_FIREBASE_APP_ID=app_id
4. Ejecuta en local
bash
Copiar
Editar
npm run dev
5. Deploy en Firebase
bash
Copiar
Editar
npm run build
firebase login
firebase init
firebase deploy
✅ Criterios de entrega
Página funcional con estructura similar a eticket.co

Conexión con Firestore para mostrar los eventos

Deploy exitoso en Firebase Hosting

Buenas prácticas de código y organización de componentes

💡 Tips
Puedes usar componentes como <Navbar />, <EventList />, <Footer /> para estructurar tu proyecto.

Usa useEffect para obtener los datos desde Firestore.

No te compliques con funcionalidades avanzadas, enfócate en la estructura general y conexión con Firebase.

📅 Plazo sugerido
No hay límite estricto, pero se recomienda completarlo en máximo 5-7 días. ¡Tómatelo como una oportunidad de aprendizaje! 💪

🙌 ¡Éxito!
No dudes en escribir si tienes preguntas o te atoras en algo. Esto es para que aprendas y te familiarices con las herramientas que usamos día a día.

yaml
Copiar
Editar

---

¿Quieres que también le añada un ejemplo base del `firebaseConfig.js` o alguna plantilla inicial con Vite y Firebase ya c
