# TimeSeriesML - Pipeline Robusto de Previsão de Séries Temporais

Um pipeline abrangente para previsão de séries temporais que suporta múltiplos modelos, incluindo XGBoost e Redes Neurais, com recursos para processamento paralelo, comparação de modelos e tratamento robusto de erros.

## 📋 Funcionalidades

- **Múltiplos Modelos**: Suporte a modelos XGBoost e Rede Neural (LSTM)
- **Processamento Paralelo**: Processamento eficiente de múltiplas séries temporais em paralelo
- **Engenharia de Features**: Geração abrangente de features incluindo lags, estatísticas móveis e características temporais
- **Comparação de Modelos**: Ferramentas embutidas para comparação de desempenho
- **Tratamento de Erros Robusto**: Manipulação elegante de erros durante o processamento
- **Suporte a GPU**: Otimizado para aceleração em GPU quando disponível
- **Logs Abrangentes**: Sistema de logs detalhado para monitoramento e depuração

## 🚀 Começando

### Pré-requisitos

- Python 3.10+
- Conda (recomendado) ou pip
- GPU compatível com CUDA (opcional, para treinamento mais rápido)

### Instalação

1. **Clone o repositório**
   ```bash
   git clone https://github.com/yourusername/TimeSeriesML.git
   cd TimeSeriesML
   ```

2. **Crie e ative o ambiente conda**
   ```bash
   conda env create -f environment.yml
   conda activate tsenv
   ```

3. **Instale o pacote em modo de desenvolvimento**
   ```bash
   pip install -e .
   ```

## 🏃‍♂️ Executando o Pipeline

### Uso Básico

```bash
# Execute com configurações padrão (apenas XGBoost)
python -m src.main

# Execute com XGBoost e Rede Neural
python -m src.main --run-nn

# Execute com tamanho de lote personalizado e processamento paralelo
python -m src.main --batch-size 100 --max-procs 4
```

### Opções de Linha de Comando

| Opção | Descrição | Padrão |
|--------|-------------|---------|
| `--run-xgb` | Treinar e prever com XGBoost | True |
| `--run-nn` | Treinar e prever com Rede Neural | False |
| `--reuse-xgb` | Usar previsões existentes do XGBoost | False |
| `--reuse-nn` | Usar previsões existentes da Rede Neural | False |
| `--reset-xgb` | Excluir artefatos do XGBoost antes do treinamento | True |
| `--reset-nn` | Excluir artefatos da Rede Neural antes do treinamento | False |
| `--batch-size` | Número de itens por lote | 50 |
| `--max-procs` | Número máximo de processos paralelos | 1 |
| `--max-xgb` | Máximo de modelos XGBoost concorrentes | 1 |
| `--max-nn` | Máximo de modelos de Rede Neural concorrentes | 1 |
| `--no-compare` | Pular comparação de modelos | False |

## 🏗️ Estrutura do Projeto

```
TimeSeriesML/
├── configs/                # Arquivos de configuração
├── data/                   # Diretório de dados
│   ├── raw/                # Dados brutos
│   ├── interim/            # Dados processados intermediários
│   └── processed/          # Dados totalmente processados
├── docs/                   # Documentação
├── logs/                   # Arquivos de log
├── notebooks/              # Jupyter notebooks para exploração
├── scripts/                # Scripts utilitários
├── src/                    # Código-fonte
│   ├── compare_models.py   # Utilitários de comparação de modelos
│   ├── data_preparation.py # Carregamento e preparação de dados
│   ├── feature_engineering.py # Geração de features
│   ├── main.py             # Pipeline principal
│   ├── train_nn.py         # Treinamento de Rede Neural
│   ├── train_xgboost.py    # Treinamento de XGBoost
│   └── utils/              # Módulos utilitários
└── tests/                  # Testes automatizados
```

## 📊 Comparação de Modelos

O pipeline inclui ferramentas para comparar o desempenho dos modelos:

```bash
# Gerar relatório de comparação
python -m src.compare_models --xgb-predictions xgb_preds.csv --nn-predictions nn_preds.csv --output relatorio_comparacao.txt
```

## 🧪 Testes

Execute os testes com:

```bash
pytest tests/
```

## 🤝 Como Contribuir

1. Faça um fork do repositório
2. Crie sua branch de recurso (`git checkout -b feature/NovaFuncionalidade`)
3. Faça commit das suas alterações (`git commit -m 'Adiciona nova funcionalidade'`)
4. Faça push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abra um Pull Request

## 📜 Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🙏 Agradecimentos

- Agradecemos a todos os colaboradores que ajudaram a moldar este projeto.
- Desenvolvido para previsão robusta de séries temporais.