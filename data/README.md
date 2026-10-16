# Datos del curso

## `exome.vcf.gz`

Subconjunto de 1000 Genomes y del Human Genome Diversity Panel (HGDP), restringido a las regiones del exoma capturadas por el kit Agilent SureSelect Human All Exon V8.

- 969 individuos, 15 poblaciones.
- 244 305 variantes en los cromosomas 1–22, en formato GRCh38 (genotipos no faseados).
- El identificador de cada individuo empieza por su población, por ejemplo `ACB_ACB1`.

| Grupo | Poblaciones |
|---|---|
| Mezcladas (a analizar) | ACB, ASW, MXL, PUR |
| Referencia africana | YRI, ESN, GWD |
| Referencia europea | GBR, IBS, TSI |
| Referencia nativa americana | Karitiana, Maya, Pima, Surui, PEL |

En el archivo, las poblaciones de referencia llevan el prefijo `forReference`, por ejemplo `forReferenceYRI_YRI1`.

## Referencias

- 1000 Genomes Project Consortium. A global reference for human genetic variation. *Nature*. 2015;526:68–74. doi:10.1038/nature15393
- Bergström A, et al. Insights into human genetic variation and population history from 929 diverse genomes. *Science*. 2020;367:eaay5012. doi:10.1126/science.aay5012
