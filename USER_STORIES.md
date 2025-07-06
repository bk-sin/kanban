# User Stories - App de Gestión de Tareas Kanban

## Épica 1: Autenticación y Gestión de Usuario

### US001 - Registro de Usuario
**Como** nuevo usuario  
**Quiero** crear una cuenta con email y contraseña  
**Para** poder acceder a la aplicación y guardar mis tareas

**Criterios de Aceptación:**
- Debo poder ingresar email, contraseña y confirmar contraseña
- El sistema debe validar que el email tenga formato válido
- La contraseña debe tener al menos 8 caracteres
- Debo recibir confirmación visual del registro exitoso
- En caso de error, debo ver un mensaje claro

**DoD (Definition of Done):**
- Validaciones frontend implementadas
- Integración con Firebase Auth
- Manejo de errores
- Tests unitarios

**Prioridad:** Alta  
**Estimación:** 5 puntos

---

### US002 - Inicio de Sesión
**Como** usuario registrado  
**Quiero** iniciar sesión con mis credenciales  
**Para** acceder a mis tareas guardadas

**Criterios de Aceptación:**
- Debo poder ingresar email y contraseña
- El sistema debe recordar mi sesión
- Debo poder cerrar sesión
- Debo ver un indicador de carga durante la autenticación

**DoD:**
- Login funcional con Firebase
- Persistencia de sesión con JWT
- Logout implementado
- Estados de carga

**Prioridad:** Alta  
**Estimación:** 3 puntos

---

### US003 - Recuperación de Contraseña
**Como** usuario  
**Quiero** recuperar mi contraseña si la olvido  
**Para** poder volver a acceder a mi cuenta

**Criterios de Aceptación:**
- Debo poder solicitar reset con mi email
- Debo recibir un enlace por email
- El enlace debe permitirme crear nueva contraseña
- Debo recibir confirmación del cambio

**DoD:**
- Integración con Firebase Password Reset
- Validaciones de nueva contraseña
- Feedback visual al usuario

**Prioridad:** Media  
**Estimación:** 3 puntos

---

## Épica 2: Gestión Básica de Tareas (CRUD)

### US004 - Crear Tarea
**Como** usuario autenticado  
**Quiero** crear una nueva tarea  
**Para** organizar mi trabajo

**Criterios de Aceptación:**
- Debo poder ingresar título, descripción, fecha límite y prioridad
- La tarea debe crearse en estado "To-Do" por defecto
- Debo ver la tarea inmediatamente en mi tablero
- Todos los campos requeridos deben estar marcados

**DoD:**
- Formulario de creación
- Validaciones
- Persistencia en base de datos
- Sincronización con API
- Feedback visual

**Prioridad:** Alta  
**Estimación:** 5 puntos

---

### US005 - Ver Lista de Tareas
**Como** usuario  
**Quiero** ver todas mis tareas organizadas por estado  
**Para** tener una visión general de mi trabajo

**Criterios de Aceptación:**
- Debo ver tres columnas: To-Do, In Progress, Done
- Cada tarea debe mostrar título, descripción corta y fecha límite
- Las tareas deben estar ordenadas por prioridad y fecha
- Debo poder scroll en cada columna independientemente

**DoD:**
- Layout de Kanban board
- Renderizado de listas
- Ordenamiento
- UI responsive

**Prioridad:** Alta  
**Estimación:** 8 puntos

---

### US006 - Editar Tarea
**Como** usuario  
**Quiero** modificar los detalles de una tarea existente  
**Para** mantener la información actualizada

**Criterios de Aceptación:**
- Debo poder tocar una tarea para editarla
- Debo poder modificar título, descripción, fecha límite y prioridad
- Los cambios deben guardarse automáticamente
- Debo ver confirmación visual de los cambios

**DoD:**
- Modal/pantalla de edición
- Validaciones
- Auto-save o save manual
- Sincronización con backend

**Prioridad:** Alta  
**Estimación:** 5 puntos

---

### US007 - Eliminar Tarea
**Como** usuario  
**Quiero** eliminar tareas que ya no necesito  
**Para** mantener mi tablero organizado

