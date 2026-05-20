# Deshacer Cambios En Git

## Deshacer Modificaciones En Un Archivo

Si modificaste un archivo y quieres volver a la ultima version confirmada:

```bash
git restore archivo.txt
```

Esto descarta los cambios no preparados y restaura el archivo a su ultimo estado en el commit.

## Quitar Un Archivo Del Staging

Si preparaste un archivo por error y quieres sacarlo del area de staging:

```bash
git restore --staged archivo.txt
```

El archivo vuelve al directorio de trabajo pero conserva tus cambios.

## Ver El Estado Despues De Restaurar

```bash
git status
```

## Ejemplo Completo

```bash
# Crear y modificar un archivo
echo "nuevo contenido" >> archivo.txt

# Ver el cambio
git status

# Deshacer el cambio
git restore archivo.txt

# Verificar que volvio al estado anterior
git status
```

## Si Ya Hiciste Commit

Si el cambio ya fue confirmado con `git commit`, puedes:

### Ver El Historial

```bash
git log --oneline
```

### Revertir Un Commit

```bash
git revert <hash-del-commit>
```

Esto crea un nuevo commit que deshace los cambios del commit especificado, sin borrar el historial.

## Advertencias

- `git restore` descarta cambios no guardados. Asegurate de no necesitar esos cambios.
- Nunca uses `git reset --hard` si no sabes que hace.
- Si tienes dudas, revisa siempre con `git status` antes y despues.

## Resumen De Comandos

| Accion | Comando |
|---|---|
| Descartar cambios en archivo | `git restore archivo.txt` |
| Quitar del staging | `git restore --staged archivo.txt` |
| Revertir un commit | `git revert <hash>` |
| Ver estado | `git status` |
