src/
├── assets/                # Imágenes, fuentes, íconos, animaciones Lottie
├── config/                # Configs globales (temas, constantes, navegación)
├── navigation/            # Stack/tab navigators centralizados
├── domain/                # Lógica pura y tipos (entidades, interfaces)
│   └── task/
│       ├── TaskEntity.ts
│       ├── TaskStatus.ts
│       └── useCases/
│           ├── createTask.ts
│           ├── updateTask.ts
│           └── ...
├── infrastructure/        # API, Firebase, almacenamiento local
│   ├── api/               # Funciones de acceso a la API (REST/GraphQL)
│   ├── firebase/          # auth, firestore, notificaciones
│   ├── localStorage/      # AsyncStorage, Realm o MMKV
│   └── repositories/      # Adaptadores a la interfaz del dominio
├── application/           # Lógica de negocio que conecta UI ↔ dominio
│   ├── stores/            # Zustand o Redux slices (app-wide state)
│   ├── services/          # Casos de uso orquestados (con lógica de UI)
│   └── hooks/             # Custom hooks (useTasks, useAuth, useNotifications)
├── presentation/          # Componentes y pantallas
│   ├── screens/
│   │   ├── LoginScreen.tsx
│   │   ├── TaskBoardScreen.tsx
│   │   └── TaskDetailScreen.tsx
│   ├── components/        # Reutilizables (Botones, Cards, Modales)
│   └── ui/                # Base visual (Text, Input, Loader, etc.)
├── types/                 # Tipado global y DTOs
├── utils/                 # Funciones auxiliares
└── App.tsx                # Entry point
