# Comandos básicos de Git

## 📌 Sobre esta carpeta

Los comandos de Git que uso de verdad en mi día a día, con los repos `Temario-Java` y `Temario-HTML` como ejemplo real.

## 🧩 Comandos

| Comando | Para qué lo uso |
| :--- | :--- |
| `git init` | Convertir una carpeta normal en un repositorio Git (seguimiento de cambios activado) |
| `git clone <url>` | Descargar una copia completa de un repo ya existente en GitHub a mi ordenador |
| `git status` | Ver qué archivos he modificado, cuáles están preparados para subir y cuáles no |
| `git add <archivo>` / `git add .` | Preparar cambios para el commit (`.` prepara todos los cambios a la vez) |
| `git commit -m "mensaje"` | Guardar los cambios preparados como un punto fijo en el historial, con un mensaje explicando qué cambió |
| `git push origin main` | Subir mis commits locales a GitHub |
| `git pull origin main` | Bajar de GitHub los cambios que no tengo en local, y combinarlos con los míos |
| `git log` | Ver el historial de commits (quién, cuándo, qué mensaje) |

## 💻 Flujo típico que sigo

```bash
# 1. Veo qué ha cambiado
git status

# 2. Preparo los cambios
git add .

# 3. Los guardo con un mensaje claro
git commit -m "feat: add OperadoresLogicos exercise"

# 4. Los subo a GitHub
git push origin main
```

## 📝 Notas

- `git add .` prepara **todo** lo que haya cambiado en la carpeta actual y sus subcarpetas — útil cuando sé que todos los cambios son del mismo commit; si solo quiero subir un archivo concreto, uso `git add nombre-del-archivo` en su lugar.
- El mensaje de `commit -m` sigo la convención de *Conventional Commits*: `feat:` para ejercicios/contenido nuevo, `docs:` para cambios de README, `fix:` para corregir algo que ya existía. Todo en minúscula tras los dos puntos.
- `git pull` es en realidad un atajo de dos pasos: `git fetch` (traer los cambios remotos sin tocar mi código) + `git merge` (combinarlos con lo mío). Lo uso siempre junto, pero es útil saber que por dentro son dos operaciones distintas.
