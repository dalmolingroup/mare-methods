# Anotação Funcional

A anotação funcional é o processo de atribuir funções biológicas aos genes previstos nos nossos dados de metagenoma, seja a partir dos contigs montados ou diretamente das reads.  
Isso nos ajuda a entender o potencial metabólico da comunidade microbiana.

## Pipeline Geral

- **Mapeamento de Vias Metabólicas**: Associação dos genes anotados a vias metabólicas conhecidas para entender os processos bioquímicos que a comunidade pode realizar.

## Ferramentas e Bancos de Dados

### eggNOG-mapper

- **Descrição**: eggNOG-mapper é uma ferramenta para anotação funcional rápida baseada em ortologia. Ela fornece anotações COG (Clusters of Orthologous Groups), KOs do KEGG, e anotações Gene Ontology (GO).
- **Comando Exemplo**:

```bash
emapper.py -i protein_sequences.faa -o eggnog_annotations --cpu 8
```

