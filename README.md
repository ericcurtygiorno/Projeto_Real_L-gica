# Projeto_Real_Logica
## Introdução:

### Ideia inicial do projeto:
+ Identificar os tipos de clientes da empresa para o melhor entendimento/direcionamento do marketing da empresa, gerando menos custos e maior assertividade nas mensagens.

### O projeto foi executado através do CRISP-DM:
+ Entendimento do Negócio
+ Entendimento dos Dados
+ Preparação dos Dados
+ Modelagem
+ Avaliação do Modelo
+ Deployment

OBS: A etapa de Deployment não foi necessária, pois atingimos o objetivo do projeto anteriormente.

### Bases disponibilizadas:
+ Base Clientes (por todo o período da empresa)
+ Base Pedidos (01/01/2022~30/06/2022)
+ Base Produtos Vendidos (01/01/2022~30/06/2022)
+ Base Vouchers (01/01/2022~30/06/2022)
+ Base Jornada do Cliente (01/01/2022~30/06/2022)

## O Projeto:

### Bibliotecas utilizadas:
+ Pandas
+ Numpy
+ Matplotlib
+ Seaborn
+ Scikit Learn
+ Scipy
+ ExplainerDashboard

#### Executamos uma limpeza e preparação de dados em cada base e buscamos entender cada uma delas a ponto de encontrar algumas oportunidades de melhorias para a empresa:
+ Base de Produtos Vendidos identificamos problemas em relação às categorias dos produtos. Existiam diversas formas escritas para o mesmo tipo de categoria e categorias com o mesmo sentido.
+ Base Jornada do Cliente onde 60367 (21,59%) dos dados eram duplicados.

## Aplicação do modelo:
#### Como era um projeto para identificar tipos de clientes, logo associamos a Clusterização, sendo assim pensamos de cara em utilizar o K-Means, visto que é um dos modelos mais utilizados para esse tipo de modelo não supervisionado.
#### Foi solicitado que usávemos o RFV (Recência, Frequência e Valor) para aplicação do modelo e assim o executamos.

#### Para o modelo utilizamos duas bases principais: Base Jornada do Cliente e Base Produtos Vendidos.
#### Após juntar as bases criamos o RFV das bases onde o R seria quantos dias o cliente não retorna a loja, o F a quantidade de itens comprados pelo cliente e V a soma dos valores de cada item comprado por cliente, sendo assim finalizamos nossa base para dar início a aplicação do modelo.
#### Aplicamos o Standard Scaler para Standardização das variáveis e o Método de Elbow para identificar a quantidade de Clusters que utilizaríamos para a análise.

#### Executamos 4 modelos através do K-Means:
+ K-Means com 4 Clusters e sem tratamento de outliers (Silhouetter Score: 77,7%)
+ K-Means com 5 Clusters e sem tratamento de outliers (Silhouetter Score: 73,6%)
+ K-Means com 4 Clusters e com tratamento de outliers (Silhouetter Score: 71,9%)
+ K-Means com 5 Clusters e com tratamento de outliers (Silhouetter Score: 60,4%)
##### Selecionamos o modelo com 5 Clusters e tratamento de outliers. Essa decisão foi feita junto com a empresa, sendo o modelo que mais fazia sentido para o negócio.

#### Logo em seguida aplicamos um modelo de GaussianMixture para comparar com o modelo selecionado.
Aplicamos um Decision Tree em ambos os modelos para poder verificar a influência das variáveis em cada Cluster. 
No K-Means cada Cluster tinha uma variável que tinha a maior porcentagem e as outras também tinham uma certa influência.
Já no GaussianMixture todos os Clusters tinha a variável valor como sua maior influência, logo acabava não fazendo sentido para nós um modelo onde somente um variável tinha influência nos Clusters.

## Conclusão do Projeto:
Dentre todos os modelos testados, o modelo Kmeans com 5 Clusters e com tratamento de outliers foi o modelo que fez mais sentido para o negócio. Desta forma, será o modelo utilizado pela empresa para melhor direcionamento do seu marketing, tendo em vista a diminuição de custos e maior assertividade no contato com o cliente e seu retorno às lojas.

## Apresentação do modelo selecionado em PowerBI:
![pbi github](https://user-images.githubusercontent.com/122547865/212483325-8bb7869d-dbc2-4b20-8882-99ec8e85623a.png)
