# Credit Scoring

> 💡 **Le notebook complet est consultable directement ici : [`credit_scoring.ipynb`](./credit_scoring.ipynb)**

Ce projet personnel a pour but de concilier mes cours d'analyse de données et mon envie de mettre cela en pratique sur un cas concret dans un secteur où les erreurs d'analyses peuvent avoir des conséquences financières directes : le secteur bancaire.

L'objectif est ici de développer un modèle de scoring pour l'octroi de crédit à la consommation. Celui-ci sera interprétable, permettant d'expliquer les décisions de manière claire et transparente.

## Approche

Le notebook suit un cycle complet de Data Science : récupération des données, analyse exploratoire, préparation des données, modélisation, évaluation du modèle et interprétation des résultats. La régression logistique a été privilégiée pour conserver un modèle interprétable pour un analyste métier.

## Résultats

Le modèle obtient une AUC proche de 0,80, ce qui indique une bonne capacité à distinguer les clients solvables des clients en défaut. Cependant, il détecte une part importante de clients en défaut (83% de rappel) au prix de nombreux faux positifs : certains clients pourtant solvables sont donc classés comme à risque.

Dans un contexte réel, le seuil de décision devrait être défini à partir d'une analyse financière permettant de déterminer le compromis optimal entre le coût des faux positifs et le coût des faux négatifs. L'objectif n'est pas de maximiser le nombre de prêts accordés, mais de minimiser le risque de pertes financières pour la banque.

Les résultats détaillés et l'interprétation des variables sont présentés dans le notebook.

## Installation

```bash
git clone https://github.com/lgadroy/credit-scoring.git
cd credit-scoring

python -m venv .venv
```

Activation de l'environnement virtuel :

```bash
# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate
```

Installation des dépendances et lancement du notebook :

```bash
pip install -r requirements.txt
jupyter notebook credit_scoring.ipynb
```

## Technologies

Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, Jupyter
