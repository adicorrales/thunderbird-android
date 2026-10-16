# Actualizar la rama Custom a la nueva release
Actualiza la rama **Release** direcatemnte en la página de GIThub.

## 1. Sincronizar release local
- Cambia (Checkout) a la rama release local en Android Studio (selector inferior derecho). 
- Haz clic en el icono de Update Project (flecha azul hacia abajo en la barra superior o Ctrl + T / Cmd + T).

## 2. Resetear rama Custom a la nueva release
- Cambia (Checkout) a la rama Custom (selector inferior derecho). 
- En el menú de ramas, busca release bajo el apartado Local, haz clic en la flecha a su derecha y selecciona 
Reset 'Custom' to 'Here' con la opción Hard.

## 3. Aplicar cambios mediante Cherry-pick
- En la pestaña Git (abajo) -> vista Log, busca en el panel izquierdo la rama remota origin/Custom. 
- Selecciona en la lista central los commits con tus cambios (desde el primero hasta el último real, omitiendo los 
commits de merge). Haz clic derecho en la selección y elige Cherry-Pick.

## 4. Compilar y verificar
- Verifica que en **BUILD** esté seleccionada la opcion **FOSS Release**, no debug.
- Ve al menú Build -> Clean Project y luego ejecuta Build -> Rebuild Project (o genera el APK). 
- Para confirmar que los cambios quedaron aplicados correctamente, verifica que los iconos y recursos personalizados 
se muestren en la compilación.

## 5. Sincronizar GitHub mediante Force Push
- Presiona Ctrl + Shift + K (o Cmd + Shift + K). 
- En la ventana de Push, haz clic en la flecha desplegable junto al botón verde Push y selecciona Force Push 
(o Push with --force-with-lease).
