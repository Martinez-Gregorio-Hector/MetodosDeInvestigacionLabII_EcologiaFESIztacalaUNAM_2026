# Código para el análisis bioinformático (por equipo)

En esta sección se trabajará en grupo para optimizar recursos computacionales

## Conectarse al servidor y dirigirse a la carpeta de trabajo

```
Dirección ip
ssh lab13@132.248.216.138

Password
ULabo13.
```

Dirigirse al a la carpeta del trabajo

```
cd /home/lab13/Documents/Ecologia2026
```

Hacer un listado de archivos y directorios

```
ls - lh
```

Cambiar al directorio que vamos a trabajar

```
cd Ecologia01
cd Ecologia02
cd Ecologia03
cd EcologiaXX
```

Hacer un directorio donde vamos a almacenar los archivos crudos

```
mkdir raw_data
```

Copiar los archivos que vamos a usar para hacer los análisis en la carpeta raw_data

```
### Ruta relativa
cp ../raw_data/Sample1* raw_data/
### Ruta absoluta
cp /home/lab13/Documents/Ecologia2026/raw_data/Sample1* raw_data/
```

Para comprobar si copiamos los archivos en la carpeta de **raw_data**, podemos usar el comando ls desde nuestro directorio de trabajo

```
ls -lh raw_data/

# -rwxr-xr-x. 1 lab13 lab13 11M Apr 29 23:44 MBC1_S1_L001_R1_001.fastq.gz
# -rwxr-xr-x. 1 lab13 lab13 12M Apr 29 23:44 MBC1_S1_L001_R2_001.fastq.gz
# -rwxr-xr-x. 1 lab13 lab13 13M Apr 29 23:44 MBC2_S2_L001_R1_001.fastq.gz
# -rwxr-xr-x. 1 lab13 lab13 15M Apr 29 23:44 MBC2_S2_L001_R2_001.fastq.gz
# -rwxr-xr-x. 1 lab13 lab13 12M Apr 29 23:44 MBC3_S3_L001_R1_001.fastq.gz
# -rwxr-xr-x. 1 lab13 lab13 14M Apr 29 23:44 MBC3_S3_L001_R2_001.fastq.gz
```

## 1. Análisis de calidad

