# Objetivo

He desarrollado este repositorio público para hacer mis pruebas con código Python para crear html.

Inicialmente se creó como un repositorio público ya que no se puede trabajar desde GitKraken con repositorios privados en la versión gratuita. Espero que pueda servir de guía para aquel que se encuentre con este repositorio en su camino a inspeccionar las posibles y variadas opciones para crear su repositorio usando código Python.

[https://marioc0093.github.io/Python_html_test/](https://marioc0093.github.io/Python_html_test/)

# Requisitos

- IDE de Python: Visual Studio Code. https://code.visualstudio.com/.
- Instalar extensión de Python: https://marketplace.visualstudio.com/items?itemName=ms-python.python.
- Instalar extensión de Quarto: https://marketplace.visualstudio.com/items?itemName=quarto.quarto.
  - Esto nos permite crear fichero Quarto Document y Quarto Project y trabajar con código Python en él.
  - También podremos hacer render sobre notebooks .ipynb con la sentencia clásica `Ctrl+Shift+K` o en Preview Format / Preview HTML
- Seguir tutorial de cómo usar Jupyter Lab en quarto: [Tutorial: Hello, Quarto](https://quarto.org/docs/get-started/hello/jupyter.html)

# Proyectos

Tenemos la opción de trabajar con un proyecto Quarto. Al crearlo tendremos que elegir la carpeta de trabajo (carpeta donde tenemos clonado el respositorio GitHub) y automáticamente tendremos la siguiente estructura:

- :file_folder: .quarto
- :file_folder: _site
- _quarto.yaml
- about.qmd
- index.qmd
- styles.css

❕ En este repositorio se ha creado la carpeta _proyecto_template_ como caso de uso.

Podemos añadir una carpeta **_output** e indicar desde el yaml que este será nuestro directorio de salida donde se creará el html y que usaremos como carpeta origen en Settings/Pages para nuestra página del proyecto.

Para adaptarnos a la estructura por defecto de GitHub, usaremos la carpeta docs en vez de _output.

Nuestro fichero yaml quedaría de la siguiente manera:

```
project:
  type: website
  output-dir: _output

website:
  title: "proyecto"
  navbar:
    left:
      - href: index.qmd
        text: Home
      - about.qmd

format:
  html:
    theme: cosmo
    css: styles.css
    toc: true
```

# output-dir en notebooks

Desde un fichero ipynb no es posible (o no he sido capaz) de hacer este tipo de modificaciones yaml en la cabecera del fichero, aunque sí creando un fichero yaml en la misma ruta donde se encuentra cargado el notebook ipynb.


# Documentación

- https://quarto.org/docs/tools/vscode.html
- https://quarto.org/docs/get-started/hello/jupyter.html
