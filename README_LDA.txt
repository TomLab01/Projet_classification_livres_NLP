README --- Topic_Modeling_LDA.ipynb --- 2021/2022


# ========================================= AUTEURS ============================================= #
> Tom LABIAUSSE
> Amine CHERIF HAOUAT
> Pierre OLLIVIER
> Cyrine NABI


# ======================================== PRE-REQUIS =========================================== #
L'utilisation de la totalité des fonctionnalités du notebook est possible avec les modules et 
versions suivantes :
> numpy : 1.19.5
> pandas : 1.1.5
> matplotlib : 3.2.2
> tqdm : 4.62.3
> nltk : 3.2.5
> fr_core_news_md : 2.2.5 (exécuter la ligne de téléchargement juste au dessus de son import au préalable)
> gensim : 3.6.0
> bayesian-optimization: 1.2.0



# ======================================= DESCRIPTION =========================================== #

Ce notebook permet de construire un modèle LDA à partir d'un corpus de textes, 
de visualiser les résultats, les évaluer et tester des pistes d'améliorations.
Le fichier se découpe en 7 grandes parties décrites ci-dessous :

> 1 - Imports
Importation des modules nécessaires pour exploiter toutes les fonctionnalités du notebook.
Connexion à un Drive Google pour faciliter la manipulation des données et modèles.

> 2 - Chargement des stopwords
Charge les stopwords et permet de visulaiser leur distribution

> 3 - Algorithme BERTopic
Entaînement d'un modèle BERTopic "BERT_model" sur les données issues de "data".
Enregistrement/Chargement d'un modèle BERTopic dans/depuis un fichier "model_file_name".

> 4 - Tokenization & Lemmatization
Met en forme chaque 4ème de couverture pour la transformer en sac de mots.

> 5 - LDA

>> 5.1 - Préparation des outils permettant de procéder à l'algorithme

>> 5.2.1 - Exécution de LDA

Vous pouvez faire tourner l'algorithme LDA sur le corpus traité précédemment

OU

>> 5.2.2 - Charger un modèle

Vous pouvez utiliser un modèle déjà sauvegardé.

>> 5.3 - Aperçu des topics

Aperçu pondéré ou non pondéré des mots qui constituent un corpus

>> 5.4 - Allocation des topics et csv contenant les prédictions de topics par document

Permet de télécharger les prédictions du modèle

>> 5.5 Prédiction des topics d'un nouveau document

Permet de prédire le topic d'un document non présent dans le corpus

> 6 - Optimisation des paramètres

> 6.1 : Préparation des outils d'optimisation

> 6.2 : Grid search

Permet de fixer des valeurs pour chaque hyperparamètre et évalue le score de cohérence de chaque combinaison de valeurs

> 6.3 - Random search

Permet de tester des combinaisons de valeurs aléatoires dans des plages définies

> 6.4 - Optimisation bayésienne

Permet d'optimiser le score de cohérence sur une plage donnée 

> 7 - Exploration avancée des topics de LDA

Cette partie contient plusieurs représentations de LDA, qui offrent plus de détails sur le modèle construit/chargé.
Elle contient :

- Un tableau qui précise les prédictions de topics pour chaque document
- Les documents qui appartiennent "le plus" à un topic donné
- La distribution de topics dans le corpus
