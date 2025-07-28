# 🎓 Dashboard – Censo da Educação Superior 2023

Este dashboard foi desenvolvido a partir dos microdados do Censo da Educação Superior de 2023, com o objetivo de **fornecer uma visão analítica sobre os cursos de graduação ofertados no Brasil**, suas instituições, perfis de alunos e distribuição territorial.

---

## Objetivo

O principal propósito deste painel é **explorar e visualizar de forma intuitiva e interativa os dados educacionais**, permitindo:

- Analisar o número de **ingressantes, matriculados e concluintes** por curso, instituição e estado;
- Avaliar a **oferta de vagas** e o volume de **inscrições**;
- Comparar o desempenho entre instituições **públicas e privadas**, por categoria administrativa e localização;
- Destacar **áreas temáticas** como Engenharia, Saúde, Licenciaturas, entre outras;
- Identificar **tendências regionais** e **perfil das IES** por campus e município;
- Apoiar **tomadores de decisão, gestores educacionais e pesquisadores** com indicadores claros e confiáveis.

> **Observação**:  
> Todos os cruzamentos e cálculos deste projeto são realizados **diretamente no Power BI**, por meio de medidas DAX e modelagem de dados. **Não há uso de queries SQL** para transformações ou junções.

---

## 🔍 O que você vai encontrar no dashboard

- Visão geral da rede pública e privada
- Distribuição por modalidade (presencial vs EAD)
- Destaque para áreas como Engenharia
- Análises por estado, município e instituição
- Classificação de cursos e instituições com filtros interativos

---

## 📊 Acesse o Dashboard

- 🔗 [Clique aqui para visualizar o dashboard no Power BI](https://app.powerbi.com/view?r=eyJrIjoiYTVhYjU0ZTktMjFkZC00OTkwLWE3N2MtMjNmZWE5YTEwMjg1IiwidCI6IjI4MTgxNWViLWUwYjgtNGY2Yi1iMmRjLTBiY2U1ODQwMDI5NiJ9)

[![Dashboard do Censo da Educação Superior](https://github.com/marianamoledo/censo_educacao_superior/blob/main/print_dash_censo_educacao.png?raw=true)](https://app.powerbi.com/view?r=eyJrIjoiYjFhMDBkNWItODAyMi00OGE5LTg4MzItNjlhYWIyZGM2ZjM5IiwidCI6IjI4MTgxNWViLWUwYjgtNGY2Yi1iMmRjLTBiY2U1ODQwMDI5NiJ9)


---

## Fonte dos Dados

- **Microdados do Censo da Educação Superior 2023** – INEP/MEC  
  Disponível para download no portal oficial do INEP/MEC:  
  https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/censo-da-educacao-superior
  
---

### Cruzamentos realizados na consulta `MICRODADOS_CADASTRO_CURSOS_2023`

#### 1. Com a tabela `CLASS_CURSOS`
- **Chave de junção:** `NOME DO CURSO` (convertido para maiúsculas)
- **Objetivo:** Classificar os cursos conforme áreas gerais, específicas e detalhadas, adicionando uma coluna `CLASS`.
- **Transformação aplicada:** Após a normalização do nome do curso (`Text.Upper`), foi feito um `Merge` com a tabela `CLASS_CURSOS` para adicionar as colunas de classificação.

#### 2. Com a tabela `DE/PARA CAMPUS`
- **Chave de junção:** coluna criada `IES/MUNICIPIO/CURSO`, que concatena `NOME IES`, `MUNICIPIO` e `NOME DO CURSO`.
- **Objetivo:** Traduzir ou agrupar variações nos nomes dos campi para fins de padronização.
- **Transformação aplicada:** Foi feita a junção (`Merge`) com a tabela `DE/PARA CAMPUS`, adicionando a coluna `CAMPUS`.

#### 3. Com a tabela `Campus Concatenado`
- **Chave de junção:** coluna `IES/MUNICIPIO`, que concatena `NOME IES` e `MUNICIPIO`.
- **Objetivo:** Associar cada entrada com a versão padronizada do nome do campus do município.
- **Transformação aplicada:** Novo `Merge` com a tabela `Campus Concatenado`, adicionando a coluna `Campus do Município`.

#### Resumo das colunas adicionadas via cruzamento:

| Fonte                  | Colunas adicionadas                                                 | Observação                                             |
|------------------------|---------------------------------------------------------------------|--------------------------------------------------------|
| `CLASS_CURSOS`         | `AREA_GERAL`, `AREA_ESPECIFICA`, `AREA_DETALHADA`, `CLASS`         | Base usada para categorizar os cursos.                 |
| `DE/PARA CAMPUS`       | `CAMPUS`                                                            | Alinha variações de campus por curso e município.      |
| `Campus Concatenado`   | `Campus do Município`                                               | Padroniza a descrição do campus com base na IES e local. |
---

