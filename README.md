# WhatsApp DS Analytics

> Pipeline completo de Data Science para análise de conversas do WhatsApp.

## 📋 Sobre

Este projeto demonstra um pipeline completo de **Data Science**, desde a investigação inicial de dados brutos até análises avançadas com clustering e visualizações. O caso de estudo é um export do WhatsApp com ~92.000 mensagens ao longo de 1 ano.

O projeto foi desenvolvido para ser **reprodutível** — permite rodar o pipeline com novos exports e integrar os resultados à base existente.

## 🔄 Pipeline

```
DATA PREPARATION                           DATA ANALYSIS
┌──────────────────────────────────────┐   ┌──────────────────────────┐
│ Profiling → Cleaning → Wrangling →   │ → │ EDA → Descritiva →       │ → Comunicação
│              Feature Engineering     │   │       Avançada           │
└──────────────────────────────────────┘   └──────────────────────────┘
```

### Etapas detalhadas

| Fase | Etapa | Descrição |
|------|-------|-----------|
| **Preparation** | Data Profiling | Investigação da estrutura do arquivo bruto |
| | Data Cleaning | Remoção de caracteres invisíveis, normalização |
| | Data Wrangling | Parsing, vinculação de mídia, transcrição |
| | Feature Engineering | Criação de 35 variáveis derivadas |
| **Analysis** | EDA | Análise exploratória |
| | Descritiva | Estatísticas e distribuições |
| | Avançada | Clustering, PCA, radar charts |

## 📁 Estrutura

```
whatsapp-ds-analytics/
│
├── index.qmd                    # Documento principal (overview)
│
├── assets/                      # Recursos estáticos
│   └── images/                  # Diagramas, screenshots
│
├── src/                         # Módulos Python
│   ├── profiling.py             # Funções de investigação
│   ├── cleaning.py              # Limpeza de dados
│   ├── parsing.py               # Parser txt → DataFrame
│   ├── wrangling.py             # Vinculação e transcrição
│   ├── features.py              # Feature engineering
│   ├── audit.py                 # Auditoria de transformações
│   └── config.py                # Configurações centralizadas
│
├── notebooks/                   # Documentos Quarto
│   ├── 00-data-profiling.qmd    # Investigação inicial
│   ├── 01-data-preparation.qmd  # Pipeline de preparação
│   ├── 02-eda.qmd               # Análise exploratória
│   └── 03-advanced.qmd          # Análises avançadas
│
├── data/                        # 🚫 Não versionado (ver data/README.md)
│   ├── raw/                     # Exports brutos por período
│   ├── interim/                 # Arquivos intermediários
│   ├── processed/               # DataFrames por execução
│   └── integrated/              # Base consolidada
│
├── analysis/                    # 🚫 Não versionado
│   ├── eda/                     # Gráficos exploratórios
│   ├── reports/                 # Relatórios gerados
│   └── figures/                 # Figuras finais
│
└── docs/
    └── data-dictionary.md       # Dicionário de dados
```

## 🛠️ Tecnologias

- **Python 3.11+**
- **Pandas** — Manipulação de dados
- **Quarto** — Documentação reprodutível
- **Matplotlib / Plotly** — Visualizações
- **Groq API (Whisper)** — Transcrição de áudios

## 📊 Dataset Final

| Métrica | Valor |
|---------|-------|
| Mensagens | ~92.000 |
| Features | 35 |
| Período | Out/2024 — Out/2025 |
| Participantes | 2 (anonimizados) |

## 🚀 Como usar

```bash
# Clone o repositório
git clone https://github.com/mrlnlms/whatsapp-ds-analytics.git
cd whatsapp-ds-analytics

# Instale dependências
pip install pandas matplotlib plotly

# Adicione seus dados
# 1. Exporte conversa do WhatsApp
# 2. Coloque em data/raw/export_YYYY-MM/

# Execute o pipeline
quarto render notebooks/00-data-profiling.qmd
```

## 📝 Documentação

- [index.qmd](index.qmd) — Overview do projeto
- [00-data-profiling.qmd](notebooks/00-data-profiling.qmd) — Investigação inicial do arquivo bruto
- [01-data-cleaning.qmd](notebooks/01-data-cleaning.qmd) — Limpeza dos dados
- [02-data-wrangling.qmd](notebooks/02-data-wrangling.qmd) — Parsing e estruturação
- [03-feature-engineering.qmd](notebooks/03-feature-engineering.qmd) — Criação de variáveis
- [04-eda.qmd](notebooks/04-eda.qmd) — Análise exploratória
- [05-advanced-analysis.qmd](notebooks/05-advanced-analysis.qmd) — Clustering, PCA, radar charts
- [data-dictionary.md](docs/data-dictionary.md) — Descrição de todas as variáveis
- [data/README.md](data/README.md) — Como organizar seus dados

## 📌 Highlights

- **Pipeline reprodutível** — rode com novos exports e integre à base
- **Transcrição automática** de áudios/vídeos via Groq API
- **Módulos reutilizáveis** com funções bem documentadas
- **Auditoria completa** de cada transformação
- **Radar chart** comparativo de perfis de comunicação

## 🔒 Privacidade

Os dados (pasta `data/` e `analysis/`) **não são versionados** por conterem informações pessoais. Veja `.gitignore` para detalhes.

---

*Projeto desenvolvido como estudo de caso em Data Science por [@mrlnlms](https://github.com/mrlnlms)*
