# Desglose de Tareas por User Story - Kanban App

## 🚀 ETAPA 0: Setup del Proyecto (Pre-desarrollo)

### T000 - Configuración del Entorno de Desarrollo

**Duración:** 1 día  
**Responsable:** Tech Lead

**Tareas:**

- [x] Instalar Node.js (versión LTS)
- [x] Instalar React Native CLI
- [x] Configurar Android Studio
- [x] Crear proyecto React Native: `npx react-native init KanbanApp`
- [x] Configurar estructura de carpetas
- [ ] Setup inicial de Git y .gitignore

**Entregables:**

- Proyecto React Native ejecutándose en emulador
- Repositorio Git configurado

---

### T001 - Configuración de Dependencias Base

**Duración:** 1 día  
**Responsable:** Tech Lead

**Tareas:**

- [ ] Instalar React Navigation: `npm install @react-navigation/native`
- [ ] Instalar Stack Navigator: `npm install @react-navigation/stack`
- [ ] Instalar Zustand: `npm install zustand`
- [ ] Instalar React Hook Form: `npm install react-hook-form`
- [ ] Instalar AsyncStorage: `npm install @react-native-async-storage/async-storage`
- [ ] Configurar ESLint y Prettier
- [ ] Setup TypeScript (si no está configurado)

**Entregables:**

- package.json con todas las dependencias
- Configuración de linting y formateo

---

### T002 - Configuración Firebase

**Duración:** 0.5 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Crear proyecto en Firebase Console
- [ ] Configurar Authentication (Email/Password)
- [ ] Configurar Firestore Database
- [ ] Configurar Cloud Messaging (FCM)
- [ ] Instalar Firebase SDK: `npm install @react-native-firebase/app`
- [ ] Instalar módulos: auth, firestore, messaging
- [ ] Configurar google-services.json / GoogleService-Info.plist

**Entregables:**

- Firebase proyecto configurado
- Credenciales y configuración lista

---

### T003 - Estructura de Proyecto y Arquitectura

**Duración:** 0.5 días  
**Responsable:** Tech Lead

**Tareas:**

- [ ] Crear estructura de carpetas:
  ```
  src/
  ├── components/
  ├── screens/
  ├── navigation/
  ├── store/
  ├── services/
  ├── utils/
  ├── types/
  └── constants/
  ```
- [ ] Configurar absolute imports
- [ ] Crear tipos TypeScript base
- [ ] Setup de constants (colors, sizes, etc.)

**Entregables:**

- Estructura de proyecto organizada
- Tipos y constantes base

---

## 📱 ÉPICA 1: Autenticación y Gestión de Usuario

### US001 - Registro de Usuario

#### T004 - Diseño UI Registro

**Duración:** 1 día  
**Responsable:** UI/UX Developer

**Tareas:**

- [ ] Crear wireframe de pantalla de registro
- [ ] Diseñar componentes:
  - [ ] TextInput personalizado
  - [ ] Button personalizado
  - [ ] Logo/Header
- [ ] Definir colores y tipografías
- [ ] Crear mockup en Figma/Sketch

**Entregables:**

- Mockups de pantalla de registro
- Componentes UI documentados

#### T005 - Implementar Formulario de Registro

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear screen `RegisterScreen.tsx`
- [ ] Implementar componente `CustomTextInput`
- [ ] Implementar componente `CustomButton`
- [ ] Setup React Hook Form para validaciones
- [ ] Implementar validaciones:
  - [ ] Email formato válido
  - [ ] Contraseña mínimo 8 caracteres
  - [ ] Confirmación de contraseña
- [ ] Manejo de estados (loading, error, success)

**Entregables:**

- RegisterScreen funcional con validaciones
- Componentes reutilizables

#### T006 - Integración Firebase Auth - Registro

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Crear service `authService.ts`
- [ ] Implementar función `createUserWithEmailAndPassword`
- [ ] Manejo de errores Firebase:
  - [ ] Email ya existe
  - [ ] Contraseña débil
  - [ ] Network errors
- [ ] Configurar Zustand store para auth
- [ ] Testing de integración

