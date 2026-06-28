# 🏎️ Dashboard F1 2025/2026 — Power BI + Databricks

Dashboard interativo de Fórmula 1 cobrindo as temporadas 2025 e 2026, construído sobre arquitetura Delta Lake no Databricks.

## 📸 Preview
![Pilotos]([images/pilotos.png](https://github.com/euovinicius/F1-dashboard-power-bi/blob/main/imagens/Pilotos.png))
![Equipes]([images/equipes.png](https://github.com/euovinicius/F1-dashboard-power-bi/blob/main/imagens/Equipes.png))
![Comparativo]([images/comparativo.png](https://github.com/euovinicius/F1-dashboard-power-bi/blob/main/imagens/Comparativos.png))

## 🎯 O que o projeto faz
- Consolida dados de corridas, pilotos e construtores F1.
- Processa em pipeline Bronze → Silver → Gold no Databricks.
- Gera dashboard interativo com filtros por temporada.
- Permite comparar desempenho de pilotos entre 2025 e 2026.

## 🏗️ Arquitetura
Bronze (raw) → Silver (limpo) → Gold (agregado) → Power BI

## 🔧 Stack
| Camada | Tecnologia |
|--------|-----------|
| Ingestão | Python + Databricks |
| Storage | Delta Lake |
| Transformação | PySpark / SQL |
| Visualização | Power BI + DAX |

## ⚠️ Desafio técnico
O Power BI atingiu o limite de complexidade de uma medida DAX única.
Solução: modularizei em 12 medidas componentes + 1 assembler.

## 📁 Estrutura do Repositório
```text
├── 📁 images/                   # Previews do dashboard
├── 📁 NOTEBOOK/ 
├── 📁 DAX/        # Definição do modelo do Power BI (PBIP)
│   └── agregacoes_gold_ipynb.tmdl  # Onde estão guardadas as fórmulas DAX
└── README.md                    # Documentação do projeto
