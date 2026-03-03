# Domaine d'application

Le Profil France NeTex pour les nouveaux modes concerne spécifiquement l'échange de données de référence pour soutenir les "nouveaux" modes alternatifs pour les services de mobilité, en ajoutant certains nouveaux concepts au schéma NeTEx (indiqués comme NeTEx v1.2.2), mais aussi en utilisant dans une large mesure des éléments de schéma existants définis dans les parties 1, 2 et 3 de NeTEx.

La conception de haut niveau pour le soutien aux modes alternatifs est dérivée d'un modèle conceptuel pour les modes alternatifs CEN PT1711 (CEN/TS 17413:2020) préparé par le groupe de travail TC278 WG17 de CEN. Cette spécification technique CEN décrit un modèle conceptuel pour les modes alternatifs comme une extension de Transmodel V6.0 et basé sur un ensemble détaillé de cas d'utilisation tirés de CEN PT1711, fournis en annexe A.

Le format NeTEx concerne un sous-ensemble des cas d'utilisation pour les données de référence (les cas d'utilisation en temps réel sont couverts par des protocoles dynamiques tels que SIRI et DATEX II). En général, il concerne les données pour les objectifs suivants :

- Permettre l'intégration des segments de voyage effectués avec des modes alternatifs avec ceux effectués avec des modes conventionnels dans des plans de voyage sans couture ;
- Décrire les zones de couverture des services de mobilité par modes alternatifs afin que les moteurs de planification de voyages et d'autres systèmes puissent informer les passagers de la possibilité de les utiliser et fournir des liens appropriés pour invoquer les services dynamiques ;
- Localiser les points d'accès pour les services de modes alternatifs, tels que les points de stationnement, les stations de covoiturage, etc., y compris leur relation avec les points d'accès pour les modes conventionnels ;

NeTEx concerne principalement l'échange de données de référence pour permettre l'intégration de nouveaux modes avec d'autres données ; il ne décrit pas les services dynamiques.

# Références normatives

Les documents de référence suivants sont indispensables pour l'application du présent document. Pour les références datées, seule l'édition citée s'applique. Pour les références non datées, la dernière édition du document de référence s'applique (y compris les éventuels amendements).

CEN/TS 16614-1, Network and Timetable Exchange (NeTEx) - Part 1: Public transport network topology exchange format

CEN/TS 16614-2, Network and Timetable Exchange (NeTEx) - Part 2: Public transport scheduled timetables exchange format

CEN/TS 16614-3, Network and Timetable Exchange (NeTEx) - Part 3: Fare exchange format

EN 12896, Road transport and traffic telematics - Public transport - Reference data model (Transmodel)

Le profil France NeTex modes Alternatifs s'appuie sur les profils NeTex France mentionnés ci-après. Les informations décrites dans ces profil nationaux ne sont pas reprises dans ce document.

NeTex Profil France v2.3 - Parking

# Termes et définitions

Pour les besoins du présent document, les termes et définitions suivants s'appliquent. Une grande partie d'entre eux est directement issue de Transmodel et NeTEx.

NOTE Les termes spécifiquement introduits par le profil d'arrêt sont signalés par le mot (profil), en italique et entre parenthèses. Les définitions ci-dessous sont des traductions littérales du document normatif.

NOTE Les définitions ci-dessus sont des traductions littérales du document normatif.

**ACTUAL VEHICLE EQUIPMENT (Équipement réel du véhicule)**

Cet élément permet de spécifier un équipement d'un type particulier effectivement disponible dans un véhicule donné.

**ALTERNATIVE MODE OF OPERATION (Transmodel)**

Tout mode d'exploitation annoncé publiquement différent du mode d'exploitation conventionnel, notamment le partage de véhicules, la location de véhicules et le covoiturage.

**COMMON VEHICLE SERVICE**

Un SERVICE DE MOBILITÉ est en soi abstrait. Un SERVICE DE VÉHICULES COMMUNS est une spécialisation d'un SERVICE DE MOBILITÉ impliquant des VÉHICULES.

Trois spécialisations d'un SERVICE DE VÉHICULES COMMUNS sont possibles :

- SERVICE DE LOCATION DE VÉHICULES : Offre de service de transport liée à la LOCATION DE VÉHICULES. Hors périmètre du présent profil,
- SERVICE DE PARTAGE DE VÉHICULES : Offre de service de transport liée au PARTAGE DE VÉHICULES.
- SERVICE DE VEHICULES PARTAGES (co voiturage) : Service de transport mettant en relation conducteur et passager(s) pour effectuer des trajets.

**CONVENTIONAL MODE OF OPERATION** (Transmodel)

Mode d'exploitation traditionnel proposé sous forme d'offre de transport programmée et/ou flexible, annoncée publiquement, s'appuyant sur un ensemble de caractéristiques :

- Les conducteurs sont des salariés ;
- La flotte appartient à une autorité, ou est détenue ou exploitée par un opérateur,
- La topologie du réseau est définie bien à l'avance et repose sur les lignes et les schémas de déplacement

**FLEET (Flotte)- (Transmodel)**

Une flotte appartient à une organisation de transport, un organisme légalement constitué lié à tout aspect du système de transport. Une organisation de transport peut posséder plusieurs flottes.

**MOBILITY CONSTRAINT ZONE (NeTEx)**

Une ZONE DE CONTRAINTE DE SERVICE DE MOBILITÉ définit des restrictions de déplacement au sein d'une zone pour un MODE DE FONCTIONNEMENT donné.

**MOBILITY SERVICE (Transmodel)**

Service de transport alternatif disponible sur un territoire étendu, par exemple le covoiturage, la location, etc.

**MODE OF OPERATION**

Un des trois type de mode d'exploitation parmi ;

- Les modes d'exploitation conventionnels,
- Les modes d'exploitation alternatifs
- Les modes d'exploitation personnels

**ONLINE SERVICES** (NeTEx)

L'entité SERVICE EN LIGNE représente tout service accessible à distance permettant d'accéder à tout mode de transport et/ou à des informations relatives aux services de transport.

**PARKING (parking) (Transmodel)**

Emplacements désignés pour stationner des véhicules tels que des voitures, des motos et des vélos.

**PARKING AREA** (zone de parking) (Transmodel)

Zone identifiée à l'intérieur d'un parking, et contenant des places de stationnement (PARKING BAYs).

**PARKING BAY** (place de stationnement) _(Transmodel)_

Emplacement où l'on peut stationner une (unique) véhicule.

**PERSONAL MODE OF OPERATION** _(Transmodel)_

Mode de d'exploitation privé excluant toute utilisation annoncée publiquement.

**SIMPLE VEHICLE TYPE** _(NeTex)_

Définit les exigences applicables à un véhicule utilisé pour fournir des services de modes alternatifs.

Il peut inclure des caractéristiques empruntées à d'autres types de véhicules (par exemple : vélos, trottinettes, scooters).

**TRANSPORT TYPE** _(NeTex)_

Un **TRANSPORT TYPE** peut être associé à un **VEHICLE MODEL**, qui décrit un ensemble de propriétés répondant à un **VEHICLE EQUIPMENT PROFILE**.

Chaque véhicule possède :

- un TRANSPORT TYPE,
- un VEHICLE MODEL.

**VEHICULE CHARGING EQUIPMENT** (NeTEx)

L'EQUIPEMENT DE RECHARGE DE VEHICULE est une spécialisation de l'EQUIPEMENT DE LIEU indiquant la disponibilité de la recharge de véhicule.

**VEHICLE MEETING PLACE** (NeTEx)

Lieux où les véhicules/voyageurs/conducteurs se rencontrent pour changer de mode de transport, pour embarquer, débarquer, prendre en charge, déposer, etc. Un LIEU DE RENCONTRE DE VÉHICULES peut être associé à un SITE spécifique (tel qu'un LIEU D'ARRÊT ou un POINT D'INTÉRÊT) ou à tout composant du SITE

**VEHICLE MODEL** (Transmodel)

Classification des véhicules de transport public d'un même type selon l'équipement ou la génération de modèle.

**VEHICLE MODEL PROFILE** (NeTEx)

Le PROFIL DU MODÈLE DE VÉHICULE décrit l'ÉQUIPEMENT installé à bord des VÉHICULES d'un MODÈLE DE VÉHICULE spécifique

**VEHICLE SHARING** (Transmodel)

Location de véhicule à court terme où le véhicule peut être pris et stationné à différents endroits de la zone urbaine, souvent sans la contrainte de ramener le véhicule à un endroit spécifique dédié.

**VEHICLE SHARING PARKING AREA** (zone de parking pour véhicule partagé) (Transmodel)

Zone identifiée à l'intérieur d'un parking dédié au véhicules partagés, et contenant des places de stationnement (PARKING BAYs).

**VEHICLE SHARING PARKING BAY** (place de stationnement pour véhicule partagé) _(Transmodel)_

Emplacement où l'on peut stationner une (unique) véhicule partagée.

**VEHICLE SHARING PLACE ASSIGNEMENT** (NeTEx)

Une ATTRIBUTION DE PLACE DE PARTAGE DE VÉHICULE peut être utilisée pour attribuer des ZONES DE STATIONNEMENT et des PLACES DE STATIONNEMENT spécifiques à utiliser par un service donné.

**VEHICLE TYPE** _(NeTex)_

Définit les exigences applicables à un véhicule programmé pour le transport de passagers. Ces exigences peuvent inclure :

- **Exigence de transport de passagers** : capacité en passagers fauteuil roulant, etc.).
- **Exigence de manœuvrabilité** : contraintes liées à la capacité de manœuvre du véhicule.
- **Exigence d'équipements** : installations requises à bord (accessibilité, siège bébé, etc.).

# Symboles et abréviations

**LOM** : Moi d'orientation des mobilités

**NeTEx** : Network Timetable Exchange

**NM** : Nouveaux Modes

**SIRI** : Service Interface for Real Time Information.

**XSD** : XML Schema Definition

# Exigences minimales liées au code des transports et la règlementation européenne

La mise à disposition des données, quand elles existent, est obligatoire et se conforme aux exigences :

