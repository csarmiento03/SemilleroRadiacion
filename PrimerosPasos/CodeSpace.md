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
./meiga-school install --pull
```

Este comando prepara el entorno Python, descarga la imagen Docker oficial del
taller (aprox. 2.4 GB) y crea el contenedor `meiga_school`. Dentro del
Codespace suele tardar **entre 3 y 8 minutos**. Verás avanzar la descarga por
capas; es normal.

La instalación terminó bien cuando aparece:

```
[OK] Instalación lista.
Primera prueba: ./meiga-school run wcd-30s --smoke 60
```

---

## Paso 6. Verificar la instalación

Ejecuta el diagnóstico:

```
./meiga-school doctor
```

Revisa que todas las líneas aparezcan como correctas (`[OK]`). Si alguna línea
marca error, ve al Paso 9 (solución de problemas).

---

## Paso 7. Ejecutar la primera simulación de prueba

```
./meiga-school run wcd-30s --smoke 60
```

`--smoke 60` significa "prueba corta con 60 partículas": sirve para comprobar
todo el flujo (simulación Geant4 + análisis + gráficas) sin esperar una
campaña completa.

Al terminar, el programa imprime la carpeta de resultados, con la forma:

```
results/runs/<run-id>/
├── run/          configuraciones y salida de MEIGA
├── analysis/     tablas y métricas
└── plots/        figuras PNG y PDF
```

`<run-id>` es un identificador que el programa muestra al final; no escribas
literalmente los símbolos `<` y `>`.

**Para ver las gráficas:** en el panel izquierdo de archivos, abre la carpeta
`results` → `runs` → (tu run-id) → `plots` y haz clic en cualquier archivo
`.png`; se abre directamente en el editor.

**Para guardar un archivo en tu computador:** haz clic derecho sobre él en el
panel izquierdo y selecciona **Download**. Hazlo con las figuras o resultados
que quieras conservar, porque el Codespace es un computador remoto.

Si llegaste hasta aquí: **la instalación quedó completa.** ✔

---

## Paso 8. Cerrar y volver a entrar

- El Codespace **se detiene solo** tras unos 30 minutos sin actividad; también
  puedes detenerlo tú: menú ☰ (arriba a la izquierda) → **Codespaces: Stop
  Current Codespace**, o desde https://github.com/codespaces con el botón ⋯ →
  **Stop codespace**.
- Para **volver a trabajar**, entra a https://github.com/codespaces (o al botón
  verde **Code → Codespaces** del repositorio) y haz clic sobre tu Codespace
  existente. **No crees uno nuevo cada vez**: perderías la instalación y los
  resultados, y gastarías cuota descargando todo otra vez.
- Al reabrirlo, todo lo instalado y tus resultados siguen allí. Si al ejecutar
  una simulación aparece un error de Docker, espera unos segundos a que el
  servicio arranque y repite el comando.
- **Advertencia:** un Codespace que pasa ~30 días sin usarse es **eliminado
  automáticamente** por GitHub, junto con sus resultados. Descarga lo
  importante (Paso 7) o entra al menos una vez antes de ese plazo.

---

## Paso 9. Qué hacer si ocurre un error

### La instalación (Paso 5) falla o se interrumpe

Vuelve a ejecutar el mismo comando; el instalador reutiliza lo que ya se
descargó y nunca borra resultados:

```
./meiga-school install --pull
```

### `permission denied` al ejecutar `./meiga-school`

```
chmod +x meiga-school scripts/*.sh
./meiga-school install --pull
```

### `Cannot connect to the Docker daemon` o `docker: command not found`

Dentro del Codespace, Docker a veces tarda unos segundos en arrancar tras
reabrirlo. Espera medio minuto y repite el comando. Si persiste:

```
sudo service docker start
./meiga-school doctor
```

### El Codespace no termina de cargar o el editor se comporta mal

1. Presiona **Ctrl + Shift + P** (en Mac: Cmd + Shift + P).
2. Escribe: `Codespaces: Rebuild Container`.
3. Selecciona esa opción y confirma.

La reconstrucción reinstala el entorno base del Codespace. **Después de una
reconstrucción, repite el Paso 5** (`./meiga-school install --pull`), porque
la imagen de MEIGA debe descargarse de nuevo. Tus resultados en
`results/runs/` no se pierden.

### No aparece la terminal

Menú superior: **Terminal → New Terminal**.

### Nada de lo anterior funciona

Copia desde la terminal el comando exacto que ejecutaste y el mensaje de error
completo, y envíalos al equipo del taller. Con esa información el diagnóstico
es mucho más rápido.

---

## Resumen: los tres comandos del taller

Una vez dentro del Codespace, toda la instalación y la prueba se reducen a:

```
./meiga-school install --pull
./meiga-school doctor
./meiga-school run wcd-30s --smoke 60
