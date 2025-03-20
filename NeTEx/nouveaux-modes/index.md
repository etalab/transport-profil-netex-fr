## Avant-propos
L’harmonisation des pratiques dans l’échange des données relatives aux offres de transport est essentielle :

* pour l’usager, aux fins d’une présentation homogène et compréhensible de l’offre de transport et de l’engagement sous-jacent des organisateurs (autorités organisatrices et opérateurs de transports) ;

* pour les AOT, de manière à fédérer des informations homogènes venant de chacun des opérateurs de transports qui travaillent pour elle. 

*   L’harmonisation des échanges, et en particulier le présent profil, pourra le cas échéant être imposée par voie contractuelle. Cette homogénéité des formats d’information permet d’envisager la mise en place de systèmes d’information multimodaux, produisant une information globale de l’offre de transports sur un secteur donné, et garantir le fonctionnement des services d’information, en particulier des calculateurs d’itinéraires, et la cohérence des résultats, que ces services soient directement intégrés dans ces systèmes d’information multimodaux ou qu’ils puisent leurs informations sur des bases de données réparties ;

* pour les opérateurs, qui pourront utiliser ce format d’échange pour leurs systèmes de planification, les systèmes d’aide à l’exploitation, leurs systèmes billettiques et leurs systèmes d’information voyageur (information planifiée et information temps réel)

* pour les industriels et développeurs pour pérenniser et fiabiliser leurs investissements sur les formats d’échanges implémentés par les systèmes qu’ils réalisent, tout en limitant fortement l’effort de spécification lié aux formats d’échange

Ce document est le fruit de la collaboration entre les différents partenaires des autorités organisatrices de transports, opérateurs, industriels, développeurs de solutions et de systèmes informatiques, et associations d'usagers ayant pour objet l’aide à l’exploitation du transport public et l’information des voyageurs. Il a pour objet de présenter le profil d’échange Profil NeTEx Nouveaux modes: "format de référence pour l'échange de données de description des nouveaux modes" (issu des travaux NeTEx et Transmodel) qui aujourd’hui fait consensus dans les groupes de normalisation (CN03/GT7 – Transport public / information voyageur).

# Introduction

Le présent format d'échange est un profil France de NeTEx.

NeTEx (CEN TS 16614-1, 16614-2 et 16614-3) propose un format et des services d'échange de données de description de l'offre de transport planifiée, basé sur Transmodel (EN 12896) et l’ancienne norme IFOPT (EN 28701). NeTEx permet non seulement d'assurer les échanges pour les systèmes d'information voyageur mais traite aussi l’ensemble des concepts nécessaires en entrée et sortie des systèmes de planification de l'offre (graphiquage, etc.) et des SAE (Systèmes d’Aide à l’Exploitation).

NeTEx se décompose en six parties :

* Partie 1 : topologie des réseaux (les réseaux, les lignes, les parcours commerciaux les missions com-merciales, les arrêts et lieux d’arrêts, les correspondances et les éléments géographiques en se limitant au strict minimum pour l’information voyageur) 

* Partie 2 : horaires théoriques (les courses commerciales, les heures de passage graphiquées, les jours types associés ainsi que les versions des horaires)

* Partie 3 : information tarifaire (uniquement à vocation d’information voyageur) 

* Partie 4 : Profil Européen pour l’information voyageur (EPIP : European Passenger Information Profile) 

* Partie 5 : NeTEx NOuveaux modes (vehicle sharing, vehicle pooling, etc.) 

* Partie 6 : Profil Europeen pour l'accesibilité

NeTEx a été développé dans le cadre du CEN/TC 278/WG 3/SG 9 piloté par la France. Les parties 1 et 2 ont été publiées en tant que spécification technique début 2014. Les travaux pour la partie 3, quant à eux, se sont terminés en 2016.

Il faut noter que NeTEx a été l'occasion de renforcer les liens du CEN/TC278/WG3 avec le secteur ferrovaire, en particulier grâce à la participation de l'ERA (Agence Européen du Rail, qui a intégré NeTEx dans la directive Eu-ropéenne 454/2011 TAP-TSI ) et de l'UIC (Union International des Chemins de fer).

