# Flujo de entrega

```bash
git switch dev
git pull origin dev
git switch -c alumno/nombre-apellido/ejercicio-001
# resolver ejercicio
git add facil/ejercicio-001/resoluciones/nombre-apellido/
git commit -m "feat(mongodb): resolver ejercicio 001"
git push -u origin alumno/nombre-apellido/ejercicio-001
```

Luego abre Pull Request hacia `dev`.

