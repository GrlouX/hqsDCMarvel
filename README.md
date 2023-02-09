## Fonte dos dados 

Os dados originais foram obtidos das enciclopédias públicas dos personagens de histórias em quadrinhos [DC Wikia](https://dc.fandom.com/wiki/DC_Comics_Database) e [Marvel Wikia](https://marvel.fandom.com/wiki/Marvel_Database). A extração desses dados foi realizada pelo usuário da plataforma **Kaggle** AMAN CHAUHAN, que os disponibilizou para download por meio do link [FiveThirtyEight Comic Characters Dataset](https://www.kaggle.com/datasets/whenamancodes/greatest-comic-book-characters).

## Carga dos dados

Os dados baixados da fonte nos arquivos do diretório de dados "dc-wikia-data.csv" (6896 x 13) e "marvel-wikia-data.csv" (16376 x 13) foram carregados integralmente no MySQL Workbench e tratados por meio do script "dataBase_hqsDCMarvel.sql". Após os tratamentos realizados, o arquivo "comic_data.csv" (23272 x 12) foi exportado do MySQL.

## Pré-processamento dos dados

Os dados exportados na etapa anterior foram integralmente importados no RStudio para outras tarefas de limpeza e transformação, dentre as quais a exclusão de alguns valores ausentes não tratáveis, por meio do script "dataCleansing_hqsDCMarvel.r". Em seguida, os dados normalizados foram exportados do RStudio para o arquivo "comic_data_norm.csv" (22388 x 13).

## Análise e visualização dos dados

Os dados preparados foram importados para o Microsoft Power BI, com perda inferior a 5% da informação original obtida da fonte, com as seguintes variáveis:

Variáveis         | Definição
------------------|--------------
`pageid`          | Identificador de cada personagem dentro da Wikia
`name`            | Nome do personagem
`identity`        | Status da identidade do personagem (Secret, Public, Known to Authorities[Marvel], No Dual[Marvel], Unknown[DC])
`align`           | Caráter do personagem (Good, Bad, Neutral, Reformed Criminals[DC])
`eye`             | Cor dos olhos do personagem
`hair`            | Cor dos cabelos do personagem
`sex`             | Sexo ou gênero do personagem
`gsm`             | Se o personagem é de um gênero ou sexo minoritário (Homosexual, Bisexual, etc.)
`alive`           | Status de sobrevivência do personagem (Deceased x Living)
`appearances`     | Número de aparições do personagem nos quadrinhos
`firstappearance` | Ano e mês da primeira aparição do personagem nos quadrinhos
`company`         | Nome da empresa a que pertence o personagem (DC x Marvel)
`multiverse`      | Multiverso onde o personagem existe (informação extraída do nome do personagem na fonte dos dados) 

Os resultados da análise podem ser visualizados na apresentação [Personagens de Quadrinhos DC vs Marvel](https://docs.google.com/presentation/d/18TTH4GyMo73ILyN-8zn5QOnBaAqFbM2_2G6_K6FJvB8).

