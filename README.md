# 🚀 Laboratorio 1 — Login en Laravel

## 📖 Introducción
Este laboratorio tuvo como objetivo implementar un sistema de autenticación básico en **Laravel**, explorando su estructura bajo el patrón **Modelo-Vista-Controlador (MVC)**.  
Se configuró un entorno de desarrollo local con WAMP, Composer y MySQL, y se personalizó el repositorio documentando los pasos y dificultades encontradas.  

### Principales carpetas en MVC
- **Models (`app/Models`)** → Contienen las clases que representan la lógica de negocio y las tablas de la base de datos.  
- **Views (`resources/views`)** → Plantillas Blade donde se muestra la interfaz de usuario.  
- **Controllers (`app/Http/Controllers`)** → Gestionan la lógica entre los modelos y las vistas.  
- **Routes (`routes/web.php`)** → Definen las rutas y endpoints que responden a las solicitudes del navegador.  

---

## ⚙️ Requisitos Previos
- PHP 8.0+  
- Composer (última versión)  
- Laravel Installer o `composer create-project`  
- WAMP Server (Apache + MySQL)  
- Editor de código (VS Code recomendado)  
- Node.js y NPM  
- Git/GitHub para el repositorio  

---

## 🛠️ Instalación y Configuración
1. **Crear proyecto Laravel**  
   ```bash
   composer create-project laravel/laravel login-lab
   cd login-lab
   ```

2. **Configurar `.env`**  
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=loginlab
   DB_USERNAME=root
   DB_PASSWORD=
   ```

3. **Migraciones**  
   ```bash
   php artisan migrate
   ```

4. **Instalar autenticación**  
   ```bash
   composer require laravel/ui
   php artisan ui bootstrap --auth
   npm install
   npm run dev
   ```

5. **Levantar servidor**  
   ```bash
   php artisan serve
   ```
   Navegar en 👉 [http://127.0.0.1:8000](http://127.0.0.1:8000).  

---

## 🗄️ Base de Datos
- Base creada: **loginlab** en MySQL.  
- Migraciones generaron las tablas:  
  - `users`  
  - `password_resets`  
  - `failed_jobs`  
  - `personal_access_tokens`  
  - `migrations`  
- Respaldo exportado desde **phpMyAdmin** incluido en el repositorio.  

---

## 📷 Resultados
Pantalla de **Login** funcionando con Bootstrap:

![Login funcionando](images/login.png)
Pantalla de **Registro**:

![Register funcionando](images/register.png)
---

## ❌ Dificultades y ✔️ Soluciones
- **Error de migración (Specified key was too long)** → Se solucionó añadiendo  
  ```php
  Schema::defaultStringLength(191);
  ```
  en `AppServiceProvider.php`.  
- **Pantalla sin estilos (todo blanco)** 
- **Configuración de base de datos** → Se ajustó el archivo `.env` para conectar correctamente con MySQL de WAMP.  

---

## 🔗 Referencias
- [Documentación oficial de Laravel](https://laravel.com/docs)  
- [Laracasts - Laravel Authentication](https://laracasts.com)  
- [Blog DesdeLinux: LVM y Laravel](https://blog.desdelinux.net)  

---

## 🧑‍💻 Información del Estudiante
Este laboratorio ha sido desarrollado por el estudiante de la **Universidad Tecnológica de Panamá**:  

- **Nombre:** William Concepción  
- **Correo:** William.concepcion1@utp.ac.pa
- **Curso:** Ingeniería Web  
- **Grupo:** ISF132  
- **Instructor:** Ing. Irina Fong  

📅 **Fecha de ejecución:** 9/28/25

---
