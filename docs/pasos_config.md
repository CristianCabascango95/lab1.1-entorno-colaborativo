# 1.1 Instalar Git
 Windows: descarga e instala Git desde https://git-scm.com
 acepta las opciones por defecto.
# Verifica instalación:
  git --version
# Configurar credenciales de usuario (local)
Ejecuta en terminal 
git config --global user.name "cristian cabascango"
git config --global user.email "sancrilex.com"
# Opcional: elegir el editor
git config --global core.editor "code --wait"  # si usas VSCode
# Verificar
git config --list
# Añadir la clave al agente SSH
# Muestra la clave pública
cat ~/.ssh/id_ed25519.pub

2. Creación y configuración del repositorio remoto
2.1 Crear repositorio en GitHub/GitLab

En GitHub → New → Repository name: lab1.1-entorno-colaborativo

Selecciona si Public o Private

2.2 Agregar descripción y README.md
 “Repositorio para Lab 1 — Configuración de Git y trabajo colaborativo”.

 3. Clonación y estructura inicial del proyecto
3.1 Clonar el repositorio remoto
https://github.com/CristianCabascango95/lab1.1-entorno-colaborativo.git

3.2 Crear estructura básica de carpetas
mkdir docs src evidencias .github


3.3 Crear .gitignore
# Node
node_modules/
dist/
.env

# Visual Studio Code
.vscode/

# Mac
.DS_Store

# Python
__pycache__/
*.pyc

3.4 Realizar el primer commit inicial
git add .
git commit -m "chore: primer commit - estructura inicial del proyecto"
git push origin main   # o master según tu repositorio

4. Trabajo colaborativo en ramas (branches)
4.1 Crear una rama para desarrollo individual

# crear y cambiar a la rama
git checkout -b feature/readme-update

4.2 Realizar cambios
Ejemplo: completar README y agregar docs/pasos_config.md.

Edita archivos con tu editor, luego:
git status
git add README.md docs/pasos_config.md
git commit -m "feat: documentar pasos de configuración de Git y SSH"

4.3Confirmar cambios y sincronizarlos (push)
git push -u origin feature/readme-update

4.4 Crear Pull Request / Merge Request

En GitHub: En el repositorio aparecerá botón Compare & pull request. Completa título y descripción y asigna revisores.


Ejemplos rápidos de comandos
# 1. Clonar
git clone git@github.com:tu_usuario/lab1.1-entorno-colaborativo.git
cd lab1.1-entorno-colaborativo

# 2. Crear estructura y .gitignore
mkdir docs src evidencias
echo "node_modules/" > .gitignore

# 3. Primer commit
git add .
git commit -m "chore: estructura inicial y .gitignore"
git push origin main

# 4. Crear rama feature
git checkout -b feature/readme
# editar README
git add README.md
git commit -m "feat: completar README con plantilla"
git push -u origin feature/readme

# 5. Hacer PR (vía web)
# 6. Tras merge, actualizar main local
git checkout main
git pull origin main