**Entregables:**

- Servicio de autenticación
- Store de estado global
- Manejo de errores

#### T007 - Estados de Carga y Feedback

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Implementar loading spinner
- [ ] Toast/Alert para success
- [ ] Toast/Alert para errores
- [ ] Deshabilitar botón durante carga
- [ ] Animación de transición post-registro

**Entregables:**

- UX completa de registro
- Feedback visual para todos los estados

---

### US002 - Inicio de Sesión

#### T008 - Diseño UI Login

**Duración:** 0.5 días  
**Responsable:** UI/UX Developer

**Tareas:**

- [ ] Diseñar pantalla de login
- [ ] Reutilizar componentes de registro
- [ ] Diseñar "Forgot Password" link
- [ ] Diseñar toggle "Remember me"

**Entregables:**

- Mockup de pantalla login
- Especificaciones de componentes

#### T009 - Implementar Pantalla Login

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `LoginScreen.tsx`
- [ ] Implementar formulario con React Hook Form
- [ ] Validaciones básicas (email, password required)
- [ ] Toggle "Remember me"
- [ ] Navegación a Register y ForgotPassword

**Entregables:**

- LoginScreen con validaciones
- Navegación entre pantallas

#### T010 - Integración Firebase Auth - Login

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `signInWithEmailAndPassword`
- [ ] Manejo de errores específicos:
  - [ ] Usuario no encontrado
  - [ ] Contraseña incorrecta
  - [ ] Demasiados intentos
- [ ] Persistencia de sesión con AsyncStorage
- [ ] Auto-login en app restart

**Entregables:**

- Login funcional
- Persistencia de sesión
- Manejo robusto de errores

#### T011 - Implementar Logout

**Duración:** 0.5 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar función `signOut`
- [ ] Limpiar AsyncStorage
- [ ] Reset de Zustand store
- [ ] Navegación a LoginScreen
- [ ] Confirmación de logout

**Entregables:**

- Logout funcional
- Limpieza completa de sesión

---

### US003 - Recuperación de Contraseña

#### T012 - Pantalla Forgot Password

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `ForgotPasswordScreen.tsx`
- [ ] Formulario con email input
- [ ] Validación de email
- [ ] Estados: idle, loading, sent, error
- [ ] Mensaje de confirmación

**Entregables:**

- Pantalla de recuperación
- UX completa

#### T013 - Integración Password Reset

**Duración:** 0.5 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `sendPasswordResetEmail`
- [ ] Manejo de errores (email no existe, etc.)
- [ ] Testing del flujo completo

**Entregables:**

- Reset de contraseña funcional
- Email enviado correctamente

---

## 📋 ÉPICA 2: Gestión Básica de Tareas (CRUD)

### US004 - Crear Tarea

#### T014 - Modelo de Datos Tarea

**Duración:** 0.5 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Definir interface `Task` en TypeScript:
  ```typescript
  interface Task {
    id: string;
    title: string;
    description: string;
    status: 'todo' | 'in_progress' | 'done';
    priority: 'low' | 'medium' | 'high';
    dueDate: Date;
    createdAt: Date;
    updatedAt: Date;
    userId: string;
  }
  ```
- [ ] Configurar Firestore collection `tasks`
- [ ] Definir índices en Firestore
- [ ] Crear Zustand store para tasks

**Entregables:**

- Modelo de datos definido
- Store configurado

#### T015 - Diseño UI Crear Tarea

**Duración:** 1 día  
**Responsable:** UI/UX Developer

**Tareas:**

- [ ] Diseñar modal/screen de crear tarea
- [ ] Componentes:
  - [ ] Title input
  - [ ] Description textarea
  - [ ] Date picker
  - [ ] Priority selector (dropdown/segmented control)
- [ ] Diseño responsive
- [ ] Estados de validación

**Entregables:**

- Mockups de crear tarea
- Especificaciones de componentes

#### T016 - Implementar Formulario Crear Tarea

