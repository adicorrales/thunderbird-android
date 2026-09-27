# Update Custom from release

Generar versión actualizada desde GIT. Se asume que la rama en GIT
está sincronizada con el release del GIT de origen.

Confirma la versión **Build** app-k9mail a fossRelease.

## Tareas

**Paso 1. Sincronizar release local:**
- Checkout a la rama **Release** local en Android Studio (selector superior izquierd).
- Update Project (flecha azul hacia abajo en la barra superior o Ctrl + T / Cmd + T).

**Paso 2. Resetear rama Custom a la nueva release:**
- Checkout a la rama **Custom** (selector superior izquierdo).
- En el menú de ramas, busca **Release** bajo el apartado Local.
- Selecciona el commit más reciente.
- Botón derecho y **Reset 'selected' to 'Here'** con la opción Hard.

**Paso 3. Aplicar cambios mediante Cherry-pick:**
- En la pestaña Git (abajo) -> vista Log, busca en el panel izquierdo la
rama **remota Custom**.
- Selecciona en la lista central los commits con tus cambios (desde el primero hasta
el último real, omitiendo los commits de merge).
- Haz clic derecho en la selección y elige Cherry-Pick.

**Paso 4.Compilar y verificar:**
- Ve al menú Build -> Clean Project y luego ejecuta Build -> Rebuild Project
(o genera el APK).
- Para confirmar que los cambios quedaron aplicados correctamente, verifica que los
iconos y recursos personalizados se muestren en la compilación.

**Paso 5 .Sincronizar GitHub mediante Force Push:**
- Presiona Ctrl + Shift + K (o Cmd + Shift + K).
- En la ventana de Push, haz clic en la flecha desplegable junto al botón verde
Push y selecciona Force Push (o Push with --force-with-lease).

El resultado final debe ser la lista de tus commits **arriba** del commit
origin Release: Mail XX.X
