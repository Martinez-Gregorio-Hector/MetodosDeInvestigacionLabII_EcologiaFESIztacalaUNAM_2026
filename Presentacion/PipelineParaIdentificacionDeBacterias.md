# Pipeline bioinformático

En esta sección describiremos el algoritmos y pipelines que se usarán para la identificación taxonómica de las bacterias de interés ecológico y clínico de las muestras que se prepararon en la primera parte del curso de ecología.

<p align="center">  
  <img src="Figuras/AlgoritmoPipeline.png? raw=true" alt="shell" width="1000" height="600">
</p>


<p align="center">  
  <img src="Figuras/AlgoritmoPipeline2.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Algoritmos que se usarán para el análisis del microbioma

<p align="center">  
  <img src="Figuras/PipelineBioinformatico.svg? raw=true" alt="shell" width="1000" height="600">
</p>

1. Evaluación de la calidad del llamado de bases: **[fastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)** y **[Multiqc](https://github.com/MultiQC/MultiQC)**

2. Ensamble de lecturas pareadas: **[PEAR](https://cme.h-its.org/exelixis/web/software/pear/doc.html)**

3. Identificación taxonómica: **[QIIME2](https://qiime2.org/)**

## 1. Evaluación de la calidad del llamado de bases antes del ensamblado

<p align="center">  
  <img src="Figuras/MultiQC2.svg? raw=true" alt="shell" width="1000" height="600">
</p>

## 2a. Ensambale de lecturas pareadas

<p align="center">  
  <img src="Figuras/Ensamble.jpg? raw=true" alt="shell" width="1000" height="600">
</p>

i) generar un solo archivo fastq 
ii) dejar aquellas bases con una calidad arriba de 20

```
pear -f [lectura_forward] –r [lectura_reverse] -o ensamblado.fastq -j 10 -q 20
```

Por cada muestra se generan tres archivos:

* Assembled, las lecturas que pudo ensamblar (un archivo).
* Discarded, lecturas descartadas (un archivo).
* Unassambled, lecturas que no ensambló por que no se traslaparon (dos archivos).

## 2b. Evaluación de la calidad del llamado de bases después del ensamblado

<p align="center">  
  <img src="Figuras/MultiQC.svg? raw=true" alt="shell" width="1000" height="600">
</p>

Las primeras(20 pb) y las últimas lecturas (a partir de 410 pb) son eliminadas más adelante con el programa de **qiime2**, en la sección de denoising.

## 3. Identificación taxonómica


