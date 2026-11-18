# Travaux pratiques (TP)
Ce TP a pour objectif de mettre en pratique les notions étudiées dans les cours précédents :
- Les bases d'un prompt.
- Les six composantes d'un bon prompt : rôle, objectif, contexte, format, ton et contraintes.
- Les techniques de Prompt Engineering : Zero-shot, One-shot, Few-shot, Role prompting et Iterative prompting.
- Les Prompt Templates et les variables dynamiques.
- Les paramètres des LLM : Temperature, Top-P et limite de tokens.
- L'évaluation et l'amélioration des réponses générées par une IA.
Thématique du TP : utiliser le Prompt Engineering pour analyser des tweets en français et identifier leur sentiment.

# Objectifs pédagogiques
À la fin du TP, l'étudiant devra être capable de :
1. Construire un prompt adapté à une tâche d'analyse de texte.
2. Comparer plusieurs techniques de Prompt Engineering.
3. Créer un Prompt Template réutilisable.
4. Tester l'influence de certains paramètres LLM.
5. Demander une réponse structurée en JSON.
6. Évaluer la qualité des résultats produits par l'IA.
7. Identifier les limites de l'IA générative dans l'analyse des sentiments.

# Déroulement du TP


 ## Étape 1 – Découverte du jeu de données

 - Ouvrir le fichier CSV.
- Identifier les deux colonnes.
- Lire quelques tweets.
- Observer les deux catégories de labels.
- Vérifier la signification des labels dans la documentation de la source, si elle est disponible.
Question : pourquoi est-il important de comprendre les données avant de construire un prompt ?
## Étape 2 – Construire un premier prompt (Zero-shot)
L'étudiant demande directement à ChatGPT de classifier un tweet sans lui fournir d'exemple.

Objectif : obtenir une première classification et observer les limites de la réponse.


## Étape 3 – Améliorer le prompt (Role prompting)

Ajouter un rôle, un contexte, une tâche précise et des contraintes.

Objectif : mesurer l'intérêt d'un prompt mieux structuré.


## Étape 4 – Utiliser Few-shot prompting
Fournir à l'IA quelques exemples de tweets dont le sentiment a été vérifié manuellement.

Objectif : étudier l'influence des exemples sur les classifications.



## Étape 5 – Construire un Prompt Template

Créer un modèle réutilisable permettant de classifier différents tweets.

Objectif : standardiser et automatiser les instructions.


## Étape 6 – Tester les paramètres LLM

Comparer plusieurs réglages de température, lorsque l'outil utilisé permet de les contrôler.

Objectif : observer l'influence des paramètres sur la stabilité des réponses.


## Étape 7 – Évaluer et interpréter les résultats

Comparer les résultats des différents prompts, analyser les erreurs et formuler des recommandations.

# Travail pratique n° 1 : créer un premier prompt

Consigne : utiliser ChatGPT pour déterminer si un tweet exprime un sentiment positif, négatif ou neutre.
Analyse le sentiment du tweet suivant :

« besoin d'un service »

Indique si le sentiment est positif, négatif ou neutre.

Questions :
1. Quelle réponse l'IA a-t-elle produite ?
2. Est-ce que le tweet est nécessairement négatif ?
3. Peut-on interpréter ce message sans tenir compte du contexte ?
4. Le résultat est-il suffisamment précis ?

# Travail pratique n° 2 : améliorer le prompt

Tu es un expert en analyse de sentiments et en traitement automatique du langage naturel (NLP).

Contexte : tu travailles sur un jeu de données constitué de tweets écrits en français.

Objectif : analyser le sentiment exprimé dans chaque tweet.

Consigne : classe le tweet dans l'une des trois catégories : positif, négatif ou neutre.

Format attendu : sentiment identifié, émotion principale, justification courte.

Contraintes : utilise uniquement le contenu du tweet, ne déduis pas des informations absentes et signale les cas ambigus.

Tweet à analyser : « besoin d'un câlin »

Questions :
- Quelles améliorations ont été apportées ?
- La réponse est-elle plus explicite ?
- L'IA justifie-t-elle correctement sa classification ?
- Le prompt permet-il de mieux identifier les cas ambigus ?

# Travail pratique n° 3 : utiliser Few-shot prompting

Tu es un spécialiste de l'analyse des sentiments.

Voici des exemples de classification :

- Tweet : « Je suis très heureux aujourd'hui ! » Sentiment : Positif.
- Tweet : « Je déteste cette situation. » Sentiment : Négatif.
- Tweet : « Le rendez-vous est prévu demain à 10 heures. » Sentiment : Neutre.

À partir de ces exemples, analyse le tweet suivant : « Je suis vraiment déçu de cette journée. »

Indique le sentiment et justifie ta réponse en une phrase.

Questions :
1. Quel est l'intérêt de fournir des exemples ?
2. Que se passe-t-il si les exemples sont mal choisis ?
3. Le résultat est-il cohérent avec les exemples fournis ?

# Travail pratique n° 4 : construire un Prompt Template

Tu es un expert en NLP et en analyse de sentiments.

Analyse le tweet suivant : {TWEET}

Détermine son sentiment parmi : Positif, Négatif, Neutre.

Retourne le résultat au format JSON avec les champs : tweet, sentiment, emotion, justification, confidence.

La confiance est une estimation de ton degré de certitude, et non une probabilité statistiquement calibrée. Si le tweet est ambigu, indique-le explicitement.






## 