De acuerdo con nuestro pipeline bioinformático, el primer paso para el análisis de nuestros es la evaluación de la calidad con **[fastqc](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)** y **[multiqc](https://github.com/MultiQC/MultiQC)**. Para hacer esta actividad vamos a activar un ambiente en python. Para listar que ambientes hay en python usar el siguiente comando

```
conda env list

# conda environments:
#
# * -> active
# + -> frozen
#                         /home/lab13/anaconda3
#                         /home/lab13/anaconda3/envs/qiime2-amplicon-2023.9
# base                 *   /home/lab13/miniconda3
# fastqc_Miriam            /home/lab13/miniconda3/envs/fastqc_Miriam
# ipyrad_envArely          /home/lab13/miniconda3/envs/ipyrad_envArely
# ipyrad_envNestor         /home/lab13/miniconda3/envs/ipyrad_envNestor
# ipyrad_envPicazo         /home/lab13/miniconda3/envs/ipyrad_envPicazo
```

Activamos el ambiente hecha en python **fastqc_Miriam** usando el siguiente comando

```
conda activate fastqc_Miriam

#### # Van a observar que del usuario base se a activar al ambiente especificado
# (base) [lab13@host-132 Equipo11]$ conda activate fastqc_Miriam
# (fastqc_Miriam) [lab13@host-132 Equipo11]$

```

Para ver que está instalado fastQC y MultiQC, corran el siguiente comando

```
##### Para FastQC
fastqc --help
#            FastQC - A high throughput sequence QC analysis tool
#
# SYNOPSIS

#	fastqc seqfile1 seqfile2 .. seqfileN
#
#    fastqc [-o output dir] [--(no)extract] [-f fastq|bam|sam]
#           [-c contaminant file] seqfile1 .. seqfileN


##### Para MultiQC
multiqc --help

#  /// MultiQC 🔍 v1.33
#  Usage: multiqc [OPTIONS] [ANALYSIS DIRECTORY]

#  MultiQC aggregates results from bioinformatics analyses across many samples into a single report.
# It searches a given directory for analysis logs and compiles an HTML report. It's a general use tool,
# perfect for summarising the output from numerous bioinformatics tools.
# To run, supply with one or more directory to scan for analysis results. For example, to run in the current
# working directory, use 'multiqc .'
```

Vamos a crear un directorio donde vamos a guardar la evaluación de la calidad del llamado de bases antes del ensamblado y posteriormente correr fastqc y multiqc

```
##### Crear la carpeta 
mkdir QC_AntesDelEnsamble

##### Correr FastQC
fastqc raw_data/* -o QC_AntesDelEnsamble/
# application/gzip
# application/gzip
# application/gzip
# application/gzip
# application/gzip
# application/gzip
# Started analysis of MBC1_S1_L001_R1_001.fastq.gz
# Approx 5% complete for MBC1_S1_L001_R1_001.fastq.gz
# Approx 10% complete for MBC1_S1_L001_R1_001.fastq.gz
# Approx 15% complete for MBC1_S1_L001_R1_001.fastq.gz
#Approx 20% complete for MBC1_S1_L001_R1_001.fastq.gz

##### Ver los archivos que se generaron 
ls -lh QC_AntesDelEnsamble/
# total 11M
# -rw-r--r--. 1 lab13 lab13  950K Apr 30 00:08 MBC1_S1_L001_R1_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  824K Apr 30 00:08 MBC1_S1_L001_R1_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13 1019K Apr 30 00:08 MBC1_S1_L001_R2_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  948K Apr 30 00:08 MBC1_S1_L001_R2_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13  938K Apr 30 00:08 MBC2_S2_L001_R1_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  799K Apr 30 00:08 MBC2_S2_L001_R1_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13 1022K Apr 30 00:08 MBC2_S2_L001_R2_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  944K Apr 30 00:08 MBC2_S2_L001_R2_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13  936K Apr 30 00:08 MBC3_S3_L001_R1_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  791K Apr 30 00:08 MBC3_S3_L001_R1_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13 1016K Apr 30 00:08 MBC3_S3_L001_R2_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  937K Apr 30 00:08 MBC3_S3_L001_R2_001_fastqc.zip

# Correr MultiQC
multiqc QC_AntesDelEnsamble/ -o QC_AntesDelEnsamble/

# /// MultiQC 🔍 v1.33

#     version_check | MultiQC Version v1.34 now available!
#       file_search | Search path: /home/lab13/Documents/Ecologia2026/Equipo11/QC_AntesDelEnsamble
#         searching | ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 12/12
#            fastqc | Found 6 reports
#     write_results | Data        : QC_AntesDelEnsamble/multiqc_data
#     write_results | Report      : QC_AntesDelEnsamble/multiqc_report.html
#           multiqc | MultiQC complete

# Después del multiqc

ls -lh QC_AntesDelEnsamble/
# -rw-r--r--. 1 lab13 lab13  950K Apr 30 00:08 MBC1_S1_L001_R1_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  824K Apr 30 00:08 MBC1_S1_L001_R1_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13 1019K Apr 30 00:08 MBC1_S1_L001_R2_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  948K Apr 30 00:08 MBC1_S1_L001_R2_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13  938K Apr 30 00:08 MBC2_S2_L001_R1_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  799K Apr 30 00:08 MBC2_S2_L001_R1_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13 1022K Apr 30 00:08 MBC2_S2_L001_R2_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  944K Apr 30 00:08 MBC2_S2_L001_R2_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13  936K Apr 30 00:08 MBC3_S3_L001_R1_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  791K Apr 30 00:08 MBC3_S3_L001_R1_001_fastqc.zip
# -rw-r--r--. 1 lab13 lab13 1016K Apr 30 00:08 MBC3_S3_L001_R2_001_fastqc.html
# -rw-r--r--. 1 lab13 lab13  937K Apr 30 00:08 MBC3_S3_L001_R2_001_fastqc.zip
# drwxr-xr-x. 2 lab13 lab13  4.0K Apr 30 00:11 multiqc_data
# -rw-r--r--. 1 lab13 lab13  2.4M Apr 30 00:11 multiqc_report.html
```

Descar de archivos con **[mobaxterm](https://mobaxterm.mobatek.net/)**


Con mobaxter hay que proporcionarle la dirección ip del servidor, la contraseña y la carpeta donde se quiere almacenar la información.

Una vez que se terminó de usar el ambiente de conda hay que desactivarlo y usaremos el siguiente comando.

```
conda deactivate
```

## 2a. Ensamblaje de lecturas

Crear un directorio donde se almacenaran los archivos ensamblados

```
mkdir ensamblaje
```

Hacer un script para correr el ensamblaje de las lecturas con el editor de vim

```
vim ensamblaje.sh
```

Copiar el siguiente código para hacer el ensamble de las lecturas

```
#!/bin/bash

fastq=($(ls raw_data/*.gz))
tLen=${#fastq[@]}
for (( i=0; i<${tLen}; i=i+2));
do
x=${fastq[$i]##*/}
pear -f ${fastq[$i]} -r ${fastq[$i+1]} -o ensamblaje/${x%_L*} -j 2 -q 20
done
wait
echo done
```

Dar permiso a nuestro script y posteriormente realizar la ejecición

```
# Darle permiso
sudo chmod u+x ensamblaje.sh

# Ejecutar el script
bash ensamblaje.sh
```

Una vez que se termina de ejecutar el script, usar el comando ls para ver los archivos que se generaron del programa de pear

```
ls -lh ensamblaje

# -rw-r--r--. 1 lab13 lab13 42M Apr 30 09:55 MBC1_S1.assembled.fastq
# -rw-r--r--. 1 lab13 lab13   0 Apr 30 09:54 MBC1_S1.discarded.fastq
# -rw-r--r--. 1 lab13 lab13 42K Apr 30 09:55 MBC1_S1.unassembled.forward.fastq
# -rw-r--r--. 1 lab13 lab13 14K Apr 30 09:55 MBC1_S1.unassembled.reverse.fastq
# -rw-r--r--. 1 lab13 lab13 50M Apr 30 09:56 MBC2_S2.assembled.fastq
# -rw-r--r--. 1 lab13 lab13   0 Apr 30 09:55 MBC2_S2.discarded.fastq
# -rw-r--r--. 1 lab13 lab13 61K Apr 30 09:56 MBC2_S2.unassembled.forward.fastq
# -rw-r--r--. 1 lab13 lab13 18K Apr 30 09:56 MBC2_S2.unassembled.reverse.fastq
```


El siguiente paso es hacer una carpeta para guardar sólo las lecturas ensambladas 

```
# Hacer directorio
mkdir ensamblados

# Mover las lecturas ensambladas en la carpeta creada
mv ensamblaje/*assembled.fastq ensamblados

# Ver el contenido de la carpeta ensablados

ls -lh ensamblados/

# total 137M
# -rw-r--r--. 1 lab13 lab13 42M Apr 30 09:55 MBC1_S1.assembled.fastq
# -rw-r--r--. 1 lab13 lab13 50M Apr 30 09:56 MBC2_S2.assembled.fastq
# -rw-r--r--. 1 lab13 lab13 46M Apr 30 09:57 MBC3_S3.assembled.fastq
```

## 2b. Evaluación de la calidad después del ensamble

Vamos a seguir el mismas instrucciones que en el paso 1

```
# Activamos el ambiente de conda
conda activate fastqc_Miriam

# Crear una carpeta donde almacenaremos el análisis de calidad
mkdir QC_DespuesDelEnsamble

# Correr FastQC
fastqc ensamblados/* -o QC_DespuesDelEnsamble/

# Ver los archivos que se generaron 
ls -lh QC_DespuesDelEnsamble/

# Realizar el análisis de MultiQc
multiqc QC_DespuesDelEnsamble/ -o QC_DespuesDelEnsamble/

# Ver el reporte final de multiqc
ls -lh QC_DespuesDelEnsamble

```

Descar de archivos con mobaxterm

Posteriormente desactivamos el ambiente de conda con el siguiente comando

```
conda deactivate

```

## 3. QIIME2

Antes de correr QIIME2 vamos hacer un carpeta donde almacenaremos nuestros datos: i) manifest.tsv y ii) sample-metadata.txt

