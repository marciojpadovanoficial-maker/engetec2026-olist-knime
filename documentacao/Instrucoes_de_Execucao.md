# Instruções de Execução — Workflow KNIME V2

## 1. Objetivo

Este documento apresenta orientações para importar e executar o workflow KNIME utilizado no estudo de classificação retrospectiva de atrasos logísticos no comércio eletrônico brasileiro, desenvolvido para o 9º EnGeTec 2026.

## 2. Requisitos

- KNIME Analytics Platform.
- Extensões necessárias aos nós utilizados no workflow, incluindo o nó SMOTE.
- Arquivos CSV da base Brazilian E-Commerce Public Dataset by Olist, disponíveis no Kaggle.
- Recursos computacionais suficientes para processar e integrar os arquivos da base.

## 3. Base de dados

Fonte: Brazilian E-Commerce Public Dataset by Olist.

Período: 2016–2018.

A base original contém 99.441 registros de pedidos. Após o tratamento e a aplicação dos critérios do experimento, foram considerados 96.476 pedidos elegíveis.

Os arquivos originais devem ser obtidos na fonte pública e mantidos em uma pasta local.

## 4. Importação do workflow

1. Baixar o arquivo .knwf disponível na pasta workflow-knime deste repositório.
2. Abrir o KNIME Analytics Platform.
3. Utilizar a opção de importação de workflows e selecionar o arquivo .knwf.
4. Abrir o workflow importado.

## 5. Configuração dos dados

1. Localizar os nós de leitura dos arquivos CSV.
2. Ajustar os caminhos dos arquivos para as respectivas pastas locais.
3. Verificar se os nós de leitura reconhecem corretamente as colunas e os tipos de dados.
4. Instalar eventuais extensões solicitadas pelo KNIME.

## 6. Processamento e modelagem

O experimento contempla as seguintes etapas:

- Importação e integração das tabelas da Olist.
- Tratamento dos dados e construção da variável de atraso.
- Engenharia e seleção de atributos.
- Particionamento dos dados.
- Aplicação do SMOTE exclusivamente ao conjunto de treinamento.
- Treinamento dos classificadores Árvore de Decisão, Árvore de Decisão com SMOTE e Random Forest.
- Avaliação por matrizes de confusão e métricas de classificação.
- Exportação dos resultados.

## 7. Variáveis utilizadas

Os atributos explicativos utilizados na modelagem são:

- Month (Number)
- Day of Week (Number)
- Year
- prazo_previsto_dias

Variável-alvo: status_atraso.

Consulte o arquivo Dicionario_de_Variaveis.md, na pasta documentacao, para obter mais informações.

## 8. Resultados de referência

O conjunto de avaliação contém 28.943 pedidos:

- No prazo: 26.982.
- Atrasados: 1.961.

Na avaliação registrada, a Árvore de Decisão com SMOTE apresentou aproximadamente:

- Acurácia: 78,09%.
- Precisão para atrasos: 15,31%.
- Recall para atrasos: 49,31%.
- F1-score para atrasos: 23,37%.

A Árvore de Decisão original e o Random Forest não identificaram casos atrasados no conjunto de avaliação.

A tabela comparativa encontra-se na pasta resultados.

## 9. Limitações e reprodutibilidade

O estudo realiza classificação retrospectiva sobre dados históricos, não constituindo validação de previsão prospectiva.

Não foram aplicadas validação cruzada nem otimização sistemática de hiperparâmetros nesta versão.

A reprodução dos resultados depende da configuração correta das fontes de dados, das extensões e das conexões do workflow. Os resultados apresentados são referências do experimento original, não garantia de reprodução idêntica em qualquer ambiente.

## 10. Finalidade

O workflow e sua documentação são disponibilizados para fins acadêmicos, de transparência metodológica e de apoio à reprodutibilidade científica.
