---
layout: nube-post
title: "¿Cómo crear un repo en Git y subirlo a GitHub?"
category: recursos
date: 2026-03-29
description: "Para no tener 20 versiones de un mismo archivo regados en la computadora, aprenderemos cómo usar los repos de Git"
---

Sé que no soy la única que cuando trabaja proyectos de investigación tiene como 5 archivos distintos y cada uno es una versión mejorada de la anterior, sobre todo cuando se trabaja con códigos de programación. Al cabo de unas semanas aquello llega a ser un desastre y no sabes en qué versión hiciste qué.


Esto mismo le pasó a un tal Linus Torvald, sipi, el creador del kernel de *Linux*. Entonces, con tales capacidad de programación pensó: *¿Por qué no hacer un programa que ayude a gestionar las versiones que vamos sacando de cada documento de código?* (bueno, si yo hubiera sido él eso hubiera pensado). El caso es que así es cómo dio vida a su segundo hijo: **Git**. Justamente `Git` es un *sistema de control de versiones distribuido* (además de código libre); que traducido al español significa que es cómo si a la carpeta en la que estamos trabajando, así como a todos los archivos que contienen, les hicieramos un clon exacto, conocido como **repositorio** y en él iremos guardando el historial de modificaciones que vayamos generando.

<figure style="text-align: center; margin: 20px 0;">
  <img src="{{ site.baseurl }}/assets/images/git+github.png" alt="Git y Git Hub. Tomado de https://miro.medium.com/max/2732/1*mtsk3fQ_BRemFidhkel3dA.png" style="border-radius: 20px; width: 100%;">
  <figcaption style="color: #777; font-size: 0.9rem; margin-top: 10px; font-style: italic;">
    Git y Git Hub. Tomado de https://miro.medium.com/max/2732/1*mtsk3fQ_BRemFidhkel3dA.png
  </figcaption>
</figure>

Entonces, imagínate en lugar de tener 10 archivos diferentes, cada uno con una versión distinta del mismo código, solo tendremos un archivo y al lado el historial de los cambios que le hemos hecho. Y luego llega `GitHub`, que es una plataforma web que tiene el propósito de alojar el código que desarrolladores suben a dicha plataforma. Ofrece varias opciones, entre ellas, evidentemente tener una copia en la nube de tus archivos locales, descargar los ficheros y carpetas exactamente como el autor los coloca (es decir, clonas el repositorio lo que garantiza la reproducibilidad); además, puedes entrar a la documentación de los proyectos y leer de qué van.

Además de estas opciones, Git permite tener ramas de un mismo proyecto es decir, la rama `main` (anteriormente conocida como master), es la rama principal y que se crea por defecto; sin embargo, supongamos que queremos hacer una variante totalmente distinta a la idea original, pero queremos conservar ambas versiones. Para ello creamos otra rama y trabajamos de la misma manera que lo hicieramos en la original.

<figure style="text-align: center; margin: 20px 0;">
  <img src="{{ site.baseurl }}/assets/images/01_git_branches.jpg" alt="Ramas en Git. Fuente: Guerrero, 2021" style="border-radius: 20px; width: 100%;">
  <figcaption style="color: #777; font-size: 0.9rem; margin-top: 10px; font-style: italic;">
    Ramas en Git. Fuente: Guerrero, 2021
  </figcaption>
</figure>

Así que en la entrada de hoy, te comparto los apuntes que tengo de **cómo podemos crear un repositorio en Git** para después **subirlo a GitHub** y así crear nuestro portafolio científico, compartir con otras personas nuestros proyectos, contribuir a la ciencia o solo llevar un tracker de nuestras actividades de programación.


# Paso 1: Tener el directorio y los archivos listos
Sé que es muy obvio, pero el secreto para que nuestros proyectos científicos funcionen y no estemos perdidos a la mitad es tener una buena estructura de organización de directorios (carpetas) y ficheros (archivos). Si tu trabajo se encuentra alrededor del área de las ciencias exactas, la estructura que me ha salvado de mucho es la siguiente:


| Directorio | Función |
|-------|--------------|
|00_DOCUMENTACION| Todos los documentos que se generan en un proyecto; desde documentación técnica hasta escritos formales y PDFs con bibliografía 
|01_DATA (INPUT) | Los datos que ocuparemos de entrada y con los cuales trabajaremos
|02_SCRIPTS | Los códigos propios o que recuperamos de otros lados para el trabajo
|03_OUTPUTS | Las salidas, evidentemente, figuras, tablas, gráficos, todo lo que vayamos generando


Obviamente, todo lo anterior puede cambiarse y ajustarse a tus necesidades. Una vez que tenemos todo organizado o al menos lo más posible, debemos crear desde nuestra computadora local el archivo `README.md`. Este es un archivo super sencillo hecho en *Markdown* en el que describimos las características generales de lo que se encuentra dentro del repositorio.


# Paso 2: Crear el repositorio local
Una vez que tenemos listos nuestros archivos, procedemos a ubicarnos en el directorio del cuál queremos crear el repositorio. Esto lo haces desde una terminal de PowerShell o una terminal de bash. Ejecutamos los siguientes comandos:


