# Simple Universities Data Clustering

Projeto de clustering usando KMeans para agrupar universidades em dois grupos: Privadas e Públicas.

## 📋 Descrição

Este projeto utiliza o algoritmo KMeans Clustering para agrupar universidades baseadas em diversas características acadêmicas e financeiras. O objetivo é demonstrar como o algoritmo de aprendizado não supervisionado performa **sem** qualquer ajuste de hiperparâmetros, normalização ou pré-processamento dos dados - servindo como uma baseline para demonstrar a importância desses passos em pipelines de clustering reais.

## 📊 Dataset

O conjunto de dados contém 777 observações sobre 18 variáveis:

- **Private**: Fator com níveis Não e Sim, indicando universidade privada ou pública
- **Apps**: Número de inscrições recebidas
- **Accept**: Quantidade de inscrições aceitas
- **Enroll**: Número de estudantes matriculados
- **Top10perc**: Percentual de novos estudantes do grupo de 10% melhores do segundo grau
- **Top25perc**: Percentual de novos estudantes do grupo de 25% melhores do segundo grau
- **F.Undergrad**: Número de alunos de graduação em tempo integral
- **P.Undergrad**: Número de alunos de graduação em tempo parcial
- **Outstate**: Aulas fora do estado
- **Room.Board**: Custos da sala
- **Books**: Custos de livros estimados
- **Personal**: Estimativa de gastos por pessoa
- **PhD**: Percentual de PHDs na universidade
- **Terminal**: Percentual da faculdade com graduação
- **S.F.Ratio**: Taxa estudantes/faculdade
- **perc.alumni**: Percentual dos ex-alunos que doam
- **Expend**: Despesas da instituição por aluno
- **Grad.Rate**: Taxa de graduação

## 🚀 Instalação

### Pré-requisitos
- Python >= 3.14

### Instalar dependências

```bash
pip install -r requirements.txt
```

Ou usando uv:

```bash
uv sync
```

## 📖 Como Executar

1. Clone este repositório
2. Navegue até o diretório do projeto
3. Instale as dependências
4. Abra o notebook Jupyter:

```bash
jupyter notebook simples-universities-cluster.ipynb
```

5. Execute as células do notebook sequencialmente

## 📁 Estrutura do Projeto

```
simple-universities-data-clustering/
├── .gitignore                 # Arquivos ignorados pelo Git
├── .python-version            # Versão do Python
├── .venv/                     # Ambiente virtual (gitignore)
├── College_Data               # Dataset do projeto
├── pyproject.toml             # Configuração do projeto (uv)
├── README.md                  # Este arquivo
├── requirements.txt           # Dependências Python
├── simples-universities-cluster.ipynb  # Notebook principal
└── uv.lock                    # Lock file do uv
```

## 🔍 Resultados

O modelo KMeans apresentou desempenho ruim na baseline:
- **Acurácia**: 22%
- **F1-score**: 0.16
- **Precision**: 0.29 (weighted avg)
- **Recall**: 0.22 (weighted avg)

### Causas identificadas:

1. **Escalas diferentes entre features**: Variáveis como Apps (81-48.094) e Top10perc (1-96) têm ordens de magnitude muito diferentes
2. **Ausência de normalização**: Dados não foram padronizados antes do clustering
3. **Possíveis outliers**: Valores extremos podem distorcer os centróides

### Melhorias possíveis:

- StandardScaler para normalização
- Feature selection
- Remoção de outliers
- PCA para redução de dimensionalidade
- Ajuste de hiperparâmetros (n_init, init)
- Teste de diferentes números de clusters

## 📝 Nota Importante

O objetivo deste projeto foi verificar como o KMeans performaria **sem** qualquer ajuste de hiperparâmetros, normalização ou pré-processamento dos dados. Em situações reais, esses passos são essenciais para obter bons resultados com clustering.

## 🛠️ Tecnologias Utilizadas

- Python 3.14+
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## 📄 Licença

Este projeto é para fins educacionais.

## 👤 Autor

Projeto criado para fins de aprendizado em Machine Learning e Data Clustering.