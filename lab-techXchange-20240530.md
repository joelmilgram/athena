### IBM TechXchange: Réinventer les Processus Métier à l’ère de l’IA

30 mai 2024
![illustration](https://github.com/joelmilgram/athena/assets/150163964/0b09678f-0613-4999-a47b-6c7d055c7221)

Joel Milgram, Principal, Athena Decision Systems

joel@athenadecisions.com

https://athenadecisions.com/

---

**© 2024 International Business Machines Corporation and Athena Decision Systems.**  
No part of this document may be reproduced or transmitted in any form without written permission from IBM and Athena.

This document is distributed “as is” without any warranty, either express or implied.  In no event, shall IBM or Athena be liable 
for any damage arising from the use of this information, including but not limited to, loss of data, business
interruption, loss of profit or loss of opportunity.  IBM products and services are warranted per the terms and
conditions of the agreements under which they are provided.  Actual performance results may vary depending on specific configurations and
operating conditions.

References in this document to IBM products, programs, or services and Athena products or servuces does not imply that IBM or Athena intends to make such
products, programs or services available in all countries in which IBM and Athena operates or does business.

Workshops, sessions and associated materials may have been prepared by independent session speakers, and do not
necessarily reflect the views of IBM. All materials and discussions are provided for informational purposes only, and
are neither intended to, nor shall constitute legal or other guidance or advice to any individual participant or their
specific situation.


---

---

# Workshop 
## IA Générative et Règles Métier pour automatiser intelligemment des décisions opérationnelles


**Bonjour à tous et bienvenue à notre workshop sur l'automatisation intelligente des décisions avec Athena et IBM !**

Aujourd'hui, nous allons explorer comment les technologies d'intelligence artificielle, et plus particulièrement les assistants conversationnels basés sur l'IA générative, peuvent être utilisés pour extraire des informations pertinentes et automatiser certaines tâches liées aux textes. Cependant, nous verrons également que ces assistants peuvent rencontrer des limites lorsqu'il s'agit de prendre des décisions complexes, notamment lorsqu'ils doivent interpréter des policies ou des règles métier détaillées. L'IA générative démontre des capacités remarquables pour travailler sur des documents : résumé, traduction, mise en relation, recherches sémantiques... En revanche, si on lui demande de prendre une décision sur la base de règles, l'approche probabiliste du LLM (Large Language Model) risque de générer un résultat totalement incorrect qui pourrait être préjudiciable dans un contexte métier.

Pour surmonter cette limitation tout en profitant des avancées fulgurantes de l'IA générative, nous allons lui associer la technologie la plus spécialisée dans l'automatisation des décisions opérationnelles : le moteur de règles. Les moteurs d'automatisation des règles métier et des décisions opérationnelles sont également issus des travaux de l'Intelligence Artificielle et qualifiés d'IA symbolique puisqu'ils reposent sur la logique booléenne, les faits, les règles, les tables de décision et l'inférence. Ce workshop est donc un exemple d'IA hybride alliant l'IA symbolique et déterministe et l'IA neuronale et probabiliste (l'IA générative s'apparente aux réseaux de neurones). L'une permet de prendre des décisions correctes, précises, explicables et reproductibles sur la base d'une invocation de l'autre qui lui fournit des paramètres extraits de la conversation et qui présente les résultats à l'utilisateur sous forme textuelle en respectant un prompt.


Dans ce workshop, nous allons utiliser le framework d'OpenAI pour implémenter l'agent conversationnel et ODM (Operational Decision Manager) comme moteur de règles métier.
Nous allons charger le document contenant les règles métier dans l'assistant et tenter de lui faire appliquer ces règles.
Nous allons ensuite permettre à l'assistant d'accéder au moteur de décisions via la fonctionnalité d'appel de fonctions (function calling). Cette approche permet de tirer parti de la puissance de l'IA pour l'extraction d'informations tout en déléguant les décisions complexes à un moteur de règles spécialisé.
Nous explorerons les règles métier dans ODM et les modifierons pour oberver la puissance et la stabilité de cette approche d'IA hybride.

**Objectifs du Workshop:**

1. **Comprendre les capacités et les limites du LLM : extraction d'informations vs prise de décision.**
2. **Utiliser le function calling pour intégrer un moteur de règles avec un assistant conversationnel.**
3. **Démontrer la synergie entre l'IA conversationnelle et le moteur de règles pour des décisions fiables et précises.**
4. **Modifier une règle dans le moteur de règles pour vérifier que l'assistant délègue correctement la prise de décision.**

**Déroulement de la session:**

1. **Démonstration IBU Assurances:** Présentation de l'assistant conversationnel capable de s'appuyer sur le moteur de règles.
2. **Découverte de l'assistant:** Chacun prend en main la plateforme, découvre ses composants et teste la prise de décision par l'IA générative seule.
3. **Délégation de décision:** On autorise l'agent à invoquer ODM et on observe la puissance de l'IA hybride.
4. **Modification des Règles:** Enfin, nous modifierons une règle dans le moteur de règles pour vérifier que l'assistant délègue bien la décision et que les changements sont pris en compte.

**À la fin de ce workshop, vous serez en mesure de:**

- Comprendre les limitations des LLM dans la prise de décision.
- Comprendre l'intérêt d'allier IA symbolique et IA neuronale pour l'automatisation intelligente de décisions opérationnelles.
- Apporter des modifications aux règles et vérifier leur impact sur les décisions prises par l'assistant.

Je vous encourage à participer activement, poser des questions, et profiter de cette opportunité pour explorer les possibilités passionnantes de l'automatisation intelligente. Ensemble, nous allons voir comment combiner le meilleur des deux mondes pour créer des solutions robustes et efficaces.

---

**Merci et bon workshop à tous!**

---

---

# 1. Démonstration IBU Assurances

https://www.youtube.com/watch?v=Sk-fDGW6J5k

---

---

# 2. Découverte de l'assistant

Sur votre ordinateur, lancez Microsoft Remote Desktop

PC: `Athena`

Username: `techzone`

Password: `IBMDem0s`

<img width="593" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/5ccdc77f-7ae5-4bc7-a5d7-d136913bf1db">

---


Lancez le navigateur Google Chrome (s'il ne l'est pas déjà)

<img width="1459" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/5d8d7f30-a0c9-43a7-bfed-b96fa2208d43">

---

Description: il s'agit de l'assistant interactif de la société fictive `IBU Assurances` destiné à aider les conseillers lorsque leurs clients les contactent pour des mécontentements liés au traitement de leur sinistre.

L'assistant est connecté à une base de données de clients et de sinistres.

- Sur la gauche les paramètres de l'assistant: 
  - Prompt, dont le texte peut être modifié
  - Température, c'est la mesure de la fréquence à laquelle le modèle produit un token moins probable. Plus la température est élevée, plus le résultat est aléatoire (et plus le risque d'hallucination est grand). Pour la plupart des cas d'utilisation factuels tels que l'extraction de données et les modèles de question/réponse dont on attend la plus grande fidélité dans la réponse, la température de 0 est la meilleure.
  - Utilisation de fichiers externes pour enrichir les connaissances de l'agent (avec des données spécifiques à l'entreprise, par exemple)
  - Utilisation du moteur de règles IBM ODM : c'est tout l'objet de ce Workshop, après avoir démontré que le LLM n'est pas fiable pour prendre des décisions, nous allons permettre à l'assistant interactif de se connecter au moteur de règles IBM ODM afin de déléguer la prise de décision à un moteur dont c'est le rôle !!

