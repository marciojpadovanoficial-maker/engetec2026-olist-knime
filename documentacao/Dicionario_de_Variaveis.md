# Dicionário de Variáveis — Experimento KNIME V2

## 9º EnGeTec 2026

Este documento descreve as principais variáveis utilizadas no experimento de classificação retrospectiva de atrasos logísticos, desenvolvido no KNIME Analytics Platform com a base Brazilian E-Commerce Public Dataset by Olist (2016–2018).

## Variáveis utilizadas na classificação

| Variável | Descrição | Tipo |
|---|---|---|
| Month (Number) | Mês do pedido, representado numericamente. | Numérica |
| Day of Week (Number) | Dia da semana do pedido, representado numericamente. | Numérica |
| Year | Ano do pedido. | Numérica |
| prazo_previsto_dias | Prazo previsto para a entrega, expresso em dias. | Numérica |
| status_atraso | Variável-alvo que distingue entregas no prazo e entregas atrasadas. | Categórica |

## Modelagem

Foram avaliados três classificadores: Árvore de Decisão, Árvore de Decisão com SMOTE e Random Forest.

O SMOTE foi aplicado exclusivamente aos dados de treinamento, para tratamento do desbalanceamento das classes.

## Observações

O estudo utiliza dados históricos da Olist e realiza classificação retrospectiva. Os resultados não representam validação de previsão prospectiva.

As definições operacionais e as transformações completas devem ser consultadas no workflow KNIME V2 disponibilizado neste repositório.
