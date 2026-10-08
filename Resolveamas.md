# Resolver divergencia de ramas (push rechazado)

## 📌 Sobre este caso

Esto me pasó de verdad trabajando en `Temario-Java`: intenté subir mis commits y Git me lo rechazó. Lo documento paso a paso porque entender *por qué* pasa esto es la mitad del aprendizaje.

## 🧩 Qué pasó

1. Hice `git push origin main` y Git respondió con un error:

```
! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to '...'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart.
```

2. **La causa:** en GitHub había un commit que mi copia local no tenía (en mi caso, porque en su momento edité un README directamente desde el editor web de GitHub). Mi rama local y la de GitHub habían "divergido" — cada una tenía algo que la otra no.

3. **La solución:**

```bash
git pull origin main
```

4. Como los cambios no tocaban exactamente las mismas líneas, Git los combinó solo, y me abrió el editor para confirmar el mensaje del *merge commit* (el archivo `MERGE_MSG`, con líneas que empiezan por `#` que son solo instrucciones y se ignoran). Guardé y cerré, y con eso quedó aceptado.

5. Con el `pull` ya hecho, `git push origin main` funcionó sin problema.

## 📝 Notas

- **Esto NO fue un conflicto de verdad** — Git pudo fusionar los cambios automáticamente porque no coincidían en las mismas líneas de los mismos archivos. Un conflicto real pasa cuando **las dos versiones cambian la misma línea de forma distinta**, y ahí Git no puede decidir por sí solo.
- Si hubiera sido un conflicto real, el archivo afectado habría quedado así, y tendría que haberlo editado a mano:

```
<<<<<<< HEAD
(mi versión del contenido)
=======
(la versión que había en GitHub)
>>>>>>> origin/main
```

  Borrando esas marcas (`<<<<<<<`, `=======`, `>>>>>>>`) y dejando el contenido final que yo decida, y luego `git add` + `git commit` + `git push` como de costumbre.

- **Cómo evitar que esto pase:** hacer todos los cambios desde un solo sitio (mi VS Code local), en vez de editar a veces desde ahí y a veces desde el editor web de GitHub. Si algún día trabajo en dos ordenadores distintos, la clave es siempre hacer `git pull` antes de empezar a trabajar, para partir de la versión más reciente.
