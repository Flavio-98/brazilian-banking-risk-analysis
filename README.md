# 🏦 Segmentação e Análise de Risco de Bancos Brasileiros

Este projeto utiliza **Ciência de Dados** e **Machine Learning Não Supervisionado** para agrupar instituições financeiras brasileiras, superando a análise tradicional por tamanho e focando em **perfil de negócio** e **risco**.


## 🎯 Objetivo
Identificar padrões ocultos nos balanços bancários para:
1.  **Segmentar o Mercado:** Agrupar bancos por modelo de atuação (Varejo e Investimento).
2.  **Detectar Anomalias:** Isolar automaticamente instituições com indicadores de risco fora do comum (Outliers).

---
📂 Dados Utilizados

Dados públicos de instituições financeiras brasileiras contendo indicadores patrimoniais, carteira de crédito, ativos totais e resultados financeiros.

A base foi utilizada para construção de indicadores de risco e desempenho, permitindo a comparação entre instituições de diferentes portes.

---
💻 Tecnologias

• Python
• Pandas
• NumPy
• Scikit-learn
• Matplotlib
• Seaborn
• K-Means
• DBSCAN

---

## 📊 Gráficos

### Segmentação de Perfil (K-Means)
O algoritmo identificou estatisticamente **4 perfis**, sendo dois grupos principais de negócio (Varejo e Investimento) e dois grupos de risco extremo.

<img width="558" height="438" alt="analise_clusters" src="https://github.com/user-attachments/assets/c2dc39e6-bc0c-472f-bd87-9f0f84ca0a24" />

*(Gráfico focado nos grupos principais. Os clusters de risco extremo (alavancagem > 50x) foram ocultados para facilitar a visualização).*



### Detecção de Risco (DBSCAN)
<img width="579" height="455" alt="analise_outliers" src="https://github.com/user-attachments/assets/20ad9c16-27b2-4d20-a38b-ca55d6b1004a" />

O algoritmo isolou instituições que divergem estatisticamente, apontando possíveis riscos de solvência.
*(Os pontos em azul escuro no gráfico representam as anomalias detectadas)*

---

## 🧠 Metodologia

### 1. Engenharia de Atributos (KPIs)
Para comparar bancos de tamanhos diferentes (ex: Banco do Brasil vs. Banco Regional), criamos índices relativos:

| Indicador | Fórmula | Interpretação |
| :--- | :--- | :--- |
| **Alavancagem** | `Ativo / Patrimônio` | **Risco:** Quanto o banco opera acima do seu capital. |
| **Foco em Crédito** | `Carteira / Ativo` | **Perfil:** Define se é Varejo (alta) ou Investimento (baixa). |
| **ROE** | `Lucro / Patrimônio` | **Performance:** Eficiência e retorno da operação. |

### 2. Algoritmos Utilizados
* **K-Means:** Para agrupar bancos por semelhança comercial.
* **DBSCAN:** Para isolar anomalias estatísticas (bancos com alavancagem >100x ou prejuízos consistentes).
   
---

## 📈 Conclusões
A análise revelou que o sistema bancário brasileiro é heterogêneo. Enquanto o **K-Means** segmentou o mercado, o **DBSCAN** realizou uma auditoria, isolando automaticamente **~100 instituições** com indicadores de risco extremos que fogem ao padrão de mercado.
