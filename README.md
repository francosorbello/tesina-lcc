# Tesina LCC

Archivos latex de mi tesina.

## Generación de PDF automático

El repositorio en Github está configurado para generar una release que contiene la versión PDF de la tesina. Sin embargo, esto sólo se ejecuta cuando se [tagea un commit](https://git-scm.com/book/en/v2/Git-Basics-Tagging).

Para tagear un commit, asegurate de haber creado uno con los cambios que quieres que aparezcan en el PDF.

Luego, revisa el número del último tag utilizando el comando: 
```sh
$ git tag
1.0.0
```

A continuación, crea un "annotated tag" utilizando el comando

```sh
$ git tag -a [nombre del tag] -m "[nombre del tag]"
```

Por ejemplo,
```sh
git tag -a 1.0.1 -m "1.0.1"
```

Finalmente, pushea los cambios con el comando:
```sh
git push --follow-tags
```

Esto creará la release "1.0.1", con el PDF del commit que fue tageado.

> Nota: si pusheas commits sin un annotated tag, no se creará el PDF. Esto es util si quieres actualizar el repositorio sin trigerear una build.