Les normes, dans leur définition même, sont des « documents établis par consensus ». Celles du CEN/TC278 sont de plus établies à un niveau européen, en prenant donc en compte des exigences qui dépassent souvent le périmètre national. 

Il en résulte des normes qui sont relativement volumineuses et dont le périmètre dépasse souvent largement les besoins d'une utilisation donnée. Ainsi, à titre d'exemple, SIRI propose toute une série d'options ou de mécanismes dont la vocation est d'assurer la compatibilité avec les systèmes développés en Allemagne dans le contexte des normes VDV 453/454. De même, SIRI propose des services dédiés à la gestion des correspondances garanties, services qui, s'ils sont dès aujourd'hui pertinents en Suisse ou en Allemagne, sont pratiquement inexistants en France. 

De plus, un certain nombre de spécificités locales ou nationales peuvent amener à préciser l'usage ou la codification qui sera utilisée pour certaines informations. Par exemple, les Anglais disposant d'un référentiel national d'identification des points d'arrêts (NaPTAN), imposeront naturellement que cette codification soit utilisée dans les échanges SIRI, ce que ne feront pas les autres pays européens.

Enfin, certains éléments proposés par ces normes sont facultatifs et il convient, lors d'une implémentation, de décider si ces éléments seront ou non implémentés.

L'utilisation des normes liées à l'implémentation de l'interopérabilité pour le transport en commun passe donc systématiquement par la définition d'un profil (local agreement, en anglais). Concrètement, le profil est un document complémentaire à la norme et qui en précise les règles de mise en œuvre dans un contexte donné. Le profil contient donc des informations comme :
* détail des services utilisés,
* détail des objets utilisés dans un échange,
* précisions sur les options proposées par la norme,
* précision sur les éléments facultatifs,
* précision sur les codifications à utiliser,
* etc.

Les principaux profils actuellement utilisés en France sont le profil de SIRI défini par le CEREMA et Île-de-France Mobilités et le uprofil SIRI France, qui en découle, est en cours de publication. Ces deux profils ont une vocation nationale. 

D'autre profils de NeTEx sont disponibles (arrêt, réseau, horaire, tarifs, parking, accessibilité), tous complémentaires et sans recouvrement. Ils s'appuient tous sur un document partagé: NeTEx - Profil Français de NETEx: éléments communs. 

Il conviendra de se référer à ce document pour tous les éléments utilisés dans le présent document, et dont la structure n'est pas détaillée.

Ce profil d’échange a pour objectif de décrire et de structurer précisément les éléments nécessaires à une bonne information de description des modes de transports alternatifs (ou nouveaux modes) :
1. à pouvoir les décrire d’une manière homogène et compréhensible à l’usager , 
2. à pouvoir les échanger entre systèmes d’information (systèmes d’information voyageurs et systèmes d’information multimodale, systèmes d’aide à l’exploitation, systèmes de planification, systèmes billettiques, etc.). 

Les éléments présentés ci-dessous couvrent donc l’ensemble des concepts propres à la description des modes alternatifs retenus dans le cadre de ce profil national. 

> NOTE IMPORTANTE	Ce document étant un profil d'échange de NeTEx, il ne se substitue en aucun cas à NeTEx, et un minimum de connaissance de NeTEx sera nécessaire à sa bonne compréhension.


# Domaine d'application

Le Profil France NeTex pour les nouveaux modes concerne spécifiquement l'échange de données de référence pour soutenir les “nouveaux” modes alternatifs pour les services de mobilité, en ajoutant certains nouveaux concepts au schéma NeTEx (indiqués comme NeTEx v1.2.2), mais aussi en utilisant dans une large mesure des éléments de schéma existants définis dans les parties 1, 2 et 3 de NeTEx.

La conception de haut niveau pour le soutien aux modes alternatifs est dérivée d’un modèle conceptuel pour les modes alternatifs CEN PT1711 (CEN/TS 17413:2020) préparé par le groupe de travail TC278 WG17 de CEN. Cette spécification technique CEN décrit un modèle conceptuel pour les modes alternatifs comme une extension de Transmodel V6.0 et basé sur un ensemble détaillé de cas d’utilisation tirés de CEN PT1711, fournis en annexe A.

