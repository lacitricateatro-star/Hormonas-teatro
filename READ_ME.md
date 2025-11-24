```markdown
# Despliegue en Netlify (Hormonas - La Cítrica Teatro)

Opciones de despliegue:

1) Conectar el repositorio a Netlify (recomendado, CI automático)
- Asegúrate de tener los archivos en la rama que usarás (por ejemplo `main`) y la carpeta `docs/` con `index.html` y `styles.css`.
- En Netlify: "New site from Git" → conecta tu cuenta GitHub → selecciona el repo `lacitricateatro-star/Hormonas-teatro`.
- En "Build settings":
  - Build command: (deja vacío)
  - Publish directory: `docs`
- Deploy site. Netlify hará deploy automático tras cada push a la rama seleccionada.

2) Drag & Drop (rápido, sin git)
- Crea una carpeta local (por ejemplo `site/`) que contenga `index.html`, `styles.css` y la carpeta `images/` si la tienes.
- Comprime o simplemente arrastra la carpeta/archivos al panel de Netlify Drop (https://app.netlify.com/drop).
- Netlify publicará el sitio inmediatamente.

3) Publicar desde la raíz del repo
- Si prefieres no usar `docs/`, puedes poner `index.html` en la raíz del repo y ajustar Netlify para publicar desde `/` (Publish directory: `.`).

Comandos útiles (desde tu máquina):
```bash
# si el repo está vacío remoto y quieres vincular uno local:
git clone https://github.com/lacitricateatro-star/Hormonas-teatro.git
cd Hormonas-teatro

# crear la carpeta docs y pegar los archivos que te di
mkdir -p docs
# pega docs/index.html y docs/styles.css en esa carpeta

git add docs/index.html docs/styles.css netlify.toml README.md
git commit -m "Add site for Netlify (docs/)"
git push -u origin main
```

Si estás creando el repo localmente por primera vez:
```bash
cd carpeta-del-proyecto
git init
git add .
git commit -m "Initial site for Netlify (docs/)"
git branch -M main
git remote add origin https://github.com/lacitricateatro-star/Hormonas-teatro.git
git push -u origin main
```

Notas y recomendaciones
- Si vas a usar vídeo de YouTube/Vimeo pega el iframe directamente en `docs/index.html` dentro de `.video-container`.
- Guarda las fotos en `docs/images/` y reemplaza los placeholders por `<img src="images/foto1.jpg" alt="...">`.
- Para dominio propio, añade un archivo `CNAME` o configúralo desde Netlify.
- Añade rel="noopener noreferrer" a los enlaces que abran en _blank.
```