**Duración:** 2 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `CreateTaskScreen.tsx` o Modal
- [ ] Implementar componentes:
  - [ ] `TaskTitleInput`
  - [ ] `TaskDescriptionInput`
  - [ ] `DatePicker` component
  - [ ] `PrioritySelector` component
- [ ] Validaciones con React Hook Form:
  - [ ] Título requerido (max 100 chars)
  - [ ] Descripción opcional (max 500 chars)
  - [ ] Fecha no puede ser pasada
- [ ] Estados de carga y error

**Entregables:**

- Formulario completo
- Validaciones implementadas

#### T017 - Integración Firestore - Crear Tarea

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Crear `taskService.ts`
- [ ] Implementar `createTask` función
- [ ] Validación server-side
- [ ] Optimistic updates en store
- [ ] Manejo de errores de red
- [ ] Testing unitario

**Entregables:**

- Servicio de tareas
- Creación funcionando
- Tests unitarios

#### T018 - Feedback Visual Crear Tarea

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Toast de confirmación
- [ ] Animación de creación
- [ ] Loading states
- [ ] Auto-dismiss modal/navigate back
- [ ] Limpiar formulario tras crear

**Entregables:**

- UX pulida de creación
- Feedback completo

---

### US005 - Ver Lista de Tareas

#### T019 - Diseño Kanban Board

**Duración:** 1.5 días  
**Responsable:** UI/UX Developer

**Tareas:**

- [ ] Diseñar layout de 3 columnas
- [ ] Diseño de Task Card:
  - [ ] Título
  - [ ] Descripción truncada
  - [ ] Fecha límite
  - [ ] Indicador de prioridad
  - [ ] Estado visual
- [ ] Header de cada columna
- [ ] Responsive design (tablet/landscape)
- [ ] Estados vacíos (empty state)

**Entregables:**

- Mockups del Kanban board
- Especificaciones de Task Card

#### T020 - Implementar Task Card Component

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `TaskCard.tsx` component
- [ ] Props interface para Task data
- [ ] Rendering condicional según prioridad
- [ ] Formateo de fechas
- [ ] Truncado de descripción
- [ ] Indicadores visuales (overdue, due today, etc.)
- [ ] Touch handling (tap para editar)

**Entregables:**

- TaskCard component reutilizable
- Todas las variantes visuales

#### T021 - Implementar Kanban Layout

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `KanbanScreen.tsx`
- [ ] Layout horizontal con ScrollView
- [ ] Tres columnas: Todo, In Progress, Done
- [ ] Headers de columnas con contadores
- [ ] FlatList/ScrollView para cada columna
- [ ] Optimización de performance (VirtualizedList)
- [ ] Pull-to-refresh

**Entregables:**

- Kanban board funcional
- Performance optimizada

#### T022 - Integración Firestore - Leer Tareas

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `getTasks` con filtros por usuario
- [ ] Real-time listener con `onSnapshot`
- [ ] Ordenamiento por prioridad y fecha
- [ ] Paginación (si es necesario)
- [ ] Manejo de estados: loading, error, empty
- [ ] Cache con AsyncStorage para offline

**Entregables:**

- Servicio de lectura de tareas
- Real-time updates
- Cache offline

#### T023 - Estados de Carga y Error

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Loading skeleton para cards
- [ ] Error state con retry button
- [ ] Empty state con CTA para crear primera tarea
- [ ] Pull-to-refresh indicator
- [ ] Shimmer loading effects

**Entregables:**

- Estados completos del Kanban
- UX pulida

---

### US006 - Editar Tarea

#### T024 - Pantalla/Modal Editar Tarea

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `EditTaskScreen.tsx` o Modal
- [ ] Reutilizar componentes de crear tarea
- [ ] Pre-llenar formulario con datos existentes
- [ ] Validaciones idénticas a crear
- [ ] Botón "Cancelar" con confirmación si hay cambios
- [ ] Auto-save o save manual

**Entregables:**

- Pantalla de edición
- Formulario pre-llenado

#### T025 - Integración Firestore - Actualizar Tarea

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `updateTask` función
- [ ] Validación de permisos (userId)
- [ ] Actualización de `updatedAt` timestamp
- [ ] Optimistic updates
- [ ] Manejo de conflictos (si otro usuario editó)
- [ ] Testing

