## Tarefa Prática: Github Actions

# ML Pipeline

Este repositório contém um **workflow automatizado de Machine Learning** que, a cada push, executa um script Python (`train.py`) para treinar um modelo de **Logistic Regression** e gera um relatório de classificação.

O relatório (`report.txt`) inclui métricas como **acurácia, precisão, recall e F1-score** e é publicado como artefato no GitHub Actions.

---

## Estrutura do repositório

ml-pipeline/
├── data/sample.csv # Dataset de exemplo
├── train.py # Script de treino do modelo
├── requirements.txt # Dependências do Python
├── report.txt # Relatório gerado pelo workflow (não versionado)
└── .github/workflows/ml.yml # Workflow do GitHub Actions

yaml
Copiar código

---

## Fluxo do workflow

1. **Disparo**: A cada push no repositório, o workflow é acionado automaticamente.  
2. **Configuração do ambiente**: Instala as dependências listadas em `requirements.txt`.  
3. **Treinamento do modelo**: Executa `train.py` que:  
   - Lê os dados de `data/sample.csv`  
   - Divide os dados em treino e teste com estratificação  
   - Treina um modelo `LogisticRegression`  
   - Gera um relatório de classificação (`classification_report`)  
4. **Publicação do relatório**: O relatório é salvo como `report.txt` e disponibilizado como artefato no GitHub Actions.

---

## Como testar localmente

1. Criar um ambiente virtual:

```bash
python -m venv venv
Ativar o ambiente virtual:

Windows (cmd):

cmd
Copiar código
venv\Scripts\activate.bat
Linux/macOS:

bash
Copiar código
source venv/bin/activate
Instalar dependências:

bash
Copiar código
pip install -r requirements.txt
Executar o script:

bash
Copiar código
python train.py
O relatório será criado localmente como report.txt.

Capturas de tela do GitHub Actions
Inclua abaixo as imagens mostrando o workflow executando com sucesso.
Exemplo:


Observações
A pasta venv/ e o arquivo report.txt não estão versionados.

O workflow utiliza a branch main como padrão.

Garantimos que o modelo treina sem warnings com stratify=y e zero_division=0.

Link do repositório
https://github.com/Victor Furumoto Puttomatti/ml-pipeline

yaml
Copiar código


git add README.md
git commit -m "Adicionar README.md completo para submissão"
git push origin main
```

## Licença

Este projeto está licenciado sob a licença MIT.  
Créditos: VictorFP335
