# Inflation-Forecast-BR
## 1 - Base de Dados:
Os scripts foram desenvolvidos para que se possa fazer possíveis futuras
atualizações no modelo, assim que ele estiver “desgastado”. Nesse contexto, temos
diversas funções de carregamento de base, atualização, tratamento.
Nossa base de dados é abastecida por meio de uma api do IBGE, a qual podemos
ter acesso importando a biblioteca no python: sydrapy. Após pegar os dados do IBGE,
fazemos a tratativa dos dados para que possam ser rodados no modelo. E para a
atualização dos dados, temos uma função, a qual pega apenas as datas faltantes sem
precisar carregar a base toda de novo..Além disso, podemos utilizar outras variáveis
como por exemplo, PIB e Taxa de investimento, as quais podem ser carregadas e
adicionadas no modelo por meio das funções criadas.
## 2 - Modelos:
Para previsão da inflação medida pelo IPCA, utilizamos modelos de Regressão
Linear para prever valores dos 3 primeiros Trimestres do ano e utilizamos a média dos
valores preditos de um conjunto de modelos para prever o 4 Trimestre. A utilização de
diferentes modelos para previsão do 4 Trimestre se da pela ineficiência do modelo de
Regressão Linear captar o efeito dessa sazonalidade.
Desse modo, temos uma regressão linear estimada pelo método dos mínimos
quadrados ordinários(OLS). O método OLS, basicamente funciona minimizando o
resíduo quadrático do modelo, dessa maneira o modelo tenta ajustar os parâmetros para
um certo conjunto de dados. Vale destacar, que essa teórica tem algumas premissas,
como por exemplo que o resíduo seja uma distribuição normal e pré assume que os
paramêtros tem uma relação linear entre si e em relação a variável y.
## 3 - Features:
Em primeiro momento usei, como features para modelo escolhes a defasagem do
IPCA em 1 e 2 períodos(escolhidas por meio da autocorrelação dos resíduos), média
móvel de 3 períodos(trimestral) e 6 períodos(semestral) e dummies trimestrais.
Entretanto, ao ir descartando as variáveis sem valor significativo a 5%, sobrou apenas
IPCA, IPCA com lag de 1 e 12 e a dummie do 4 Trimestre do ano. Dessa forma, o
modelou performou melhor que muitos outros testados.
## 4 - Bibliografia:
Como fonte foi usado muito stackoverflow/google para poder criar classes e
funções e montar o dashboard em python. Em relação a parte teoria, além do
conhecimento adquirido na faculdade, os post do Analise Macro de previsão do IPCA
foram de grande utilidade, o qual deu bons insight em relação sazonalidade e pegar a
média dos y estimados por diferentes modelos, por exemplo.
## 5 - Conclusão:
Para futuras previsões vale destacar modelos e métodos mais eficientes e um
estudo mais profundo do assunto, como testar mais modelos e variáveis, o próprio
código tem funções e classes para tal procedimento.