**Entregables:**

- Actualización funcionando
- Manejo de conflictos

#### T026 - UX de Edición

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Transición suave a edición
- [ ] Indicador de cambios no guardados
- [ ] Confirmación antes de descartar cambios
- [ ] Toast de confirmación al guardar
- [ ] Loading states durante update

**Entregables:**

- UX completa de edición
- Prevención de pérdida de datos

---

### US007 - Eliminar Tarea

#### T027 - Implementar Swipe to Delete

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Añadir swipe gesture a TaskCard
- [ ] Biblioteca: `react-native-swipe-list-view` o custom
- [ ] Animación de swipe reveal
- [ ] Botón de eliminar revealed
- [ ] Colores de feedback (rojo para delete)

**Entregables:**

- Swipe to delete funcional
- Animaciones suaves

#### T028 - Confirmación y Undo

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Modal de confirmación con detalles de tarea
- [ ] Botones: "Cancelar" y "Eliminar"
- [ ] Implementar Undo toast (5 segundos)
- [ ] Queue de eliminaciones pendientes
- [ ] Cancel undo si usuario quiere
- [ ] Animación de eliminación

**Entregables:**

- Confirmación y undo completos
- UX segura para eliminar

#### T029 - Integración Firestore - Eliminar Tarea

**Duración:** 0.5 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `deleteTask` función
- [ ] Soft delete vs hard delete (decidir)
- [ ] Validación de permisos
- [ ] Optimistic delete con rollback
- [ ] Testing

**Entregables:**

- Eliminación funcionando
- Rollback en caso de error

---

## 🔄 ÉPICA 3: Gestión de Estados y Flujo Kanban

### US008 - Cambiar Estado de Tarea (Drag & Drop)

#### T030 - Investigación Drag & Drop

**Duración:** 0.5 días  
**Responsable:** Tech Lead

**Tareas:**

- [ ] Evaluar bibliotecas:
  - [ ] `react-native-draggable-flatlist`
  - [ ] `react-native-dnd-board`
  - [ ] Custom implementation con PanGestureHandler
- [ ] Proof of concept
- [ ] Decisión técnica documentada

**Entregables:**

- Decisión de biblioteca
- POC funcional

#### T031 - Implementar Drag & Drop Básico

**Duración:** 2 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Integrar biblioteca elegida
- [ ] Hacer TaskCard draggable
- [ ] Configurar drop zones (columnas)
- [ ] Feedback visual durante drag:
  - [ ] Shadow/elevation en card
  - [ ] Placeholder en posición original
  - [ ] Highlight en drop zone válido
- [ ] Validaciones de drop (no drop en misma posición)

**Entregables:**

- Drag & drop funcional
- Feedback visual completo

#### T032 - Animaciones de Drag & Drop

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Animación smooth de drag start
- [ ] Animación de hover sobre drop zones
- [ ] Animación de drop exitoso
- [ ] Animación de revert si drop inválido
- [ ] Spring animations con React Native Reanimated
- [ ] Performance optimization

**Entregables:**

- Animaciones pulidas
- Performance optimizada

#### T033 - Integración Backend - Cambio Estado

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `updateTaskStatus` función
- [ ] Validaciones de estado válido
- [ ] Optimistic updates inmediatos
- [ ] Rollback en caso de error de red
- [ ] Batch updates si múltiples cambios
- [ ] Testing de estados de red

**Entregables:**

- Cambio de estado confiable
- Manejo robusto de errores

---

### US009 - Progreso Visual del Proyecto

#### T034 - Diseño Dashboard de Progreso

**Duración:** 1 día  
**Responsable:** UI/UX Developer

**Tareas:**

- [ ] Diseñar header con métricas:
  - [ ] Progress bar circular
  - [ ] Números: total, completadas, pendientes
  - [ ] Breakdown por prioridad
- [ ] Diseño de gráficos:
  - [ ] Pie chart de distribución
  - [ ] Bar chart de progreso por día/semana