Le format NeTEx concerne un sous-ensemble des cas d'utilisation pour les données de référence (les cas d'utilisation en temps réel sont couverts par des protocoles dynamiques tels que SIRI et DATEX II). En général, il concerne les données pour les objectifs suivants :

* Permettre l'intégration des segments de voyage effectués avec des modes alternatifs avec ceux effectués avec des modes conventionnels dans des plans de voyage sans couture ;

* Décrire les zones de couverture des services de mobilité par modes alternatifs afin que les moteurs de planification de voyages et d’autres systèmes puissent informer les passagers de la possibilité de les utiliser et fournir des liens appropriés pour invoquer les services dynamiques ;

* Localiser les points d'accès pour les services de modes alternatifs, tels que les points de stationnement, les stations de covoiturage, etc., y compris leur relation avec les points d'accès pour les modes conventionnels ;

NeTEx concerne principalement l’échange de données de référence pour permettre l’intégration de nouveaux modes avec d’autres données ; il ne décrit pas les services dynamiques. 

## Modes de transport

Tous les modes de transport public de masse sont pris en compte par NeTEx, y compris le train, le bus, le car, le métro, le tramway, le ferry, l’avion et leurs sous-modes. Ces modes sont fournis par des opérateurs de transport, qui peuvent exploiter un ou plusieurs modes.

Ce profil s'appuie sur la partie 5 de NeTEx qui élargit le concept d'opérateur pour inclure les fournisseurs d'autres formes de transport, et introduit le concept distinct de « mode d’exploitation » pour classer la manière dont les services sont fournis : conventionnel, flexible, covoiturage, partage, etc.

## Produits et prix
L'approche générale pour la définition des produits pour les modes alternatifs dans la partie 5 de NeTEx (Modes alternatifs) suit l’approche utilisée par Transmodel v6.0 Partie 5 (modèle de données de gestion tarifaire), à savoir à travers la définition des droits d'accès plutôt que des produits en tant que tels. Les prix sont séparés des objets qu’ils tarifient. Le modèle existant permet également de récupérer des prix dynamiques à partir d'un moteur de tarification.

Cette approche d’utilisation des droits d'accès liés au transport public urbain (pour tous les modes urbains) peut être appliquée à n’importe quel mode, y compris le rail à longue distance et les modes alternatifs.

## Protocoles d’échange
L’échange de données au format NeTEx peut être effectué à l’aide de divers protocoles. Par exemple : via des services web dédiés, par des échanges de fichiers de données par FTP ou autres, ou en utilisant le protocole d’échange SIRI tel que décrit dans la partie 2 de la documentation SIRI. NeTEx ajoute des services supplémentaires utilisant les mécanismes de transport SIRI communs.

# Références Normatives
Les documents de référence suivants sont indispensables pour l'application du présent document. Pour les références datées, seule l'édition citée s'applique. Pour les références non datées, la dernière édition du document de référence s'applique (y compris les éventuels amendements).

CEN/TS 16614-1, Network and Timetable Exchange (NeTEx) — Part 5: Alternative modes exchange format
CEN/prEN 12896-10: 2021, Public transport - Reference data model -Part 10 : Alternative modes

<span style='color:green'>***A rédiger ***</span>

# Vocabulaires

Pour les besoins du présent document, les termes et définitions suivants s'appliquent. Ils sont directement issus de Transmodel et NeTEx. Pour une information complète, il conviendra toutefois de se référer au document nor-matif.
> NOTE	Les définitions ci-dessus sont des traductions littérales du document normatif. Seules les définitions spécifiques du profil France 'Nouveaux Modes' sont proposées ici, celles relatives aux autres profils sont disponibles dans les profils correspondants. 

## Elements de contexte

Préalablement aux définitions des termes utilisés, ce paragraphe introduit les différentes catégorisations de modes de transport et des modes alternatifs.

