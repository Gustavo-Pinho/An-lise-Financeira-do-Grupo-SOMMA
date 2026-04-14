# 🎵 Análise Financeira — Agência de Marketing de Influência Musical
### Desafio Técnico: Analista de Dados Financeiros Júnior

> **Período analisado:** Q1 2026 (Janeiro – Março)  
> **Dataset:** 71 campanhas | 29 artistas | 7 labels | 11 gêneros musicais  
> **Ferramenta:** Python (Pandas, NumPy, Matplotlib) via Google Colab

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1yFCVNI2dEVNtlP44o4XqOfKgH8EJntl8?usp=sharing)

---

## 📋 Sumário

- [Visão Geral](#visão-geral)
- [Estrutura do Notebook](#estrutura-do-notebook)
- [Resultados por Análise](#resultados-por-análise)
- [Visualizações](#visualizações)
- [Recomendações Estratégicas](#recomendações-estratégicas)
- [Resumo Executivo KPIs](#resumo-executivo-kpis)
- [Como Executar](#como-executar)
- [Dependências](#dependências)

---

## Visão Geral

Este notebook realiza uma análise financeira e operacional completa de uma **agência de marketing de influência musical**, respondendo perguntas estratégicas do desafio com análises visuais e recomendações práticas.

### Dataset
| Aba | Registros | Descrição |
|---|---|---|
| `Campanhas 2026` | 71 linhas × 13 colunas | Dados gerais de campanhas |
| `Custos` | 71 linhas × 6 colunas | Verba, custo operacional e posts |
| `Resumo Mensal` | 17 linhas × 7 colunas | Consolidado mensal |

---

## Estrutura do Notebook

```
📓 Analise_Financeira_SOMMA_2026.ipynb
│
├── 📥 1. Carregamento e Limpeza dos Dados
│   ├── Importação das 3 abas do Excel
│   ├── Enriquecimento (CPM, mês, classificação de margem)
│   └── Visão geral do dataset
│
├── 📊 Parte 1 — Visão Financeira
│   ├── (a) Faturamento mês a mês vs. meta anual
│   ├── (b) O que é necessário para bater a meta até dezembro
│   ├── (c) Ticket médio por mês, artista e empresa
│   ├── (d) Análise de margem operacional — Regra dos 50%
│   └── (e) Concentração de faturamento por label
│
├── ⚙️ Parte 2 — Visão Operacional
│   ├── (f) Análise por responsável
│   ├── (g) Análise por gênero musical
│   └── (h) CPM médio por gênero e label
│
└── 💡 Parte 3 — Recomendações Estratégicas
    ├── Dashboard executivo com 4 recomendações priorizadas
    └── Resumo final de todos os KPIs
```

---

## Resultados por Análise

### (a) Faturamento Mensal vs. Meta

| Mês | Faturamento | % da Meta Mensal | Status |
|---|---|---|---|
| Janeiro | R$ 567.000 | 113,4% | ✅ Acima |
| Fevereiro | R$ 518.000 | 103,6% | ✅ Acima |
| Março | R$ 351.500 | 70,3% | ⚠️ Abaixo |
| **TOTAL Q1** | **R$ 1.436.500** | **23,9% da meta anual** | — |

> 💡 Meta anual: **R$ 6.000.000** | Meta mensal: **R$ 500.000**

---

### (b) Ritmo e Projeção Anual

| Métrica | Valor |
|---|---|
| Ritmo mensal atual | R$ 478.833 |
| Projeção anual no ritmo atual | R$ 5.746.000 |
| GAP para a meta | **R$ 254.000** |
| Receita necessária/mês (Q2–Q4) | R$ 507.056 |
| Campanhas necessárias/mês (ticket atual) | ~13 campanhas |

**Cenários alternativos para fechar o GAP:**

| Estratégia | Campanhas/mês necessárias |
|---|---|
| Ritmo atual (sem mudança) | ~13 |
| +10% no ticket médio | ~12 |
| +20% no ticket médio | ~11 |
| +30% no ticket médio | ~10 |

---

### (c) Ticket Médio

**Ticket Médio Geral: R$ 40.465**

Por mês — tendência de queda ao longo do Q1:
| Mês | Ticket Médio |
|---|---|
| Janeiro | R$ 28.350 |
| Fevereiro | R$ 20.720 |
| Março | R$ 14.060 |

**Top 5 Artistas por Ticket Médio:**
| Artista | Ticket Médio |
|---|---|
| Rick Montana | R$ 37.200 |
| Isa Monteiro | R$ 36.000 |
| Tom Barreto | R$ 34.000 |
| Gabi Noronha | R$ 33.333 |
| Bia Santos | R$ 30.000 |

---

### (d) Margem Operacional — Regra dos 50%

> A agência utiliza como referência que o custo operacional não deve superar **50% da verba** de cada campanha.

| Status | Campanhas | % do total |
|---|---|---|
| ✅ Dentro da margem (≤ 50%) | 17 | 24% |
| 🔴 Estouraram a margem (> 50%) | 53 | **76%** |

- **Margem média real:** 57,0% — 7 p.p. acima do limite
- **Margem mediana:** 57,4%

⚠️ **Alerta crítico:** 3 em cada 4 campanhas estão com custo acima do limite definido.

---

### (e) Concentração por Label

| Label | Faturamento | % do Total | Acumulado |
|---|---|---|---|
| Pulse Music Group | R$ 308.000 | 21,4% | 21,4% |
| Estrela Distribuição | R$ 253.000 | 17,6% | 39,1% |
| Onda Records | R$ 216.500 | 15,1% | 54,1% |
| Tropicália Music | R$ 205.000 | 14,3% | 68,3% |
| … | … | … | … |

> Top 3 labels concentram ~54% do faturamento — risco de dependência moderado.

---

### (f) Performance por Responsável

| Responsável | Campanhas | Faturamento | Ticket Médio | Carga |
|---|---|---|---|---|
| Analista 1 | 22 (31%) | R$ 503.500 (35%) | R$ 22.886 | 🔴 Alto |
| Analista 3 | 21 (30%) | R$ 404.000 (28%) | R$ 19.238 | 🟡 Médio |
| Analista 2 | 16 (23%) | R$ 343.000 (24%) | R$ 21.438 | 🟡 Médio |
| Coordenador | 11 (16%) | R$ 186.000 (13%) | R$ 16.909 | 🟢 Baixo |

---

### (g) Volume e Faturamento por Gênero

| Gênero | Campanhas | Faturamento | % Total | Ticket Médio |
|---|---|---|---|---|
| Eletrônica | 8 | R$ 291.000 | 20,3% | R$ 36.375 |
| Trap | 11 | R$ 281.000 | 19,6% | R$ 25.545 |
| R&B | 8 | R$ 150.000 | 10,4% | R$ 18.750 |
| Funk | 7 | R$ 145.000 | 10,1% | R$ 20.714 |
| Axé | 7 | R$ 139.000 | 9,7% | — |

---

### (h) CPM por Gênero e Label

> **CPM (Custo por Mil):** Valor em reais para gerar 1.000 views. Menor = mais eficiente.

**CPM Médio Geral: R$ 1,6478 por 1.000 views**

| Gênero | CPM Médio | Eficiência |
|---|---|---|
| R&B | R$ 0,352 | 🟢 Muito eficiente |
| Sertanejo | R$ 0,504 | 🟡 Moderado |
| Axé | R$ 0,543 | 🟡 Moderado |
| Forró | R$ 0,570 | 🟡 Moderado |
| Funk | R$ 0,628 | 🟡 Moderado |
| Eletrônica | R$ 5,26+ | 🔴 Alto CPM |

---

## Visualizações

O notebook gera **8 painéis gráficos** com visual dark theme personalizado:

| # | Gráfico | Tipo |
|---|---|---|
| 1 | Faturamento Mensal vs. Meta | Barras + Linha acumulada |
| 2 | Cenários para bater a meta | Gauge + Barras comparativas |
| 3 | Ticket Médio (mês, label, gênero) | Triple barras |
| 4 | Margem Operacional — Regra 50% | Pizza + Histograma + Barras |
| 5 | Concentração por Label (Pareto) | Barras horizontais + Curva |
| 6 | Performance por Responsável | Barras duplas + Ticket |
| 7 | Volume e Faturamento por Gênero | Pizza + Barras horizontais |
| 8 | CPM por Gênero e Label | Barras horizontais coloridas |

> **Para visualizar os gráficos interativamente, abra o notebook no Google Colab** usando o badge acima. ▲

---

## Recomendações Estratégicas

### 🔴 01 — ALERTA AUTOMÁTICO DE MARGEM `[Prioridade: Alta]`
**Problema:** 76% das campanhas estouraram o limite de 50% de custo. Margem média real: 57% — 7 p.p. acima do limite.  
**Ação:** Implementar alerta quando custo atingir 40% da verba. Revisar precificação mínima por tipo de campanha.

### 🟡 02 — ACELERAÇÃO DO RITMO DE CAMPANHAS `[Prioridade: Crítica]`
**Problema:** Q1 executou apenas 24% da meta anual. Ticket médio caiu 37% de Janeiro (R$ 28k) a Março (R$ 14k).  
**Ação:** Manter mínimo de 27 campanhas/mês ou aumentar ticket em 20%. Prospecção ativa no Q2 para compensar a queda de Março.

### 🟢 03 — PRIORIZAR GÊNEROS DE ALTA EFICIÊNCIA (CPM) `[Prioridade: Média]`
**Problema:** R&B e Sertanejo têm CPM de R$ 0,35–0,50, gerando 4–10x mais views por real vs. Eletrônica (R$ 5,26).  
**Ação:** Ampliar portfólio em R&B e Sertanejo. Usar CPM como argumento de venda para labels.

### 🔵 04 — BALANCEAR CARTEIRA E DIVERSIFICAR LABELS `[Prioridade: Média]`
**Problema:** Analista 1 carrega 31% das campanhas. Top 3 labels concentram 54% do faturamento.  
**Ação:** Redistribuir carteira entre analistas. Prospectar novas labels para reduzir dependência.

---

## Resumo Executivo KPIs

```
📊 FINANCEIRO
   Faturamento Q1:           R$  1.436.500
   % Meta Anual Atingida:         23,9%
   Ticket Médio:             R$     40.465
   Melhor Mês:               Janeiro (R$ 567.000)
   Pior Mês:                 Março   (R$ 351.500)

⚙️ OPERACIONAL
   Total Campanhas:          70
   Gênero Top Faturamento:   Eletrônica (R$ 291.000)
   Gênero Top Volume:        Trap (11 campanhas)
   Melhor CPM (eficiência):  R&B (R$ 0,352 / 1k views)
   Analista + Campanhas:     Analista 1 (22 campanhas)
   Analista + Faturamento:   Analista 1 (R$ 503.500)

💰 MARGEM
   Dentro da margem (≤ 50%): 17 (24%)
   Estouraram (> 50%):       53 (76%)
   Margem média real:        57,0%

🎯 PROJEÇÃO
   Ritmo mensal atual:       R$ 478.833
   Projeção anual:           R$ 5.745.996
   GAP para meta:            R$ 254.004
   Necessário/mês (Q2–Q4):   R$ 507.056
```

---

## Como Executar

### Opção 1 — Google Colab (recomendado)

1. Acesse o link: [Abrir no Colab](https://colab.research.google.com/drive/1yFCVNI2dEVNtlP44o4XqOfKgH8EJntl8?usp=sharing)
2. Faça upload do arquivo Excel de dados quando solicitado
3. Execute as células em ordem: `Runtime > Run all`

### Opção 2 — Localmente (Jupyter)

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/analise-financeira-somma-2026.git
cd analise-financeira-somma-2026

# Instale as dependências
pip install -r requirements.txt

# Abra o notebook
jupyter notebook Analise_Financeira_SOMMA_2026.ipynb
```

---

## Dependências

```txt
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
openpyxl>=3.0.0
```

---

## 📁 Estrutura do Repositório

```
analise-financeira-somma-2026/
├── Analise_Financeira_SOMMA_2026.ipynb   ← Notebook principal
├── README.md                              ← Este arquivo
├── requirements.txt                       ← Dependências Python
└── assets/
    └── plots/                             ← Gráficos exportados (gerados ao rodar)
```

---

*Análise desenvolvida como parte do Desafio Técnico — Analista de Dados Financeiros Júnior.*