- [ ] Filtros temporales (hoy, semana, mes)

**Entregables:**

- Mockups de dashboard
- Especificaciones de gráficos

#### T035 - Implementar Métricas y Cálculos

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `StatsService.ts` para cálculos
- [ ] Implementar métricas:
  - [ ] Porcentaje completado
  - [ ] Total por estado
  - [ ] Distribución por prioridad
  - [ ] Tareas overdue
  - [ ] Productividad (tareas/día)
- [ ] Filtros por fecha
- [ ] Optimización de performance (memoization)

**Entregables:**

- Servicio de estadísticas
- Cálculos optimizados

#### T036 - Componentes de Visualización

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Implementar `ProgressCircle` component
- [ ] Implementar `StatsCard` component
- [ ] Biblioteca de gráficos: `react-native-chart-kit`
- [ ] Pie chart para distribución
- [ ] Bar chart para progreso temporal
- [ ] Animaciones de entrada
- [ ] Responsive design

**Entregables:**

- Componentes de visualización
- Gráficos animados

#### T037 - Dashboard Header Integration

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Integrar dashboard en KanbanScreen header
- [ ] Real-time updates de métricas
- [ ] Collapse/expand del dashboard
- [ ] Transiciones suaves
- [ ] Performance optimization

**Entregables:**

- Dashboard integrado
- Updates en tiempo real

---

## 💾 ÉPICA 4: Funcionalidades Offline y Sincronización

### US010 - Uso Offline

#### T038 - Configuración AsyncStorage Structure

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Diseñar estructura de datos offline:
  ```typescript
  interface OfflineStorage {
    tasks: Task[];
    pendingActions: PendingAction[];
    lastSync: number;
    user: User;
  }
  ```
- [ ] Implementar `OfflineService.ts`
- [ ] Funciones CRUD para AsyncStorage
- [ ] Encriptación de datos sensibles
- [ ] Testing de persistencia

**Entregables:**

- Servicio de almacenamiento offline
- Estructura de datos definida

#### T039 - Queue de Acciones Offline

**Duración:** 2 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `ActionQueue.ts`:
  - [ ] Queue para create, update, delete
  - [ ] Timestamp y retry logic
  - [ ] Conflict resolution strategy
- [ ] Tipos de acciones:
  ```typescript
  interface PendingAction {
    id: string;
    type: 'create' | 'update' | 'delete';
    data: any;
    timestamp: number;
    retries: number;
  }
  ```
- [ ] Manejo de dependencias entre acciones
- [ ] Testing de queue operations

**Entregables:**

- Queue de acciones offline
- Conflict resolution

#### T040 - Network Detection

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Instalar `@react-native-netinfo/netinfo`
- [ ] Crear `NetworkService.ts`
- [ ] Hook para status de conexión
- [ ] Indicador visual en UI
- [ ] Listener para cambios de conectividad

**Entregables:**

- Detección de red
- Indicadores visuales

#### T041 - Sync Strategy Implementation

**Duración:** 2 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar `SyncService.ts`:
  - [ ] Full sync on app start
  - [ ] Incremental sync en background
  - [ ] Batch sync de pending actions
- [ ] Conflict resolution:
  - [ ] Last write wins
  - [ ] Server priority para conflictos
- [ ] Retry logic con exponential backoff
- [ ] Error handling y logging

**Entregables:**

- Servicio de sincronización
- Estrategia de conflictos

#### T042 - UI States para Offline

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Indicadores offline en TaskCard
- [ ] Toast notifications para acciones offline
- [ ] Progress indicator durante sync
- [ ] Error states para sync failures
- [ ] Manual sync button
- [ ] Pending actions counter

**Entregables:**

- UI completa para offline
- Feedback visual claro

---

### US011 - Sincronización en Tiempo Real

#### T043 - WebSocket/Firebase Realtime Setup

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Configurar Firebase Realtime listeners
- [ ] Implementar `RealtimeService.ts`
- [ ] Listeners para changes en tasks collection
- [ ] Debouncing para múltiples updates
- [ ] Connection state management
- [ ] Cleanup de listeners

