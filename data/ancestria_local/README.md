# Datos para ancestría local (semana 5)

Generados con [`notebooks/preparar_datos_ancestria_local.ipynb`](../../notebooks/preparar_datos_ancestria_local.ipynb) a partir del panel HGDP + 1000 Genomas faseado con SHAPEIT5 (Koenig et al., 2024). Solo cromosoma 22, GRCh38, SNPs bialélicos con frecuencia del alelo menor ≥ 5 %: **81 350 SNPs**.

## Poblaciones

| Rol | Poblaciones | Personas |
|---|---|---|
| Consulta (mezcladas) | CLM (Medellín), MXL (ascendencia mexicana), PUR (Puerto Rico), PEL (Lima) | 345 |
| Referencia africana (AFR) | YRI (Ibadán, Nigeria) | 118 |
| Referencia europea (EUR) | IBS (España) | 104 |
| Referencia nativa americana (NAT) | Karitiana, Pima, Surui y Colombian (HGDP) | 41 |

Los Maya de HGDP **no** se usan como referencia: analizados con RFMix como si fueran personas mezcladas, 8 de 21 tenían más de 5 % de ancestría no nativa en el cromosoma 22 (uno, 41 % europea). Una referencia mezclada haría que RFMix confundiera segmentos europeos con nativos americanos.

En las referencias nativas americanas tampoco se aplica el filtro de parentesco de gnomAD: son poblaciones pequeñas y aisladas con muchos parientes entre sí, y con el filtro quedaban solo 2 Karitiana y 1 Surui. En una referencia importa más cubrir la diversidad de haplotipos.

## Archivos

| Archivo | Qué es |
|---|---|
| `chr22_consulta.vcf.gz` (+ `.tbi`) | Haplotipos faseados de las 345 personas mezcladas |
| `chr22_consulta_clase.vcf.gz` (+ `.tbi`) | Las 10 personas de CLM que se analizan en vivo en la clase |
| `chr22_referencia.vcf.gz` (+ `.tbi`) | Haplotipos faseados de las 263 personas de referencia |
| `sample_map.txt` | Para RFMix: cada persona de referencia y su ancestría (AFR, EUR o NAT) |
| `poblaciones.tsv` | Población, proyecto y rol de cada persona |
| `genetic_map_chr22_GRCh38.txt` | Mapa genético del cromosoma 22 en formato RFMix, distribuido con Eagle |
| `rfmix_todos.msp.tsv.gz` | Ancestría local de las 345 personas, ya calculada |
| `rfmix_todos.rfmix.Q` | Ancestría global de las 345 personas, calculada por RFMix |

## Cómo se calcularon los resultados precalculados

```
rfmix -f chr22_consulta.vcf.gz \
      -r chr22_referencia.vcf.gz \
      -m sample_map.txt \
      -g genetic_map_chr22_GRCh38.txt \
      -o rfmix_todos \
      --chromosome=chr22 \
      --n-threads=2 -w PESO -t 50
```

`PESO` es el valor que RFMix calibra solo (`Maximum scoring weight`) y que el cuaderno de la sesión 5 reutiliza para no repetir esa calibración, que tarda varios minutos. El valor exacto está en el cuaderno.

## Referencias

- Koenig Z, et al. A harmonized public resource of deeply sequenced diverse human genomes. *Genome Res*. 2024;34(5):796. doi:10.1101/gr.278378.123
- Maples BK, et al. RFMix: a discriminative modeling approach for rapid and robust local-ancestry inference. *Am J Hum Genet*. 2013;93:278–288. doi:10.1016/j.ajhg.2013.06.020
- Loh PR, et al. Reference-based phasing using the Haplotype Reference Consortium panel. *Nat Genet*. 2016;48:1443–1448. doi:10.1038/ng.3679
- Byrska-Bishop M, et al. High-coverage whole-genome sequencing of the expanded 1000 Genomes Project cohort including 602 trios. *Cell*. 2022;185:3426–3440. doi:10.1016/j.cell.2022.08.004
- Bergström A, et al. Insights into human genetic variation and population history from 929 diverse genomes. *Science*. 2020;367:eaay5012. doi:10.1126/science.aay5012
