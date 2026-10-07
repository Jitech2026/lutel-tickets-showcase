<div align="center">

# 🎫 LUTEL Tickets

### Sistema de gestión de reportes técnicos con seguimiento en tiempo real

[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Vite](https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white)](https://vitejs.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind-3-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Supabase](https://img.shields.io/badge/Supabase-Backend-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com)
[![Ionic](https://img.shields.io/badge/Ionic-Mobile-3880FF?logo=ionic&logoColor=white)](https://ionicframework.com)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-000000?logo=vercel&logoColor=white)](https://vercel.com)

[Demo en vivo](https://lutel.vercel.app/login) · [Reportar bug](../../issues) · [Solicitar feature](../../issues)

</div>

---

## 📖 El problema

**LUTEL S.R.L.**, empresa de telecomunicaciones en Cajamarca, Perú, gestionaba sus reportes técnicos de internet a través de **WhatsApp**.

Esto generaba problemas operativos graves:

- 📵 **Las evidencias fotográficas se perdían** entre conversaciones
- 🔀 **Los tickets se mezclaban** con mensajes personales
- 📍 **No había visibilidad** de dónde estaba cada técnico
- 📊 **Cero trazabilidad** y cero métricas de productividad
- ⏱️ **Sin control** del tiempo de resolución por ticket
- 🚫 **Sin roles ni permisos**: cualquiera podía cerrar cualquier reporte

El supervisor no tenía forma de auditar el trabajo de los técnicos ni de saber cuántos tickets estaban pendientes realmente.

---

## 💡 La solución

**LUTEL Tickets** es una plataforma Fullstack que centraliza toda la operación técnica:

| Antes (WhatsApp) | Después (LUTEL Tickets) |
|------------------|--------------------------|
| Fotos perdidas en el chat | Evidencias organizadas en Supabase Storage |
| Sin trazabilidad | Historial completo por ticket |
| Sin ubicación de técnicos | Mapa interactivo en tiempo real |
| Sin roles | RLS: admin cierra, técnico ejecuta |
| Sin métricas | Dashboard con KPIs y gráficos |
| Sin app móvil | App Ionic + Capacitor para Android |

**Proyecto calificado con 19/20 por el supervisor de LUTEL S.R.L.** durante la evaluación de sustentación, destacando su aplicabilidad directa al negocio real.

---

## ✨ Funcionalidades

### 👨‍💼 Panel de Administrador
- Dashboard con KPIs en tiempo real (total, pendientes, en proceso, finalizados)
- Lista de tickets con búsqueda y filtros
- Vista detallada de cada ticket con historial de comentarios
- **Mapa interactivo** con ubicación de técnicos (Leaflet + OpenStreetMap)
- Gráficos analíticos: tickets por estado y por prioridad
- Asignación de técnicos a tickets
- Cierre y validación de tickets (rol exclusivo del admin)
- Gestión de clientes y técnicos
- Subida de evidencias fotográficas

### 🔧 App móvil para Técnicos (Ionic + Capacitor)
- Login con Supabase Auth
- Vista de **solo sus tickets asignados** (RLS por usuario)
- Subida de evidencias fotográficas desde la cámara
- **Sincronización offline**: la foto se guarda localmente y se sube automáticamente cuando se recupera señal
- Actualización de estado del ticket
- Comentarios en el ticket

### 🔐 Seguridad
- Autenticación con Supabase Auth
- **Row Level Security (RLS)** por rol y por usuario:
  - Técnicos: solo ven y actualizan sus tickets asignados
  - Admin: acceso total, único que puede cerrar tickets
- Variables de entorno protegidas

---

## 🛠️ Stack técnico

### Frontend Web
- **React 18** + **TypeScript**
- **Vite** como build tool
- **Tailwind CSS** para estilos
- **Recharts** para gráficos
- **Leaflet** + **OpenStreetMap** para mapas
- Arquitectura **MVVM**: `views/`, `viewmodels/`, `models/`, `services/`, `hooks/`

### App Móvil
- **Ionic Framework** + **React**
- **Capacitor** para compilación nativa (Android)
- Cámara y almacenamiento local para evidencias

### Backend / Base de datos
- **Supabase**:
  - PostgreSQL (5 tablas relacionadas)
  - Auth (login por email)
  - Realtime (suscripciones a cambios en tickets)
  - Storage (evidencias fotográficas)
  - Row Level Security (policies por rol)

### Deploy
- **Vercel** (frontend web + app híbrida)
- Migraciones SQL versionadas en el repo (`supabase_migration.sql`)

---

## 📸 Capturas

### Dashboard del Administrador
<img width="1351" height="630" alt="Captura de pantalla 2026-10-07 152522" src="https://github.com/user-attachments/assets/95d1250a-f5f5-4be0-8279-b6f900a25bb7" />


### Mapa de Técnicos en Tiempo Real
![Mapa de Técnicos](./screenshots/03-mapa-tecnicos.png)
<img width="1365" height="638" alt="Captura de pantalla 2026-10-07 152803" src="https://github.com/user-attachments/assets/b17f2402-43c0-4aae-b119-e1a35e05a546" />


### Detalle del Ticket con Evidencia Fotográfica
![Detalle del Ticket](./screenshots/04-detalle-ticket.png)
<img width="458" height="540" alt="Captura de pantalla 2026-10-07 152848" src="https://github.com/user-attachments/assets/8927db90-fede-47e8-8d6f-ddba8f308abb" />

### Formulario de Creación de Ticket
![Crear Ticket](./screenshots/05-crear-ticket.png)
<img width="1327" height="592" alt="Captura de pantalla 2026-10-07 152912" src="https://github.com/user-attachments/assets/63734ed9-43ab-490e-900b-1301f23a3fa1" />

### Reportes y Analítica
![Reportes](./screenshots/06-reportes.png)
<img width="122" height="112" alt="Captura de pantalla 2026-10-07 153213" src="https://github.com/user-attachments/assets/59c0382a-acae-4d8b-940d-241494c70d4b" />
<img width="1152" height="396" alt="Captura de pantalla 2026-10-07 153256" src="https://github.com/user-attachments/assets/7fa06cf5-7de3-4ef5-8334-14d9f30a7b7e" />

### App Móvil (Ionic + Capacitor)
![App Móvil](./screenshots/07-app-movil.jpg)
![Uploading Captura de pantalla 2026-10-07 153213.png…]()

---

## 🏗️ Arquitectura
