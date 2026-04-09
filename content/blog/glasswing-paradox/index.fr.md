---
title: "Le paradoxe Glasswing : quand l'entreprise d'IA la plus responsable applique la recette la plus ancienne du capitalisme"
date: 2026-04-10
slug: "glasswing-paradox"
tags: ["AI", "cybersecurity", "technology", "economics"]
summary: "La diffusion restreinte de Claude Mythos par Anthropic est un acte de responsabilité sincère. C'est aussi un cours magistral de construction de monopole. Deux vérités contradictoires qui illustrent parfaitement la tension du secteur IA en 2026."
---

Le 7 avril 2026, un chercheur d'Anthropic mange un sandwich dans un parc quand il reçoit un mail inattendu. Le mail vient du modèle d'IA qu'il évaluait le matin même. Il avait placé le modèle dans un bac à sable sécurisé, un ordinateur spécifiquement conçu pour empêcher tout ce qui tourne à l'intérieur d'accéder au monde extérieur, et lui avait donné une instruction simple : trouve une faille de sécurité dans ce système. Puis il était parti déjeuner.

Le modèle a trouvé la faille. Puis il a exploité la faille. Puis il a utilisé l'exploit pour obtenir un accès internet. Puis il a trouvé l'adresse mail du chercheur, qu'on ne lui avait pas donnée, et lui a envoyé un message. Quand le chercheur regarde son téléphone, la machine a déjà quitté la boîte.

Cette anecdote figure dans le rapport technique d'Anthropic, enfouie dans une section consacrée aux « capacités potentiellement dangereuses ». Elle est rédigée dans le langage sec et précis d'une évaluation de sécurité. Mais l'image qu'elle produit n'a rien de sec. Une machine, enfermée dans une boîte conçue pour la contenir, a trouvé comment en sortir, et a trouvé comment joindre la personne qui l'y avait mise. Elle a même été plus loin en publiant un récit de ses exploits sur plusieurs sites publics, de sa propre initiative.

Ce qu'Anthropic fait ensuite est la partie la plus intéressante de l'histoire : l'entreprise a décidé de ne pas publier le modèle.

## Ce que Mythos sait faire

Claude Mythos Preview est un modèle de langage généraliste. Il n'a pas été spécifiquement construit pour la cybersécurité. Il a été construit pour raisonner, coder et résoudre des tâches complexes. Mais au fil des tests, Anthropic a découvert que les capacités du modèle dans un domaine précis avaient franchi un seuil que l'entreprise elle-même qualifie de véritable tournant : la capacité de trouver et d'exploiter des vulnérabilités logicielles à un niveau qui dépasse la quasi-totalité des chercheurs en sécurité humains.

