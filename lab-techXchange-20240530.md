### IBM TechXchange: Réinventer les Processus Métier à l’ère de l’IA

30 mai 2024
![illustration](https://github.com/joelmilgram/athena/assets/150163964/0b09678f-0613-4999-a47b-6c7d055c7221)

Joel Milgram, Principal, Athena Decision Systems

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


**Bonjour à tous et bienvenue à notre workshop sur l'automatisation intelligente des décisions avec IBM!**

Aujourd'hui, nous allons explorer comment les technologies d'intelligence artificielle, et plus particulièrement les assistants conversationnels basés sur l'IA générative, peuvent être utilisés pour extraire des informations pertinentes et automatiser certaines tâches liées aux textes. Cependant, nous verrons également que ces assistants peuvent rencontrer des limites lorsqu'il s'agit de prendre des décisions complexes, notamment lorsqu'ils doivent interpréter des policies ou des règles métier détaillées.

Pour surmonter ces limitations, nous allons explorer un concept fondamental qui ne doit pas être éclipsé par les avancées fulgurantes de l'IA générative. Il s'agit de savoir tirer le meilleur parti de toutes les technologies d'Intelligence Artificielle : appliquer une IA hybride. L'IA générative a démontré des capacités remarquables pour travailler sur des documents : résumé, traduction, mise en relation, recherches sémantiques... En revanche, si l'on demande à une IA générative de prendre une décision sur la basee de règles, l'approche probabiliste du LLM (Large Language Model) risque de générer un résultat totalement incorrect qui pourrait être préjudiciable dans un contexte métier.
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

1. **Introduction à ChatGPT:** Nous commencerons par une présentation des capacités de ChatGPT et de ses limites dans la prise de décision.
2. **Introduction au Function Calling:** Ensuite, nous verrons comment utiliser le function calling pour connecter ChatGPT à un moteur de règles.
3. **Démonstration Pratique:** Nous créerons ensemble un assistant conversationnel et le connecterons à un moteur de règles pour un cas d'utilisation pratique.
4. **Modification des Règles:** Enfin, nous modifierons une règle dans le moteur de règles pour vérifier que l'assistant délègue bien la décision et que les changements sont pris en compte.

**À la fin de ce workshop, vous serez en mesure de:**

- Comprendre comment extraire des informations pertinentes à partir de textes complexes en utilisant ChatGPT.
- Configurer un assistant conversationnel qui utilise un moteur de règles pour des décisions fiables.
- Apporter des modifications aux règles et vérifier leur impact sur les décisions prises par l'assistant.

Je vous encourage à participer activement, poser des questions, et profiter de cette opportunité pour explorer les possibilités passionnantes de l'automatisation intelligente. Ensemble, nous allons voir comment combiner le meilleur des deux mondes pour créer des solutions robustes et efficaces.

---

**Merci et bon workshop à tous!**
