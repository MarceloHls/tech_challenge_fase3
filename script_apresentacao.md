# Script de Apresentação — Tech Challenge Fase 3

---

## ABERTURA
*"O projeto é sobre prever se um voo vai atrasar ou não, usando dados de voos domésticos dos EUA em 2015."*

---

## CÉLULA 1 — Imports
*"Aqui só carrego as bibliotecas que vou usar."*

---

## CÉLULA 2 — Carga dos dados
*"O arquivo tem 5 milhões de voos, então carrego uma amostra de 200 mil para ficar rápido. Também carrego as tabelas de companhias e aeroportos."*

---

## CÉLULA 3 — Visão geral
*"Aqui vejo o shape, os tipos de coluna e as estatísticas básicas — média, mínimo, máximo."*

---

## CÉLULA 4 — Valores ausentes
*"Colunas de causa de atraso têm muitos valores vazios porque só são preenchidas quando o voo atrasa. Não é erro, é o comportamento esperado."*

---

## CÉLULA 5 — Distribuição do atraso
*"A maioria dos voos chega no prazo. A linha vermelha é o limite de 15 minutos — acima disso, o voo é considerado atrasado. Cerca de 30% dos voos atrasam."*

---

## CÉLULA 6 — Atraso por companhia
*"Cada companhia tem uma taxa diferente. Algumas passam de 35%, outras ficam em 20%. Isso reflete a operação de cada uma."*

---

## CÉLULA 7 — Atraso por dia e mês
*"Sexta e domingo são os piores dias — mais passageiros. Junho e julho são os piores meses — verão americano e férias."*

---

## CÉLULA 8 — Aeroportos mais críticos
*"Top 15 aeroportos com maior taxa de atraso, filtrando só os que têm volume suficiente de voos para a comparação ser justa."*

---

## CÉLULA 9 — Preparação dos dados
*"Removo voos cancelados, crio a hora de partida a partir do formato HHMM, crio o período do dia, e converto texto em número porque o modelo só aceita número."*

---

## CÉLULA 10 — Treinamento
*"Divido em 80% treino e 20% teste.*

*Treino dois modelos:*

**Regressão Logística:**
*"É o modelo mais simples. Ele olha para todas as características do voo — hora, mês, companhia, distância — e tenta encontrar uma combinação matemática que separe os voos atrasados dos pontuais. É como traçar uma linha divisória entre dois grupos. Rápido, fácil de entender, mas limitado para padrões mais complexos."*

**Random Forest:**
*"É um modelo mais poderoso. Ele cria 100 árvores de decisão diferentes — cada árvore é como uma sequência de perguntas: 'o voo é de sexta? a distância é maior que 1000km? a companhia é X?' — e no final todas as árvores votam juntas. A resposta final é a que a maioria escolheu. Por usar muitas árvores, ele consegue capturar padrões que a Regressão Logística não enxerga."*

---

## CÉLULA 11 — Métricas
*"Avalio os dois com precision, recall, F1 e ROC-AUC. O Random Forest ficou melhor, com AUC em torno de 0.65. Não é perfeito porque não temos dados de clima, que é a maior causa de atraso."*

---

## CÉLULA 13 — Importância das features
*"O Random Forest me diz quais variáveis mais influenciaram. Distância e hora de partida foram as mais importantes."*

---

## CÉLULA 14, 15, 16, 17 — Clustering (não supervisionado)
*"Aqui não tenho target. Uso KMeans para agrupar aeroportos com perfil parecido de atraso.*

*Uso o Elbow Method para escolher 4 grupos. Como os dados têm 4 dimensões, uso PCA para visualizar em 2D.*

*Resultado: 4 perfis — grandes hubs com muito atraso, aeroportos médios, regionais pequenos e pontuais, e os mais imprevisíveis."*

---

## CONCLUSÃO
*"Random Forest foi melhor que Regressão Logística. A performance é moderada porque falta dado de clima. O clustering mostrou 4 perfis claros de aeroportos. Próximo passo seria adicionar clima e testar XGBoost."*

---