**Entregables:**

- Real-time listeners configurados
- Connection management

#### T044 - Optimistic Updates

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Implementar optimistic updates en store
- [ ] Rollback mechanism para failed updates
- [ ] Visual feedback para pending updates
- [ ] Queue de optimistic actions
- [ ] Testing de scenarios de fallo

**Entregables:**

- Optimistic updates funcionando
- Rollback confiable

#### T045 - Conflict Resolution UI

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Modal para conflictos detectados
- [ ] Side-by-side comparison de cambios
- [ ] Opciones: "Keep Local", "Accept Remote", "Merge"
- [ ] Auto-resolution para cambios simples
- [ ] History de resoluciones

**Entregables:**

- UI para resolver conflictos
- Auto-resolution inteligente

#### T046 - Background Sync

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Implementar background tasks
- [ ] Sync cuando app vuelve a foreground
- [ ] Periodic sync en background (iOS/Android differences)
- [ ] Battery optimization considerations
- [ ] Sync status persistence

**Entregables:**

- Background sync funcionando
- Optimización de batería

---

## 📱 ÉPICA 5: Notificaciones y Recordatorios

### US012 - Notificaciones Push de Tareas Pendientes

#### T047 - Firebase Cloud Messaging Setup

**Duración:** 1 día  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Configurar FCM en Firebase Console
- [ ] Setup server key y certificados
- [ ] Instalar `@react-native-firebase/messaging`
- [ ] Request permissions (iOS/Android)
- [ ] Token registration y refresh
- [ ] Testing de push notifications

**Entregables:**

- FCM completamente configurado
- Tokens registrándose correctamente

#### T048 - Notification Scheduling System

**Duración:** 2 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Crear sistema de scheduling:
  - [ ] Notificaciones de fecha límite (1 día antes, día de)
  - [ ] Notificaciones de tareas overdue
  - [ ] Resumen diario de tareas pendientes
- [ ] Implementar cron jobs o Firebase Functions
- [ ] Database para tracking notifications sent
- [ ] Prevent duplicate notifications
- [ ] Testing de scheduling

**Entregables:**

- Sistema de scheduling
- Prevención de duplicados

#### T049 - User Notification Preferences

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `NotificationSettingsScreen.tsx`
- [ ] Toggles para tipos de notificaciones:
  - [ ] Due date reminders
  - [ ] Overdue tasks
  - [ ] Daily summary
  - [ ] Time selection para daily summary
- [ ] Persistence en Firestore
- [ ] Sync con backend scheduling

**Entregables:**

- Pantalla de configuración
- Preferencias persistentes

#### T050 - Notification Handling

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Handler para notifications en foreground
- [ ] Navigation desde notification tap
- [ ] Badge count management
- [ ] Deep linking a tareas específicas
- [ ] Notification history (opcional)

**Entregables:**

- Manejo completo de notifications
- Deep linking funcionando

---

### US013 - Notificaciones In-App

#### T051 - Toast Notification System

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `ToastService.ts` global
- [ ] Componente `Toast.tsx` customizable
- [ ] Tipos: success, error, warning, info
- [ ] Queue de toasts múltiples
- [ ] Auto-dismiss con timers
- [ ] Manual dismiss
- [ ] Positioning y animations

**Entregables:**

- Sistema de toasts completo
- Animations suaves

#### T052 - Badge Indicators

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Badge component para TaskCard
- [ ] Badges para:
  - [ ] Overdue tasks (rojo)
  - [ ] Due today (amarillo)
  - [ ] High priority (naranja)
- [ ] Dynamic badge colors
- [ ] Positioning y sizing

**Entregables:**

- Sistema de badges
- Indicadores visuales claros

#### T053 - Activity Feed (Opcional)

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `ActivityScreen.tsx`
- [ ] Log de actividades:
  - [ ] Task created/updated/completed
  - [ ] Notifications sent
  - [ ] Sync events
- [ ] Timeline UI component
- [ ] Persistence en AsyncStorage
- [ ] Clear activity history

**Entregables:**

