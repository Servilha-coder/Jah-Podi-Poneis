# Jah'Podi Pôneis - Trabalho Semestral de Aprendizado de Máquina

## Introdução

O objetivo deste trabalho é utilizar modelos e estratégias de aprendizado de máquina para prever o band gap de materiais de duas formas distintas:

1. Utilizando como features apenas a proporção molar dos materiais.
2. Utilizando como features a proporção molar multiplicada pelos valores de eletronegatividade dos átomos que compõem os materiais.

O dataset utilizado é o `expt_gap` da biblioteca matminer, que contém diversas propriedades termoelétricas, incluindo o band gap. Serão treinados três modelos para cada caso: baseline, regressão Lasso e floresta aleatória.


## Descrição

## Tratamento e Organização dos Dados

1. **Tratamento do Dataset:**
   - Remoção de colunas não utilizadas e linhas com valores NaN.
   - Utilização da biblioteca pymatgen para criar uma lista de dicionários representando as composições em proporção molar.
   - Adição de colunas ao dataframe para cada elemento químico presente no dataset.

2. **Eletronegatividade:**
   - Uso do módulo mendeleev para obter os valores de eletronegatividade de Pauling dos elementos.
   - Criação de colunas contendo a proporção molar multiplicada pela eletronegatividade de cada átomo.

3. **Separção de Features:**
   - Divisão dos conjuntos de features que serão utilizados nos Casos 1 e 2: `FEATURES1` contém apenas a proporção molar, `FEATURES2` contém a proporção molar multiplicada pela eletronegatividade, e `TARGET` contém o valor do band gap.

## Caso 1 - Apenas Proporção Molar

### Modelos

1. **Modelo Baseline:**
   - Utilização de um modelo dummy que prediz a média dos valores de condutividade dos dados de treino.

2. **Regressão Linear com PCA:**
   - Utilização de PCA para redução de dimensionalidade antes de treinar um modelo de regressão linear.

3. **Floresta Aleatória:**
   - Otimização de hiperparâmetros por meio de busca aleatória para um modelo de floresta aleatória.


### Resultados

- RMSE do modelo baseline: 1.71
- RMSE da regressão linear com PCA: 1.65
- RMSE da floresta aleatória otimizada: 1.21


## Caso 2 - Proporção Molar Multiplicada pela Eletronegatividade

### Modelos

1. **Modelo Baseline:**
   - Utilização de um modelo dummy que prediz a média dos valores de condutividade dos dados de treino.

2. **Regressão Lasso:**
   - Aplicação da regressão Lasso para penalizar coeficientes desnecessários.

3. **Floresta Aleatória:**
   - Otimização de hiperparâmetros por meio de busca aleatória para um modelo de floresta aleatória.

### Resultados

- RMSE do modelo baseline: 1.71
- RMSE da regressão Lasso: 1.22
- RMSE da floresta aleatória otimizada: 0.99

## Conclusão



## Dependências

- Python 3.x
- pandas
- numpy
- scikit-learn
- matminer
- pymatgen
- mendeleev

## Como Executar

1. Instale as dependências usando `pip install -r requirements.txt`.
2. Execute `python main.py` para treinar e avaliar os modelos.


## Configuração
- Configure as opções no arquivo `config.yaml` conforme necessário.

## Contribuição
Contribuições são bem-vindas! Para contribuir:
1. Faça um fork do projeto.
2. Crie uma branch para sua contribuição.
3. Faça as alterações.
4. Abra um pull request.

## Créditos
- O projeto utiliza a biblioteca `ucsb_thermoelectrics`, disponível em (https://next-gen.materialsproject.org).

## Contato
Para questões ou sugestões, entre em contato com [NOSSO EMAIL VAI AQUI].

## Badges
[![Build Status](https://travis-ci.org/Servilha-coder/Jah-Podi-Poneis.svg?branch=main)](https://travis-ci.org/Servilha-coder/Jah-Podi-Poneis)
[![Coverage Status](https://coveralls.io/repos/github/Servilha-coder/Jah-Podi-Poneis/badge.svg?branch=main)](https://coveralls.io/github/Servilha-coder/Jah-Podi-Poneis?branch=main)

## Notas de Versão
- **Versão 1.0.0 (Data):**
  - Funcionalidade principal implementada.
  
## Perguntas Frequentes (FAQ)
1. **Como posso ajustar os parâmetros do modelo?**
   - Consulte o arquivo `config.yaml` para ajustes de parâmetros.


### Agradecimentos

Agradecemos ao professor Daniel Roberto Cassar (FAPESP: https://bv.fapesp.br/pt/pesquisador/71367/daniel-roberto-cassar/) por orientar este trabalho e à comunidade de código aberto por fornecer ferramentas essenciais para pesquisa em aprendizado de máquina.

---

Este README fornece uma visão geral do trabalho realizado, dos dados utilizados, das estratégias de aprendizado de máquina adotadas e dos resultados obtidos. Para mais detalhes, consulte o código fonte e os comentários nos arquivos correspondentes.

**Jah'Podi Pôneis - Todos os direitos reservados.**
