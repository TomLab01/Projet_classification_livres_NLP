README --- Topic_Modeling_BERTopic.ipynb --- 2021/2022


# ========================================= AUTEURS ============================================= #
> Tom LABIAUSSE
> Amine CHERIF HAOUAT
> Pierre OLLIVIER
> Cyrine NABI


# ======================================== PRE-REQUIS =========================================== #
L'utilisation de la totalité des fonctionnalités du notebook est possible avec les modules et 
versions suivantes :
> numpy==1.21.5
> panda==1.1.5
> matplotlib==3.2.2
> pickle==4.0
> xlwt==1.3.0
> sentence_transformers==2.1.0
> gensim==3.6.0
> scipy==1.4.1
> umap==0.5.2
> hdbscan==0.8.27
> sklearn==1.0.1
> bertopic==0.9.4


# ============================ STRUCTURES DE DONNEES PRINCIPALES ================================ #
> data : dataframe Python contenant les données nécessaires pour entraîner un modèle BERTopic
> BERT_model : modèle BERTopic
> model_file_name : nom de fichier d'enregistrement d'un modèle BERTopic
> doc2topics : liste donnant en position i le numéro du topic auquel appartient le texte i
> doc2bigtopics : liste donnant en position i le numéro du big topic auquel appartient le texte i
> topic_clustering : liste donnant en position k l'ensemble des topics composant le big topic k


# ======================================= DESCRIPTION =========================================== #

Ce notebook permet de construire un modèle BERTopic à partir d'un corpus de textes, 
de visualiser les résultats, les évaluer et tester des pistes d'améliorations.
Le fichier se découpe en 9 grandes parties décrites ci-dessous :

> 1 - Imports
Importation des modules nécessaires pour exploiter toutes les fonctionnalités du notebook.
Connexion à un Drive Google pour faciliter la manipulation des données et modèles.

> 2 - Chargement des données
Construction d'un dataset de textes "data" à partir de plusieurs fichiers Excel.
Les textes sont supposés être écrits en language courant (pas de formatage informatique).

> 3 - Algorithme BERTopic
Entaînement d'un modèle BERTopic "BERT_model" sur les données issues de "data".
Enregistrement/Chargement d'un modèle BERTopic dans/depuis un fichier "model_file_name".

> 4 - Visualisation des résultats
Visualisation des topics via les mots les plus représentatifs de chacun d'entre eux.
Affichage des documents composant un topic donné.
Aperçu des relations entre topics via l'Intertopic Distance Map.
Prédictions de topics par mots clefs.
Prédictions de topics pour de nouveaux textes.
Enregistrement/Chargement de correspondances textes-topics avec "doc2topics".

> 5 - Evaluation des résultats
Calcul d'un score de cohérence Cv pour un modèle BERTopic.

> 6 - Réduction du nombre de topics (avec topic embeddings et Intertopic Distance Map)
Réduction de dimension des topic embeddings d'un modèle BERTopic.
Clustering hierarchique sur les topics réduits et identification de big topics (clusters de topics).
Enregistrement/Chargement de correspondances textes-bigtopics avec "doc2bigtopics".
Enregistrement/Chargement de correspondances topics-bigtopics avec "topic_clustering".
Calcul des mots représentatifs pour chaque big topic avec les méthodes c-TF ou c-TF-iDF.
Visualisation des big topics via les mots les plus représentatifs de chacun d'entre eux.

> 7 - Sauvegarde du Topic Modeling
Sauvegarde lisible du Topic Modeling obtenu sur les données issues de "data" dans un fichier Excel.

> 8 - Réduction du nombre de topics (avec BERTopic directement)
Réduction de topics par BERTopic. Visualisation du nouveau Topic Modeling et sauvegarde du modèle.

> 9 - Algorithme BERTopic décomposé = BERT + UMAP + HDBSCAN
Execution de l'algortihmes BERTopic en trois étapes :
- Calcul des embeddings de documents grâce à BERT
- Réduction de la dimension des embeddings par UMAP
- Clustering des embeddings réduits par HDBSCAN
Visualisation des topics via la méthode c-TF-iDF.
Affichage des documents composant un topic donné.