- Activity feed funcional
- Timeline UI

---

## 🎨 ÉPICA 6: Experiencia de Usuario Avanzada

### US014 - Búsqueda y Filtros

#### T054 - Search Bar Component

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `SearchBar.tsx` component
- [ ] Search input con debouncing
- [ ] Clear search button
- [ ] Search suggestions (opcional)
- [ ] Keyboard handling
- [ ] Integration con KanbanScreen

**Entregables:**

- SearchBar component
- Debouncing implementado

#### T055 - Search & Filter Logic

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Implementar search en `TaskService.ts`:
  - [ ] Search por título
  - [ ] Search por descripción
  - [ ] Case-insensitive
  - [ ] Highlight de matches
- [ ] Filtros implementados:
  - [ ] By status
  - [ ] By priority
  - [ ] By date range
  - [ ] By overdue status
- [ ] Combine search + filters
- [ ] Performance optimization

**Entregables:**

- Search y filtros funcionando
- Performance optimizada

#### T056 - Filter UI Components

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `FilterModal.tsx`
- [ ] Filter chips para active filters
- [ ] Multi-select para filtros
- [ ] Date range picker
- [ ] Clear all filters button
- [ ] Save/preset filters (opcional)

**Entregables:**

- UI de filtros completa
- Filter management

#### T057 - Search Results UI

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Results counter
- [ ] Highlight search terms en TaskCard
- [ ] Empty search results state
- [ ] Clear search from results
- [ ] Performance para large datasets

**Entregables:**

- UI de resultados pulida
- Performance optimizada

---

### US015 - Temas y Personalización

#### T058 - Theme System Architecture

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `ThemeContext.tsx`
- [ ] Define theme interfaces:
  ```typescript
  interface Theme {
    colors: ColorPalette;
    typography: Typography;
    spacing: Spacing;
    shadows: Shadows;
  }
  ```
- [ ] Light y Dark theme definitions
- [ ] Theme switching logic
- [ ] Persistence en AsyncStorage

**Entregables:**

- Sistema de temas base
- Light/Dark themes

#### T059 - Color Customization

**Duración:** 1.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Crear `CustomizationScreen.tsx`
- [ ] Color picker para priority colors
- [ ] Preview de cambios en tiempo real
- [ ] Reset to defaults option
- [ ] Export/Import theme settings
- [ ] Validation de contrast ratios

**Entregables:**

- Customización de colores
- Theme preview

#### T060 - Theme Application

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Aplicar themes a todos los componentes
- [ ] Update de styled-components o theme usage
- [ ] Status bar styling por theme
- [ ] Icon theming
- [ ] Testing en ambos themes

**Entregables:**

- Theming completo en app
- Consistency across screens

#### T061 - Theme Transitions

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Smooth transition animations
- [ ] Fade/slide effects para theme change
- [ ] Prevent flashing durante switch
- [ ] Performance optimization

**Entregables:**

- Transiciones suaves
- UX pulida

---

### US016 - Animaciones y Micro-interacciones

#### T062 - Animation Library Setup

**Duración:** 0.5 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Install React Native Reanimated v3
- [ ] Install Lottie React Native
- [ ] Configure libraries
- [ ] Create animation utils
- [ ] Performance testing

**Entregables:**

- Animation libraries configuradas
- Utils para animaciones

#### T063 - Lottie Animations

**Duración:** 1 día  
**Responsable:** UI/UX Developer + Frontend Developer

**Tareas:**

- [ ] Crear/encontrar Lottie animations:
  - [ ] Loading spinner
  - [ ] Success checkmark
  - [ ] Error animation
  - [ ] Empty state illustration
  - [ ] Celebration para task completion
- [ ] Integrate en componentes
- [ ] Optimize file sizes

**Entregables:**

- Lottie animations integradas
- Tamaños optimizados

#### T064 - Micro-interactions

**Duración:** 2 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Button press feedback (scale, opacity)
- [ ] TaskCard tap animations
- [ ] Swipe gesture feedback
- [ ] Input focus animations
- [ ] Page transition animations
- [ ] Tab switching animations
- [ ] Pull-to-refresh animation

