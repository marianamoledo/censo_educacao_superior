## Processamento de Dados em Arquivos CSV do Censo Educacional Superior

Ao longo do tempo, é importante notar que a estrutura dos arquivos CSV pode ter mudado. Neste repositório, você encontrará um conjunto de scripts em Python que realizam diversas operações de processamento de dados em arquivos CSV relacionados ao censo educacional superior. O objetivo principal desses scripts é tratar e criar uma base de dados consolidada com informações desde 2009, abrangendo tanto os arquivos do `MICRODADOS_CADASTROS_CURSO` quanto do `MICRODADOS_ED_SUP_IES`.

### MICRODADOS_CADASTROS_CURSO

### Visão Geral do Código

1. **Listagem e Exploração de Arquivos CSV**: Os scripts listam os arquivos CSV em um diretório específico e exploram as colunas de cada arquivo para entender a estrutura dos dados.

2. **Contagem de Colunas e Linhas**: Os scripts contam o número de colunas e linhas em cada arquivo CSV, fornecendo informações sobre a dimensão dos dados.

3. **Identificação de Diferenças nas Colunas**: Comparamos as colunas de diferentes arquivos CSV para identificar discrepâncias na estrutura dos dados, garantindo consistência nos dados ao longo do tempo.

4. **Fusão de Dados**: Aqui os dados dos arquivos CSV desde 2009 são combinados em um único DataFrame para futuras análises.

### MICRODADOS_ED_SUP_IES

### Visão Geral do Código

1. **Exploração dos Dados**: Os scripts exploram os arquivos CSV do `MICRODADOS_ED_SUP_IES`, listando os arquivos e extraindo informações sobre as colunas de cada arquivo.

2. **Contagem de Colunas**: Contamos o número de colunas em cada arquivo CSV, fornecendo informações sobre a dimensão dos dados.

3. **Identificação de Diferenças nas Colunas**: Os scripts comparam as colunas de diferentes arquivos CSV para identificar discrepâncias na estrutura dos dados ao longo do tempo.

4. **Fusão de Dados**: Aqui os dados dos arquivos CSV desde 2009 são combinados em um único DataFrame para futuras análises.

### Contribuições

Contribuições são bem-vindas! Se você tiver ideias de como melhorar ou estender esses scripts, sinta-se à vontade para abrir um pull request ou criar uma issue neste repositório.
