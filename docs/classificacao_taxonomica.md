# Classificação Taxonômica

A classificação taxonômica é o processo de identificar quais organismos (bactérias, arquéias, vírus, fungos, etc.) estão presentes em nossas amostras de metagenoma e em que abundância relativa.

## Pipeline Geral

Nosso fluxo de trabalho padrão para a classificação taxonômica envolve as seguintes etapas:

- **Controle de Qualidade (QC)**: Remoção de reads de baixa qualidade e adaptadores usando ferramentas como `fastp` ou `Trimmomatic`.
- **Remoção de Contaminação do Hospedeiro**: (Se aplicável) Alinhamento das reads contra o genoma do hospedeiro (ex: plantas de restinga ou mangue) para remover sequências não-microbianas.
- **Classificação**: Utilização de ferramentas como `Kraken2`, `Kaiju` ou `MetaPhlAn` para atribuir taxonomia às reads.

## Ferramentas Utilizadas

### Kraken2

- **Descrição**: Kraken2 é um classificador taxonômico ultrarrápido que usa k-mers para mapear reads contra um banco de dados de genomas microbianos.
- **Banco de Dados Padrão**: Utilizamos o banco de dados padrão do Kraken2, que inclui genomas completos de bactérias, arquéias e vírus do RefSeq.
- **Comando Exemplo**:

```bash
kraken2 --db /path/to/krakendb --threads 8 --report report.txt --output kraken.out paired_reads_1.fastq paired_reads_2.fastq
```

### Bracken

- **Descrição**: Bracken (Bayesian Reestimation of Abundance with KrakEN) é usado para reestimar a abundância em nível de espécie a partir dos resultados do Kraken2.
- **Comando Exemplo**:

```bash
bracken -d /path/to/krakendb -i report.txt -o bracken_species.txt -r 150 -l S
```

