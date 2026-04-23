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

<p align="center">  
  <img src="Figuras/qiime.png? raw=true" alt="shell" width="1000" height="600">
</p>

**[Bolyen et al., 2019](https://www.nature.com/articles/s41587-019-0209-9)**

## Ejemplo de análisis de qiime2

<p align="center">  
  <img src="Figuras/CancerDeColon2.png? raw=true" alt="shell" width="800" height="600">
</p>

<p align="center">  
  <img src="Figuras/CancerDeColon.svg? raw=true" alt="shell" width="1000" height="600">
</p>

<p align="center">  
  <img src="Figuras/CancerDeColon3.png? raw=true" alt="shell" width="1000" height="600">
</p>

**[Sukjung Choi et al., 2021](https://link.springer.com/article/10.1186/s12967-021-03154-0)**

## ¿Cómo se almacena la información en qiime2?

El algoritmo de qiime proporciona dos tipos de datos **qza** y **qzv**. **[QIIME 2 View](https://view.qiime2.org/)** permite visualizar archivos **qza** y **qzv** directamente en un navegador.

**qza** son los archivos de datos procesados que se usan como entrada en los siguientes pasos
  
- demux.qza → Secuencias importadas
- table.qza → Tabla de abundancia (ASVs/OTUs)
- rep-seqs.qza → Secuencias representativas
- taxonomy.qza → Clasificación taxonómica
- rooted-tree.qza → Árbol filogenético

  
**qzv** son archivos para visualizar resultados

- demux.qzv → Calidad de secuencias
- table.qzv → Resumen de tabla
- taxonomy.qzv → Resultados taxonómicos
- alpha-rarefaction.qzv → Curvas de rarefacción
- barplot.qzv → Gráficos de abundancia taxonómica

En el tutorial de qiime2 podemos ver las características de estos **[archivos](https://docs.qiime2.org/2023.7/tutorials/pd-mice/)**

## Niveles taxonómicos

<p align="center">  
  <img src="Figuras/Taxonomic_Rank_Graph.svg? raw=true" alt="shell" width="1000" height="600">
</p>

## Métodos para el estudio del microbioma

<p align="center">  
  <img src="Figuras/TecnicasBacterias.svg? raw=true" alt="shell" width="1000" height="600">
</p>