Les concepts liés aux modes de transport et moyens de transport sont définis par Transmodel. La figure suivante permet de délimiter le périmètre auquel va s'attacher le profil NeTEx France Nouveaux Modes.

![Figure Définition du périmètre des modes alternatifs](media/Perimetre_Nouveaux_Modes.jpg)

**Dans ce profil, l'utilisation de "mode alternatif" ou "nouveau mode" est synonyme.**

### Catégorisation des modes de transport
Le terme 'mode' désigne tout moyen de transport utilisé ou disponible. Il est divisé en 'mode véhicule' et 'mode d'accès'.
* Le **'mode véhicule'** est une caractérisation de l'exploitation du transport public selon le moyen de transport, par exemple, bus, tramway, métro, train, ferry, bateau ou vélo.
* Le **'mode d'accès'** (par exemple, la marche, le cyclisme, la conduite de voiture privée, etc.) est une caractérisation du mouvement du voyageur (par exemple, marcher, faire du vélo, etc.) lui permettant d'atteindre le 'mode véhicule' ou de réaliser un voyage complet.

### Modes alternatifs
Les modes et sous-modes définis comme des 'moyens de transport' peuvent être caractérisés en termes de types de fonctionnement, c'est-à-dire des façons dont ils sont opérés.
Ce document distingue les types suivants de 'mode de fonctionnement' :

* **Mode de fonctionnement conventionnel** : le mode de fonctionnement traditionnel qui est proposé sous forme d'une offre de transport public annoncée et/ou flexible, selon un horaire fixe et/ou flexible. Ce mode de fonctionnement suit soit un horaire et des itinéraires fixes, soit est lié à un réseau/horaires fixes mais offre de la flexibilité, afin d'optimiser par exemple le service ou de répondre à la demande des passagers ;

* **Mode alternatif de fonctionnement** : tout mode de fonctionnement public annoncé différent du mode de fonctionnement conventionnel, notamment le partage de véhicules, la location de véhicules et le covoiturage ;

* **Mode personnel de fonctionnement** : un mode de transport privé excluant toute utilisation publiquement annoncée.
La distinction entre les modes de fonctionnement alternatif et conventionnel repose sur le fait qu'un mode conventionnel repose sur un ensemble de caractéristiques : les conducteurs sont des employés, la flotte est détenue par un opérateur ou une autorité, et la topologie du réseau est définie à l'avance et repose sur des lignes et des modèles de trajets ; tandis que les modes alternatifs peuvent ne pas remplir une ou plusieurs de ces caractéristiques.
Ce profil concerne le mode alternatif de fonctionnement.

### Termes & définitions