**Criterios de Aceptación:**
- Debo poder eliminar una tarea con swipe o botón
- Debo recibir confirmación antes de eliminar
- La tarea debe desaparecer inmediatamente del tablero
- Debo poder deshacer la eliminación por unos segundos

**DoD:**
- Acción de eliminar
- Confirmación modal
- Undo functionality
- Animaciones suaves

**Prioridad:** Media  
**Estimación:** 3 puntos

---

## Épica 3: Gestión de Estados y Flujo Kanban

### US008 - Cambiar Estado de Tarea (Drag & Drop)
**Como** usuario  
**Quiero** arrastrar tareas entre columnas  
**Para** actualizar su estado de manera intuitiva

**Criterios de Aceptación:**
- Debo poder arrastrar una tarea de una columna a otra
- La tarea debe cambiar de estado automáticamente
- Debo ver animaciones suaves durante el movimiento
- El cambio debe persistirse inmediatamente

**DoD:**
- Drag & drop implementation
- Animaciones fluidas
- Estado actualizado en backend
- Feedback visual

**Prioridad:** Alta  
**Estimación:** 8 puntos

---

### US009 - Progreso Visual del Proyecto
**Como** usuario  
**Quiero** ver el progreso general de mis tareas  
**Para** entender qué tan avanzado está mi trabajo

**Criterios de Aceptación:**
- Debo ver un indicador de progreso (% de tareas completadas)
- Debo ver estadísticas: total de tareas, completadas, pendientes
- Los datos deben actualizarse en tiempo real
- Debo poder ver progreso por periodo (día/semana/mes)

**DoD:**
- Dashboard con métricas
- Gráficos/barras de progreso
- Cálculos en tiempo real
- Filtros temporales

**Prioridad:** Media  
**Estimación:** 5 puntos

---

## Épica 4: Funcionalidades Offline y Sincronización

### US010 - Uso Offline
**Como** usuario  
**Quiero** usar la app sin conexión a internet  
**Para** seguir trabajando en cualquier lugar

**Criterios de Aceptación:**
- Debo poder ver mis tareas sin conexión
- Debo poder crear, editar y cambiar estado offline
- Los cambios deben guardarse localmente
- Al reconectar, todos los cambios deben sincronizarse

**DoD:**
- AsyncStorage implementation
- Queue de acciones offline
- Sincronización automática
- Indicadores de estado de conexión

**Prioridad:** Alta  
**Estimación:** 13 puntos

---

### US011 - Sincronización en Tiempo Real
**Como** usuario con múltiples dispositivos  
**Quiero** que mis cambios se reflejen en todos mis dispositivos  
**Para** mantener consistencia en mi trabajo

**Criterios de Aceptación:**
- Los cambios deben sincronizarse automáticamente
- Debo ver actualizaciones en tiempo real
- Los conflictos deben resolverse automáticamente
- Debo recibir notificación de cambios remotos

**DoD:**
- WebSocket o Firebase Real-time
- Conflict resolution strategy
- Background sync
- Optimistic updates

**Prioridad:** Media  
**Estimación:** 8 puntos

---

## Épica 5: Notificaciones y Recordatorios

### US012 - Notificaciones Push de Tareas Pendientes
**Como** usuario  
**Quiero** recibir recordatorios de tareas importantes  
**Para** no olvidar completar trabajo importante

**Criterios de Aceptación:**
- Debo recibir notificaciones de tareas próximas a vencer
- Debo poder configurar cuándo recibir recordatorios
- Las notificaciones deben funcionar aunque la app esté cerrada
- Debo poder desactivar notificaciones si lo deseo

**DoD:**
- Push notifications setup (Firebase)
- Scheduling system
- Configuración de usuario
- Permissions handling

**Prioridad:** Media  
**Estimación:** 8 puntos

---

### US013 - Notificaciones In-App
**Como** usuario activo en la app  
**Quiero** recibir notificaciones dentro de la aplicación  
**Para** estar al tanto de actualizaciones importantes

**Criterios de Aceptación:**
- Debo ver badges en tareas próximas a vencer
- Debo recibir toast notifications para acciones importantes
- Las notificaciones deben ser discretas pero visibles
- Debo poder marcar notificaciones como leídas

