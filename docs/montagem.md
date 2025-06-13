# Montagem de Genomas (Assembly)

A montagem de genomas a partir de dados metagenômicos (Metagenome Assembly) consiste em reconstruir sequências genômicas mais longas (chamadas de contigs) a partir das leituras curtas (reads) do sequenciamento.  
O objetivo é reconstruir genomas parciais ou completos dos microrganismos presentes na amostra, conhecidos como MAGs (Metagenome-Assembled Genomes).

## Pipeline Geral

- **Controle de Qualidade (QC)**: Assim como na classificação taxonômica, a primeira etapa é garantir a alta qualidade das reads.
- **Montagem**: As reads limpas são fornecidas a um montador de metagenomas.
- **Binning**: Os contigs montados são agrupados (*binned*) em conjuntos que representam genomas de espécies individuais.
- **Avaliação de Qualidade dos MAGs**: Os MAGs são avaliados quanto à sua completude e contaminação.

## Ferramentas Utilizadas

### MEGAHIT

- **Descrição**: MEGAHIT é um montador rápido e com baixo uso de memória, ideal para grandes e complexos conjuntos de dados de metagenomas. Ele utiliza grafos de De Bruijn sucintos.
- **Comando Exemplo**:

```bash
megahit -1 reads_1.clean.fastq -2 reads_2.clean.fastq -o megahit_output --min-contig-len 1000
```

### MetaBAT2

- **Descrição**: MetaBAT2 é uma ferramenta de binning popular que agrupa contigs em MAGs com base na cobertura diferencial e na composição de tetrancleotídeos.
- **Comando Exemplo**:

```bash
# Primeiro, é preciso mapear as reads de volta aos contigs para obter a cobertura
bwa index final.contigs.fa
bwa mem -t 8 final.contigs.fa reads_1.clean.fastq reads_2.clean.fastq | samtools sort -o sorted.bam

# Executar o MetaBAT2
metabat2 -i final.contigs.fa -a sorted.bam -o bins_folder/bin
```

### CheckM

- **Descrição**: CheckM é a ferramenta padrão para avaliar a qualidade dos MAGs, estimando a completude, contaminação e heterogeneidade da cepa com base em marcadores de genes de cópia única.
- **Comando Exemplo**:

```bash
checkm lineage_wf -t 8 -x fa bins_folder/ checkm_output/
```