- Au niveau européen, du règlement délégué (UE) 2017/1926 de la Commission du 31 mai 2017 modifié par le règlement délégué (UE) 2024/490 de la Commission du 29 novembre 2023 (&lt;<https://eur-lex.europa.eu/eli/reg_del/2017/1926/2024-03-04>&gt;), dit "règlement MMTIS" ;
- Au niveau français, des articles L. 1115-1 à L. 1115-7 , D. 1115-1, R. 1115-2 à R. 1115-8 et D. 1115-9 à D. 1115-11 du code du transports, notamment créés ou modifiés par les articles 25 et 27 de loi n° 2019-1428 du 24 décembre 2019 d'orientation des mobilités, dites loi « LOM ».

Ces mêmes articles de la LOM précise le calendrier de mise à disposition des données.

Le tableau ci-dessous résulte de l'analyse du code des transports et du règlement MMTIS et fournit la liste des concepts concernés dans le présent profil correspondant aux données mentionnées dans l'annexe du règlement. Il sera donc nécessaire de fournir ces données pour être conforme au cadre réglementaire (il s'agit bien de mettre à disposition toutes les données existantes dans les SI transport, et non de créer des données qui n'existeraient pas encore sous forme informatique).

Notez que beaucoup de concepts dépendent des concepts issus de Transmodel/NeTEx et sont liés entre eux, soit par héritage, soit par relation au sens UML des termes. Par ailleurs, certains concepts additionnels peuvent relever d'autres parties du profil France précisés dans le tableau le cas échéant.

De plus, les noms des catégories (colonnes Catégorie et Détail) ont été conservés dans la langue originale du document (l'anglais) pour éviter tout risque de confusion.

La première colonne reprend la notion de _\*niveau\*_ tel qu'il est décrit et utilisé par le règlement européen et a notamment une incidence sur le calendrier de mise à disposition de la donnée (voir le règlement pour plus de détails).

Les différents concepts retenus ne sont bien sûr pas détaillés dans ce tableau, mais dans le profil lui-même. C'est aussi dans la description du profil que l'on trouvera les détails concernant les attributs (obligatoire/facultatif, règles de remplissage, codification, etc.).

Pour ce qui est des attributs facultatifs, la règle reste que, pour les objets ci-dessous, toute information disponible est supposée être fournie (mais on ne crée pas d'information si elle n'est pas disponible).

L'attente du règlement délégué est très vaste et ne permet malheureusement pas de réaliser une sélection de concepts dans ce que propose NeTEx (qui est de plus très vaste).

| **Niveau** | **Catégorie** | **Détail** | **Concept** | **Autre Concept** |
| --- | --- | --- | --- | --- |
| 2   | Recherche de localisation (origine/destination) | Identifiants d'adresse (numéro de bâtiment, nom de rue, code postal) | ENTRANCE (VÉHICULE et PASSAGER) PARKING |     |
| 2   | Recherche de localisation (modes à la demande) | \- Arrêts Park & Ride<br><br>\- Stations de partage de vélos<br><br>\- Stations de covoiturage<br><br>\- Stations de ravitaillement accessibles au public (stations de recharge pour véhicules électriques) | PARKING<br><br>PARKING AREA<br><br>VEHICLE CHARGING EQUIPMENT |     |
| 2   | Service d'information | Où et comment acheter des billets pour les modes programmés, modes à la demande et le stationnement (tous modes programmés et à la demande, incluant canaux de vente, méthodes de distribution, modes de paiement) | PARKING (attributs relatifs à la tarification) |     |
| 3   | Service d'information (tous modes) | Comment réserver le covoiturage, les, la vélos partage, etc. (incluant canaux de vente, méthodes de distribution, modes de paiement) | BOOKING ARRANGEMENTS |     |
| 3   | Service d'information (tous modes) | Où et comment payer le stationnement, les stations de recharge publiques pour véhicules électriques et les points de ravitaillement pour véhicules au GNC/GNL, hydrogène, essence et diesel (incluant canaux de vente, méthodes de distribution, modes de paiement) |     |     |
| 1   | Types des données routières statiques | Localisation des places de stationnement et zones de service | **PARKING** | **PARKING AREA** |
| 1   | Types des données routières statiques | Localisation des points de recharge pour véhicules électriques et conditions d'utilisation | VEHICLE CHARGING EQUIPMENT |     |

_Table 1 - Concepts relatifs à la LOM et à la Règlementation Européenne_

# Description du profil d'échange

## Conventions de représentation

### Tableaux d'attributs

**NOTE** les choix de conventions présentées ici ont pour vocation d'être cohérents avec ceux réalisés dans le cadre du profil SIRI (Île-de-France Mobilités et CEREMA). De plus tous les profils NeTEx partagent les mêmes conventions.

Les messages constituant ce profil d'échange sont décrits ci-dessous selon un double formalisme: une description sous forme de diagrammes XSD (leur compréhension nécessite une connaissance préalable de XSD: XML Schema Definition) et une description sous forme tabulaire. Les tableaux proposent ces colonnes:

| Classification | Nom | Type | Cardinalité | Description |
| --- | --- | --- | --- | --- |

**Classification** : permet de catégoriser l'attribut. Les principales catégories sont:

PK (Public Key) que l'on peut interpréter comme Identifiant Unique: il permet à lui seul d'identifier l'objet, de façon unique, pérenne et non ambiguë. C'est l'identifiant qui sera utilisé pour référencer l'objet dans les relations.

AK (Alternate Key) est un identifiant secondaire, généralement utilisé pour la communication, mais qui ne sera pas utilisé dans les relations.

FK (Foreign Key) indique que l'attribut contient l'identifiant unique (PK) d'un autre objet avec lequel il est en relation.

GROUP est un groupe XML nommé (ensemble d'attributs utilisables dans différents contextes) (cf: <http://www.w3.org/TR/2001/REC-xmlschema-0-20010502/#AttrGroups> )

**Nom** : nom de l'élément ou attribut XSD

**Type** : type de l'élément ou attribut XSD (pour certains d'entre eux, il conviendra de se référer à la XSD NeTEx)

**Cardinalité** : cardinalité de l'élément ou attribut XSD exprimée sous la forme "**_minimum:maximum_**" ("0:1" pour au plus une occurrence; "1:\*" au moins une occurrence et sans limites de nombre maximal; "1:1" une et une seule occurrence; etc.).

Description : texte de description de l'élément ou attribut XSD (seul les attributs retenus par le profil ont un texte en français; les textes surlignés en jaune indiquent une spécificité du profil par rapport à NeTEx).

Les textes surlignés en jaune sont ceux présentant une particularité (spécialisation) par rapport à NeTEx: une codification particulière, une restriction d'usage, etc.

Les textes surlignés en bleu correspondent à des éléments de NeTEx non retenus dans le cadre de ce profil (présentés à titre informatif donc). Dans les diagrammes XSD, les éléments et attributs apparaissant sur fond bleu sont ceux qui ne sont pas retenus par le profil (et ce sont donc systématiquement des éléments ou attributs facultatifs de NeTEx).

La description XSD utilisée est strictement celle de NeTEx, sans aucune modification (ceci explique notamment que tous les commentaires soient en anglais).

Les attributs et éléments rendus obligatoires dans le cadre de ce profil restent facultatifs dans l'XSD (le contrôle de cardinalité devra donc être réalisé applicativement).

### Valeurs de code de profil

Dans la mesure du possible, le profil sélectionne les valeurs de code à utiliser pour caractériser des éléments et les limite à un ensemble de valeurs documentées. NETEX propose plusieurs mécanismes différents pour spécifier les valeurs de code autorisées:

- Des énumérations fixes définies dans le cadre du schéma XSD NeTEx. Le profil impose alors un sous-ensemble des codes NeTEx.
- Des spécialisations de TYPE OF VALUE, utilisées pour définir des ensembles de codes ouverts pouvant être ajoutés au fil du temps sans modifier le schéma, par exemple, pour enregistrer des classifications d'entités héritées. Le profil lui-même utilise le mécanisme TYPE OF VALUE dans quelques cas pour spécifier des codes normalisés supplémentaires : ceux-ci sont affectés à un CODESPACE «FR_IV_metadata» (<https://netex-cen.eu/FR_IV>) indiqué par un préfixe «FR_IV». (par exemple, «FR_IV: monomodal».
- Des instances TypeOfFrame: le profil utilise plusieurs TYPES DE FRAME pour spécifier l'utilisation de VERSION FRAME dans le profil.

### Indication des classes abstraites

NeTEx, et Transmodel, utilisent largement l'héritage de classe; cela simplifie considérablement la spécification en évitant les répétitions puisque les attributs partagés sont déclarés par une superclasse et que des sous-classes viennent ensuite les spécialiser sans avoir à répéter ces attributs et en n'ajoutant que ceux qui lui sont spécifiques. La plupart des superclasses sont «abstraites» - c'est-à-dire qu'il n'existe aucune instance concrète; seules les sous-classes terminales sont «concrètes».

Un inconvénient de l'héritage est que si l'on veut comprendre les propriétés d'une classe concrète unique, il faut également examiner toutes ses super-classes. Pour cette raison, le profil inclut les classes abstraites nécessaires pour comprendre les classes concrètes, même si ces classes concrètes ne sont jamais directement instanciées dans un document NeTEx.

- Les super-classes sont signalées dans les en-têtes par le suffixe «_(abstrait)_»
- Dans les diagrammes UML (comme pour NeTEx et Transmodel), les noms des classes abstraites sont indiqués en italique et les classes abstraites sont de couleur gris clair.
- Certaines super-classes ne sont techniquement pas abstraites dans NeTEx, mais ne sont pas utilisées comme classes concrètes dans le profil : elles sont signalées avec la même convention que les classes abstraites.

### Classes de sous-composants

Un certain nombre de classes ont des sous-composants qui constituent leur définition. Celles-ci fournissent des détails auxiliaires (par exemple, AlternativeText, AlternativeName, TrainComponent) et sont signalées dans les en-têtes par le suffixe « _(objet inclus)_ ».

## Les éléments non définis dans l'offre des service (réseau et horaires)

Sans Objet

# Concepts de base pour la description des modes de transport alternatif

Le terme 'mode' désigne tout moyen de transport utilisé ou disponible. Il est divisé en 'mode véhicule' et 'mode d'accès'.

Le 'mode véhicule' est une caractérisation de l'exploitation du transport public selon le moyen de transport, par exemple, bus, tramway, métro, train, ferry, bateau ou vélo.

Le 'mode d'accès' (par exemple, la marche, le cyclisme, la conduite de voiture privée, etc.) est une caractérisation du mouvement du voyageur (par exemple, marcher, faire du vélo, etc.) lui permettant d'atteindre le 'mode véhicule' ou de réaliser un voyage complet.

Figure 1 : Catégorisation des modes de transport



Une distinction est faite entre le 'mode véhicule' et le 'type de véhicule'. Chaque 'mode véhicule' peut correspondre à une gamme de 'types de véhicules' (par exemple, pour le 'mode véhicule' 'autobus', on peut avoir des types comme 'standard', 'articulé', 'minibus', 'à deux étages').

Une catégorisation plus fine des modes de transport est fournie par le concept de 'sous-mode', qui est une variante d'un 'mode'. Par exemple, pour le mode 'rail', les sous-modes possibles sont 'rail international' ou 'rail domestique' ; pour le mode 'autobus', l'exemple de sous-mode est 'autobus régional', pour le mode 'voiture', les exemples de sous-modes sont 'voiture électrique', 'voiture conventionnelle', 'voiture autonome'.

Figure 2 : Catégorisation des modes de transport

Les modes et sous-modes définis comme des 'moyens de transport' peuvent être caractérisés en termes de types de fonctionnement, c'est-à-dire des façons dont ils sont opérés.

Ce document distingue les types suivants de 'mode de fonctionnement' :

- **Mode de fonctionnement conventionnel** : le mode de fonctionnement traditionnel qui est proposé sous forme d'une offre de transport public annoncée et/ou flexible, selon un horaire fixe et/ou flexible. Ce mode de fonctionnement suit soit un horaire et des itinéraires fixes, soit est lié à un réseau/horaires fixes mais offre de la flexibilité, afin d'optimiser par exemple le service ou de répondre à la demande des passagers ;
- **Mode alternatif de fonctionnement** : tout mode de fonctionnement public annoncé différent du mode de fonctionnement conventionnel, notamment le partage de véhicules, la location de véhicules et le covoiturage ;
- **Mode personnel de fonctionnement** : un mode de transport privé excluant toute utilisation publiquement annoncée.

Le champ d'application de ce document concerne le mode de fonctionnement alternatif, à l'exception de la location de véhicules. La distinction entre les modes de fonctionnement alternatif et conventionnel repose sur le fait qu'un mode conventionnel repose sur un ensemble de caractéristiques : les conducteurs sont des employés, la flotte est détenue par un opérateur ou une autorité, et la topologie du réseau est définie à l'avance et repose sur des lignes et des modèles de trajets ; tandis que les modes alternatifs peuvent ne pas remplir une ou plusieurs de ces caractéristiques.

Ce document concerne le mode alternatif de fonctionnement.

# Cas d'utilisation & Concepts rattachés

La prise en charge par NeTEx des modes alternatifs vise à inclure l'échange de données de référence afin de permettre une information voyageur intégrée pour tous les modes. On suppose que l'échange de données dynamiques, telles que les statuts et prévisions en temps réel, les offres de trajets en temps réel, etc., sera couvert par d'autres API pour les fonctions dynamiques liées aux modes alternatifs qui ne relèvent pas du champ d'application de NeTEx, mais qui sont incluses dans le périmètre de Transmodel et, pour la plupart, couvertes par SIRI pour l'échange de données.

Le champ de couverture du profil France Nouveaux Modes partie Statique inclut les cas d'utilisation suivants. Pour les aspects tarification et parking, il convient de se reporter aux profils France NeTEx associés.

## Description du réseau

| **Cas d'utilisation** | **Description** | **Éléments de modélisation concernés dans ce document** |
| --- | --- | --- |
| Recherche de localisation : Parc-relais | Trouver l'emplacement d'un parc-relais | **PARKING** |
| Recherche de localisation : Stations de vélopartage | Trouver une station de vélopartage | **STOP PLACE**, **SITE** |
| Recherche de localisation : Stations d'autopartage | Trouver une station d'autopartage | Modèle **PARKING** |
| Recherche de localisation : Stations de ravitaillement accessibles au public pour véhicules à combustion, stations de recharge pour véhicules électriques | Trouver des stations de ravitaillement accessibles au public<br><br>**NB** : les détails sont définis dans le Profil FR Parking | **PARKING MODEL**, |
| Recherche de localisation : Stationnement sécurisé pour véhicules | Trouver des stationnements sécurisés pour vélos et autres types de véhicules, y compris horaires d'ouverture et durées de stationnement autorisées | Modèle **PARKING** |
| Véhicules disponibles | Fourniture de services avec des véhicules enregistrés | Modèles **FLEET** et **VEHICLE MODE** |
| Couverture de service | Disponibilité d'un service alternatif dans une zone donnée | **MOBILITY SERVICE** |
| Découverte de services | Services en ligne disponibles | **ON-LINE SERVICE** |

_Table 2 - Cas d'utilisation Description du réseau_

## Planification de trajets Multi Modes (yc NM)

A compléter ultérieurement

## Informations relatives aux trajets

| **Cas d'utilisation** | **Description** | **Éléments de modélisation concernés dans ce document** |
| --- | --- | --- |
| Équipements et services disponibles (Siège Auto, Navigation, Nombre de places, …) | Équipements que le voyageur peut trouver dans le mode alternatif | **FACILITY SET**, **FACILITY**, **EQUIPMENT** |
| Comment réserver un service d'autopartage, un vélo en libre-service, etc. | Inclut les canaux de vente, les méthodes de délivrance, les moyens de paiement | **BOOKING ARRANGEMENTS** |
| Comment accéder à un véhicule | Procédures d'accès à un véhicule partagé | **SERVICE ACCESS CODE**, **VEHICLE ACCESS ASSIGNMENT** |
| Où et comment payer pour un stationnement, un plein d'hydrogène, de carburant ou une recharge électrique | Inclut les canaux de vente, les méthodes de délivrance, les moyens de paiement | **BOOKING ARRANGEMENTS**, **TICKETING EQUIPMENT**, CHARGING EQUIPEMENT |

_Table 3 - Cas d'utilisation Information générale_

# Description fonctionnelle

À la suite d'un mode de fonctionnement alternatif, de **nouveaux services** sont proposés et mis en œuvre à destination des voyageurs.

Cette section décrit ces **nouveaux services** à travers certains aspects et fonctions qui les caractérisent.

Les **deux aspects suivants** sont particulièrement pertinents :

- **Types de véhicules** : vélos, voitures, types de vélos, types de voitures, etc., caractérisés en particulier par leur **équipement**,
- **Modes de fonctionnement** : covoiturage, partage, location, usage personnel,

Les **domaines fonctionnels** principalement concernés par les modes alternatifs sont regroupés dans les catégories suivantes :

- **Fourniture d'informations (au voyageur)** : activités consistant à fournir au voyageur des informations sur les règles et conditions liées à un service de transport,
- **Services aux voyageurs** : activités (généralement initiées par les utilisateurs) visant à faciliter ou permettre un déplacement,
- **Services opérationnels** : activités réalisées par les acteurs responsables de l'exploitation d'un service.

Les sections suivantes décrivent plus en détail les **domaines fonctionnels**, en les présentant selon les **fonctions (activités)**, avec une courte définition de chaque fonction.

Comme mentionné précédemment au point 0, l'objectif principal des sections suivantes est **d'illustrer le périmètre du modèle conceptuel de données développé**, en mettant l'accent sur la **fourniture d'informations**.

Les **spécificités de chaque mode de fonctionnement particulier** sont décrites dans les sections correspondantes (partage de vélos, vélo, covoiturage, partage de voitures).

## Fonctions relatives à la mise à disposition d'informations aux voyageurs

Les fonctions suivantes sont consacrées à la fourniture d'informations aux voyageurs. Dans la plupart des cas, la fourniture d'informations peut être générale (concernant une zone entière) ou spécifique, liée à une requête particulière d'un utilisateur avec des paramètres définis.

### Informations sur la réservation

Cette activité consiste à fournir des informations sur les règles de réservation ainsi que des données complémentaires permettant à l'utilisateur de décider de réserver un service. Les informations suivantes sont considérées comme pertinentes :

- Méthodes de réservation : description du mode de réservation (par Internet, via une agence, etc.)
- Conditions de réservation : délai minimal de réservation, nécessité d'une garantie, etc.
- Coordonnées de contact : URL, adresse, etc. pour contacter le service de réservation
- Nombre/type de véhicules disponibles par station ;
- Règles d'utilisation : conditions temporelles, lieux de prise en charge et de restitution, pénalités, profil utilisateur, etc.

### Informations sur la disponibilité du service

Cette activité consiste à fournir des informations sur la disponibilité d'un mode de fonctionnement particulier, par exemple les heures d'ouverture

### Informations sur la disponibilité des véhicules des modes alternatifs

Cette activité consiste à fournir des informations, statiques (ou dynamiques), sur la disponibilité de véhicules dans les zones dédiées aux modes alternatifs.

- L'information statique correspond à la capacité prévue des zones.
- L'information dynamique (présence réelle de véhicules disponibles) peut être dérivée des données de localisation des véhicules et des données prévues de disponibilité.

### Informations sur l'accès à l'infrastructure

Cette activité consiste à fournir des informations indiquant où et comment accéder à un emplacement dédié à un mode alternatif (partage de véhicule), et où restituer le véhicule après usage. L'information est statique.

### Informations sur la localisation des véhicules

Cette activité consiste à fournir des informations dynamiques indiquant où trouver un véhicule ou où il a été déposé.

### Informations sur l'accès au véhicule

Cette activité consiste à fournir des informations expliquant comment déverrouiller un véhicule avant usage et comment le sécuriser après usage, en particulier pour les services de partage. Les informations peuvent être statiques ou dynamiques.

### Informations tarifaires

Cette activité consiste à fournir des informations sur les règles tarifaires, les formules de prix (à l'heure, à la semaine, au mois), les réductions, etc. L'information est généralement statique.

### Informations sur le paiement

Cette activité consiste à fournir des informations sur les moyens et méthodes de paiement, ainsi que les lieux de paiement. L'information est généralement statique.

Elle comprend :

- Méthodes de paiement : espèces, carte bancaire, paiement mobile, etc.
- Garanties de paiement : garantie par carte bancaire, coordonnées bancaires, enregistrement d'identité.

### Informations sur l'équipement des zones de modes alternatifs

Cette activité consiste à fournir des informations sur les équipements présents dans les emplacements dédiés aux modes alternatifs : installations de stockage sécurisé, stations de recharge, mais aussi bornes de billetterie, guichets d'information, etc.

Les informations peuvent être statiques (présence prévue) ou dynamiques (état actuel de fonctionnement).

### Informations sur les parkings des modes alternatifs

Cette activité consiste à fournir des informations sur les zones de stationnement où un véhicule peut être garé et laissé sans surveillance, ainsi que sur le nombre de places disponibles pour le dépôt. Cette information est dynamique.

### Informations sur l'inscription

Cette activité consiste à fournir des informations sur le processus d'inscription pour être reconnu comme utilisateur du service.

Les informations pertinentes sont :

- Informations d'identité : nom, prénom, date et lieu de naissance, adresse de résidence
- Coordonnées : adresse e-mail du service, numéro de mobile et adresse e-mail de l'utilisateur
- Informations supplémentaires : données de paiement (carte bancaire, compte bancaire) - principalement utilisées comme garantie de paiement.

### Informations sur les services de réparation

Cette activité consiste à fournir des informations sur les lieux où la réparation et/ou la maintenance des véhicules est possible. Une description des réparations possibles peut être fournie (ex. : réparation de crevaisons, remplacement de chaîne, réparation d'éclairage). Ces informations peuvent être statiques ou dynamiques (disponibilité en temps réel).

## Services aux voyageurs

Les paragraphes suivantes donnent des exemples de services aux voyageurs. Cette liste n'est pas exhaustive, mais fournit des exemples typiques rencontrés dans le contexte des nouveaux modes. Par exemple, les fonctions d'aide au voyage comme la planification d'itinéraire ne sont pas décrites ici, car elles sont largement couvertes par les normes liées aux modes conventionnels.

### Réservation

La réservation est un service aux voyageurs (électronique ou non) dédié à la réservation d'un véhicule ou d'un trajet à une date et heure définie dans le cadre de la mobilité urbaine.

### Inscription

L'inscription est un service aux voyageurs considéré comme l'identification initiale, virtuelle ou physique, de l'utilisateur pour accéder à un service de transport. Elle peut être effectuée à distance via une plateforme Internet (PC ou mobile) ou physiquement dans des lieux spécifiques.

### Contrôle d'accès au véhicule

Service consistant à vérifier et à activer les mécanismes de déverrouillage et de verrouillage d'un véhicule utilisé dans le cadre d'un mode alternatif.

### Contrôle d'accès aux stations

Activité consistant à autoriser ou refuser l'accès à une station d'arrêt à des véhicules fonctionnant selon des modes alternatifs.

### Paiement

Le paiement est un service permettant de régler un service de transport. Dans le contexte des modes alternatifs, il s'effectue principalement par moyens électroniques.

### Planification de trajet

La planification de trajet est applicable au contexte du covoiturage.

Les outils modernes d'aide au déplacement permettent aux voyageurs de préparer leur trajet, notamment en répondant à une demande de trajet. Cette fonction identifie les lieux de départ et d'arrivée d'un voyage et propose une ou plusieurs solutions de déplacement, en prenant en compte les contraintes ou préférences de l'utilisateur (durée minimale, nombre d'interconnexions, tarif le plus bas, etc.).

Le système propose ensuite un modèle de trajet, incluant les transferts à pied ou en correspondance, ainsi que les différents modes de transport public et alternatifs. Il est possible de calculer une durée précise (ou moyenne), les coûts correspondants, la compatibilité avec les personnes à mobilité réduite, etc.

Si la demande concerne un trajet le jour même, les conditions suivies en temps réel peuvent être prises en compte pour affiner la proposition (ex. : perturbations, retards, annulations).

## Services opérationnels

### Transfert de véhicules

Activité consistant à transférer des véhicules à travers la ville, notamment pour assurer un bon équilibre entre les stations de partage de véhicules (disponibilité de véhicules et d'emplacements).

### Réparation et maintenance

Fourniture de services de réparation et d'entretien pour tous types de véhicules, dans des zones équipées d'outils et de pièces de rechange.

### Recharge et ravitaillement

Processus de recharge des véhicules électriques (par exemple dans une station de partage) et de ravitaillement en carburant des véhicules thermiques lorsque nécessaire.

## Partage de véhicules (Vehicle Sharing)

### Cycles

Ce paragraphe décrit certains aspects spécifiques supplémentaires liés au cyclisme.

Le cyclisme désigne l'utilisation d'un cycle par un utilisateur pour effectuer un déplacement. Dans le cadre du mode du partage de vélos (VLS).

La modélisation des informations liées au cyclisme peut être utilisée pour fournir des services aux voyageurs ; par exemple, les algorithmes existants de planification d'itinéraires peuvent utiliser des données relatives au cyclisme pour calculer des trajets multimodaux incluant la location et le partage de vélos.

Le partage de vélos repose sur une relation commerciale entre un utilisateur et une organisation mettant des vélos à disposition.

Les types de cycles suivants sont pris en compte dans ce document :

- **Cycle classique** : véhicule composé de roues attachées à un cadre. Il est propulsé par la force musculaire humaine ;
- **Cycle à propulsion électrique** : véhicule équipé d'un moteur électrique de faible puissance ; entrent dans cette catégorie les vélos électriques, mais aussi les gyropodes, hoverboards, monocycles motorisés, etc.

#### Partage de vélos

Le partage de vélos est un mode d'exploitation dédié à la location de vélos généralement de courte durée, dans lequel le vélo peut être pris et déposé à différents endroits, n'importe où en zone urbaine.

L'une des principales différences entre le partage de vélos et la location de vélos réside dans leur mode de fonctionnement. Le partage de vélos s'appuie sur un ensemble d'utilisateurs abonnés qui partagent le service, en général pour des trajets courts en durée ou en distance, moyennant un abonnement mensuel ou annuel fixe. Le tarif dépend d'un ensemble de paramètres, par exemple le « profil de voyageur fréquent ».

##### Réservation

Les services de partage de vélos offrent une réservation à court terme permettant aux utilisateurs de vérifier la station disponible la plus proche, de réserver un vélo et de s'enregistrer en peu de temps. Cependant, la plupart du temps, il n'y a pas de réservation à l'avance ; l'utilisateur prend un des vélos disponibles à la station la plus proche.

##### Tarifs et paiement

Dans le cadre du partage de vélos, dans la plupart des cas, les utilisateurs paient le service une seule fois lors de l'abonnement, puis chaque fois qu'ils ont utilisé le vélo au-delà de la durée gratuite de location.

##### Scénarios de disponibilité

Les scénarios suivants sont possibles selon le type de système de partage de vélos :

- **Docké (stationné)** : les vélos sont obtenus à partir d'un emplacement prédéterminé spécifique tel qu'une station de vélos où la station communique la disponibilité d'un vélo et enregistre quand il est pris et retourné ainsi que par qui. La station dispose de systèmes pour libérer un vélo au voyageur potentiel. Une station peut en fait avoir une capacité supérieure au nombre strict de docks si elle dispose de personnel capable d'apporter des véhicules supplémentaires depuis ou vers un stockage afin d'équilibrer la demande - ce que l'on appelle un « service voiturier ». Il peut être tout aussi important pour un utilisateur qu'il y ait un dock vide disponible pour rendre son vélo à la fin de son trajet, sinon il risque une recherche longue et même une pénalité pour utilisation prolongée.
- **Station virtuel** : Idem que le point précédent sans dock physique associé. Les cycles peuvent être obtenus / restitué dans des zones virtuelles définis par l'opérateur de transport.
- **Flottant (free-floating)** : pour les vélos d'un système de partage sans station, qui possèdent généralement un verrou d'immobilisation intégré à leur cadre, une station n'est pas nécessaire. Le vélo peut être laissé à n'importe quel endroit sûr dans la zone du service et être immobilisé ou réactivé à l'aide d'un code.

##### Géorepérage et zones d'usage autorisé

- La plupart des systèmes de partage de véhicules (vélos, trottinettes, voitures, etc.) fonctionnent uniquement dans une zone spatiale spécifique. Cette zone peut être indiquée via des cartes ou des informations aux usagers, ou, pour les véhicules équipés de systèmes d'immobilisation à distance, être appliquée électroniquement grâce à la détection GNSS.
- De plus, certaines zones à l'intérieur de la zone opérationnelle peuvent être restreintes pour des raisons opérationnelles, de sécurité ou autres, par exemple pour contrôler la pollution environnementale. Des sanctions financières peuvent être appliquées en cas de violation des limites restreintes à tout moment ou à des moments précis.
- Les zones autorisées peuvent être décrites à l'aide de zones de contraintes de mobilité, chacune exprimant une étendue spatiale et les usages permis.

### Voitures

#### Partage de Voiture

Le partage de voitures consiste en l'utilisation d'un véhicule appartenant à un fournisseur commercial de partage de voitures pour une durée spécifiée et préalablement convenue.

Le partage de voitures se distingue du covoiturage en ce que c'est le véhicule qui est partagé, et non un groupe de voyageurs utilisant simultanément le même véhicule pour effectuer un trajet.

Les principaux types de partage de voitures sont :

- Mise à disposition de véhicules par une organisation (partage commercial) ;
- Mise à disposition entre particuliers (club d'autopartage) ;
- Location de voitures classique.

Seule la gestion du premier type est intégrée au profil France NeTex.

Les types de voitures pris en compte dans ce document sont :

- Voitures conventionnelles : voitures de différentes tailles, équipements et types de boîte de vitesses utilisant un carburant liquide conventionnel (essence ou diesel) ; les voitures hybrides ne nécessitant pas de recharge peuvent aussi faire partie de cette catégorie ;
- Voitures à propulsion électrique : voitures nécessitant une recharge après les trajets ou à la fin de la période de partage ;

##### Partage commercial de voitures

Plusieurs types de partage commercial existent : Business to Business (B2B) et Business to Consumer (B2C). Seul le B2C est intégré au présent profil France -

Il est à noter que NeTEx permet de faire du B2B.

- Business to Consumer (B2C) : c'est le partage de voitures conventionnel, où une organisation dispose d'un parc de véhicules disponibles en partage aux consommateurs enregistrés sur demande.

##### Enregistrement

Pour la majorité des services commerciaux, l'utilisateur doit s'enregistrer auprès de la société de partage de voitures. Cet enregistrement permet de mettre en place un mode de paiement, d'enregistrer les informations du conducteur pour l'utilisation du service, et éventuellement un dépôt couvrant les risques en cas de dommages ou perte du véhicule. Cet enregistrement crée aussi les applications nécessaires pour accéder et utiliser le service.

##### Scénarios de disponibilité

Selon le type de partage de voitures, le véhicule peut se trouver à un emplacement prédéterminé (place de stationnement pour partage de voitures) ou à l'endroit où il a été laissé après son dernier usage. Plusieurs scénarios existent autour de ces deux conditions :

- **Boucle fermée** : la voiture est prise et rendue au même emplacement, aussi appelé « voyage en boucle à partir d'une station » ;
- **Aller simple** : la voiture est prise à un endroit et rendue à un autre emplacement prédéfini, aussi appelé « station de pool en libre-service » ;
- **Free floating (libre-service sans station)** : la voiture est prise là où elle a été laissée précédemment et rendue où le trajet se termine. L'application de partage guide l'utilisateur vers l'emplacement le plus proche ou accessible d'un véhicule adapté, également appelé « zone opérationnelle « free floating» ;
- Installations spéciales de docking (pour véhicules électriques).

Certains types de véhicules nécessitent des emplacements adaptés à leur type de carburant. Les véhicules électriques doivent être garés à des endroits équipés de bornes de recharge. Par conséquent, l'option free floating n'est pas toujours applicable.

##### Tarifs et paiement

Plusieurs modèles de paiement existent pour ce service :

- Service par abonnement donnant droit à un nombre d'utilisations et un kilométrage convenus ;
- Paiement au kilomètre, avec facturation basée sur les kilomètres parcourus ;
- Paiement au temps d'utilisation, facturant la durée pendant laquelle le véhicule est utilisé et indisponible pour d'autres ;
- Ou une combinaison des deux (temps et distance).

Le présent profil ne décrit pas les modalités de tarification. Le Profil NeTex France Tarif s'applique pour ces cas d'utilisation.

## Covoiturage

### Introduction

Le covoiturage consiste &agrave; partager des voitures particulières (ou &&eacute;ventuellement d’autres types de v&eacute;hicules ou modes de transport) entre des voyageurs pour des trajets particuliers ou des portions de trajets (le plus souvent, le conducteur et les passagers ne partagent pas la même origine ni la même destination).

Dans le pr&eacute;sent document, le covoiturage est consid&eacute;r&eacute; comme planifi&&eacute; et organis&&eacute;, et non informel.

Le covoiturage n’est pas toujours organis&&eacute; sur l’int&&eacute;gralit&eacute; d’un trajet. En particulier pour les longs trajets, il est courant que les passagers ne participent qu’&agrave; une partie du parcours et versent une contribution proportionnelle &agrave; la distance parcourue.

### Covoiturage g&eacute;n&eacute;rique

Les conducteurs proposent une place pour des trajets sp&eacute;cifiques, &agrave; une date et une heure donn&eacute;es, via un service en ligne (g&eacute;n&eacute;ralement un site web ou une application). Les passagers consultent ces offres et s&eacute;lectionnent celle qui leur convient.

Diff&eacute;rents algorithmes de mise en relation offre-demande sont disponibles. Une fois qu’un passager a trouv&eacute; une offre appropri&eacute;e (qui peut concerner une partie du trajet propos&eacute; ou n&eacute;cessiter une l&eacute;gère modification du parcours), un contact est &eacute;tabli entre le conducteur et le passager afin de convenir des d&eacute;tails du trajet.

La r&eacute;servation finale (une fois tous les d&eacute;tails convenus) et le paiement peuvent varier selon le service de covoiturage utilis&eacute;.

### Covoiturage dynamique

\[Non retenu dans le cadre du profil France : Pas retenu pour L’instant 15/01/26\]. Ce n’est pas du planif&eacute;

Le covoiturage dynamique est similaire au covoiturage conventionnel, mais permet la mise en relation une fois le trajet commenc&eacute;. Il est principalement adapt&eacute; au contexte urbain (par opposition aux longues distances, g&eacute;n&eacute;ralement interurbaines et planifi&eacute;es &agrave; l’avance).

### Fonctions du covoiturage

Les paragraphes suivants d&eacute;crivent les fonctions du covoiturage

#### Tarification

\[Description A confirmer dans le profil FR\] 15/01/26 renvoyer vers le profil Tarif\] Permet de failre les abn

Le prix que le passager doit payer pour son trajet en covoiturage est cens&eacute; couvrir une partie des coûts du conducteur (carburant, coûts du v&eacute;hicule, etc.), mais ne constitue jamais un moyen pour le conducteur de r&eacute;aliser un b&eacute;n&eacute;fice (contrairement aux taxis et aux voitures avec chauffeur).

Le principe de base de la tarification consiste &agrave; calculer le prix en divisant la somme du carburant, des p&eacute;ages &eacute;ventuels, de la d&eacute;pr&eacute;ciation li&eacute;e &agrave; l’achat et &agrave; l’entretien du v&eacute;hicule, de l’assurance et des taxes pay&eacute;es par le conducteur, r&eacute;partie entre les voyageurs proportionnellement &agrave; la distance parcourue par le passager et au nombre de personnes ayant partag&eacute; le v&eacute;hicule.

Une tarification bas&eacute;e sur la distance a &eacute;galement &eacute;t&eacute; propos&eacute;e par certains services de covoiturage (ind&eacute;pendamment du nombre de voyageurs, sur la base du nombre maximal de voyageurs).

Il est &agrave; noter que la tarification n&eacute;cessite presque toujours un accord sur la distance du trajet avant le d&eacute;part (la dur&eacute;e du trajet n’entre pas dans le calcul du prix). Le d&eacute;tour effectu&eacute; par un conducteur pour prendre un passager doit &eacute;galement être pris en compte.

Il convient &eacute;galement de noter que la tarification n’a pas toujours lieu : dans certains cas, il peut s’agir d’un &eacute;change de services ou d’un accord pour être conducteur lors d’un trajet futur.

#### Preuve de covoiturage

\[Pas de preuve de port&eacute;e par NeTex\] Int&eacute;rêt

Pour être pay&eacute; ou pour pouvoir b&eacute;n&eacute;ficier de certains avantages r&eacute;serv&eacute;s aux conducteurs en covoiturage (par exemple le stationnement gratuit ou l’accès aux voies r&eacute;serv&eacute;es aux v&eacute;hicules &agrave; occupation multiple), le conducteur peut avoir besoin d’une preuve de covoiturage.

Cette preuve peut &eacute;galement être requise &agrave; des fins fiscales pour le conducteur (contrôle des revenus) ou pour le voyageur (preuve d’achat lorsqu’un remboursement est possible, par exemple pour les employ&eacute;s d’une entreprise).

Il n’est pas toujours possible d’obtenir une preuve de covoiturage et il n’existe pas de m&eacute;thode totalement fiable pour l’obtenir. En pratique, cette preuve peut être une d&eacute;claration personnelle, dans laquelle le covoitureur atteste avoir effectivement pratiqu&eacute; le covoiturage ce jour-l&agrave;. Cette d&eacute;claration peut être v&eacute;rifi&&eacute;e, par exemple en contrôlant les plaques d’immatriculation ou, sur des voies d&&eacute;di&&eacute;es, en v&&eacute;rifiant le nombre de personnes &agrave; l’int&&eacute;rieur du v&&eacute;hicule.

#### Inscription

- Valable pour Partage & Covoiturage – Description de service Usage Parameter – Vehicle Sharing Service \[A int&&eacute;grer dans le Profil\] -VehicleAccessCredential.

&&eacute;tant donn&&eacute; que le covoiturage est une activit&&eacute; de personne &agrave; personne, les services sont cens&&eacute;s offrir un très haut niveau de confiance et de s&&eacute;curit&&eacute; (s&&eacute;curit&&eacute; personnelle, en plus de la s&&eacute;curit&&eacute; financière).

Par cons&&eacute;quent, l’inscription implique le plus souvent plusieurs niveaux de v&&eacute;rification et de validation de l’identit&&eacute;, notamment :

- L’adresse e-mail (fournie pour mettre en relation deux utilisateurs) ;
- Le num&&eacute;ro de t&&eacute;l&&eacute;phone (fourni pour mettre en relation deux utilisateurs) ;
- Le lien vers un r&&eacute;seau social (afin que les utilisateurs puissent consulter le type d’activit&&eacute; sur un compte Facebook, par exemple) ;
- Le num&&eacute;ro de carte d’identit&&eacute; ou de passeport (seul le fait que la v&&eacute;rification a &&eacute;t&&eacute; effectu&&eacute;e est communiqu&&eacute; aux autres utilisateurs) ;
- Le permis de conduire et l’assurance.

#### M&&eacute;canismes de mise en relation et de r&&eacute;servation des trajets

\[Pr&&eacute;ciser si via Site ou Num Tel\] Laisser la partie explicative / Seule info n&&eacute;cessaire a l’echange cf Booking Arrangement

Les m&&eacute;canismes de mise en relation des trajets peuvent être très simples (correspondance origine/destination et fenêtre temporelle) ou assez complexes, pouvant int&&eacute;grer des fonctionnalit&&eacute;s telles que :

- L’utilisation d’un algorithme r&&eacute;el de planification de trajets bas&&eacute; sur le r&&eacute;seau routier (d’autres peuvent se contenter de « corridors » g&&eacute;ographiques, de simples points de passage ou de villes) ;
- L’&&eacute;largissement possible de la zone autour des lieux de d&&eacute;part et d’arriv&&eacute;e ;
- L’int&&eacute;gration possible de trajets multimodaux ;
- L’int&&eacute;gration de zones de covoiturage (et &&eacute;ventuellement une aide &agrave; leur localisation) ;
- L’int&&eacute;gration de d&&eacute;tours possibles ;
- L’int&&eacute;gration de la correspondance des profils utilisateurs ;
- L’int&&eacute;gration de connexions possibles avec les transports publics (en proposant aux voyageurs de commencer ou de terminer leur trajet en transport public ou, dans certains cas, de basculer vers le covoiturage en cas de perturbation des transports publics) ;
- L’enregistrement des demandes et la r&&eacute;ception d’alertes lorsqu’une offre correspondante est disponible (par exemple alertes SMS, e-mails, notifications dans les applications et autres formats de messagerie).

#### Paiement

Pas trait&&eacute; dans ce Profil : Cf Profil FR Tarification

Les services de covoiturage intègrent un m&&eacute;canisme de paiement s&&eacute;curis&&eacute;, jouant le rôle d’interm&&eacute;diaire entre le conducteur et le voyageur. Les moyens de paiement les plus courants, tels que la carte de cr&&eacute;dit, PayPal, le virement bancaire (pour les conducteurs), etc., sont g&&eacute;n&&eacute;ralement accept&&eacute;s.

Diff&&eacute;rents sc&&eacute;narios et caract&&eacute;ristiques peuvent exister :

- Il n’y a pas de paiement direct du voyageur au conducteur ;
- Le voyageur paie via le service en ligne (site web ou application) au moment de la r&&eacute;servation du trajet ;
- Le paiement inclut g&&eacute;n&&eacute;ralement le coût du trajet, les frais de service et les taxes &&eacute;ventuelles ;
- Une fois le trajet termin&&eacute; et si aucun &&eacute;v&&eacute;nement particulier n’a &&eacute;t&&eacute; signal&&eacute;, le conducteur est g&&eacute;n&&eacute;ralement pay&&eacute; quelques jours après le voyage, afin de laisser au voyageur le temps de signaler d’&&eacute;ventuels problèmes ;
- En cas de problème ou si, pour une raison quelconque, le trajet n’a pas &&eacute;t&&eacute; effectu&&eacute;, le voyageur peut être rembours&&eacute; (g&&eacute;n&&eacute;ralement sous conditions et pas toujours &agrave; 100 % ; les frais de service ne sont en g&&eacute;n&&eacute;ral pas rembours&&eacute;s).

#### Accessibilit&&eacute; pour les personnes &agrave; mobilit&&eacute; r&&eacute;duite

Certains services de covoiturage fournissent une description du v&&eacute;hicule et indiquent la capacit&&eacute; du conducteur &agrave; transporter des voyageurs en situation de handicap, notamment en fauteuil roulant ; toutefois, ce n’est pas la situation la plus courante et cela reste g&&eacute;n&&eacute;ralement sp&&eacute;cifique &agrave; certains services de covoiturage.

#### Infrastructures

En plus du r&&eacute;seau routier lui-même, certaines infrastructures plus sp&&eacute;cifiques peuvent être utilis&&eacute;es pour le covoiturage.

Les aires de covoiturage sont des zones signal&&eacute;es où un conducteur peut prendre ou d&&eacute;poser un passager pour commencer ou terminer un trajet en covoiturage. Il n’existe pas de structure pr&&eacute;d&&eacute;finie pour une aire de covoiturage :

- Il peut s’agir simplement d’une zone signal&&eacute;e accessible depuis le r&&eacute;seau routier ;
- Elle peut faire partie d’une aire de stationnement ;
- Elle peut être une zone d&&eacute;di&&eacute;e ;
- Elle peut être ferm&&eacute;e ou ouverte ;
- L’accès &agrave; la zone peut être gratuit, contrôl&&eacute; ou r&&eacute;glement&&eacute; ;

L’accès pour les passagers peut se faire uniquement &agrave; pied, mais la zone peut aussi offrir des places de stationnement (sous conditions convenues) permettant aux passagers de laisser leur propre voiture ou leur v&&eacute;lo et de commencer un trajet en covoiturage ; ou encore, une aire de covoiturage signal&&eacute;e peut être utilis&&eacute;e &agrave; d’autres fins (aire de repos, etc.).

Les aires de covoiturage ne sont pas obligatoires pour pratiquer le covoiturage ; elles visent principalement &agrave; le faciliter, &agrave; le promouvoir et &agrave; garantir une prise en charge et une d&&eacute;pose en toute s&&eacute;curit&&eacute;. Dans certains pays, il peut exister des r&&eacute;glementations concernant la signalisation et la gestion des aires de covoiturage.

### Utilisateurs du covoiturage

#### G&&eacute;n&&eacute;ralit&&eacute;s

Les profils des utilisateurs du covoiturage sont essentiels pour instaurer la confiance dans le service. Il existe deux principaux types de profils utilisateurs :

- Le profil du conducteur ;
- Le profil du voyageur.

Afin d’offrir un niveau de confiance suffisant, les utilisateurs (et donc les services de covoiturage) attendent la fourniture d’un maximum d’informations, ce qui soulève n&&eacute;anmoins des questions potentielles de protection de la vie priv&&eacute;e qui doivent être g&&eacute;r&&eacute;es par les services de covoiturage.

#### Conducteurs

En g&&eacute;n&&eacute;ral, davantage de donn&&eacute;es sont collect&&eacute;es pour le conducteur que pour le voyageur. Le niveau de d&&eacute;tail fourni varie selon l’&&eacute;tape du processus de r&&eacute;servation :

- Phase initiale de mise en relation (liste des trajets disponibles) : niveau minimal d’information ;
- S&&eacute;lection d’un trajet : informations un peu plus d&&eacute;taill&&eacute;es (le nom et les coordonn&&eacute;es du conducteur ne sont pas fournis, la communication se fait g&&eacute;n&&eacute;ralement via le service) ;
- Acceptation de la demande par le conducteur : informations complètes.

Les informations suivantes concernant le conducteur sont g&&eacute;n&&eacute;ralement requises :

- **Nom** (g&&eacute;n&&eacute;ralement partiellement masqu&&eacute; lors des premières &&eacute;tapes de la r&&eacute;servation) ;
- Permis de conduire et assurance valides ;
- Âge ;
- Niveau de v&&eacute;rification du compte du conducteur (adresse e-mail, num&&eacute;ro de t&&eacute;l&&eacute;phone, carte d’identit&&eacute;, etc.) ;
- Statistiques du compte du conducteur : nombre de trajets propos&&eacute;s, nombre de personnes transport&&eacute;es, date de première inscription, date du dernier trajet propos&&eacute;, etc. ;
- Style de conduite du conducteur, selon les voyageurs ;
- Caractère bavard ou r&&eacute;serv&&eacute; du conducteur ;
- Statut fumeur ou non-fumeur ;
- Pr&&eacute;sence &&eacute;ventuelle d’un animal dans le v&&eacute;hicule, même s’il n’est pas pr&&eacute;sent lors du trajet concern&&eacute; ;
- &&eacute;valuations des voyageurs : note moyenne, nombre d’&&eacute;valuations, etc. ;
- Commentaires des voyageurs ;
- Type de v&&eacute;hicule, incluant &&eacute;ventuellement des d&&eacute;tails sur celui-ci ;
- Int&&eacute;gration aux r&&eacute;seaux sociaux : nombre d’amis sur Facebook, etc.

Exigences accept&&eacute;es concernant les passagers :

- Possibilit&&eacute; de transporter des bagages, avec indication des dimensions ;
- Possibilit&&eacute; de d&&eacute;tours (y compris en termes de temps et de distance) ;
- Possibilit&&eacute; de transporter un animal ;
- &&eacute;quipements pour les voyageurs en situation de handicap ;
- Accompagnateurs pour les voyageurs en situation de handicap.

#### Voyageurs

Le profil du voyageur est transmis au conducteur, qui peut alors accepter la demande, engager une discussion avec le voyageur demandeur ou rejeter la demande.

Le profil du voyageur est g&&eacute;n&&eacute;ralement similaire &agrave; celui du conducteur, &agrave; l’exception des informations sp&&eacute;cifiques au conducteur (type de v&&eacute;hicule, etc.).

Les conducteurs peuvent &&eacute;valuer les voyageurs, tout comme les voyageurs peuvent &&eacute;valuer les conducteurs (ils sont g&&eacute;n&&eacute;ralement tous deux inform&&eacute;s de toute &&eacute;valuation ou commentaire, comme sur tout r&&eacute;seau social).

#### Priorit&&eacute;

Le covoiturage peut b&&eacute;n&&eacute;ficier d’une priorit&&eacute; pour l’utilisation des voies de transport public ou d’une priorit&&eacute; aux feux de circulation, avec l’autorisation des autorit&&eacute;s locales de gestion du trafic. Une information par signalisation sur ces priorit&&eacute;s est n&&eacute;cessaire, ainsi qu’un moyen robuste de d&&eacute;terminer quels v&&eacute;hicules pratiquent effectivement le covoiturage &agrave; un instant donn&&eacute;.

\[Pas dans le profil &agrave; date : Cf travaux en cours sur les infrastructure velo\]

# Modèle de donn&&eacute;es

## Les modes Alternatifs (nouveaux modes)

### Modèle ConceptuelModèle de donn&&eacute;es

#### MODE OF OPERATION (Mode d’exploitation)

Table 4 — Mode d’op&&eacute;ration

#### Alternative Mode OfOperation (Mode d’exploitation Alternatif)

Il s’agit d’un mode de transport public, diff&&eacute;rent des modes conventionnels, par exemple l’auto Table 5 — Mode d’op&&eacute;ration alternatif

##### COVOITURAGE

A r&&eacute;diger ult&&eacute;rieurement

##### VEHICLE SHARING (Partage de v&&eacute;hicule)

Location de v&&eacute;hicule &agrave; court terme où le v&&eacute;hicule peut être pris et stationn&&eacute; &agrave; diff&&eacute;rents endroits dans la zone urbaine, &&eacute;ventuellement sans l'obligation de ramener le v&&eacute;hicule &agrave; un lieu sp&&eacute;cifique.

Table 6 — Paratage de v&&eacute;hicule

###### VEHICULE SHARING TYPE (Type de partage de v&&eacute;hicule)

Table 7 — Type de Partage de v&&eacute;hicule

###### TypeOfModeOfOperation

Classification de MODE OF OPERATION.

Table 8 — Type de mode d’op&&eacute;ration

## Flotte de v&&eacute;hicule

**Statut impl&&eacute;mentation : OBLIGATOIRE** : Cette partie du profil peut être impl&&eacute;ment&&eacute;e en en fonction du contexte.
# Modèle de données

## Les modes Alternatifs (nouveaux modes)

### Modèle Conceptuel

Figure 3 : Mode Alternatif NM

### Modèle de données

#### MODE OF OPERATION (Mode d'exploitation)

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | TypeOfValue | ::> | MODE OF OPERATION hérite de TYPE OF VALUE. |
| «PK» | id  | ModeOfOperationIdType | 1:1 | Identifiant du MODE OF OPERATION. |
| «FK» | TypeOfModeOfOperationRef | TypeOfModeOfOperationRef | 0:1 | Référence à un TYPE OF MODE OF OPERATION. |
| «FK» | submodes | SubmodeRef | 1:\* | Référence à un SUB MODE. |

Table 4 - Mode d'opération

#### Alternative Mode OfOperation (Mode d'exploitation Alternatif)

Il s'agit d'un mode de transport public, différent des modes conventionnels, par exemple l'auto partage, le vélo en libre-service, ou le covoiturage

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | ModeOfOperation | ::> | ALTERNATIVE MODE OF OPERATION hérite de MODE OF OPERATION. |
| «PK» | id  | AlternativeModeOfOperationIdType | 1:1 | Identifiant d'un ALTERNATIVE MODE OF OPERATION. |

Table 5 - Mode d'opération alternatif

##### COVOITURAGE

A rédiger ultérieurement

##### VEHICLE SHARING (Partage de véhicule)

Location de véhicule à court terme où le véhicule peut être pris et stationné à différents endroits dans la zone urbaine, éventuellement sans l'obligation de ramener le véhicule à un lieu spécifique.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | AlternativeModeOfOperation | ::> | VEHICLE SHARING hérite de ALTERNATIVE MODE OF OPERATION. |
| «PK» | id  | VehicleSharingIdType | 1:1 | Identifiant de VEHICLE SHARING MODEL OF OPERATION. |
| «enum» | VehicleSharingType | VehicleSharingTypeEnum | 0:1 | Valeurs autorisées pour un VEHICLE SHARING. Cf la table ci-après |

Table 6 - Paratage de véhicule

###### VEHICULE SHARING TYPE (Type de partage de véhicule)

Cette table indique les valeurs autorisées pour VehicleSharingType dans le cadre du profil France

| **Valeur** | **Description** |
| --- | --- |
| carSharingClub | Car Sharing Club. |
| peerToPeerCarSharingClub | Peer-to-peer Car Sharing Club. |
| vehicleSharing | Partage de véhicule |

Table 7 - Type de Partage de véhicule

###### TypeOfModeOfOperation

Classification de MODE OF OPERATION.

<div class="joplin-table-wrapper"><table><tbody><tr><th><p><strong>Classification</strong></p></th><th><p><strong>Nom</strong></p></th><th><p><strong>Type</strong></p></th><th><p><strong>Cardinalité</strong></p></th><th><p><strong>Description</strong></p></th></tr><tr><td><p>::&gt;</p></td><td><p>::&gt;</p></td><td><p>TypeOfValue</p></td><td><p>::&gt;</p></td><td><p>TYPE OF MODE OF OPERATION hérite de TYPE OF VALUE.</p></td></tr><tr><td><p><a id="BKM_2D231185_EAE2_440B_8E14_F78C1D499CE1"></a>«PK»</p></td><td><p>id</p></td><td><p>TypeOfModeOfOperationIdType</p></td><td><p>1:1</p></td><td><p>Identifiant de TYPE OF MODE OF OPERATION.</p><p>Pour le partage de véhicule sont autorisés&nbsp;:</p><ul><li>Stationless Vehicle Sharing</li><li>Cycle sharing</li><li>Commercial Car sharing</li></ul></td></tr></tbody></table></div>

Table 8 - Type de mode d'opération

## Flotte de véhicule

### Modèle Conceptuel

**Le modèle de flotte NM décrit la flotte de véhicules, définie comme un ensemble de véhicules de tout type. Le concept de flotte est général, c'est-à-dire qu'il ne dépend pas du mode d'exploitation, mais il est particulièrement utile pour décrire les services offerts par certains modes d'exploitation alternatifs (NM).**

**Une flotte appartient à une organisation de transport, un organisme légalement constitué lié à un aspect quelconque du système de transport. Une organisation de transport peut posséder plusieurs flottes.**

Figure 4 : Flotte de véhicule NM

### Modèle de données

#### Fleet (Flotte)

**Un ensemble de véhicule de tout type****.**

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _GroupOfEntities_ | ::> | FLEET hérite de GROUP OF ENTITies. |
| «PK» | **_id_** | _FleetIdType_ | 1:1 | Identifiant de FLEET. |
| «cntd» | **_members_** | _Vehicle_ | 0:\* | VEHICULES de la flotte. Cf VEHICULE<br><br>Voir § 10.6. |
| «FK» | **_TransportOrganisationRef_** | _TransportOrganisationRef_ | 0:1 | Identifiant de l'organisation TRANSPORT ORGANISATION possédant la Flotte |
| «FK» | **_TypeOfFleetRef_** | _TypeOfFleetRef_ | 0:1 | Identifiant du TYPE OF FLEET. |
| «cntd» | **_transportTypes_** | _TransportTypeRef_ | 0:\* | TRANSPORT TYPEs et VEHICLE TYPEs de la Flotte. |

Table 9 - Flotte

##### Type of Fleet (Type de Flotte)

Classification d'une flotte de véhicule.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _TypeOfValue_ | ::> | TYPE OF FLEET hérite de TYPE OF VALUE. |
| «PK» | **_id_** | _TypeOfFleetIdType_ | 1:1 | Identifiant de TYPE OF FLEET. |

Table 10 - Type de flotte

### Flotte - XML Exemple

#### Cas du vélo Partage

Exemple xml 1 : Flotte de vélos

#### Cas d'une flotte de voitures

Exemple xml 2 : Flotte de véhicules

## Service En ligne

### Modèle conceptuel

L'entité SERVICE EN LIGNE représente tout service accessible à distance offrant un accès à un mode de transport et/ou à des informations relatives aux services de transport.

Un OPÉRATEUR DE SERVICE EN LIGNE est responsable de la gestion d'un SERVICE EN LIGNE (mais pas nécessairement du transport lui-même, c'est-à-dire différent d'un OPÉRATEUR DE TRANSPORT), par exemple pour fournir des informations à un utilisateur sur des offres de covoiturage disponibles ou adaptées, via une application web. Le SERVICE EN LIGNE assure une interface entre les utilisateurs ou entre utilisateurs et opérateurs.

Figure 5 : Services en ligne NM

### Modèle de données

#### OnlineServiceOperator (Opérateur de Service en ligne)

Une organisation qui fournit un accès en ligne à un SERVICE EN LIGNE sans nécessairement exploiter des services de transport pour les voyageurs.

Note : un SERVICE EN LIGNE peut être exploité par tout OPÉRATEUR, mais un OPÉRATEUR DE SERVICE EN LIGNE gère uniquement des SERVICES EN LIGNE.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _TransportOrganisation_ | ::> | ONLINE SERVICE OPERATOR hérite de TRANSPORT ORGANISATION |
| «PK» | **_id_** | _OnlineServiceOperatorIdType_ | 1:1 | Identifiant de ONLINE SERVICE OPERATOR. |
| "cntd» | **_onlineServices_** | _OnlineServiceRef_ | 0:\* | ONLINE SERVICES opérés par l'opérateur |

Table 11 - OnlineServiceOperator

##### OnlineService (Service en ligne)

Tout service accessible à distance offrant un accès à un mode de transport et/ou à des informations relatives aux services de transport

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _MobilityService_ | ::> | ONLINE SERVICE hérite de MOBILITY SERVICE |
| «PK» | **_id_** | _OnlineServiceIdType_ | 1:1 | Identifiant de ONLINE SERVICE. |
|     | **_LoginRequired_** | _xsd:boolean_ | 0:1 | Utilisation d'un login pour accéder au service (oui/non) |
| «cntd» | **_proposingServices_** | _CommonVehicleServiceRef_ | 0:\* | VEHICLE SERVICEs proposéspar ONLINE SERVICE. |

Table 12 - OnlineService

### Exemple d'Online Service

#### Service en ligne pour VLS

Exemple xml 3 : Online Service

## Zone de Stationnement

### Modèle conceptuel

La description des zones de stationnement pour les modes de déplacement de type véhicule partagé est décrite dans le profil France Parking ;

Cette partie du modèle permet de décrire les zones de dépôt des véhicules. Le lien avec les véhicules et services rattachés Sont décrits au paragraphe 10.7.2.2.

Figure 6 Modèle Emplacement NM

### Modèle de données

#### PARKING (Station)

La définition des zones de stationnement et de leurs emplacements est décrite dans le profil France Parking (paragraphe 6.2).

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | ParkingArea | ::> | VEHICLE SHARING PARKING AREA hérite PARKING AREA. |
| «PK» | id  | VehicleSharingParkingAreaIdType | 1:1 | Identifiant de VEHICLE SHARING PARKING AREA. |

Table 13 - **PLACES DE STATIONNEMENT**

#### VEHICLE SHARING PARKING AREA (Zone de partage de véhicule)

L'affectation d'une VEHICLE SHARING PARKING AREA à tout type de service de partage de véhicule

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | VehicleServicePlaceAssignment | ::> | VEHICLE SHARING PLACE ASSIGNMENT hérite de VEHICLE SERVICE PLACE ASSIGNMENT. |
| «PK» | id  | VehicleSharingPlaceAssignmentIdType | 1:1 | Identifiant de VEHICLE SHARING PLACE ASSIGNMENT. |
| «cntd» | VehicleCommonServiceRef | VehicleSharingServiceRef | 0:\* | Référence à VEHICLE SHARING SERVICE |
| «FK» | VehicleSharingParkingAreaRef | VehicleSharingParkingAreaRef | 1:1 | Référence un VEHICLE SHARING PARKING AREA. |
| «FK» | VehicleSharingParkingBayRef | ParkingBayRef | 1:1 | Référence à VEHICLE SHARING PARKING BAY. |

Table 14 - **PLACES DE STATIONNEMENT POUR VÉHICULES PARTAGÉS**

#### ParkingBay (Place de stationnement)

Une place dans le PARKING réservée au partage de véhicules.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | ParkingBay | ::> | VEHICLE SHARING PARKING BAY hérite PARKING BAY. |
| «PK» | id  | VehicleSharingParkingBayIdType | 1:1 | Identifiant de VEHICLE SHARING PARKING BAY. |

Table 15 - **Dock de stationnement pour véhicule**

##### **_VehicleSharingParkingBay (Emplacement de parking à l'usage de partage de véhicule)_**

Permet de définir un Place de parking pour le partage de véhicule.

| **Classifi­cation** | **Name** | **Type** | **Cardin­ality** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _ParkingBay_ | ::> | VEHICLE SHARING PARKING BAY hérite de PARKING BAY. |
| «PK» | **_id_** | _VehicleSharingParkingBayIdType_ | 1:1 | Identifiant du VEHICLE SHARING PARKING BAY. |

Table 16 - **Dock de stationnement pour véhicule partagé**

## Géofencing

**Une ZONE DE CONTRAINTE DE SERVICE DE MOBILITÉ** (MOBILITY SERVICE CONSTRAINT ZONE ) impose des restrictions sur les déplacements à l'intérieur d'une zone pour un **MODE DE FONCTIONNEMENT** donné.

Une **RESTRICTION DE ZONE PAR TYPE DE VÉHICULE** (VEHICLE TYPE ZONE RESTRICTION ) spécifie quel **TYPE DE RESTRICTION** s'applique à un **TYPE DE TRANSPORT (**TRANSPORT TYPE) donné.

### Modèle conceptual

Figure 7 Modèle Géofencing NM

### Modèle de données

#### MobilityConstraintZone (Zone de mobilité contrainte)

ZONE définissant une zone de restriction de l'utilisation d'un MOBILITY SERVICE, par exemple : interdiction d'entrée, interdiction de dépose, etc

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | Zone | ::> | MOBILITY SERVICE CONSTRAINT ZONE hérite de ZONE. |
| «PK» | id  | MobilityConstraintZoneIdType | 1:1 | Identifiant d'une MOBILITY SERVICE CONSTRAINT ZONE. |
| «enum» | RuleApplicability | RuleApplicabilityEnum | 0:1 | Indique si la règle s'applique à l'intérieur ou l'extérieur de la zone.<br><br>Par Défaut : Intérieur. |
| «enum» | ZoneUse | ZoneUseTypeEnum | 0:1 | Comment la zone peut être utilisée |
| «cntd» | vehicleTypeRestrictions | VehicleTypeZoneRestriction | 0:\* | Restrictions applicables à différents types de véhicules |
|     | MaximumSpeed | Speed | 0:1 | Vitesse maximale dans la zone |
| «FK» | MobilityServiceRef | MobilityServiceRef | 0:1 | MOBILITY SERVICE associés à la MOBILITY SERVICE CONSTRAINT ZONE. |

Table 17 - MobilityConstraintZone

##### ZoneUseType (Type de zone d'usage)

Les valeurs autorisées pour **ZoneUseType (**ZoneUseTypeEnumeration**) sont les suivantes** **:**

| **Valeur** | **Description** |
| --- | --- |
| allUsesAllowed | Toute utilisation autorisée : Ramassage, dépose, via |
| forbiddenZone | Interdiction de ramassage ou de Dépôt dans la zone |
| cannotPickUpInZone | Interdiction d'entrée dans la zone |
| cannotDropOffInZone | Interdiction de dépôt dans la zone |
| mustPickUpInZone | Obligation d'entrée dans la zone |
| mustDropOffInZone | Obligation de dépôt dans la zone |
| passThroughUseOnly | Interdiction d'entrée ou de Dépôt dans la zone mais possibilité de traversée |
| noPassThrough | Interdiction de traverse uniquement (obligation de ramassage ou dépôt dans la zone) |
| cannotPickUpAndDropOfInSameZone | Interdiction d'entrée et dépôt dans la même zone. |
| mustPickUpAndDropOffInSameZone | Obligation d'entrée et dépôt dans la zone |
| other | Autres restrictions. |

Table 18 - ZoneUseType

##### VehicleTypeZoneRestriction (Zone de restriction de Circulation)

Restriction d'utilisation dans une MOBILITY SERVICE CONSTRAINT ZONE TRANSPORT TYPE pour un mode de transport.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | VersionedChild | ::> | VEHICLE TYPE ZONE RESTRICTION hérite de VERSIONED CHILD. |
| «PK» | id  | PoolOfVehiclesIdType | 1:1 | Identifiant VEHICLE TYPE ZONE RESTRICTION. |
| «enum» | ZoneUse | ZoneUseTypeEnum | 0:1 | Modalité d'utilisation de la zone. |
|     | MaximumSpeed | Speed | 0:1 | Vitesse maximum dans MOBILITY SERVICE CONSTRAINT ZONE. |
| «FK» | MobilityServiceConstraintZoneRef | MobilityServiceConstraintZoneRef | 0:1 | MOBILITY SERVICE CONSTRAINT ZONE auxquels les restrictions s'appliquent |
| «FK» | TransportTypeRef | TransportTypeRef | 0:1 | TRANSPORT TYPE auxquels les restrictions s'appliquent |

Table 19 - Type de zone de restriction

## Véhicules

### Modèle conceptual

La définition d'un véhicule (Cycle, Voiture) répond à la décomposition conceptuelle suivante.

Figure 8 : Véhicule - MC

L'équipement réel du véhicule spécifie le type d'équipement à utiliser dans un véhicule Donné

Figure 9 : Actual Vehicle Equipment MC

### Modèle de données

Le modèle **SIMLE** **VEHICLE TYPE** décrit les véhicules « personnels » et leurs propriétés.

Les véhicules peuvent être classés en fonction des exigences de planification, notamment :

- Le modèle,
- La capacité,
- Les équipements embarqués (Siège bébé, …)

Ces mêmes exigences peuvent être associées à un **SERVICE JOURNEY** pour indiquer que ce service doit être assuré par un véhicule de ce type.

#### Vehicle (Véhicule)

Description d'un véhicule transport des passagers.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | DataManagedObject | ::> | VEHICLE hérite de DATA MANAGED OBJECT. |
| «PK» | **_id_** | VehicleIdType | 1:1 | Identifiant |
|     | **_Name_** | MultilingualString | 0:1 | Nom du véhicule |
|     | ShortName | MultilingualString | 0:1 | Nom court VEHICLE. |
| «AK» | Registration­Number | xsd:normalizedString | 0:1 | Immatriculation du VEHICULE. |
|     | Registration Date | xsd:date | 0:1 | date d'immatriculation du VEHICULE |
| «AK» | OperationalNumber | xsd:normalizedString | 0:1 | Operational number of VEHICLE. |
| «AK» | PrivateCode | PrivateCode | 0:1 | Identifiant alternatif du VEHICULE.<br><br>Peut être utilisé pour les identifiant interne. |
| «FK» | TransportOrganisationRef | TransportOrganisationRef | 1:1 | Identifiant de l'OPERATEUR ou d'une TRANSPORT ORGANISATION. |
| «FK» | TransportTypeRef | TransportTypeRef | 0:1 | Identifiant d'un TRANSPORT TYPE du VEHICLE |
| «FK» | VehicleModelRef | VehicleModelRef | 0:1 | Identifiant MODEL du VEHICLE |
| «FK» | VehicleModelProfileRef | VehicleModelProfileRef | 0:1 | Identifiant MODEL EQUIPMENT PROFILE of VEHICLE |
| «cntd» | actualVehicle­Equipments | (EquipmentRef) \| (Equipment) | 0:1 | Identifiant ou description du Actual vehicle equipment, i.e., EQUIPMENT for VEHICLE |

Table 20 - Vehicle - Element

#### Actual Vehicle Equipment (Équipement réel du véhicule)

Cet élément permet de spécifier un équipement d'un type particulier effectivement disponible dans un véhicule donné.

| **Classification** | **Name** | **Type** | **Cardinality** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _InstalledEquipment_ | ::> | ACTUAL VEHICLE EQUIPMENT hérite de PASSENGER EQUIPMENT. |
| «PK» | **_id_** | _ActualVehicleEquipmentIdType_ | 1:1 | Identifiant ACTUAL VEHICLE EQUIPMENT. |
|     | **_Units_** | _xsd:nonNegativeInteger_ | 0:1 | Nombre d'exemplaires de l'ACTUAL VEHICLE EQUIPMENT there are on vehicle. |
| «FK» | **_VehicleTypeRef_** | _VehicleTypeRef_ | 0:1 | VEHICLE TYPE auquel s'applique l'ACTUAL VEHICLE EQUIPMENT. |
| «cntd» | **_Accessibility­Assessment_** | _AccessibilityAssessment_ | 0:1 | ACCESSIBILITY ASSESSMENT de l'ACTUAL VEHICLE EQUIPMENT.<br><br>Se reporter au profil France accessibilité. |

Table 21 - Equipement disponible dans le véhicule

#### TransportType (Type de transport)

Classification de tout type de véhicule en fonction de ses caractéristiques

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | DataManagedObject | ::> | TRANSPORT TYPE hérite de DATA MANAGED OBJECT. |
| «PK» | id  | TransportTypeIdType | 1:1 | Identifiant TRANSPORT TYPE. |
|     | Name | MultilingualString | 0:1 | nom du TRANSPORT TYPE. |
|     | ShortName | MultilingualString | 0:1 | Nom court TRANSPORT TYPE. |
|     | Description | MultilingualString | 0:1 | Description of TRANSPORT TYPE. |
| «AK» | PrivateCode | PrivateCode | 0:1 | Identifiant interne TRANSPORT TYPE. |
| XGRP | TransportType­PropertiesGroup | xmlGroup | 0:1 | Elément décrivant les propriétés du TRANSPORT TYPE. Voir ci-dessous |
| «enum» | TransportMode | AllVehicleModesEnum | 0:1 | Mode de transport : Valeurs autorisées |
|     | EuroClass | xsd:normalizedString | 0:1 | Euroclass du véhicule type. |
| «cntd» | Passenger­Capacity | PassengerCapacity | 0:1 | Capacité en nombre de passage du TRANSPORT TYPE. |

Table 22 - Transport Type

##### TransportTypePropertiesGroup (Groupe de propriétés des types de transport)

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
|     | Reversing­Direction | xsd:boolean | 0:1 | Whether VEHICLE TYPE has a reversing direction. |
|     | SelfPropelled | xsd:boolean | 0:1 | Whether VEHICLE TYPE is self-propelled. |
| «enum» | PropulsionType | PropulsionTypeEnum | 0:1 | Type de carburant du VEHICLE TYPE. Cf ci-dessous |
| «enum» | FuelType | FuelTypeEnum | 0:1 | Type of Fuel of VEHICLE TYPE. See allowed values below. |
|     | TypeOfFuel | FuelTypeEnum |     | DEPRECATED - renamed to FuelType |
|     | MaximumRange | DistanceType | 0:1 | Autonomie maximale en km |

Table 23 -TransportTypePropertiesGroup

###### PropulsionType (Type de propulsion)

| **Valeurs** | **Description** |
| --- | --- |
| combustion | Thermique de tout type |
| hybrid | Hybride Electrique / Thermique |
| human | Humaine (Pédalage) |
| electricAssist | Assistance Electrique (velo / Trotinette) |
| other | Autres |

Table 24 -PropulsionType - Valeurs

###### FuelType (Type de carburant)

Valeurs autorisées pour **_FuelType_** (_FuelTypeEnum_).

| **valeurs** | **Description** |
| --- | --- |
| battery | Batterie |
| biodiesel | Biodiesel. |
| _diesel_ | Diesel |
| dieselBatteryHybrid | Hybride Diesel & Batteried |
| electricContact | Electrique nécessitant un contact avec un cable ou un rail. |
| ethanol | Ethanol |
| hydrogen | Hydrogène. |
| liquidGas | Gaz Liquide |
| _tpg_ | TPG (Thermochemical Power Group). |
| methane | Methane. |
| _petrol_ | Essence. |
| petrolLeaded | Essence Plomb |
| petrolUnLeaded | Essence Sans Plomb |
| petrolBatteryHybrid | Hybride Essance & Batterie. |
| other | Autre carburant |
| none | Pas de carburant necessaire |

Table 25 - FuelType - Valeurs

#### VéhicleModel (Modèle de Véhicule)

Classification des véhicules de transport public d'un même type, par exemple selon les spécifications de l'équipement ou la génération du modèle.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | DataManagedObject | ::> | VEHICLE MODEL hérite de DATA MANAGED OBJECT. |
| «PK» | **_id_** | VehicleModelIdType | 1:1 | Identifiant de VEHICLE MODEL. |
|     | **_Name_** | MultilingualString | 0:1 | Nom du VEHICLE MODEL. |
|     | Description | MultilingualString | 0:1 | Description du VEHICLE MODEL. |
|     | Manufacturer | MultilingualString | 0:1 | Fabricant du VEHICLE MODEL. |
| «FK» | TransportTypeRef | TransportTypeRef | 1:1 | Identifiant du TRANSPORT TYPE ou du VEHICLE TYPE du VEHICLE MODEL. |
| «FK» | VehicleModelProfileRef | VehicleModelProfileRef | 0:1 | VEHICLE MODEL PROFILE du VEHICLE MODEL |
| «FK | equipmentProfiles | VehicleEquipmentProfileRef | 0:\* | Equipment profile for VEHICLE MODEL. |

Table 26 - Modèle de véhicule

##### Vehicle Model Profile (Profil de Modèle de véhicule)

Ensemble des caractéristiques des équipements installés dans un véhicule et définissant un modèle de véhicule.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _DataManagedObject_ | ::> | VEHICLE MODEL PROFILE hérite de DATA MANAGED OBJECT. |
|     | **_Name_** | _MultilingualString_ | 0:1 | Nom du VEHICLE MODEL PROFILE. |
|     | **_NumberOfGears_** | _xsd:nonNegativeInteger_ | 0:1 | Nombre de Vitesse du véhicule VEHICLE. |
| «enum» | **_ChildSeat_** | _ChildSeatEnumeration_ | 0:1 | Indique la présence d'un siège enfant à bord. |
|     | **_RangeBetweenRefuelling_** | _DistanceType_ | 0:1 | Autonomie du véhicule MODEL PROFILE. |
|     | **_IsPortable_** | _xsd:boolean_ | 0:1 | Indique si le véhicule peut être transporté facilement : concerne les scooter, skateboard, bicycle pliable. |

Table 27 - Profil de modèle de véhicule

###### ChildSeat (Siège Enfant)

La définition du siège enfant peut prendre les valeurs suivantes : **_._**

| **Valeur** | **Description** |
| --- | --- |
| _Baby_ | Siège adapté pour les bébés |
| _smallChild_ | Siège adapté pour les enfants entre 9-18 kg. |
| _olderChild_ | Siège adapté pour les enfants entre 15-36 kg. |
| _None_ | No child. |
| _other_ | Autre type de siège |

Table 28 - Définition d'un siège Enfant

#### SimpleVehicleType (Type de Véhicule Simple)

Un type de véhicule simple, définit les exigences pour un VÉHICULE utilisé afin de fournir des services de modes alternatifs et peut inclure des caractéristiques d'autres types de véhicules tels que les vélos, trottinettes, etc. »

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | _::>_ | _TransportType_ | ::> | SimpleVehicleType hérite de TransportType |
| «PK» | **_id_** | _SimpleVehicleTypeIdType_ | 1:1 | Identifiant de SIMPLE VEHICLE TYPE. |
| «enum» | **_LicenceRequirements_** | _LicenceRequirementsEnum_ | 0:1 | Indique si ce type de véhicule nécessite un permis. |
|     | **_MinimumAge_** | _xsd:integer_ | 0:1 | Age minimum pour l'utilisation du véhicule |
| «enum» | **_VehicleCategory_** | _VehicleCategoryEnum_ | 0:1 | Catégorie du véhicule |
|     | **_Portable_** | _xsd:boolean_ | 0:1 | Indique si le véhicule est portable, par exemple un vélo pliant ou une trottinette. |

Table 29 - Type de véhicule simple

##### LicenceRequirements - Valeurs autorisées

Valeurs autorisées pour un permis d'utilisation (_LicenceRequirementsEnum_).

| **Value** | **Description** |
| --- | --- |
| _full_ | _Permis nécessaire_ |
| _provisional_ | _Requires at least a provisional licence_ |
| _additional_ | _Requires additional vehicle category licence._ |
| _none_ | _Aucun permis requis_ |

Table 30 - Type de véhicule simple

##### PersonalVehicleCategory- v Valeurs autorisées

Valeurs autorisées pour la catégorie de véhicule Personnel _PersonalVehicleCategoryEnum_).

| **Value** | **Description** |
| --- | --- |
| _scooter_ | Scooter - small wheeled low mobile platform. |
| _bicycle_ | Bicycle. |
| _tricycle_ | Tricycle. |
| _tandem_ | Tandem bicycle. |
| _moped_ | Moped (Petite moto). |
| _motorcycle_ | Moto. |
| _quadbike_ | Quad |
| _car_ | Voiture |
| _microCar_ | Extremely small vehicle. |
| _miniCar_ | Very small vehicle. |
| _smallCar_ | Small vehicle. |
| _mediumCar_ | Compact vehicle. |
| _largeCar_ | Large vehicle. |
| _minivan_ | Minivan. |
| _transporter_ | minibus. |
| _snowmobile_ | MotoNeige |
| _other_ | Autre |

Table 31 - Type de Véhicule

### Exemple d'utilisation «  SimpleVehicleType »

#### Cas d'une flotte de vélos

Exemple xml 4 : Exemple modélisation « SimpleVehiculeType »

## Services

### Services de mobilité

#### Modèle conceptual

Figure 10 : Service En ligne - MC

#### Modèle de données

##### MOBILITY SERVICE (Service de mobilité)

Un service nommé disponible sur une vaste zone, par exemple le covoiturage, le partage de véhicule, etc. Le service peut être accessible à des emplacements désignés. SITEs or ADDRESSABLE PLACEs.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | Equipment | ::> | MOBILITY SERVICE hérite EQUIPMENT. |
| «PK» | id  | MobilityServiceIdType | 1:1 | Identifiant de MOBILITY SERVICE. |
|     | ShortName | MultilingualString | 0:1 | Nom court d'un service |
|     | StartDate | xsd:date | 0:1 | Date à laquelle le service devient opérationnel. |
| «FK» | OrganisationRef | OrganisationRef | 0:1 | Identifiant d'une ORGANISATION... |
| «FK» | TopographicPlaceRef | TopographicPlaceRef | 0:1<br><br>1:1 | Identifiant d'un TOPOGRAPHIC PLACE associé au SERVICE.<br><br>Obligatoire pour le profil France |
| «FK» | TypeOfMobilityServiceRef | TypeOfMobilityServiceRef | 0:1 | Identifiant d'un type MOBILITY SERVICE. |
| «cntd» | BookingArrangements | ServiceBookingArrangements | 0:1 | Modalité de réservation du service |

Table 32 - Service de mobilité

##### CommonVehicleService (Service de mobilité usuel )

Un service de transport qui utilise des véhicules pour effectuer des trajets. La zone de couverture du service peut être indiquée par un LIEU TOPOGRAPHIQUE. »

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | MobilityService | ::> | COMMON VEHICLE SERVICE hérite de MOBILITY SERVICE |
| «PK» | id  | CommonVehicleServiceIdType | 1:1 | Identifiant de COMMON VEHICLE SERVICE. |
|     | BookingRequired | xsd:boolean | 1:1 | Indique si une réservation du service est nécessaire. |
|     | RegistrationRequired | xsd:boolean | 0:1 | Indique si un enregistrement est nécessaire |
| «cntd» | proposedByServices | OnlineServiceRef | 0:\* | Identifiant du ONLINE SERVICEs qui propose le service |

Table 33 - Service de mobilité usuel

##### VehicleSharingService (Service de partage de véhicule)

Un Service type Vélo en libre-service ou Auto-partage.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | CommonVehicleService | ::> | VEHICLE SHARING SERVICE hérite de COMMON VEHICLE SERVICE. |
| «PK» | id  | VehicleSharingServiceIdType | 1:1 | Identifiant VEHICLE SHARING SERVICE. |
| «FK» | VehicleSharingRef | VehicleSharingRef | 0:1 | Référence à un VEHICLE SHARING mode d'exploitation. |
|     | SharingPolicyUrl | xsd:anyURI | 1:1 | URL pour la politique d'utilisation |
|     | MinimumSharingPeriod | xsd:duration | 0:1 | Durée minimum de partage VEHICLE SHARING. |
|     | MaximumSharingPeriod | xsd:duration | 0:1 | Durée maximum de partage VEHICLE SHARING_._ |
|     | FloatingVehicles | xsd:boolean | 0:1 | Indique si le partage de véhicule est de type free floating. |
| «FK» | fleets | FleetRef | 0:\* | Référence à une FLEETs qui gère le service de partage. |

Table 34 -VehicleSharingService - Element

##### CarPoolingService (Covoiturage)

A completer ultérieurement

### Services aux voyageurs

#### Réservation

Les dispositions de réservation décrivent les paramètres spécifiques des règles de réservation pour un service et sont utilisées par plusieurs entités différentes.

Pour les nouveaux modes, les dispositions de réservation peuvent être appliquées aux services de mobilité liés aux modes d'exploitation alternatifs, notamment la location de véhicules, le partage de véhicules et le covoiturage de véhicules. La réservation des services de location, de partage et de covoiturage de véhicules peut être effectuée via un service en ligne

##### Modèle conceptual

Figure 11 : Réservation - MC

##### Modèle de données

###### Booking Arrangements

Information relative aux méthodes de réservation d'un véhicule partagé.

**_Pour plus de détail sur les valeurs autorisées se reporter au Profil NeTex France Réseaux._**

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ««cntd» | **_BookingContact_** | _ContactDetails_ | 0:1 | Information contractuelle |
| «enum» | **_BookingMethods_** | _BookingMethodListEnum_ | 0:\* | Méthode de reservation |
| «enum» | **_BookingAccess_** | _BookingAccessEnum_ | 0:1 | Qui peut faire une réservation |
| «enum» | **_BookWhen_** | _PurchaseWhenEnum_ | 0:1 | Créneaux de réservation |
| «enum» | **_BuyWhen_** | _PurchaseMomentEnum_ | 0:\* | Créneaux d'achat |
|     | **_LatestBookingTime_** | _MultilingualString_ | 0:1 | Heure au plus tard de réservation |
|     | **_MinimumBooking­Period_** | _xsd:duration_ | 0:1 | Intervalle minimum avant le début de la commande. |
|     | **_MaximumBooking­Period_** | _xsd:duration_ | 0:1 | Intervalle minimum avant le début de la commande |
|     | **_BookingUrl_** | _xsd:anyURI_ | 0:1 | url de réservation |
| «cntd» | **_BookingNote_** | _MultilingualString_ | 0:1 | Information complémentaire |

Table 35 - BookingArrangements

#### Information sur les zones de dépôt des véhicules

##### Modèle Conceptuel

###### **Vehicle Meeting Place** (Zone de dépôt/Station)

Le **modèle NM Vehicle Meeting Place** définit les points d'arrêt où les passagers retrouvent leurs modes de transport alternatifs.

Au sens le plus large, il peut s'agir de tout lieu disposant d'une adresse. Cela peut inclure des points d'arrêt (**STOP PLACE)** et des stations (**PARKING)**, ainsi que leurs composants, tels que définis dans la Partie 1.

Une station (**PARKING)** représente un emplacement désigné pour laisser des véhicules tels que voitures, motos ou vélos. Transmodel inclut un modèle permettant de décrire les éléments de stationnement comme des spécialisations de **SITE COMPONENTs**.

La connexion entre les points d'arrêt et les services qui y opèrent se trouve dans le **modèle NM service de mobilité**.

Le **modèle NM Vehicle Meeting Place** distingue deux grands types de **ADDRESSABLE PLACE** (lieux pouvant être localisés par coordonnées spatiales et/ou adresse postale ou routière) :

- **VEHICLE MEETING PLACEs** : lieux où véhicules, voyageurs et conducteurs se rencontrent pour changer de mode de transport, embarquer, débarquer, prendre ou déposer des passagers, etc.

Un **VEHICLE MEETING PLACE** peut être associé à un **SITE** spécifique (tel qu'un **STOP PLACE** ou un **POINT OF INTEREST**) ou à tout composant à l'intérieur de ce **SITE**.

- **PARKING COMPONENTs** : emplacements désignés pour laisser des véhicules tels que voitures, motos ou vélos.

Ces lieux se distinguent par leur usage : dans un **VEHICLE MEETING PLACE**, il n'est pas possible de laisser un véhicule sans surveillance pour une durée prolongée.

Figure 12 :NM Point de rencontre (UML)

###### VEHICLE SERVICE PLACE ASSIGNMENT -

Les différents **services de véhicules** utilisent des **emplacements spécifiques** pour **embarquer et débarquer les passagers**, ou pour permettre aux voyageurs de **prendre ou restituer un véhicule**.

Des spécialisations du mécanisme générique **Transmodel ASSIGNMENT** permettent de **lier les arrêts et les emplacements de stationnement correspondants aux services de véhicules**.

Chaque service est décrit individuellement ci-dessous.

Figure 13 NM Vehicle Service Place Assignment MODEL (UML)

###### VEHICLE SHARING PLACE ASSIGNMENT -

Les **services d'autopartage** et de **location de véhicules** ont besoin d'**emplacements** pour que les utilisateurs puissent **prendre ou déposer les véhicules**. Ces emplacements peuvent être **exclusifs à un service** ou **partagés**. Un **Vehicle Sharing Place Assignment** permet d'**attribuer des zones et places de stationnement** à un service particulier.

Certains services d'autopartage, dits **« Free-Floating »**, permettent de **déposer et récupérer le véhicule n'importe où**, par exemple à un **emplacement identifiable quelconque**, représenté par des **points de rencontre pour véhicules**.

Un même **Vehicle Sharing Place Assignment** peut **servir soit à l'autopartage, soit à la location**, mais **pas aux deux en même temps**. Si une zone de stationnement est utilisée pour un assignment et un service d'autopartage, **deux assignments distincts doivent être définis**.

Figure 14 : NM Vehicle Sharing Place Assignment MODEL (UML)

##### Modèle de données

###### **VehicleMeetingPlace**

Lieu où véhicules et passagers se rencontrent pour changer de mode de transport, pour embarquer, débarquer, prendre ou déposer des passagers, etc.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _AddressablePlace_ | ::> | VEHICLE MEETING PLACE Hérite de ADDRESSABLE PLACE. |
| «PK» | **_id_** | _VehicleMeetingPlaceIdType_ | 1:1 | Identifiant de VEHICLE MEETING PLACE. |
| «FK» | **_TopographicPlaceRef_** | _TopographicPlaceRef_ | 0:1 | Référence à un TOPOGRAPHIC PLACE.. |
| «FK» | **_SiteElementRef_** | _SiteElementRef_ | 0:1 | Référence à un SITE ELEMENT, tel que PARKING, PARKING AREA, PARKING BAP, STOP PLACE, QUAY, POINT OF INTEREST, etc. |

Table 36 - **VehicleMeetingPlace**

###### **Vehicle Service Place Assignment**

Affectation d'un dock à un MOBILITY SERVICE

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _Assignment_ | ::> | VEHICLE SERVICE PLACE ASSIGNMENT inherits from ASSIGNMENT. |
| «PK» | **_id_** | _VehicleServicePlaceAssignmentIdType_ | 1:1 | Identifier of TAXI SERVICE PLACE ASSIGNMENT. |

Table 37 - VehicleServicePlaceAssignment - Element

###### **VehicleSharingPlaceAssignment**

The allocation of a VEHICLE SHARING PARKING AREA to any vehicle sharing or rental service.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _VehicleServicePlaceAssignment_ | ::> | VEHICLE SHARING PLACE ASSIGNMENT inherits from VEHICLE SERVICE PLACE ASSIGNMENT. |
| «PK» | **_id_** | _VehicleSharingPlaceAssignmentIdType_ | 1:1 | Identifier of VEHICLE SHARING PLACE ASSIGNMENT. |
| «cntd» | **_VehicleCommonServiceRef_** | _VehicleSharingServiceRef_ \| _VehicleRentalServiceRef_ | 0:\* | Reference to a VEHICLE SHARING SERVICE or a VEHICLE RENTAL SERVICE. |
| «FK» | **_VehicleSharingParkingAreaRef_** | _VehicleSharingParkingAreaRef_ | 1:1 | Reference to a VEHICLE SHARING PARKING AREA.. |
| «FK» | **_VehicleSharingParkingBayRef_** | _ParkingBayRef_ | 1:1 | Reference to a VEHICLE SHARING PARKING BAY. |

Table 38 - VehicleSharingPlaceAssignment - Element

##### Exemple XML VehicleSharingParkingArea

Le fragment de code suivant montre un **stationnement** pour une **station de vélos en libre-service** avec **10 emplacements** :

Exemple xml 5 : Zone de Stationnement pour véhicule partagé

#### Disponibilité des véhicules des modes alternatifs

##### Modèle conceptuel

Le MODÈLE d'information sur la disponibilité des véhicules décrit la disponibilité prévue des véhicules pour un SERVICE DE MOBILITÉ particulier, exploité à un emplacement topographique particulier. La disponibilité prévue correspond à la présence potentielle de véhicules stationnés à un emplacement et correspond généralement à la capacité des PARKINGS et de leurs composants dédiés aux différents services.

Ces informations peuvent être globales, concernant la capacité de l'ensemble du PARKING, ou indiquer la capacité des ZONES DE STATIONNEMENT par TYPE DE VÉHICULE. Il convient toutefois de noter que, pour équilibrer l'offre et la demande dans les gares très fréquentées, les opérateurs proposent parfois un service de personnel pour fournir ou retirer les véhicules supplémentaires d'un dépôt fixe ou de les placer sur des véhicules mobiles. Cela signifie que la capacité « virtuelle » d'un PARKING peut être supérieure au nombre de places physiques.

Figure 15 : Disponibilité prévue des véhicules - MC

##### Modèle de données

###### ParkingAreaCapacityAssignement

L'Affectation de la capacité d'une aire de stationnement permet l'Attribution d'un nombre de places pour un type de véhicule particulier dans une aire de stationnement.

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _Assignment_ | ::> | PARKING AREA CAPACITY ASSIGNMENT hérite de ASSIGNMENT. |
| «PK» | **_id_** | _ParkingAreaCapacityAssignmentIdType_ | 1:1 | Identifiant du PARKING AREA CAPACITY ASSIGNMENT. |
| «FK» | **_TransportTypeRef_** | _TransportTypeRef_ | 0:1 | TRANSPORT TYPE associé au PARKING AREA CAPACITY. |
| «FK» | **_ParkingAreaRef_** | _ParkingAreaRef_ | 1:1 | PARKING AREA associé au PARKING AREA CAPACITY ASSIGNMENT. |
| «enum» | **_CapacityType_** | _ParkingCapacityTypeEnum_ | 1:1 | Type de capacité |
|     | **_NumberOfSpaces_** | _xsd:nonNegativeInteger_ | 0:1 | Nombre de place |
|     | **_AdditionalVehicleCapacity_** | _xsd:nonNegativeInteger_ | 0:1 | Nombre de places additionnelles qui peuvent être occupées par d'autres véhicules |

Table 39 - Capacité des stations

Note : Pour tout complément d'information se référer au profil France Parking.

#### Equipements de rechargement

##### Modèle conceptuel

La définition des équipements de rechargement pour les véhicules partagés électrique peut être rattachée à un emplacement de véhicule en station.

A noter que l'information d'existance de capacité de rechargement électrique est portée au niveau de la Station (Recharging Availability).

Figure 16 : Equipement de rechargement - MC

##### Modèle de données

Les **ZONES DE STATIONNEMENT POUR LE PARTAGE/CO-VOITURAGE DE VÉHICULES** peuvent être associées à des équipements spécifiques, tels que des bornes de recharge, etc.

L'emplacement des équipements est spécifié à l'aide d'un **EMPLACEMENT D'ÉQUIPEMENT**.

Les **COMPOSANTS DE STATIONNEMENT** particuliers et l'**EMPLACEMENT D'ÉQUIPEMENT** doivent faire référence au même **COMPOSANT DE SITE**

###### Vehicle charging Equipment (Equipement de rechargement des véhicules)

| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |
| --- | --- | --- | --- | --- |
| ::> | ::> | _PlaceEquipment_ | ::> | VEHICLE CHARGING EQUIPMENT hérite de PLACE EQUIPMENT |
| «PK» | **_id_** | _VehicleChargingEquipmentId_ | 1:1 | Identifiant VEHICLE CHARGING EQUIPMENT. |
|     | **_FreeRecharging_** | _xsd:boolean_ | 0:1 | Identique si le chargement est gratuit |
|     | **_Reservation_** | _xsd:boolean_ | 0:1 | Indique si une réservation est nécessaire |
|     | **_ReservationUrl_** | _xsd:anyURI_ | 0:1 | URL de réservation. |

Table 40 - Equipement de rechargement