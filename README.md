# Prevendo o comportamento da segunda onda de COVID-19 no Brasil utilizando Evolução Diferencial e combinação de pacotes de onda Gaussianos.

  *Analysis of time series datasets of recorded cases and deaths from COVID-19 and cases and deaths from SARS (severe acute respiratory syndrome) using Differential Evolution and the combination of Gaussian wave packets to forecast the behavior of the second wave of COVID-19 in Brazil.*

  Análise de datasets contendo séries temporais de casos e óbitos registrados de Covid-19 e casos e óbitos por SRAG (síndrome respiratória aguda grave) utilizando Evolução Diferencial e combinação de pacotes de onda gaussianos na previsão do comportamento da segunda onda de COVID-19 no Brasil.

## Sobre ED, Gaussianas e COVID-19:

 Evolução Diferencial é um algorítmo evolutivo simples da categoria de algorítmos meta-heurísticos, que através da criação de populações de soluções, suas seleções e recombinações, é capaz de obter um solução ótima ou aproximadamente ótima para um problema.
 
 Desde que tenhamos dados o suficiente, é possível, facilmente, utilizar Evolução Diferencial para ajustar curvas/séries temporais provenientes de fenômenos físicos, por exemplo. Assim, podemos ajustar curvas geradas por fenômenos antropológicos como os relacionados ao COVID-19, desde que escolhamos um modelo matemáticos conveniente, que possa ser ajustado aos dados.

 Pelo Teorema do Limite Central, podemos encontrar que utilizar uma função de distribuição Gaussiana pode aproximar a solução de nosso problema já que variáveis aleatórias independentes podem estar gerando nosso conjunto de dados (na verdade, estas variáveis no caso da análise de dados de COVID-19 são tão independentes assim, logo, o ideal seria utlizar alguma função de distruibuição correspondente à uma Gaussiana Modificada). Apesar de não ser a melhor opção neste caso, podemos utilizar a sobreposição de dois pacotes gaussianos como função objetiva na solução de nosso problema de otimização com Evolução Diferencial. Assim, simplificadamente, podemos escrever:
 
 *f(&alpha;<sub>1</sub>, &beta;<sub>1</sub>, &gamma;<sub>1</sub>, &alpha;<sub>2</sub>, &beta;<sub>2</sub>, &gamma;<sub>2</sub>) = &alpha;<sub>1</sub>exp[-(x-&beta;<sub>1</sub>)^2/2&gamma;<sub>1</sub>^2] + &alpha;<sub>2</sub>exp[-(x-&beta;<sub>2</sub>)^2/2&gamma;<sub>2</sub>^2]*

 E encontrar os parâmeros que melhor ajustam a curva do modelo aos devidos dados utilizando Evolução Diferencial como algoritmo de otimização.

## Ajustando casos de COVID-19:

## Ajustando óbitos por COVID-19:

## Ajustando casos de SRAG:

## Ajustando óbitos por SRAG:

## Prevendo o pior momento da segunda onda de COVID-19 no Brasil:

## ETAPA 1: Visualizar os dados:

  Os dados utilizados nesta parte do projeto são provenientes do site: 'https://bigdata-covid19.icict.fiocruz.br/', que é administrado pelo ICICT (Instituto de Comunicação e Informação Científica e Tecnológica em Saúde) e possui relações com a Fundação Oswaldo Cruz (Fiocruz). Estes dados, por ventura, são uma fração dos dados contidos na plataforma 'InfoGripe' da Fiocruz. (Olhar referências)
  
  Inicialmente, analisaremos o *dataset* referente à mortes causadas por Síndrome Respiratória Aguda (SRAG) durante os anos 2018, 2019 e 2020 (até a 18ª semana epidemiológica). Donde podemos obter o sequinte gráfico:
  
  Gráfico antigo:
  
  <p align="center">
  <img src="obitos_srag_semana_epidemiologica_brasil.png" align=middle/>
  </p>
  
  Gráfico atualizado (03/01/2021):
  
  <p align="center">
  <img src="obitos_semana_epidemiologica_brasil_new.png" align=middle/>
  </p>
  
## ETAPA 2: Estimar uma série temporal de mortes causadas por COVID-19 (junto a problemas advindos da pandemia) a partir dos dados anteriores:

  A metodologia foi obter médias dos casos (morte por SRAG) dos anos anteriores disponíveis (2018 e 2019) e gerar uma "curva" para que, então, subtraiamos da "curva" de mortes do ano decorrente (2020), e assim obtenhamos uma nova séries temporal de pontos correspondentes à uma estimativa de mortos por SRAG causada por COVID-19. Os resultados foram os seguintes:
  
  Gráfico antigo:
  
  <p align="center">
  <img src="estimativa_obitos_covid_19.png" align=middle/>
  </p>

  Gráfico atualizado (03/01/2021):
  
  <p align="center">
  <img src="obitos_semana_epidemiologica_brasil_media_new.png" align=middle/>
  </p>

  *Obs: é de se notar que quanto mais anos tivessemos para gerar a "curva média" mais bem comportada ela ficaria, desta forma, pode ser de senso comum que o ajuste de uma curva gaussiana poderia solucionar esse problema. Porém, desta forma correriamos o risco de perder informação que estaria contida em uma "curva média" ideal. Assim, foi decidido deixar a "curva média" da forma que está. Onde uma solução válida seria adicionar dados de anos anteriores, para que assim a "curva média" corresponda fielmente à realidade.*

## ETAPA 3: Estimar mortes subnotificadas causadas por COVID-19:

  Podemos obter a quantidade de mortes por SRAG esperadas por ano tomando a média dos pontos da curva de média de mortes dos anos 2018 e 2019. Fazendo o somatório dos valores da série temporal da média e dos casos de morte do ano de 2020 (até a 18ª semana epidemiológica) podemos obter a diferença, que corresponderá à uma estimativa do número de mortes causadas exclusivamente por fatores advindos do COVID-19.
 
   **Resultados atualizados (03/01/2021):**
  
  - Mortes decorrentes de SRAG esperadas por ano: 5403.0 
  - Mortes decorrentes de SRAG até a 50ª semana epidemiológica: 5336.0  
  - Estimativa de mortes decorrentes de COVID-19 até a 50ª semana epidemiológica: 252620.0
  - Óbitos confirmados por COVID-19 até a 50ª semana epidemiológica: 182110.0
  - Estimativa de mortes por COVID-19 que não foram catalogadas como tal: 70510.0 
  - Porcentagem de mortes por COVID-19 subnotificadas: 27.9114876% 
  
## Referências:

* **"MonitoraCovid-19"** https://bigdata-covid19.icict.fiocruz.br/; (Visualizado em: 03/01/2021) (Daqui foram obtidos os *datasets* utilizados.

* **"InfoGripe"** http://info.gripe.fiocruz.br/; (Visualizado em: 16/05/2020) (Onde os dados são divulgados originalmente. Daqui é possível obter *datasets* mais robustos com registros até o ano de 2009).