```
# Hacer una carpeta
mkdir data

# i) Manifest file, generamos un archivo con dos columnas y posteriormente llenar el archivo con la información correcta

echo -e "sample-id\tabsolute-filepath" > data/manifest.tsv

for f in `ls ensamblados/*fastq`; do n=`basename $f`; echo -e "${n%.fastq.gz}\t$PWD/$f"; done >> data/manifest.tsv

# Vemos el contenido del archivo manifest

less data/manifest.tsv

# sample-id       absolute-filepath
# MBC1_S1.assembled.fastq /home/lab13/Documents/Ecologia2026/Equipo11/ensamblados/MBC1_S1.assembled.fastq
# MBC2_S2.assembled.fastq /home/lab13/Documents/Ecologia2026/Equipo11/ensamblados/MBC2_S2.assembled.fastq
# MBC3_S3.assembled.fastq /home/lab13/Documents/Ecologia2026/Equipo11/ensamblados/MBC3_S3.assembled.fastq

# ii) metadata file

echo -e "sample-id\trun_prefix\tCurso" > data/sample-metadata.txt

for f in `ls ensamblados/*fastq`; do n=`basename $f`; echo -e "${n%.fastq.gz}\t${n%.fastq.gz}\tEcologia2026"; done >> data/sample-metadata.txt

# Vemos el contenido  de sample-metadata.txt

less data/sample-metadata.txt

# sample-id       run_prefix      Curso
# MBC1_S1.assembled.fastq MBC1_S1.assembled.fastq Ecologia2026
# MBC2_S2.assembled.fastq MBC2_S2.assembled.fastq Ecologia2026
# MBC3_S3.assembled.fastq MBC3_S3.assembled.fastq Ecologia2026
```


Hacer un script para correr QIIME2 con el editor de vim

```
vim qiime2.sh
```

```
#!/bin/bash

start=`date +%s`

mkdir -p qiime2/qzv qiime2/qza

# Activar conda
conda activate /home/lab13/anaconda3/envs/qiime2-amplicon-2023.9

# Importar datos
qiime tools import \
--input-path data/manifest.tsv \
--type 'SampleData[SequencesWithQuality]' \
--input-format SingleEndFastqManifestPhred33V2 \
--output-path qiime2/qza/Fastqs.qza

# Resumen de la importación de los datos
qiime demux summarize \
--i-data qiime2/qza/Fastqs.qza \
--o-visualization qiime2/qzv/se-demux.qzv

# Denoising
qiime dada2 denoise-single \
--i-demultiplexed-seqs qiime2/qza/Fastqs.qza \
--p-trim-left 20 \
--p-trunc-len 410 \
--p-n-threads 1 \
--o-denoising-stats qiime2/qza/stats-dada2.qza \
--o-representative-sequences qiime2/qza/seqs-dada2.qza \
--o-table qiime2/qza/table-dada2.qza

# Visualización del proceso de denoising
qiime feature-table tabulate-seqs \
--i-data qiime2/qza/seqs-dada2.qza \
--o-visualization qiime2/qzv/rep-seqs-dada2.qzv

end=`date +%s`
runtime=$((end-start))
echo 'run time = ' $runtime'(sec)'

echo done .....

```

Darle permiso a nuestro scipt

```
# Darle permiso
sudo chmod u+x qiime2.sh

# Ejecutar el script en segundo plano
nohup sh qiime2.sh > qiime2.out&
```

Para monitorear nuestros script podemos usar los siguientes comandos

```
# 
htop

# Ejecutar el script en segundo plano
nohup sh qiime2.sh > qiime2.out&
```


##########################################################
# Hacer un script para correr qiime2
vim qiime2_equipoXX.sh
# Correr en un segundo plano
nohup bash qiime2_equipoXX.sh > qiime2_equipoXX.out&
##########################################################


#!/bin/bash

start=`date +%s`

mkdir -p qiime2/qzv qiime2/qza

# Activar conda
source activate qiime2-amplicon-2023.9
# Importar datos
qiime tools import \
--input-path data/manifest.tsv \
--type 'SampleData[SequencesWithQuality]' \
--input-format SingleEndFastqManifestPhred33V2 \
--output-path qiime2/qza/Fastqs.qza
wait
# 
qiime demux summarize \
--i-data qiime2/qza/Fastqs.qza \
--o-visualization qiime2/qzv/se-demux.qzv
wait
# Denoising
qiime dada2 denoise-single \
--i-demultiplexed-seqs qiime2/qza/Fastqs.qza \
--p-trim-left 20 \
--p-trunc-len 410 \
--p-n-threads 1 \
--o-denoising-stats qiime2/qza/stats-dada2.qza \
--o-representative-sequences qiime2/qza/seqs-dada2.qza \
--o-table qiime2/qza/table-dada2.qza
wait
# Visualizar
qiime feature-table tabulate-seqs \
--i-data qiime2/qza/seqs-dada2.qza \
--o-visualization qiime2/qzv/rep-seqs-dada2.qzv
wait

NOS QUEDAMOS AQUI


# Para ver la profundidad maxima de los datos
qiime feature-table summarize \
--i-table qiime2/qza/table-dada2.qza \
--m-sample-metadata-file data/sample-metadata.txt \
--o-visualization qiime2/qzv/table-dada2.qzv
wait
qiime metadata tabulate \
--m-input-file qiime2/qza/stats-dada2.qza \
--o-visualization qiime2/qzv/denoising-stats.qzv
wait
# Filogenia
qiime phylogeny align-to-tree-mafft-fasttree \
--i-sequences qiime2/qza/seqs-dada2.qza \
--o-alignment qiime2/qza/aligned-rep-seqs.qza \
--o-masked-alignment qiime2/qza/masked-aligned-rep-seqs.qza \
--o-tree qiime2/qza/unrooted-tree.qza \
--o-rooted-tree qiime2/qza/rooted-tree.qza
wait
# Clasificacion taxonomica
# Generar un archivo temporal
mkdir tmp
export TMPDIR=tmp
wait
#
silva138=/home/lab13/Documents/Ecologia2025/Reference/silva-138-99-nb-classifier.qza

qiime feature-classifier classify-sklearn \
--i-classifier $silva138 \
--i-reads qiime2/qza/seqs-dada2.qza \
--o-classification qiime2/qza/taxonomy.qza
wait
#
qiime metadata tabulate \
--m-input-file qiime2/qza/taxonomy.qza \
--m-input-file qiime2/qza/seqs-dada2.qza \
--o-visualization qiime2/qzv/taxonomy.qzv
wait
# rarefaction
qiime diversity alpha-rarefaction \
  --i-table qiime2/qza/table-dada2.qza \
  --i-phylogeny qiime2/qza/rooted-tree.qza \
  --p-max-depth 21778 \
  --m-metadata-file data/sample-metadata.txt \
  --o-visualization qiime2/qzv/alpha-rarefaction.qzv
wait
qiime taxa barplot \
  --i-table qiime2/qza/table-dada2.qza \
  --i-taxonomy qiime2/qza/taxonomy.qza \
  --m-metadata-file data/sample-metadata.txt \
  --o-visualization qiime2/qzv/taxa-bar-plots.qzv
wait

end=`date +%s`
runtime=$((end-start))
echo 'run time = ' $runtime'(sec)'

echo done .....


####
tail - f qiime2_equipoXX.out

scp -r lab13@132.248.216.138:/home/lab13/Documents/Ecologia2024/Equipo01/qiime2/qzv .

