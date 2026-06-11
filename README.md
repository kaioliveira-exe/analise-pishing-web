# Análise de Dados: Detecção de Phishing em Páginas Web

## Sobre o Projeto
Este projeto foi desenvolvido para analisar e identificar padrões em URLs fraudulentas (Phishing). O objetivo é entender quais características estruturais de uma URL (como tamanho, uso de caracteres especiais e redirecionamentos) servem como indicadores estatísticos de que um site é falso e tenta enganar usuários.

A análise simula um cenário real de engenharia de dados, onde as informações originais do dataset *'Web Page Phishing Dataset'* (Kaggle) foram divididas e armazenadas em duas tabelas relacionais em um banco SQLite, sendo unificadas via consulta SQL para a extração dos insights.

## Tecnologias e Ferramentas Utilizadas
* **Python (Pandas, Seaborn e Matplotlib):** Utilizados para manipulação das tabelas, análise estatística de correlação e visualização de distribuição (Boxplots).
* **SQL (SQLite):** Utilizado para realizar a junção (`INNER JOIN`) das tabelas relacionais emulando um ambiente de banco de dados em produção.

## Principais Insights
1. Quais campos têm maior e menor correlação com Phishing?

O número de barras (n_slash) e o número de hifens (n_hypens) apresentam as maiores correlações positivas. Isso faz sentido, pois criminosos criam subpastas e estruturas longas para imitar domínios reais. Por outro lado, caracteres como (~), (,) e (*) têm correlação praticamente nula ou irrelevante, indicando que não são padrões comuns utilizados para mascarar fraudes.

2. O comprimento da URL (url_length) é um forte indicador?

Não necessariamente. Embora exista uma leve tendência de variação, a análise de quartis (.describe()) e a identificação de outliers via Boxplot mostram que o comprimento médio não é um fator decisivo isolado. URLs legítimas de e-commerce ou portais de notícias também costumam ser muito longas, o que invalida o comprimento puro como uma métrica de bloqueio.

3. Como decifrar se uma URL é Phishing?

Atenção aos Caracteres de Máscara: Monitore a presença excessiva de hifens e barras. Phishings costumam usar hifens para criar nomes falsos parecidos com empresas reais (ex: suporte-netflix-br.com).

Não confie apenas no tamanho da URL: Muitas ferramentas bloqueiam sites só por serem longos, mas os dados provam que isso gera falsos positivos.


## Estrutura do código

scripts/main.ipynb: Jupyter Notebook documentado contendo a criação do banco .db, ingestão das tabelas e análise estatística/gráfica completa.




