# Exerice 1 - GitHub Actions

## Questions

1. Quelles étapes (steps) sont réalisées par cette action ?
2. Une étape est définie au minimum par 2 éléments, lesquels sont-ils et à quoi servent-ils ?
3. La première étape contient le mot-clé ‘with’, a quoi sert-il ?

## Réponses

1. Les étapes réalisées par cette action sont :

- Checkout : Cette étape utilise l'action `actions/checkout@v4` pour récupérer le code source du dépôt GitHub.
- Setup python : Cette étape utilise l'action `actions/setup-python@v3` pour configurer l'environnement Python avec la version spécifiée (3.10).
- Lint with flake8 : Cette étape exécute la commande `flake8 .` pour analyser le code source à la recherche de problèmes de style et de qualité.
- Test with pytest : Cette étape exécute la commande `pytest` pour lancer les tests unitaires du projet.

2. Les deux éléments qui définissent une étape sont :

- `name` : C'est le nom de l'étape, qui sert à identifier l'étape dans les logs et les rapports d'exécution.
- `run` : C'est la commande ou les commandes à exécuter pour réaliser l'action de l'étape. C'est ce qui définit ce que l'étape va faire concrètement.

3. Le mot-clé `with` est utilisé pour fournir des paramètres ou des options à une action spécifique. Dans ce cas, il est utilisé pour spécifier la version de Python à configurer dans l'étape "Setup python". En utilisant `with`, on peut passer des arguments à l'action `actions/setup-python@v3` pour personnaliser son comportement, comme la version de Python à installer.
