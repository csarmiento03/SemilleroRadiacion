# Guía para trabajar en el Codespace del Taller MEIGA

Dirigida principalmente a quienes no cuentan con Linux en sus computadoras.
Un **Codespace** es un computador Linux virtual que funciona desde el navegador:
no necesitas instalar nada en tu propio equipo.

Tiempo total estimado: **15 a 20 minutos** con buena conexión a Internet.

---

## Paso 1. Crear una cuenta en GitHub

GitHub es la plataforma donde está el repositorio del taller y desde donde se
crea el Codespace. Si ya tienes cuenta y puedes iniciar sesión, salta al Paso 2.

1. Abre el navegador e ingresa a: https://github.com/
2. Haz clic en **Sign up** (esquina superior derecha).
3. Escribe tu correo electrónico.
4. Crea una contraseña.
5. Elige un nombre de usuario.
6. Selecciona tu país.
7. Revisa tu correo y confirma la cuenta con el código que recibirás.
8. Regresa a GitHub e inicia sesión.

**Importante:** debes tener la sesión iniciada antes de crear el Codespace.
La cuenta gratuita es suficiente para todo el taller.

---

## Paso 2. Ingresar al repositorio del taller

Ingresa a:

https://github.com/rmartinezra/introduccion-simulacion-detectores-meiga

---

## Paso 3. Crear el Codespace

1. Dentro del repositorio, localiza el botón verde **Code**.
2. Haz clic en **Code** y selecciona la pestaña **Codespaces**.
3. Haz clic en los **tres puntos horizontales (⋯)** y luego en
   **Create codespace with options** (crearlo "con opciones" es lo que permite
   elegir la máquina del punto siguiente).
4. En **Machine type**, selecciona **4-core** (16 GB de RAM). El taller
   necesita al menos 8 GB de RAM, así que no uses la máquina de 2 núcleos.
5. Haz clic en **Create codespace**.

> **Sobre la cuota gratuita:** GitHub regala 120 horas-núcleo al mes.
> Con una máquina de 4 núcleos eso equivale a unas **30 horas de uso al mes**,
> más que suficiente para el taller. Al final de cada sesión, detén el
> Codespace (ver Paso 8) para no gastar horas innecesariamente.

---

## Paso 4. Esperar a que el Codespace cargue

GitHub preparará el entorno y abrirá Visual Studio Code en el navegador.
Esto tarda normalmente **2 a 3 minutos**. Pueden aparecer mensajes como
"Setting up your codespace" o "Configuring codespace". No cierres la pestaña.

El Codespace está listo cuando ves:

- Las carpetas del proyecto en el panel izquierdo
  (`analysis`, `container`, `docs`, `experiments`, `modules`, `scripts`...).
- Un editor en el centro.
- Una **terminal** en la parte inferior, con una ruta parecida a:

  ```
  /workspaces/introduccion-simulacion-detectores-meiga
  ```

Si no ves la terminal: en el menú superior selecciona
**Terminal → New Terminal**.

**Ojo:** en este punto el Codespace está encendido, pero el software del
taller **todavía no está instalado**. La instalación se hace en el paso
siguiente y solo se hace una vez.

---

## Paso 5. Instalar el entorno MEIGA (solo la primera vez)

En la terminal de la parte inferior, escribe el siguiente comando y presiona
Enter. No agregues `sudo` ni `docker` delante:

```
docker pull rmartinezmaple/arti_lidera:latest
```

Este comando prepara el entorno Python, descarga la imagen Docker ARTI
(aprox. 2.4 GB) y crea el contenedor `meiga_school`. Dentro del
Codespace suele tardar **entre 3 y 8 minutos**. Verás avanzar la descarga por
capas; es normal.

Ahora: 

docker run -it --name arti_name_of_container -v /local/path:/workspace --entrypoint bash rmartinezmaple/arti_lidera:latest

# EXAMPLE: Run container named "arti_dev" mounting the folder /home/csarmiento/proyectos into /workspace

docker run -it --name arti_csarmiento -v /home/csarmiento/proyectos:/workspace --entrypoint bash rmartinezmaple/arti_lidera:latest