**DoD:**
- In-app notification system
- Badge indicators
- Toast notifications
- Read/unread state

**Prioridad:** Baja  
**Estimación:** 3 puntos

---

## Épica 6: Experiencia de Usuario Avanzada

### US014 - Búsqueda y Filtros
**Como** usuario con muchas tareas  
**Quiero** buscar y filtrar mis tareas  
**Para** encontrar rápidamente lo que necesito

**Criterios de Aceptación:**
- Debo poder buscar tareas por título o descripción
- Debo poder filtrar por estado, prioridad y fecha
- Los resultados deben mostrarse en tiempo real
- Debo poder combinar múltiples filtros

**DoD:**
- Search bar implementation
- Filter components
- Real-time filtering
- Clear filters option

**Prioridad:** Media  
**Estimación:** 5 puntos

---

### US015 - Temas y Personalización
**Como** usuario  
**Quiero** personalizar la apariencia de la app  
**Para** tener una experiencia más agradable

**Criterios de Aceptación:**
- Debo poder elegir entre tema claro y oscuro
- Debo poder cambiar colores de prioridad
- Los cambios deben persistirse entre sesiones
- La transición entre temas debe ser suave

**DoD:**
- Theme system implementation
- Color customization
- Persistence
- Smooth transitions

**Prioridad:** Baja  
**Estimación:** 5 puntos

---

### US016 - Animaciones y Micro-interacciones
**Como** usuario  
**Quiero** una interfaz fluida y responsive  
**Para** tener una experiencia de uso agradable

**Criterios de Aceptación:**
- Las transiciones entre pantallas deben ser suaves
- Los botones deben tener feedback visual al tocarlos
- Las acciones de carga deben tener indicadores animados
- Las animaciones no deben afectar el rendimiento

**DoD:**
- Lottie animations
- Gesture feedback
- Loading states
- Performance optimization

**Prioridad:** Media  
**Estimación:** 8 puntos

---

## Épica 7: Colaboración (Futuro)

### US017 - Compartir Tableros
**Como** usuario  
**Quiero** compartir mis tableros con otros usuarios  
**Para** colaborar en proyectos

**Criterios de Aceptación:**
- Debo poder invitar usuarios por email
- Los usuarios invitados deben poder ver y editar tareas
- Debo poder controlar permisos (ver/editar)
- Debo ver qué usuario hizo cada cambio

**DoD:**
- User invitation system
- Permission management
- Activity log
- Real-time collaboration

**Prioridad:** Baja (Futuro)  
**Estimación:** 21 puntos

---

## Resumen de Prioridades

### Iteración 1 (MVP - 4 semanas)
- US001: Registro de Usuario (5 pts)
- US002: Inicio de Sesión (3 pts)
- US004: Crear Tarea (5 pts)
- US005: Ver Lista de Tareas (8 pts)
- US006: Editar Tarea (5 pts)
- US008: Drag & Drop (8 pts)
**Total: 34 puntos**

### Iteración 2 (Core Features - 3 semanas)
- US003: Recuperación de Contraseña (3 pts)
- US007: Eliminar Tarea (3 pts)
- US010: Uso Offline (13 pts)
- US012: Notificaciones Push (8 pts)
**Total: 27 puntos**

### Iteración 3 (Polish & Advanced - 3 semanas)
- US009: Progreso Visual (5 pts)
- US011: Sincronización Real-time (8 pts)
- US014: Búsqueda y Filtros (5 pts)
- US016: Animaciones (8 pts)
**Total: 26 puntos**

### Iteración 4 (Nice to Have - 2 semanas)
- US013: Notificaciones In-App (3 pts)
- US015: Temas y Personalización (5 pts)
**Total: 8 puntos**

---

## Definiciones Globales

### Definition of Ready (DoR)
- User story tiene criterios de aceptación claros
- Mockups/wireframes disponibles (si aplica)
- Dependencias identificadas
- Estimación realizada por el equipo

### Definition of Done (DoD) Global
- Código implementado y revisado
- Tests unitarios pasando
- Integración con backend funcionando
- UI/UX según diseño
- Performance aceptable
- Funciona en iOS y Android
- Documentación actualizada
