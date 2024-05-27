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

Sur votre ordinateur, lancer Microsoft Remote Desktop

PC: l'URL de l'instance réservée pour vous

Username: `techzone`

Password: ÌBMDem0s`

<img width="590" alt="image" src="https://github.com/joelmilgram/athena/assets/150163964/9d44e3f6-50a5-4476-a3c8-1fc63e87f8f5">

---

---

# 3. Découverte de l'assistant

---

---

# 4. Découverte de l'assistant