**Entregables:**

- Micro-interactions completas
- Feel responsive en toda la app

#### T065 - Performance Optimization

**Duración:** 1 día  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Profile animation performance
- [ ] Optimize heavy animations
- [ ] Reduce jank en scrolling
- [ ] Memory leak prevention
- [ ] FPS monitoring durante development

**Entregables:**

- Performance optimizada
- Smooth 60fps experience

---

## 🤝 ÉPICA 7: Colaboración (Futuro)

### US017 - Compartir Tableros

#### T066 - Multi-tenancy Data Model

**Duración:** 2 días  
**Responsable:** Backend Developer

**Tareas:**

- [ ] Extend data model para shared boards:
  ```typescript
  interface Board {
    id: string;
    name: string;
    ownerId: string;
    members: BoardMember[];
    tasks: Task[];
    permissions: BoardPermissions;
  }
  ```
- [ ] Update Firestore security rules
- [ ] Migration strategy para existing tasks
- [ ] Testing de permissions

**Entregables:**

- Multi-tenant data model
- Security rules actualizadas

#### T067 - Invitation System

**Duración:** 3 días  
**Responsable:** Backend Developer + Frontend Developer

**Tareas:**

- [ ] Email invitation flow
- [ ] Invitation codes generation
- [ ] Accept/decline invitation UI
- [ ] Permission levels (view, edit, admin)
- [ ] Member management screen
- [ ] Notification de nuevos miembros

**Entregables:**

- Sistema de invitaciones completo
- Member management

#### T068 - Real-time Collaboration

**Duración:** 3 días  
**Responsable:** Backend Developer + Frontend Developer

**Tareas:**

- [ ] Real-time cursors (optional)
- [ ] Live editing indicators
- [ ] Activity feed por board
- [ ] User avatars en tasks
- [ ] Conflict resolution para multi-user editing
- [ ] Performance con múltiples usuarios

**Entregables:**

- Colaboración en tiempo real
- Multi-user experience

#### T069 - Collaboration UI

**Duración:** 2 días  
**Responsable:** Frontend Developer

**Tareas:**

- [ ] Member list component
- [ ] Permission indicators
- [ ] Share board modal
- [ ] Activity timeline
- [ ] User presence indicators
- [ ] Collaborative editing feedback

**Entregables:**

- UI colaborativa completa
- User presence system

---

## 📊 Resumen de Estimaciones

### Por Épica:

- **Etapa 0 (Setup):** 3 días
- **Épica 1 (Auth):** 8 días
- **Épica 2 (CRUD):** 12 días
- **Épica 3 (Kanban):** 8 días
- **Épica 4 (Offline):** 10 días
- **Épica 5 (Notifications):** 8 días
- **Épica 6 (UX Advanced):** 8 días
- **Épica 7 (Collaboration):** 10 días (futuro)

### Total MVP (Épicas 0-3): ~31 días

### Total Core (Épicas 4-5): ~18 días

### Total Polish (Épica 6): ~8 días

---

## 🔧 Consideraciones Técnicas

### Performance:

- Lazy loading de pantallas
- Image optimization
- Bundle size optimization
- Memory leak prevention

### Testing:

- Unit tests para services
- Integration tests para flows críticos
- E2E tests para user journeys principales
- Performance testing

### CI/CD:

- GitHub Actions setup
- Automated testing
- Code coverage
- Automated builds (iOS/Android)

### Monitoring:

- Crash reporting (Crashlytics)
- Analytics (Firebase Analytics)
- Performance monitoring
- User feedback collection

---

## 📱 Device Testing Matrix

### iOS:

- iPhone SE (small screen)
- iPhone 12/13/14 (standard)
- iPhone 12/13/14 Pro Max (large)
- iPad (tablet layout)

### Android:

- Low-end device (Android 8+)
- Mid-range device
- High-end device
- Tablet sizes

### Testing Scenarios:

- Low memory conditions
- Poor network connectivity
- Background/foreground transitions
- Notification handling
- Deep linking
