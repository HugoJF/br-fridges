# INMETRO / PBE Data Fetching

This repo uses the official Programa Brasileiro de Etiquetagem (PBE) data published by INMETRO for monthly refrigerator power consumption.

## Official endpoints

- Base site: `https://pbe.inmetro.gov.br`
- Program attributes: `https://pbe.inmetro.gov.br/integracao/api/atributos/293`
- Refrigerator item list: `https://pbe.inmetro.gov.br/integracao/api/itens/buscar-todos`
- Registro detail pages: `https://registro.inmetro.gov.br/consulta/detalhe.aspx?NumeroRegistro=<REGISTRO>&pag=1`

`293` is the PBE program id for `Refrigeradores e Assemelhados`.

## How the data is fetched

1. Fetch the attribute map for program `293`:

```bash
curl 'https://pbe.inmetro.gov.br/integracao/api/atributos/293'
```

Relevant attribute ids:

- `493` = `Volume Total (litros)`
- `494` = `Consumo de Energia Mensal (kWh/mês)`
- `499` = `Consumo Medio de Energia Mensal (kWh/mês)`
- `500` = `Classe de Eficiência Energética`
- `501` = `Índice de Eficiência Energética`

2. Fetch all refrigerator items:

```bash
curl \
  -X POST \
  -H 'Content-Type: application/json' \
  -d '{"idPrograma":293}' \
  'https://pbe.inmetro.gov.br/integracao/api/itens/buscar-todos'
```

3. Match repo models to official PBE records by:

- brand
- exact model code when possible
- grouped official model strings when the official record covers multiple variants
- registro detail page when manual confirmation is needed

## Monthly power selection rule

When both fields are present, use:

1. `499` (`Consumo Medio de Energia Mensal`)
2. else `494` (`Consumo de Energia Mensal`)

This preference reflects the newer PBE schema that appears on many current records.

## Why blanks remain

A model stays blank in `index.html` when any of these happens:

- no current official monthly value is exposed in PBE/registro
- there is no confident current PBE match for the exact model
- multiple current official variants exist with different monthly values and the repo row does not yet distinguish them cleanly

In those cases the repo keeps `kwh: null` instead of guessing.

## Human verification

Every model markdown file under `models/` should include:

- matched official model string
- registro number
- which PBE field was used (`499` or `494`)
- direct official URLs for manual re-checking

## Notes

- Retailer or manufacturer pages are useful for dimensions and features, but monthly energy consumption should come from INMETRO/PBE whenever possible.
- PBE and `registro.inmetro.gov.br` may show grouped model names, suffix variants, or multiple voltages under one registration. Always verify that the selected official record really covers the table row being filled.
