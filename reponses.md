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

# Exercice 2 - Qualité du code

## Partie A

### Questions

1. Sur l’onglet Summary d’une analyse de code, SonarCloud fournit 4 indicateurs. Quels sont-ils et quelles sont leurs utilités ?
2. À quoi sert l’indicateur Quality Gate ?

### Réponses

1. Les quatre indicateurs fournis par SonarCloud sur l'onglet Summary sont :

- New Issues : Le nombre de nouvelles issues détectées dans le code depuis la dernière analyse. Cela permet de suivre l'évolution de la qualité du code au fil du temps.
- Accepted Issues : Le nombre d'issues qui ont été acceptées ou ignorées par les développeurs. Cela peut indiquer que certaines issues ne sont pas considérées comme des problèmes par l'équipe.
- Duplications : Le pourcentage de code dupliqué dans le projet. Un taux élevé de duplications peut indiquer un manque de réutilisation du code et une maintenance plus difficile.
- Coverage : Le pourcentage de code couvert par les tests unitaires. Un taux de couverture élevé est généralement un indicateur de la qualité des tests et de la fiabilité du code.

2. L'indicateur Quality Gate est un ensemble de critères définis pour évaluer la qualité du code. Il sert à déterminer si le code passe ou échoue en fonction de ces critères, tels que le nombre d'issues, le taux de duplications, la couverture des tests, etc. Si le code ne respecte pas les critères du Quality Gate, il est considéré comme ayant échoué, ce qui peut empêcher la fusion du code dans la branche principale ou déclencher des actions correctives. Le Quality Gate est un outil essentiel pour maintenir un niveau de qualité élevé dans le projet.

## Partie B

### Questions

1. Quelle est la différence entre les sections New code et Overall Code dans l’onglet Summary ?
2. Y a-t-il des Code Smells ? Si oui, combien et pour quelle(s) raisons(s) ?
3. Y a-t-il des Security Hotspots ? Si oui, combien et pour quelle(s) raison(s) ?

### Réponses

1. New Code est une section concernant les dernières modifications apportées tandis que Overall Code concerne l'ensemble du code du projet.

2. Oui, il y a des Code Smells. La méthode `spend_money` dans la classe `Wallet` est la même que la méthode `spend_cash`. Il y a également des paramètres inutilisés.
3. Oui, il y a des Security Hotspots. En utilisant une action dans une GitHub Action, il est préférable d'utiliser le hash complet du commit plutôt que la version ou la branche.

# Exercice 3 - Gitlab CI/CD

## Partie A

### Questions

1. Que fait le job pytest ?
2. Que fait le job image-creation ?
3. Que fait le job package-creation ?
4. Dans quel ordre les différents jobs sont-ils exécutés et pourquoi ?
5. Le stage 2 génère une image Docker. Où est-elle stockée et comment pouvez-vous la retrouver ?
6. Le stage 3 génère un wheel Python. Où est-il stocké et comment pouvez-vous le retrouver ?

### Réponses

1. Le job pytest exécute les tests unitaires du projet en utilisant la commande `pytest`.
2. Le job image-creation construit une image Docker à partir du Dockerfile présent dans le projet.
3. Le job package-creation construit un package Python à partir du code source.
4. Les jobs sont exécutés dans l'ordre suivant : pytest, image-creation, package-creation. Cet ordre est déterminé par les dépendances entre les jobs.
5. Elle est stockée dans le registre de conteneurs de GitLab. Vous pouvez la retrouver en accédant à la section "Container Registry" du projet dans GitLab.
6. Il est stocké dans le registre des paquets de GitLab. Vous pouvez le retrouver en accédant à la section "Packages & Registries" du projet dans GitLab, puis en sélectionnant "Package Registry".
