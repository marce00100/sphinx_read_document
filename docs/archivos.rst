


I Archivo
=====================

Sphinx es una distribución de Python, para instalarlo es necesario tener Python, este ya viene instalado en las distribuciones de Linux.

Instalacion de librerias Python
-------------------------------

Para instalar el repositorio de librerias de python se debe realizar:

    $ sudo apt-get install python-pip python-dev build-essential

Luego para instalar Sphinx se realiza mediante el siguiente comando

    $ easy_install sphinx

Creacion de proyecto sphinx
---------------------------
Para crear un proyecto Sphinx se debe ingresar a la carpeta donde estaran los documentos en formato .rst (restucturedText) y se genera el proyecto mediante la siguiente orden:

    $ sphinx-quickstart

Seguir los pasos

- Root path : el directorio base donde estaran la documentacion (por ejemplo /dir/docs/). Si se esta ubicado en el directorio colocar "."

- Project name: Nombre del proyecto. (Ejemplo: Documentos Estructurados)

- Author: Nombre del autor que tendra la documentacion. (Ejemplo: NN). No se puede dejar en blanco.

- Version: Version del proyecto (ejemplo: 1.0)

- Release: Version del proyecto liberado (ejemplo: 1.0)

- Seguir las otras opciones de configuracion por defecto (presionando enter, con la configuracion propuesta por defecto), **con excepcion de la opcion**:
 
		**autodoc**: la cual se debe colocar "Y"

	Seguir el resto de la configuracion por defecto (simplemente presionando enter)	


Generación de HTML a partir de los Documentos rst.
--------------------------------------------------

Una vez creada la estructura del proyecto (configurado con sphinx-quickstart), en la carpeta docs se tienen los  siguientes elementos nuevos:

* Makefile: Archivo que contiene instrucciones para compilar salidas de documentación cuando se usa el comando make .

* _build: Este es el directorio donde los archivos generados (html, pdf, LaTex, etc) serán colocados Después de que una salida específica es desencadenada.

* _static: Los archivos que no son parte del código de origen (como las imágenes) son colocados aquí y después se enlazan en el directorio de compilación.

* conf.py: Este es un archivo de Python que contiene valores de configuración para Sphynx, incluyendo aquellos seleccionados cuando sphinx-quickstart fue ejecutado en el terminal.

* index.rst: La raíz del proyecto de documentación. 

En la carpeta `docs`, se alojaran los archivos rst, y de ser necesario estarán organizados en subdirectorios. 

Abrir el archivo index.rst, y modificarlo según las necesidades. Lo que si es importante es hacer referencia a los documentos rst existentes, para ello se deben aumentar los nombres de los archivos en el archivo index.rst debajo de la directiva :maxdepth, como se muestra a continuación.  

.. code-block::

   Contents:    
   
   .. toctree::   
     :maxdepth: 2
    
      archivo-ejemplo
      archivo2.rst
      manuales/manual-de-usuario    


 
Estos archivos deben ser referenciados manteniendo tres espacios en blanco desde el borde izquierdo, se puede omitir la extensión rst.

Luego para generar los archivos html se debe ejecutar la orden en la carpeta raiz (docs) donde se ecnuentran los documentos rst:

.. code-block:: 

   $ make html

Esto genera los html dentro de _buil/html donde se encuentra el archivo index.html el cual la raiz de la generacion html.

 
   docs/_build/html/index.html