# Libro de Quarto: Computational Analysis of Communication (Análisis Computacional de la Comunicación)

Esto es una re-renderización en quarto de los archivos originales de latex+ipynb del libro.

Esta es la fuente "oficial" del libro en castellano, y la que estamos utilizando para la publicación en acceso 
abierto [cssbook.net](https://cssbook.net) y las actualizaciones.

En inglés, tenemos una [github action](https://github.com/vanatteveldt/cssbook/actions) para hacer las 
actualizaciones automáticamente al confirmarlas [cssbook.net](https://cssbook.net), de forma que 
puedas hacer cambios pequeños desde github y/p trabajar de forma local para luego realizar los 
cambios. 

# Configuración

Pasos necesarios para renderizar el libro:
 - Instala quarto
 - Clona este repositorio
 - Activa el antorno virtual de R `renv`, por, ejemplo, usando [renv/install.R].

En mi sistema, haciéndolo así funciona bien:

```
# Instala quarto
wget https://github.com/quarto-dev/quarto-cli/releases/download/v1.2.313/quarto-1.2.313-linux-amd64.deb
sudo apt install ./quarto-1.2.313-linux-amd64.deb

# Instala los prerequisitos para los paquetes de R (puede que esté incompleto, por favor, añade los 
requisitos extra que encuentres)
sudo apt install gfortran cmake liblapack-dev libgsl-dev libpng-dev libpoppler-cpp-dev libmagick++-dev

# Clona el repositorio
git clone git@github.com:vanatteveldt/cssbook
cd cssbook

# Activa el renv
Rscript renv/install.R
```

# Renderiza el libro

```
quarto render
```

# Una nota sobre el almacenamiento en caché

La primera vez que renderices el libro tardará bastanta.
Después de hacerlo, el contenido está "congelado" a nivel de capítulo y guardado en el caché al 
nivel en el que es sensible.

Ten en cuenta que knitr caching para python no guarda las variables globales, por lo que los 
fragmentos de pythonque crean objetos utilizados en otros fragmentos no deben almacenarse en el 
caché.
Los objetos de R sí que se pueden almacenar en el caché.
