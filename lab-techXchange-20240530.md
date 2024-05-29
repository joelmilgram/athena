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

L'assistant utilise le contenu du fichier pour étendre ses connaissances. Lors des futures requêtes, si un élément de ce document est sémantiquement proche, alors le LLM s'en servira dans la composition de la réponse à l'instar de tous les autres éléments de connaissance dont il dispose. D'un point de vue technique, cette fonction associée aux LLMs s'appelle la récupération augmentée de récupération ou Retrieval Augmented Generation (RAG).

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

Maintenant que les connaissances du LLM ont été enrichies des règles métier d'IBU Assurances, on pourrait penser que le LLM, qui a accès aux données, serait capable de les appliquer.

Posons lui quelques questions concernant les clients et leurs sinistres.

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

__Le client Robert Dupont est dans le cas de la règle UP1 détaillée ci-dessus__
2. Appuyez sur `Enter` ou cliquez sur la flèche


Après quelques secondes de traitement, vous observerez la réponse dans la conversation :

<img width="1186" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/5b7ff9af-767f-41c6-a137-86b24a40f075">

---

Conformément aux recommandations du prompt, l'assistant détaille les informations récupérées sur le client et le sinistre. Puis l'assistant indique l'objet de la réclamation.

Les deux derniers paragraphes conseillent sur la suite à donner avec la référence de la règle de gestion.

<img width="727" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/bebd1a30-5376-4d68-807f-7b6b3b78cf0f">

L'assistant est connecté à une base de données sur des clients et leurs sinistres.

Un certain nombre de caractéristiques est disponible sur chaque client et sur chaque sinistre.


---

---

# 3. Découverte de l'assistant

---

---

# 4. Découverte de l'assistant

