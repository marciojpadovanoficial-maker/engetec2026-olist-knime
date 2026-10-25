# Classificação de Atrasos Logísticos no Comércio Eletrônico Brasileiro

**9º EnGeTec 2026 | Experimento científico desenvolvido no KNIME Analytics Platform**

## Sobre o projeto

Este repositório documenta um experimento de classificação retrospectiva de atrasos de entrega no comércio eletrônico brasileiro, utilizando técnicas de aprendizado de máquina implementadas no KNIME Analytics Platform.

O estudo utiliza a base pública Brazilian E-Commerce Public Dataset by Olist, referente ao período de 2016 a 2018.

## Objetivo

Comparar o desempenho de três configurações de classificação na identificação de entregas atrasadas, considerando o desbalanceamento entre entregas no prazo e atrasadas.

## Base de dados

- Fonte: Brazilian E-Commerce Public Dataset by Olist (Kaggle).
- Período: 2016–2018.
- Registros originais de pedidos: 99.441.
- Pedidos elegíveis após tratamento: 96.476.
- Conjunto de avaliação: 28.943 pedidos, sendo 26.982 no prazo (93,22%) e 1.961 atrasados (6,78%).

## Metodologia

O processamento foi realizado no KNIME Analytics Platform, abrangendo importação e integração de dados, tratamento, engenharia de atributos, definição da variável-alvo, particionamento, treinamento, classificação e avaliação.

Foram avaliadas três configurações:

1. Árvore de Decisão sem SMOTE.
2. Árvore de Decisão com SMOTE aplicado somente aos dados de treinamento.
3. Random Forest sem SMOTE.

A variável-alvo distingue entregas **No prazo** e **Atrasada**. Os atributos explicativos utilizados foram mês, dia da semana, ano e prazo previsto de entrega em dias.

## Resultados do conjunto de avaliação

| Modelo | Acurácia | Precisão para atrasos | Recall para atrasos | F1 para atrasos |
|---|---:|---:|---:|---:|
| Árvore de Decisão | 93,22% | 0% | 0% | 0% |
| Árvore de Decisão com SMOTE | 78,09% | 15,31% | 49,31% | 23,37% |
| Random Forest | 93,22% | 0% | 0% | 0% |

A Árvore de Decisão com SMOTE identificou 967 das 1.961 entregas atrasadas no conjunto de avaliação. Os outros dois modelos não identificaram casos de atraso. Os resultados evidenciam a importância de avaliar métricas específicas da classe minoritária, e não apenas a acurácia global.

## Limitações

O experimento é retrospectivo, baseado em dados históricos de 2016 a 2018. Não foi realizada validação cruzada nem otimização sistemática de hiperparâmetros nesta versão. Os resultados não constituem comprovação de capacidade preditiva prospectiva.

## Reprodutibilidade

Os arquivos do workflow KNIME, as configurações e os resultados serão disponibilizados progressivamente neste repositório, após organização e conferência dos materiais.

## Autoria

Márcio José Padovan de Antônio — Pesquisa acadêmica em Engenharia de Produção.

## Referência da base

Olist. Brazilian E-Commerce Public Dataset by Olist. Kaggle: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
