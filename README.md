# 🎫 Clon de eTicket - Proyecto de Práctica con React y Firebase

## 📝 Descripción General
Este proyecto tiene como objetivo replicar el diseño básico de [eticket.co](https://www.eticket.co) utilizando React y Firebase. Se implementará una estructura de carpetas profesional (frontend/backend) y operaciones CRUD básicas en Firestore.

## 🛠️ Tecnologías Utilizadas
- **Frontend:** React + Vite
- **Backend:** Firebase (Firestore + Hosting)
- **Control de Versiones:** Git y GitHub
- **Node.js:** v16+ recomendada
- **Concurrently:** Para ejecutar frontend y backend simultáneamente

## ✨ Características a Implementar

### 🔷 Frontend (React)
- Barra de navegación
- Carrusel/banner principal
- Sección de eventos
- Pie de página
- Diseño responsivo
- Panel de administración (CRUD eventos)
- Estados de carga y manejo de errores

### 🔶 Backend (Firebase)
- Conexión a Firestore
- Colección `eventos` con operaciones CRUD:
  - **C**rear: Agregar eventos nuevos
  - **R**ead: Mostrar listado de eventos
  - **U**pdate: Modificar eventos existentes
  - **D**elete: Eliminar eventos
- Despliegue en Firebase Hosting

## 📁 Estructura de Carpetas
```
Replica-eTicket-Prueba/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── atoms/      # Botones, inputs, etc
│   │   │   ├── molecules/  # Cards, formularios
│   │   │   └── organisms/  # Navbar, EventList
│   │   ├── pages/
│   │   ├── firebase/
│   │   ├── App.jsx
│   │   └── main.jsx
│   └── vite.config.js
├── backend/
├── .env
└── package.json
```

## 🚀 Instalación y Configuración

### 1. Clonar e Instalar Dependencias
```bash
git clone git@github.com:MiguelLoaizaDev/Replica-eTicket-Prueba.git
cd Replica-eTicket-Prueba
npm install
cd frontend
npm install
```

### 2. Configuración de Firebase
1. Ve a [Firebase Console](https://console.firebase.google.com)
2. Crea un nuevo proyecto
3. Configura Firestore:
   ```javascript
   // frontend/src/firebase/firebaseConfig.js
   import { initializeApp } from "firebase/app";
   import { getFirestore } from "firebase/firestore";

   const firebaseConfig = {
     apiKey: import.meta.env.VITE_FIREBASE_API_KEY,
     authDomain: import.meta.env.VITE_FIREBASE_AUTH_DOMAIN,
     projectId: import.meta.env.VITE_FIREBASE_PROJECT_ID,
     storageBucket: import.meta.env.VITE_FIREBASE_STORAGE_BUCKET,
     messagingSenderId: import.meta.env.VITE_FIREBASE_MESSAGING_SENDER_ID,
     appId: import.meta.env.VITE_FIREBASE_APP_ID
   };

   const app = initializeApp(firebaseConfig);
   const db = getFirestore(app);

   export { db };
   ```

### 3. Configuración de Eventos CRUD
```javascript
// frontend/src/firebase/eventosService.js
import { collection, addDoc, getDocs, updateDoc, deleteDoc, doc } from 'firebase/firestore';
import { db } from './firebaseConfig';

// Crear evento
export const crearEvento = async (eventoData) => {
  try {
    const docRef = await addDoc(collection(db, "eventos"), eventoData);
    return docRef.id;
  } catch (error) {
    console.error("Error al crear evento:", error);
    throw error;
  }
};

// Obtener eventos
export const obtenerEventos = async () => {
  const querySnapshot = await getDocs(collection(db, "eventos"));
  return querySnapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  }));
};
```

### 4. Desarrollo
```bash
# Desde la raíz del proyecto
npm run dev
```

### 5. Despliegue
```bash
cd frontend
firebase login
firebase init
npm run build
firebase deploy
```

## ✅ Entregables y Criterios
- [ ] Página principal con eventos desde Firestore
- [ ] Panel de administración CRUD funcional
- [ ] Estructura frontend/backend implementada
- [ ] Despliegue en Firebase Hosting
- [ ] Manejo de estados de carga y errores
- [ ] Diseño atómico implementado

## 💡 Buenas Prácticas
- Usar Atomic Design para componentes
- Implementar estructura de archivos ordenada
- Manejar estados de carga y errores
- Modularizar servicios de Firebase
- Usar variables de entorno
- Documentar funciones principales

## ⏰ Tiempo Estimado
- **Duración:** 5 días
- **Prioridades:**
  1. Configuración inicial y estructura
  2. Lectura de eventos (READ)
  3. Operaciones CRUD restantes
  4. Mejoras de UI/UX
  5. Despliegue final