* ACCESS MODE (Mode d'accès)

Caractérisation du déplacement du voyageur (par exemple, marche, vélo, etc.) lui permettant de se rendre à un arrêt de transport public ou d'effectuer une étape de son voyage.

*  ALTERNATIVE MODE (Mode Alternatif)

Mode d'exploitation annoncé publiquement, différent du mode d'exploitation conventionnel, en particulier le partage de véhicules, la location de véhicules et la mise en commun de véhicules.

* VEHICULE POOLING (CO-VOITURAGE)

Un MODE ALTERNATIF D'EXPLOITATION d'un véhicule privé consiste à partager le véhicule pour un trajet entre le conducteur qui effectue en même temps un voyage et au moins un autre voyageur.

* MODE OF OPERATION (MODE OPERATOIRE)

Méthode de mise à disposition des moyens de transport, qui peut être un MODE D’EXPLOITATION CONVENTIONNEL, ALTERNATIF ou PERSONNEL.

* CONVENTIONAL MODE OF OPERATION (MODE OPERATOIRE CONVENTIONNEL)

Un mode d’exploitation hérité qui met à disposition une offre de transport planifiée ou flexible, publiquement promue.

 * ALTERNATIVE MODE OF OPERATION (MODE OPERATOIRE ALTERNATIF)

Toute autre mode d’exploitation qui est publiquement promu et est ni un MODE D’EXPLOITATION CONVENTIONEL. Par exemple : PARTAGE DE VEHICULE, LOCATION DE VEHICULES OU PARTAGE DE TRAJETS

* VEHICLE SHARING (VEHICULE PARTAGE)
Location de véhicules à court terme où le véhicule peut être pris et garé à différents endroits de la zone urbaine, souvent sans la contrainte de ramener le véhicule à un endroit spécifique dédié.

* PERSONAL MODE OF OPERATION (MODE OPERATOIRE PERSONEL)

Un MODE D’EXPLOITATION en propre de véhicules, qui n’est pas publiquement promu

* VEHICLE SHARING SERVICE (SERVICE DE PARTAGE DE VEHICULE)

Location de véhicule à court terme où le véhicule peut être pris et garé à différents endroits dans la zone urbaine, possiblement sans l'obligation de ramener le véhicule à un endroit spécifique.

* Mode de marche (walking mode)

La marche est considérée comme un mode d'accès, c'est-à-dire que le voyageur marche jusqu'à un point d'arrêt pour accéder aux autres modes de transports.


# Symboles & abréviations

* NeTEx
* ...

# Description du profil d'échange

## Conventions de représentation

NOTE	les choix de conventions présentées ici ont pour vocation d'être cohérents avec celle réalisée dans le cadre du profil SIRI. De plus tous les profils NeTEx partagent les mêmes conventions.

### Tableaux d'attributs

Les messages constituant ce profil d'échange sont décrits ci-dessous selon un double formalisme: une description sous forme de diagrammes XSD (leur compréhension nécessite une connaissance préalable de XSD: XML Schema Definition) et une description sous forme tabulaire. Les tableaux proposent ces colonnes:

![Representation tabulaire](media/ConventionReprésentation1.jpg)

* Classification : permet de catégoriser l'attribut. Les principales catégories sont:

    -  PK (Public Key) que l'on peut interpréter comme Identifiant Unique: il permet à lui seul d'identifier l'o NOTE	les choix de conventions présentées ici ont pour vocation d'être cohérents avec celle réalisée dans le cadre du profil SIRI. De plus tous les profils NeTEx partagent les mêmes conventions.

    -	AK (Alternate Key) est un identifiant secondaire, généralement utilisé pour la communication, mais qui ne sera pas utilisé dans les relations.
    -	FK (Foreign Key) indique que l'attribut contient l'identifiant unique (PK) d'un autre objet avec lequel il est en relation.
    -	GROUP est un groupe XML nommé (ensemble d'attributs utilisables dans différents contextes) 
        (cf: http://www.w3.org/TR/2001/REC-xmlschema-0-20010502/#AttrGroups )

* Nom : nom de l'élément ou attribut XSD

* Type : type de l'élément ou attribut XSD	(pour certains d'entre eux, il conviendra de se référer à la XSD NeTEx)

* Cardinalité : cardinalité de l'élément ou attribut XSD exprimée sous la forme "minimum:maximum" ("0:1" pour au plus une occurrence; "1:*" au moins une occurrence et sans limites de nombre maximal; "1:1" une et une seule occurrence; etc.).

*	Description : texte de description de l'élément ou attribut XSD (seul les attributs retenus par le profil ont un texte en français; les textes surlignés en jaune indiquent une spécificité du profil par rapport à NeTEx).

Les textes surlignés en <span class="hl">Jaune</span> sont ceux présentant une particularité (spécialisation) par rapport à NeTEx: une codification particulière, une restriction d'usage, etc.

La description XSD utilisée est strictement celle de NeTEx, sans aucunemodification (ceci explique notamment que tous les commentaires soient en anglais).

Les attributs et éléments rendus obligatoires dans le cadre de ce profil restent facultatifs dans l'XSD (le contrôle de cardinalité devra donc être réalisé applicativement).

### Valeurs de code de profil

Dans la mesure du possible, le profil sélectionne les valeurs de code à utiliser pour caractériser des éléments et les limite à un ensemble de valeurs documentées. NETEX propose plusieurs mécanismes différents pour spéci-fier les valeurs de code autorisées:

* des énumérations fixes définies dans le cadre du schéma XSD NeTEx. Le profil impose alors un sous-ensemble des codes NeTEx.

* des spécialisations de TYPE OF VALUE, utilisées pour définir des ensembles de codes ouverts pouvant être ajoutés au fil du temps sans modifier le schéma, par exemple, pour enregistrer des classifications d'entités héritées. Le profil lui-même utilise le mécanisme TYPE OF VALUE dans quelques cas pour spécifier des codes normalisés supplémentaires : ceux-ci sont affectés à un CODESPACE «FR_IV_metadata» (https://netex-cen.eu/FR_IV) indiqué par un préfixe «FR_IV». (par exemple, «FR_IV: monomodal»).

* des instances TypeOfFrame: le profil utilise plusieurs TYPES DE FRAME pour spécifier l'utilisation de VERSION FRAME dans le profil. 

### Indication des classes abstraites

NeTEx, et Transmodel, utilisent largement l'héritage de classe; cela simplifie considérablement la spécification en évitant les répétitions puisque les attributs partagés sont déclarés par une superclasse et que des sous-classes viennent ensuite les spécialiser sans avoir à répéter ces attributs et en n’ajoutant que ceux qui lui sont spécifiques. La plupart des superclasses sont «abstraites» - c’est-à-dire qu’il n’existe aucune instance concrète; seules les sous-classes terminales sont «concrètes».

Un inconvénient de l'héritage est que si l'on veut comprendre les propriétés d'une classe concrète unique, il faut également examiner toutes ses super-classes. Pour cette raison, le profil inclut les classes abstraites néces-saires pour comprendre les classes concrètes, même si ces classes concrètes ne sont jamais directement ins-tanciées dans un document NeTEx.

* Les super-classes sont signalées dans les en-têtes par le suffixe «(abstrait)» 

* Dans les diagrammes UML (comme pour NeTEx et Transmodel), les noms des classes abstraites sont indiqués en italique et les classes abstraites sont de couleur gris clair.

* Certaines super-classes ne sont techniquement pas abstraites dans NeTEx, mais ne sont pas utilisées comme classes concrètes dans le profil : elles sont signalées avec la même convention que les classes abstraites.

![Classe Abstraite](media/ClasseAbstraite.jpg)

## Les fonctions spécifiques

### Géorepérage et zones d'utilisation autorisées

La plupart des systèmes de partage de véhicules (vélo, trottinette, voiture, etc.) ne fonctionnent que dans une zone géographique spécifique. Cette zone peut être indiquée par des cartes ou des informations aux passagers, ou pour les véhicules avec des systèmes d'immobilisation à distance, peut même être imposée électroniquement par détection GPS. En outre, certaines zones de la zone opérationnelle peuvent être restreintes en raison de raisons opérationnelles, de sécurité ou autres, par exemple pour contrôler la pollution environnementale. Des pénalités financières peuvent être associées à la violation des limites restreintes à tout moment ou à un moment donné.
Les zones autorisées peuvent être décrites à l'aide de zones de contraintes de service de mobilité, chaque zone exprimant une étendue spatiale et les usages autorisés.

### Réservation

Les services de partage de vélos offrent une capacité de réservation à court terme, permettant aux utilisateurs de vérifier la station disponible la plus proche, de réserver un vélo et de s'enregistrer dans un délai court. Cependant, il n'y a généralement pas de réservation à l'avance ; l'utilisateur prend l'un des vélos disponibles à la station la plus proche.

### Tarifs et paiement

Dans le cadre du partage de vélos, dans la plupart des cas, les utilisateurs ne paient le service qu'une seule fois lors de l'abonnement et chaque fois qu'ils ont utilisé le vélo plus longtemps que la durée de location gratuite.

## Les cas d'usage

Le profil NeTEx pour les modes alternatifs est destiné à inclure l’échange de données de référence pour soutenir l’information intégrée des passagers pour tous les modes. 

Il est supposé que l’échange de données dynamiques, telles que les places disponibles en stations l'état de charge des véhicules électriques, ... seront couverts  pour les fonctions dynamiques des modes alternatifs, hors du périmètre de NeTEx, mais qui sont dans le périmètre de Transmodel,  par SIRI pour l’échange de données. 

Le périmètre de la couverture de NeTEx inclut les cas d’utilisation suivants.

<div class="table-title">Cas d'Usage Profil France Nouveaux Modes</div>

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 30%" />
<col style="width: 30%" />
<col style="width: 30%" />
</colgroup>
<thead>
<tr class="header">
<th>Num</th>
<th>Cas d'usage</th>
<th>Description</th>
<th>Documents Liés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> 1</td>
<td> Recherche de localisation vélo libre service</td>
<td> Trouver une localisation de vélo en livre service</td>
<td> Profil NeTex France Parking <td>
</tr>
<tr class="even">
<td>2</td>
<td> Recherche de localisation d'une Station de vélos en libre Service</td>
<td> Trouver une localisation de station de vélos en livre service</td>
<td> Profil NeTex France Elements communs et Arrêts <td>
</tr>
<tr class="even">
<td>3</td>
<td> Recherche des informations  d'une station</td>
<td> Connaitre la capcité d'une station par type (électriques / non électriques), les modes de paiement disponibles</td>
<td> Profil NeTex France Parking <td>
</tr>
<tr class="even">
<td>4</td>
<td> Principes de tarification</td>
<td> Connaitre les modalités de tarification d'un service</td>
<td> Profil NeTex France Tarifs <td>
</tr>
</tbody>
</table>

## Les services disponibles

### Véhicules partagés

Dans le cadre du profil France deux services sont distingués : le vélo en libre service et la voiture partagé.

#### Vélo en libre Service

##### Description

Le partage de vélos est un mode d'exploitation dédié à la location de vélos à court terme, dans lequel le vélo peut être pris et garé à différents endroits dans une zone urbaine. L'une des principales différences entre le partage de vélos et la location de vélos réside dans le système sous lequel ils fonctionnent. La location de vélos est généralement ponctuelle. Le partage de vélos repose sur un ensemble d'utilisateurs abonnés qui partagent le service, généralement pour de courtes durées ou pour effectuer de petits trajets, moyennant un abonnement mensuel ou annuel fixe. 

Le tarif dépend d'un certain nombre de paramètres : il peut s'agir d'un simple intervalle de temps, d'un tarif pour excès de temps, ou inclure des réductions pour une utilisation fréquente en fonction d'un "profil de voyageur fréquent". Il convient de noter que, comme pour les services de transport conventionnels, les tarifs reposent sur un contrat qui peut être implicite et anonyme (mais dans de nombreux cas, le contrat est personnel), et ce contrat exprime l'"adhésion" à une communauté d'utilisateurs de services spécifiques

##### Avec Station
les vélos sont obtenus à partir d'un emplacement prédéterminé, comme une station de stationnement de vélos, où la station communique la disponibilité du vélo et enregistre quand il a été pris et retourné et par qui. La station de stationnement disposera de systèmes pour libérer un vélo pour le voyageur potentiel. Une station peut en réalité avoir une capacité supérieure au nombre strict de bornes si elle dispose de personnel pour récupérer des véhicules supplémentaires du stockage ou y en ramener afin d'équilibrer la demande – le service « voiturier ». Il peut être tout aussi important pour un utilisateur qu'il y ait une borne libre disponible pour y retourner son vélo à la fin de son trajet, sinon il pourrait faire face à une recherche chronophage et même à une pénalité pour usage prolongé.

##### Sans Station (Flottant)
Pour les vélos dans un système de partage de vélos sans station, qui disposent généralement de verrous d'immobilisation intégrés dans leur cadre, aucune station n'est nécessaire. Le vélo peut être laissé à n'importe quel endroit sûr dans la zone du schéma et être immobilisé ou réactivé à l'aide d'un code.

#### Voitures en libre Service

##### Description

##### Sans station

## Modèle de données

### Mode d'exploitation

### Localisation

### Capacité

### Type de véhicule

### Principes de tarification

### Mode de Paiement

### Restriction d'usage







# Entêtes NeTEx

# Annexes

# Bibliographie
