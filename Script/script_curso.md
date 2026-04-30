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

## Análisis de calidad

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




##########################################################
# III. Obtener los datos que vamos a analizar

cd Ecologia01
mkdir raw_data_fastq
# Escoger las muestras que ustedes prepararon
cp ../raw_data/I16-00XXXXR* raw_data_fastq/
cp ../raw_data/I16-00XXXXR* raw_data_fastq/
# Hacer un listado de los archivos que hemos seleccionado
ls -lh raw_data_fastq
##########################################################
# IV. Analisis de la calidad

# Establecer el entorno en formato unicode 
export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8
# Correr fastqc y multiqc
fastqc raw_data_fastq/*
multiqc raw_data_fastq/* .
mv multiqc_report.html multiqc_report_before.html
scp -r lab13@132.248.216.138:/home/lab13/Documents/Ecologia2025/EcologiaXX/multiqc_report_before.html .
# Crear carpetas y mover archivos html y zip
mkdir fastqc_zip_resultados fastqc_html_resultados
# listar para ver si se crearon los archivo
mv raw_data_fastq/*html fastqc_html_resultados
mv raw_data_fastq/*zip fastqc_zip_resultados

##########################################################
# V. Ensamblaje de lecturas

# Crear un directorio donde se almacenaran los archivos ensamblados
mkdir ensamblaje
# Hacer un script para correr el ensamblaje de las lecturas
vim ensamblaje.sh
# El archivo generado correr con
bash ensamblaje.sh

#!/bin/bash

fastq=($(ls raw_data_fastq/*.gz))
tLen=${#fastq[@]}
for (( i=0; i<${tLen}; i=i+2));
do
x=${fastq[$i]##*/}
echo pear -f ${fastq[$i]} -r ${fastq[$i+1]} -o ensamblaje/${x%_L*} -j 1 -q 30
done
wait
echo done
##########################################################
# VI. Guardar y distribuir las lecturas ensambladas
mkdir ensamblados
mv ensamblaje/*assembled.fastq ensamblados
# VII. Evaluación de la calidad
fastqc ensamblados/*
multiqc ensamblados/* .
mv multiqc_report_1.html multiqc_report_after.html
mkdir fastqc_zip_after_resultados fastqc_html_after_resultados
mv ensamblados/*zip fastqc_zip_after_resultados
mv ensamblados/*html fastqc_html_after_resultados

scp -r lab13@132.248.216.138:/home/lab13/Documents/Ecologia2025/Ecologia100/multiqc_report_after.html .

##########################################################
# VIII. QIIME2 - HACER LA METADATA

mkdir data
# MANIFIES FILE
# 1. Generamos un archivo con dos columnas
echo -e "sample-id\tabsolute-filepath" > data/manifest.tsv
# 2. Hacer el archivo de manifiesto con  unloop
for f in `ls ensamblados/*fastq`; do n=`basename $f`; echo -e "12802.${n%.fastq.gz}\t$PWD/$f"; done >> data/manifest.tsv
# METADATA FILE
# 1. Generamos un archivo con tres columnas
echo -e "sample-id\trun_prefix\tCurso" > data/sample-metadata.txt
# 2. Hacer el archivo de manifiesto con un loop
for f in `ls ensamblados/*fastq`; do n=`basename $f`; echo -e "12802.${n%.fastq.gz}\t${n%.fastq.gz}\tEcologia2025"; done >> data/sample-metadata.txt
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