```bash
#inicia el repositorio local
git init 

#añade los archivos y carpetas que queramos respaldar 
git add [archivos] #sin los corchetes 
#si quieres respaldar todo puedes usar 
git add *

#guardamos los cambios
git commit -m "Inicio del repo"
#el -m le dice a git que vamos a introducir el nombre de la versión que estamos guardando.
```

Después de lo anterior, verás que se crea en un carpeta actual (de la que hiciste el respaldo) una carpeta oculta nombrada como .git

**Observación:**

En caso de que alguna de tus carpetas tenga archivos demasiado grandes, es recomendable mejor solo respaldar los scripts de descarga (GitHub no permite subir archivos grandes, recuerda que más bien es para respaldar código y documentos ligeros).

# Paso 3: Crear una cuenta y un repo en GitHub

En este paso, debemos ingresar a [la página oficial de GitHub](https://github.com). Dentro, debemos crear una cuenta iniciando sesión con las opciones que nos da o inttroduciendo manualmente los datos.

![]({{ site.baseurl }}/assets/images/)
<figure style="text-align: center; margin: 20px 0;">
  <img src="{{ site.baseurl }}/assets/images/01_new_repo_gh.png" alt="Creación de repo en GitHub. Fuente: Creación propia" style="border-radius: 20px; width: 100%;">
  <figcaption style="color: #777; font-size: 0.9rem; margin-top: 10px; font-style: italic;">
    Creación de repo en GitHub. Fuente: Creación propia
  </figcaption>
</figure>

Después, damos click en el botón verde de la barra lateral izquierda que tiene el texto *New*. Con esto se habilitará un menú del cual debemos llenar únicamente la sección `1) General`, es decir, solo colocamos el nombre del repositorio y la descripción del mismo (algo corto). Presionamos en el botón *"Create repository"*. Podemos seleccionar si lo queremos privado o público, así que elige lo que más te convenga. El resto de opciones lo dejamos como aparece por default.

<figure style="text-align: center; margin: 20px 0;">
  <img src="{{ site.baseurl }}/assets/images/01_repo_ops_gh.png" alt="Cómo se crea un repositorio nuevo en GutHub. Fuente: Creación propia" style="border-radius: 20px; width: 100%;">
  <figcaption style="color: #777; font-size: 0.9rem; margin-top: 10px; font-style: italic;">
    Cómo se crea un repositorio nuevo en GutHub. Fuente: Creación propia
  </figcaption>
</figure>

Ahora debemos subir el repositorio local a la nube y lo haremos ejecutando:

```bash
#Conecta el repo local (Git) con el que creamos en la nube (GitHub)
git remote add origin https://github.com/Nubetrosfera/teste1.git
#! IMPORTANTE: Aquí sustituirás la liga por la que te da la ventana que se despliega en GitHub

#Define en qué rama del proyecto queremos guardar los cambios
git branch -M main

#git push -u origin main
```
Notarás que estas opciones te las sugerirá GitHub una vez que creas nuevos repositorios.

<figure style="text-align: center; margin: 20px 0;">
  <img src="{{ site.baseurl }}/assets/images/01_subir_repo_gh.png" alt="Ventana de las opciones que GitHub ofrece para sincronizar un repositorio local. Fuente: Creación propia" style="border-radius: 20px; width: 100%;">
  <figcaption style="color: #777; font-size: 0.9rem; margin-top: 10px; font-style: italic;">
    Ventana de las opciones que GitHub ofrece para sincronizar un repositorio local. Fuente: Creación propia
  </figcaption>
</figure>

# ¿Cómo usar las opciones cuándo estemos trabajando de manera normal?

Una vez que está creado el repo local y sincronizado con el de la nube, lo único que deberemos ejecutar luego de haber hecho los cambios necesarios en nuestro proyecto (o sea, de haber avanzado alguito), ejecutaremos

```bash
git add . #Para añadir las actualizaciones del directorio (o archivo) actual
git commit -m "Título del avance" #Guardar el archivo en Git
git push #sincroniza los ajustes/cambios guardados en Git a GitHub
```
Puedes conocer más leyendo los manuales que Git ofrece de manera gratuita o que otros autores comparten en internet.


## Fuentes consultadas

* Fernández, Y. (2019, 30 octubre). Qué es Github y qué es lo que le ofrece a los desarrolladores. Xataka. Recuperado de https://www.xataka.com/basics/que-github-que-que-le-ofrece-a-desarrolladores en 24 de marzo de 2026.

* Guerrero, S., (2021, 17 mayo). Como trabajar con Ramas en Git y Github. Blog Escola Espai. Recuperado de https://www.espai.es/blog/2021/05/como-trabajar-con-ramas-en-git-y-github/ en 24 de marzo de 2026

* HolaMundo. (2022, 18 febrero). Aprende GIT ahora! curso completo GRATIS desde cero [Vídeo]. YouTube. https://www.youtube.com/watch?v=VdGzPZ31ts8


* Mijacobs. (s. f.). ¿Qué es Git? - Azure DevOps. Microsoft Learn. Recuperado de https://learn.microsoft.com/es-es/devops/develop/git/what-is-git en 24 de marzo de 2026.