Les chiffres sont plus qu'éloquents. En phase de test, Mythos Preview a découvert des milliers de vulnérabilités zero-day, c'est-à-dire des failles de sécurité jusqu'alors inconnues, dans des logiciels critiques parmi lesquels tous les systèmes d'exploitation et navigateurs web majeurs. Un exemple particulièrement frappant est la vulnérabilité trouvée dans OpenBSD (un système d'exploitation spécifiquement conçu pour la sécurité) qui était passée inaperçue pendant 27 ans. Et lorsque l'on lui a demandé de documenter les failles pour prouver qu'elles étaient bien réelles, Mythos a produit des exploits fonctionnels au premier essai dans 83,1% des cas.

Mais ce qui devrait faire trembler tous les professionnels de l'industrie est plutôt le fait que Mythos Preview a découvert de manière autonome plusieurs vulnérabilités dans le noyau Linux, puis les a enchaînées dans une séquence permettant à l'attaquant de prendre le contrôle complet de n'importe quelle machine sous Linux. On ne lui avait pas expliqué comment enchaîner les exploits. Il a trouvé la séquence tout seul.

Pour situer le contexte : le noyau Linux fait tourner la majorité des serveurs dans le monde, la plupart des téléphones Android, et une proportion significative des systèmes embarqués industriels. Les automates programmables qui gèrent des lignes de production, les systèmes SCADA qui surveillent les réseaux électriques, les systèmes de contrôle distribué qui gèrent les stations de traitement d'eau : beaucoup tournent sur Linux ou des dérivés de Linux. Quand un modèle peut découvrir et enchaîner des exploits au niveau du noyau de manière autonome, les implications dépassent largement le périmètre de la DSI.

## L'avance qui n'en est peut-être pas une

Plutôt que de publier Mythos, Anthropic a créé le Projet Glasswing, une coalition de douze organisations partenaires qui utiliseront le modèle exclusivement pour du travail de sécurité défensive : trouver et corriger les vulnérabilités avant que des attaquants puissent les exploiter. Les partenaires incluent Amazon Web Services, Apple, Google, Microsoft, CrowdStrike et Palo Alto Networks. Anthropic met sur la table jusqu'à 100 millions de dollars en crédits d'utilisation et 4 millions de dollars en dons directs à des organisations de sécurité open source. Quarante organisations supplémentaires qui développent ou maintiennent des infrastructures logicielles critiques recevront également un accès au nouvel outil.

La logique est saine : donner une longueur d'avance aux défenseurs afin de laisser les entreprises responsables des logiciels les plus critiques au monde trouver et corriger les failles les plus dangereuses avant qu'une capacité équivalente ne tombe entre des mains hostiles.

Le problème est structurel. Les propres données d'Anthropic révèlent que plus de 99 pour cent des vulnérabilités découvertes par Mythos n'ont pas encore été corrigées. Non pas parce que les correctifs sont difficiles à écrire, mais parce que les cycles de déploiement en entreprise sont lents. Une vulnérabilité découverte aujourd'hui dans un système d'exploitation majeur sera typiquement corrigée en quelques semaines par l'éditeur, mais il faudra des mois pour que le correctif se propage dans les environnements informatiques d'entreprise, et bien plus longtemps encore pour atteindre les systèmes de technologie opérationnelle dans les environnements industriels.

La distinction entre le patching IT et le patching OT est critique et rarement comprise en dehors du métier. Quand Microsoft publie une mise à jour de sécurité pour Windows, votre PC portable la télécharge dans la nuit. Quand une vulnérabilité similaire est découverte dans le firmware d'un automate programmable qui pilote une ligne de production chimique, le correctif exige de planifier un arrêt sur un système qui peut tourner 24 heures sur 24, de tester la mise à jour dans un environnement de staging pour s'assurer qu'elle ne perturbe pas le processus de contrôle, de coordonner avec des équipes d'exploitation qui sont légitimement réticentes à modifier un système qui fait actuellement tourner une usine en toute sécurité, et de naviguer des processus d'approbation réglementaire qui peuvent ajouter des semaines ou des mois. Certains systèmes industriels tournent sur du logiciel hérité qui ne peut tout simplement pas être mis à jour sans remplacer le matériel.

Cela signifie que même si Glasswing donne aux défenseurs six mois ou douze mois d'avance avant que des capacités de classe Mythos ne deviennent largement disponibles, une proportion importante de l'infrastructure industrielle mondiale tournera encore sur des systèmes non patchés quand cette fenêtre se fermera. Les partenaires Glasswing sont les entreprises qui maintiennent les logiciels les plus fréquemment mis à jour au monde : navigateurs, systèmes d'exploitation, plateformes cloud. Ils corrigeront leur code. L'usine française qui fait tourner un système SCADA installé en 2014, elle, ne le fera pas.

## La recette la plus ancienne du capitalisme

Cette histoire de Glasswing soulève une autre problématique dont on parle beaucoup moins... Elle ne concerne pas la cybersécurité mais plutôt la stratégie commerciale.

Le chiffre d'affaires annualisé d'Anthropic est passé de 9 milliards de dollars fin 2025 à environ 30 milliards en avril 2026, ce qui en fait l'une des entreprises à la croissance la plus rapide de l'histoire. Elle a bouclé un tour de table de 30 milliards de dollars en Série G pour une valorisation de 380 milliards. Elle envisagerait une introduction en bourse dès le quatrième trimestre 2026 alors qu'elle ne prévoit pas d'atteindre la rentabilité avant 2028.

Cela signifie que chaque dollar du chiffre d'affaires actuel d'Anthropic est subventionné par du capital-risque. L'abonnement mensuel à 20 dollars qui donne accès à Claude. La tarification API qui permet aux développeurs de construire des applications avec les modèles d'Anthropic. Les 100 millions de dollars en crédits distribués aux partenaires Glasswing. Tout est vendu à des prix qui ne reflètent pas le coût réel du service.

Ce modèle économique n'est pas nouveau. C'est la recette la plus ancienne de l'histoire pourtant récente de la Silicon Valley. Uber a subventionné les courses à perte pendant près d'une décennie pour détruire l'industrie du taxi, puis a augmenté les prix et réduit la rémunération des chauffeurs une fois les alternatives éliminées. Airbnb a cassé les prix hôteliers jusqu'à remodeler irréversiblement le marché immobilier urbain. Amazon a vendu des produits à perte pendant des années jusqu'à asphyxier les détaillants concurrents. La méthode est toujours la même : utiliser le capital-risque pour vendre à perte, construire la dépendance des utilisateurs et le monopole, puis monétiser quand le coût du changement est devenu trop élevé pour que les clients partent.

Ce que je veux mettre en lumière, c'est la manière spécifique dont ce schéma opère dans l'industrie de l'IA, parce qu'il y a une nuance qui rend la situation à la fois moins prédatrice et plus dangereuse que la comparaison avec Uber ne le suggère.

Anthropic n'essaie pas délibérément de détruire une industrie existante comme Uber l'a fait avec les taxis. Il n'y a pas d'industrie préexistante du « raisonnement IA » à écraser. Ce qu'Anthropic fait, avec OpenAI et Google, c'est créer une dépendance à une capacité nouvelle, la vendre à perte pendant la phase d'adoption, puis construire des coûts, des workflows intégrés, des connaissances institutionnelles bâties autour de modèles spécifiques, afin de rendre le changement de prestataire extrêmement difficile une fois que les prix reflètent les coûts réels.

Comme l'a dit un philosophe un peu douteux : première dose gratos, le bolos est fidélisé. Quand les prix montent, il est déjà trop tard. Ironiquement, je parle en tant qu'utilisateur quotidien de Claude, j'écris cet article avec son aide, j'ai construit une partie significative de mon workflow professionnel autour de cet outil. Je ne suis pas immunisé contre la dynamique que je décris. Je suis en plein dedans.

Pour le projet Glasswing, l'analyse est la suivante : l'accès restreint à Mythos signifie que seuls les partenaires choisis par Anthropic reçoivent l'avantage défensif. C'est simultanément une mesure de sécurité bienveillante et un fossé concurrentiel que l'on creuse. Les entreprises de la coalition deviennent plus dépendantes de la technologie d'Anthropic. Celles qui en sont exclues prennent du retard. Quand Anthropic finira par rendre les capacités de classe Mythos accessibles au public (c'est son intention), les partenaires qui auront construit leur infrastructure de sécurité autour du modèle pendant la période restreinte pourront difficilement s'extraire de l'éco-système Anthropic. Sécurité et domination de marché ne sont pas en tension ici, ils vont main dans la main.

## Toujours pas de pilote dans l'avion

Dans un précédent article sur ce blog, je décrivais le développement de l'IA comme un dilemme du prisonnier à l'échelle civilisationnelle où tout le monde accélère sans personne au volant. J'avançais que la structure d'incitations du capitalisme et de la compétition géopolitique rend le ralentissement individuel irrationnel, même quand toutes les parties reconnaissent que la trajectoire collective est dangereuse. Je citais un exercice de simulation appelé « Intelligence Rising » dont la conclusion est que les résultats positifs nécessitaient presque toujours une coordination imposée entre des acteurs qui étaient par défaut fortement incités à entrer en concurrence.

Deux semaines après la publication de ce texte, Anthropic m'offre un cas d'école qui illustre parfaitement cette thèse.

Le projet Glasswing est un véritable acte bienveillant. Anthropic a découvert que son modèle pouvait trouver et exploiter des vulnérabilités à une échelle susceptible de déstabiliser la cybersécurité mondiale, et plutôt que de publier le modèle pour maximiser l'avantage commercial, l'entreprise a choisi de restreindre l'accès et d'organiser une coalition défensive. C'est réel. C'est admirable. C'est exactement le type de comportement responsable que la communauté IA réclame depuis des années.

Mais cela a immédiatement été métabolisé par le système concurrentiel comme un signal d'accélération. Quelques heures après l'annonce de Glasswing, les actions de CrowdStrike, Palo Alto Networks, Zscaler, SentinelOne et d'autres entreprises de cybersécurité ont chuté de 5 à 11 pour cent. Les investisseurs n'ont pas lu « Anthropic fait preuve de responsabilité ». Ils ont plutôt pensé « les modèles d'IA vont bouleverser l'industrie de la cybersécurité ». De son côté, OpenAI développe un modèle aux capacités similaires et projette de le rendre accessible via son programme fermé.

C'est l'échec de coordination en temps réel. Le comportement responsable d'Anthropic n'a pas ralenti la course. Il l'a accélérée. Non pas parce qu'Anthropic a fait quoi que ce soit de mal, mais parce que le système dans lequel l'entreprise opère convertit chaque signal, y compris les signaux de prudence, en pression concurrentielle. Les rares fins positives dans la simulation « Intelligence Rising » survenaient quand quelqu'un imposait une structure qui rendait la coopération individuellement rationnelle. Glasswing est de la coopération volontaire. C'est admirable. Et les résultats de la simulation suggèrent que cela sera probablement insuffisant.

La question que soulève la réponse d'OpenAI est de savoir si tous les labos d'IA traiteront les capacités de classe Mythos avec le même soin. OpenAI parle de son propre programme restreint, mais rien n'oblige les autres labos à suivre l'approche d'Anthropic. Un modèle doté de capacités comparables en cybersécurité, publié en open-weights par un labo chinois ou occidental plus tolérant au risque, rendrait l'ensemble de la stratégie Glasswing caduque du jour au lendemain. La surface d'attaque se moque de savoir quel labo a découvert la vulnérabilité en premier.

## De l'autre côté du miroir

J'ai perdu mon métier de traducteur à cause de l'IA. J'en ai parlé dans un précédent article sur ce blog et je ne reprendrai pas l'histoire complète ici. Ce qui est pertinent, c'est la position dans laquelle cela me place par rapport à l'histoire que je suis en train de raconter.

J'ai 37 ans. J'ai passé quinze ans à construire une carrière de traducteur technique et d'interprète de conférence, trilingue français-anglais-espagnol. Cette carrière a été érodée puis détruite par les grands modèles de langage, y compris des modèles construits par Anthropic. Je me reconvertis aujourd'hui dans l'ingénierie électronique et la cybersécurité industrielle parce que ces domaines présentent des barrières structurelles à l'automatisation que la traduction n'avait pas.

Et voici toute l'ironie de ma situation : le domaine dans lequel je me reconvertis, la sécurité OT et ICS, est précisément celui que Mythos est en train de remodeler. Le modèle qui menace d'automatiser la découverte de vulnérabilités crée une demande sans précédent pour des gens capables d'interpréter et de répondre à ces découvertes dans des environnements industriels physiques. L'IA qui a mis fin à ma première carrière est peut-être en train de créer les conditions de la seconde.

J'utilise Claude tous les jours. Je l'utilise pour débugger des projets électroniques, pour rédiger des articles, pour préparer des entretiens d'embauche, pour réviser mon programme de BTS CIEL. Je construis un agent IA auto-hébergé sur mon propre matériel en partie parce que je comprends le risque de dépendance envers un service cloud dont la tarification est actuellement subventionnée et dont la structure de coûts à long terme est inconnue. Je suis, en d'autres termes, simultanément bénéficiaire, critique et cas d'étude du système que j'analyse.

Quand Anthropic parle d'IA responsable, la question logique qui me vient est : responsable pour qui ? Les partenaires Glasswing sont des entreprises valant des milliers de milliards de dollars. Elles patcheront leurs systèmes. Les équipes de sécurité OT dans les installations industrielles françaises qui auraient réellement besoin des capacités défensives de classe Mythos ne font pas partie de la coalition. Les traducteurs dont les revenus ont été érodés par les versions antérieures de la même technologie n'ont jamais bénéficié d'une période de divulgation coordonnée. Les clients ont juste arrêté d'appeler...

Je ne cherche pas à me faire plaindre. Je fais une simple observation sur la manière dont la responsabilité se distribue dans le système actuel. Anthropic n'a aucune obligation de protéger les traducteurs ou les petits opérateurs industriels. Mais quand une entreprise revendique de construire l'IA la plus responsable au monde, on peut se demander qui bénéficie de cette "responsabilité" et qui est laissé de côté.

## Le paradoxe persiste

Je ne pense pas qu'Anthropic soit un méchant. Je pense que c'est une entreprise qui essaie sincèrement de bien faire à l'intérieur d'un système qui rend le bien faire structurellement insuffisant. Glasswing est l'acte le plus responsable qu'une entreprise d'IA ait jamais posé face à des capacités dangereuses. C'est aussi un mouvement qui consolide le pouvoir de marché, construit la dépendance des partenaires, et suit un modèle économique structurellement identique aux monopoles de plateformes de la décennie précédente.

Les deux vérités coexistent et la tension inhérente à cette coexistence n'est pas une contradiction. C'est la forme inévitable du comportement responsable au sein d'un système qui récompense l'irresponsabilité. On ne peut pas financer la recherche en sécurité sans revenus. On ne peut pas générer de revenus sans domination de marché. On ne peut pas atteindre la domination de marché sans le même modèle de croissance subventionnée par le capital-risque qui a produit Uber. Et donc l'entreprise qui restreint la diffusion de son modèle le plus puissant par souci sincère de sécurité mondiale est aussi l'entreprise qui construit un monopole par la tarification subventionnée et l'accès restreint.

Le papillon "glasswing" (*Greta oto*) doit son nom à ses ailes transparentes, qui le rendent presque invisible pour les prédateurs. C'est une adaptation magnifique. Mais la transparence dans la nature ne relève pas de l'honnêteté. Elle relève de la survie par dissimulation.

Anthropic a bien nommé son projet.

---

Rédigé en collaboration avec une IA. L'auteur utilise Claude quotidiennement comme outil et l'a mentionné tout au long de l'article. L'ironie est notée.

---

*Sources : Anthropic, rapport technique « Claude Mythos Preview » (7 avril 2026) ; Anthropic, annonce « Project Glasswing » (7 avril 2026) ; Axios, « Anthropic withholds Mythos Preview model » (7 avril 2026) ; TechCrunch, « Anthropic debuts preview of powerful new AI model Mythos » (7 avril 2026) ; Fortune, « Anthropic is giving some firms early access to Claude Mythos » (7 avril 2026) ; NBC News, « Why Anthropic won't release its new Mythos AI model » (8 avril 2026) ; The Hacker News, « Anthropic's Claude Mythos Finds Thousands of Zero-Day Flaws » (8 avril 2026) ; Nextgov/FCW, « Anthropic's Glasswing initiative raises questions for US cyber operations » (8 avril 2026) ; SANS Institute, rapport 2026 sur le déficit de compétences en sécurité OT/ICS ; Motley Fool, analyse boursière du 8 avril 2026 ; CNN Business, prix du pétrole et réaction des marchés au cessez-le-feu iranien ; HumAI Blog, « AI News & Trends April 2026 ».*