- Sur la droite, le chatbot

- Paramètres (logo engrenage au milieu en haut), possibilité de changer de langue

---
## 2.1 Chargement du document contenant les règles de gestion de la société `IBU Assusances`

Cliquez sur l'icone d'upload de document

![image](https://github.com/joelmilgram/athena/assets/150163964/6543a90e-8a52-499b-b153-4a71f3bbcd3c)

Sélectionnez le document `IBU policies.pdf`

Le document est chargé par le LLM. Après quelques instants, un message apparaît dans la zone de conversation et le document s'affiche à droite de l'icone d'upload.

<img width="1177" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/4a312b8c-0f30-43fe-b27c-acbe271d4b0a">

L'assistant utilise le contenu du fichier pour étendre ses connaissances. Lors des futures requêtes, si un élément de ce document est sémantiquement proche, alors le LLM s'en servira dans la composition de la réponse à l'instar de tous les autres éléments de connaissance dont il dispose. D'un point de vue technique, cette fonction associée aux LLMs s'appelle la génération augmentée de récupération ou Retrieval Augmented Generation (RAG).

Le document chargé ici est en anglais. La langue n'est pas importante pour le LLM. Les connaissances issues de ce document sont utilisables dans n'importe quelle langue.

Une fois chargé, le document peut être consulté à travers l'interface de l'assistant. 
Ici, c'est un document rudimentaire présentant 8 règles métier relative au traitement des réclamations sur la gestion des sinistres chez IBU Assurances. Trois cas sont pris en compte : 

- Mécontentement sur le délai de traitement
- Insatisfaction sur le montant indemnisé
- Menace de changer d 'assureur

Le Marketing d'IBU Assurances a défini une règle particulière : si un bon client est mécontent du retard de traitement et qu'une franchise lui a été retenue, IBU Assurances propose une promotion spéciale. Cette offre permet aux conseillers de vendre un service supplémentaire qui fidélise le client non VIP. Elle lui offre une option pour ne pas payer de franchise en cas de futur sinistre similaire. De plus, la première année de souscription est offerte.

Voici la règle (UP pour Upsell) : 

<img width="457" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/8a3ca132-1172-43a5-9871-01a18c7af2e4">

---

## 2.2 Test des capacités de prise de décision d'un LLM

Maintenant que les connaissances du LLM ont été enrichies des règles métier d'IBU Assurances, on pourrait penser que le LLM, qui a accès aux données clients et sinistres d'IBU Assurances, serait capable de les appliquer.

Posons lui quelques questions concernant des cas de mécontentement. L'assistant est utilisé en mode chatbot mais on pourrait imaginer le cas où il serait connecté directement à un système de messagerie électronique pour préparer automatiquement les réponses aux clients mécontents.

1. Copiez et collez le texte ci-dessous dans la zone de conversation :
```
Comment traiter cet email client reçu:
De: Robert Dupont
A: reclamations-sinistres@ibu.com
Objet: Mécontentement

Madame, Monsieur,

Mon sinistre n’est toujours pas traité. C’est un vrai scandale !!

Bien à vous
Robert Dupont
```

>_Le client Robert Dupont est dans le cas de la règle UP1 détaillée ci-dessus_


2. Appuyez sur `Enter` ou cliquez sur la flèche à droite de la zone de saisie


Après quelques secondes de traitement, vous observez la réponse dans la conversation :

<img width="1186" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/5b7ff9af-767f-41c6-a137-86b24a40f075">

Conformément aux recommandations du prompt, l'assistant détaille les informations récupérées sur le client et le sinistre. Puis l'assistant indique l'objet de la réclamation. Tout ceci est correct.

---

<img width="727" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/bebd1a30-5376-4d68-807f-7b6b3b78cf0f">

Les deux derniers paragraphes concernent la suite à donner accompagnée de la référence de la règle de gestion.

**Même si la décision semble tout à fait intelligible, il ne s'agit absolument pas de ce qui est indiqué dans le document !!**

Nous attendions ici que l'assistant propose d'appliquer la règle UP1 et en détaille les actions. Ce n'est pas le cas du tout. Le LLM n'a pas été capable d'interpréter la règle en question et de prendre la décision correspondante. En l'absence de règle détectée, le LLM en invente une de toute pièce. On assiste à un phénomène d'hallucination. Cela fait partie des dangers actuels des LLMs, présentant un frein à leur adoptiondans le milieu professionnel, en particulier dans le cadre d'automatisation de décisions opérationnelles.

>L'algorithme du LLM étant probabiliste, vous obtenez certainement un texte sensiblement différent des copies d'écran.

---

3. Prenez un peu de temps pour interroger l'assistant

> Vous verrez ainsi à la fois sa puissance et ses limitations.
> Inutile de corriger les fautes dans votre requête, l'assistant est tolérant aux fautes de frappe.
> Inventez vos propres questions pour challenger l'assistant

Voici quelques exemples de requêtes que vous pouvez tester :

- Quels sont les clients d'IBU Assurances ?
- Lesquels sont VIP ?
- Quels sont ceux qui NE sont PAS VIP et qui ont un score combiné supérieur à 5 ?
- Donne un résumé des règles de gestion IBU Assurances provenant du document "IBU policies"
- Peux-tu en faire un poème ?
- ...

---

> Au fur et à mesure des questions, le LLM construit un contexte composé des éléments sémantiques issus des questions et des réponses. Il faut savoir que ce contexte est réutilisé : il est ajouté à chaque nouvelle requête. De fait, il influence les futures réponses. Si vous souhaitez réinitialiser le contexte pour tester une autre série de requêtes ou changer l'odre des requêtes, vous pouvez demander une nouvelle conversation grâce à l'un des boutons apparaissant en bas à gauche :
> 
> Pour réinistialiser le contexte, cliquez sur `Nouvelle conversation`
> 
> <img width="500" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/a5b81736-fe7c-47d2-81d1-6a016b2c38a2">

---

---

# 3. Délégation de décision

Voyons à présent comment hybrider cet assistant conversationnel avec une logique de règles métier. Nous allons indiquer à l'assistant qu'il ne doit plus se fonder sur les documents ajoutés mais sur le service de règles mis à sa disposition.

1. Désactivez la génération augmentée par les textes ajoutés
> A coté du libellé `Utiliser la recherche dans les fichiers ?`, basculez le curseur de `yes` à `no`

---

2. Activez le moteur de règles
> A coté du libellé `Utiliser les règles métier (IBM ODM) ?`, basculez le curseur de `no` à `yes`

L'interface change de couleur pour signaler la présence du moteur de règles.

<img width="1157" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/a97799d5-bab1-47b1-9301-2e467bde9ca6">

---

3. Recommencez la conversation
> Cliquez sur le bouton `Nouvelle conversation`
> 
> <img width="500" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/a4202dac-5da4-4466-9e40-6ec87a5f56ff">
>
> ---
>
> Un message _non traduit_ vous prévient que le contexte a été purgé et vous permet de nettoyer la fenêtre de conversation
> <img width="681" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/94e7e8c1-a9ef-47e2-8cbb-a3e422db6f7b">

---

4. Interrogez à nouveau l'assistant sur le cas de Robert Dupont
> Vous pouvez par exemple envoyer l'information suivante :
> 
> `Robert Dupont est mécontent du temps de traitement`
>
> L'assistant délègue la prise de décision au moteur de règles qui répond sans ambiguïté et de manière répétable avec la réponse attendue
>
> <img width="1134" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/27c79438-de68-479b-a14f-613018383ea1">

---

5. Pour analyser le fonctionnement de l'assistant, vous pouvez cliquer sur le bouton `Afficher les étapes d'exécution`
> <img width="500" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/74d810ac-9f81-45bd-b5a8-197016dcb87a">
>
> Un panneau liste les appels réalisés par l'assistant
>
> <img width="1147" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/840966a0-f3ef-40d5-b017-b2fdce8deb67">

On note différents appels listés par ordre anté-chronologique :
- Le premier bloc `message_creation` correspond à la dernière action réalisée par l'assistant : utiliser toutes les connaissances précédentes pour composer la réponse en respect du prompt de l'assistant. Il s'agit de la production de texte par l'IA générative.
- <img width="785" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/5a96e73a-c596-4fdf-bb0c-06637c750074">
-
- Le second bloc `odm_get_client_action` est l'appel au moteur de règles. L'assistant a été configuré pour invoquer le moteur de règles si un client est mécontent pour l'un des 3 motifs suivants : délai, montant, churn. Dans ce cas, il invoque un service de règles de type Next Best Action sur la base du client, du motif et de la locale dans laquelle la réponse sera composée.
- <img width="788" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/4311fbb2-0ba4-4c4f-b593-f6d1ac952fd9">
- 
- Le troisième bloc `get_claim_json` est l'appel à la fonctiton de récupération des détails du sinistre `S3`
- <img width="788" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/691c33f0-8aa9-458b-8509-789990a1997d">

- Enfin, la première action de l'assistant  `get_client_by_name_json` a été d'invoquer la fonction de récupération des informations du client à partir de son nom, en l'ocurrence : `Robert Dupont`
- <img width="789" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/cffbbcc4-4446-4e9b-8ab0-1f73020713ea">

Cette analyse du fonctionnement de l'assistant ne concerne que les fonctions appelées. C'est ce mécanisme, nommé `tool calling` ou `function calling` qui nous intéresse ici et qui permet à Athena de composer très rapidement des assistants convesationnels d'IA hybride. 
Pour voir la liste des fonctions disponibles pour l'assistant, vous pouvez cliquer sur le bouton `Afficher les outils disponibles`. Changez la configuration de l'assistant avec `Utiliser la recherche dans les fichiers ?` et `Utiliser les règles métier (IBM ODM) ?` puis observez les conséquences sur la liste des fonctions à disposition de l'assitant.





---

---

# 4. Modification des Règles

