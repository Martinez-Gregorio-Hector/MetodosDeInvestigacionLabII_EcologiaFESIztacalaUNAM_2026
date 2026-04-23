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

1. Evaluación de la calidad del llamado de bases: **(fastQC)[https://www.bioinformatics.babraham.ac.uk/projects/fastqc/]** y **(Multiqc)[https://github.com/MultiQC/MultiQC]**

2. Ensamble de lecturas pareadas: **(PEAR)[https://cme.h-its.org/exelixis/web/software/pear/doc.html]**

3. Identificación taxonómica: **(QIIME2)[https://qiime2.org/]**




