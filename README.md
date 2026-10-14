# Página de Aquetxali

Práctica independiente en Python + Flask. Diseño adaptable a celulares, sin API ni AWS. El HTML y CSS están en templates/index.html; app.py entrega la página.

## Probar en Windows
Abre PowerShell en esta carpeta (donde está app.py):

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe app.py
```
Abre http://127.0.0.1:5000. Mantén la terminal abierta; Ctrl+C detiene el servidor local. Si py no se reconoce pero python sí, sustituye py por python en el primer comando. Requiere Python 3.11 o posterior.

## Subir a GitHub
Crea un repositorio vacío llamado aquetxali-web. Desde esta carpeta, con Git instalado:

```powershell
git init
git add .
git commit -m "Crea pagina de bienvenida de Aquetxali"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/aquetxali-web.git
git push -u origin main
```
Sustituye TU_USUARIO. Autentícate cuando GitHub lo solicite. Si Git pide tu identidad, configura user.name y user.email con tus datos y repite el commit. No subas .venv ni contraseñas. Alternativa: sube los archivos y la carpeta templates con la interfaz de GitHub, conservando su estructura. No subas el ZIP como único archivo.

## Publicar en Vercel
1. En Vercel, crea un proyecto e importa el repositorio de GitHub.
2. Confirma que el directorio raíz contiene app.py y requirements.txt (si subiste una carpeta contenedora, selecciónala como Root Directory).
3. Confirma la detección de Flask. Usa la configuración predeterminada del framework, sin comando de compilación personalizado ni carpeta de salida de frontend.
4. Selecciona Deploy y abre la URL HTTPS cuando termine.

Vercel detecta la instancia app en app.py y ejecuta Flask en su runtime Python. El app.run del bloque __main__ se utiliza únicamente en pruebas locales. No necesitas Waitress, un rewrite a AWS ni vercel.json para esta prueba básica.

Edita el texto o los colores en templates/index.html, guarda, haz commit y push para practicar una nueva publicación mediante la integración de GitHub.

Documentación: https://vercel.com/docs/frameworks/backend/flask
