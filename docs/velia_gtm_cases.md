Simulations GTM Engineer — Vélia
19 nov. 2026 · @Alexandre Kuzo
Trois demandes internes simulées, à traiter comme si tu étais le GTM Engineer de Vélia. Chaque cas peut devenir une preuve technique publiée.
Mode d'emploi
Traite chaque cas comme un vrai ticket : la demande est volontairement floue, comme en entreprise. Le travail commence par la découverte, pas par le code.
1.  Cadrer. Pose-moi tes questions dans le chat : je joue le stakeholder et je réponds comme lui, y compris de façon incomplète ou contradictoire.
2.  Proposer. Rédige une note d'une page (problème, options, recommandation, ce qui est hors périmètre) avant de construire.
3.  Construire. Sur une Developer Edition Salesforce, avec des données de démo que je peux générer.
4.  Livrer. Démo, README, et un message de restitution au stakeholder.
5.  Débriefer. Je te dis ce qu'un manager exigeant aurait relevé, et quels pièges tu as évités ou ratés.
Chaque cas contient des pièges non écrits ici. Une bonne découverte les fait remonter ; c'est ce qui sépare un exécutant d'un GTM Engineer.
L'entreprise
Vélia (fictive) édite un logiciel SaaS de planning pour les réseaux de magasins et franchises. 180 salariés, siège à Nantes, environ 1 200 clients en France et en Belgique. Tu viens d'arriver comme premier GTM Engineer, rattaché au Head of RevOps.
Brique
Outil
À savoir
CRM
Salesforce Sales Cloud
Source de vérité commerciale ; Leads, Accounts, Opportunities
Marketing automation
HubSpot Marketing
Formulaires du site, campagnes, UTM ; synchronisé avec Salesforce via le connecteur natif
Communication
Slack
Un canal par équipe, peu d'automatisations
Appels commerciaux
Modjo
Enregistrement et transcription des démos
Produit
PostgreSQL + Metabase
Données d'usage, pas encore reliées au CRM
Équipe
Qui
Effectif
Sales
Karim, Head of Sales
4 SDR, 8 AE (SMB et Mid-Market), découpés par région
Marketing
Claire, CMO
6 personnes dont 1 Marketing Ops
RevOps
Nadia, Head of RevOps (ta manager)
1 admin Salesforce + toi
Customer Success
Thomas, Head of CS
7 CSM, 2 Account Managers pour l'upsell
Cas 1 — Les demandes de démo attendent trop longtemps
Karim (Head of Sales), dans #revops : « On a des demandes de démo qui attendent 2 jours avant qu'un SDR les appelle. Hier un prospect m'a dit qu'il avait déjà signé chez un concurrent. Je veux que chaque demande soit prise en charge dans l'heure. Tu peux regarder ? »
Ce que tu sais
• Les demandes arrivent par le formulaire HubSpot « Demander une démo », puis deviennent des Leads Salesforce via la synchro.
• L'assignation actuelle est une règle d'attribution Salesforce par région, écrite il y a 3 ans.
• Environ 120 demandes par mois. Personne ne mesure aujourd'hui le délai de premier contact.
Livrables attendus
• Une mesure du problème : délai médian entre la demande et le premier contact, sur des données de démo réalistes.
• Un routing revu : bon interlocuteur, répartition équitable, cas particuliers gérés.
• Une alerte Slack quand un lead approche ou dépasse le délai d'une heure, avec escalade.
• Un tableau de bord « speed-to-lead » par SDR et par semaine.
Critères de réussite : 90 % des demandes contactées en moins d'une heure en heures ouvrées ; aucune demande sans propriétaire ; Karim comprend le dispositif sans toi.
Compétences travaillées : Flow ou Apex, logique d'assignation, heures ouvrées (Business Hours), Slack, reporting Salesforce.
Cas 2 — Marketing et Sales ne comptent pas le même pipe
Nadia (Head of RevOps), en 1:1 : « Au dernier comité de direction, Claire a annoncé que le marketing avait généré 60 % du pipe du trimestre. Karim a répondu que c'était plutôt 25 %. Le CEO m'a demandé un chiffre fiable pour le prochain comité, dans 3 semaines. Je te confie le sujet. »
Ce que tu sais
• Claire tire ses chiffres de HubSpot ; Karim, d'un rapport Salesforce sur le champ Lead Source des Opportunités.
• Le champ Lead Source est rempli par la synchro HubSpot, mais aussi à la main par les commerciaux.
• Les UTM sont capturés par HubSpot sur les formulaires. Personne ne sait s'ils arrivent jusqu'aux Opportunités.
Livrables attendus
• Un diagnostic : pourquoi les deux chiffres diffèrent, avec des exemples concrets d'enregistrements.
• Une définition partagée de « pipe sourcé marketing », à faire valider par Claire et Karim.
• Un modèle de données corrigé (champs, mapping de synchro, règles de mise à jour) et un script de rattrapage de l'historique.
• Un rapport ou tableau de bord unique que les deux équipes acceptent.
Critères de réussite : un seul chiffre présenté au comité, sa méthode explicable en deux phrases, et les nouveaux leads correctement tracés désormais.
Compétences travaillées : modèle de données Salesforce, synchro HubSpot ↔ Salesforce, modèles d'attribution, scripts de correction de données (Python ou Batch Apex), et surtout la médiation entre deux équipes.
Cas 3 — Le forecast n'est pas fiable
Karim (Head of Sales), dans #revops : « On a raté le forecast de 30 % le trimestre dernier. La moitié des opportunités ont une date de closing dépassée ou pas de prochaine étape. Les AE disent qu'ils n'ont pas le temps de remplir Salesforce. Il me faut une vision fiable du pipe chaque lundi, sans transformer mes AE en secrétaires. »
Ce que tu sais
• Les Opportunités ont des champs MEDDICC créés il y a un an, remplis sur moins de 20 % des deals.
• Toutes les démos sont enregistrées et transcrites dans Modjo.
• La revue de pipe a lieu le lundi à 10 h, à partir d'un rapport Salesforce exporté dans Google Sheets.
Livrables attendus
• Un repérage automatique des deals à risque : date dépassée, aucune activité depuis 14 jours, étape incohérente avec le montant ou la qualification.
• Un agent qui lit la transcription d'un appel et propose la mise à jour de l'Opportunité : prochaine étape, champs MEDDICC, risques, informations manquantes.
• Une validation par l'AE dans Slack avant toute écriture dans Salesforce.
• Un résumé du pipe envoyé à Karim chaque lundi à 8 h.
Critères de réussite : moins de 5 minutes par AE et par semaine consacrées à la mise à jour ; champs MEDDICC remplis sur plus de 70 % des deals actifs en un mois ; Karim prépare sa revue sans export manuel.
Compétences travaillées : LangGraph, extraction structurée par LLM, validation humaine dans Slack, Scheduled Flow ou Batch Apex, et l'adoption par les commerciaux.
Pour les transcriptions, des transcriptions fictives suffisent ; je peux t'en générer une dizaine, avec leurs cas tordus.