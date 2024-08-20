# Objetivo

He desarrollado este repositorio público para hacer mis pruebas con código Python para crear html.

Inicialmente se creó como un repositorio público ya que no se puede trabajar desde GitKraken con repositorios privados en la versión gratuita. Espero que pueda servir de guía para aquel que se encuentre con este repositorio en su camino a inspeccionar las posibles y variadas opciones para crear su repositorio usando código Python.

[https://marioc0093.github.io/Python-for-Quarto/](https://marioc0093.github.io/Python-for-Quarto/)

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

# Render en notebooks

Por defecto, al hacer render desde un fichero ipynb el output que se genera (HTML, PDF...) no ejecuta el código Python y solo representa las celdas que hayamos incluido y los outputs que tengamos en el notebook.

Si queremos que hacemas de generar el fichero output también ejecute el código incluido en las celdas debemos incluir el siguente código yaml:

```
execute:
    enabled: true
```

# Conflictos de Python y VS Code.

El único conflicto que me he encontrado en la generación de este repositorio ha no tener acceso al ejecutable de Python:

<img src="https://github.com/user-attachments/assets/25e371eb-0281-44da-8fc2-3344a3bbe298" alt="image"/>
&nbsp;
<img src="https://github.com/user-attachments/assets/e67bd15f-5363-4e1c-94c1-64e88e8273fd" alt="image" width="500"/>

Siguiendo estas recomendaciones se debería resolver:

1. Desinstalar todas las versiones Python de la Tienda de Microsoft.
   1.1 Abrir el menú de inicio y busca "Python".
   1.2 Hacer clic derecho sobre Python y selecciona "Desinstalar".

2. Cambier el intérprete actual.
   2.1 Seleccionar el nombre del intérprete en la barra de estado. VS nos recomienda el intérprete a usar.  
   &nbsp;
   <img src="https://github.com/user-attachments/assets/19dc6757-cb1d-4e29-9531-48a0912b446f" alt="image" width="500"/>&nbsp;
   <img src="https://github.com/user-attachments/assets/607ac344-b51a-47c1-8197-b45a87ae8e3d" alt="image" width="500"/>
   
4. Verificar que Quarto para usar la instalación correcta de Python.  
   <img src="https://github.com/user-attachments/assets/ed1989e3-d6eb-4394-9273-89510c8ca3a2" alt="image" width="500"/>


# Documentación

- https://quarto.org/docs/tools/vscode.html
- https://quarto.org/docs/get-started/hello/jupyter.html
