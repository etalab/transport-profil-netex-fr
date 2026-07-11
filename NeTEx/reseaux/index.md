---
title: "NeTEx - Profil France v2.4 - Description des réseaux"
date: 2025-12-191T11:05:00+00:00
draft: false
tags: ["NeTEx"]
autonumbering: true
weight: 3
---

**Avant-propos**

L’harmonisation des pratiques dans l’échange des données relatives aux
offres de transport est essentielle :

- pour l’usager, aux fins d’une présentation homogène et
  compréhensible de l’offre de transport et de l’engagement
  sous-jacent des organisateurs (autorités organisatrices et
  opérateurs de transports) ;

- pour les AOT, de manière à fédérer des informations homogènes venant
  de chacun des opérateurs de transports qui travaillent pour elle.
  L’harmonisation des échanges, et en particulier le présent profil,
  pourra le cas échéant être imposée par voie contractuelle. Cette
  homogénéité des formats d’information permet d’envisager la mise en
  place de systèmes d’information multimodaux, produisant une
  information globale de l’offre de transports sur un secteur donné,
  et garantir le fonctionnement des services d’information, en
  particulier des calculateurs d’itinéraires, et la cohérence des
  résultats, que ces services soient directement intégrés dans ces
  systèmes d’information multimodaux ou qu’ils puisent leurs
  informations sur des bases de données réparties ;

- pour les opérateurs, qui pourront utiliser ce format d’échange pour
  leurs systèmes de planification, les systèmes d’aide à
  l’exploitation, leurs systèmes billettiques et leurs systèmes
  d’information voyageur (information planifiée et information temps
  réel)

- pour les industriels et développeurs pour pérenniser et fiabiliser
  leurs investissements sur les formats d’échanges implémentés par les
  systèmes qu’ils réalisent, tout en limitant fortement l’effort de
  spécification lié aux formats d’échange

Ce document est le fruit de la collaboration entre les différents
partenaires des autorités organisatrices de transports, opérateurs,
industriels et développeurs de solutions et de systèmes informatiques
ayant pour objet l’aide à l’exploitation du transport public et
l’information des voyageurs. Il a pour objet de présenter le profil
d’échange Profil NeTEx Réseaux: "format de référence pour l'échange de
données de description des réseaux de transport en commun" (issu des
travaux *NeTEx, Transmodel et IFOPT)* qui aujourd’hui fait consensus
dans les groupes de normalisation (CN03/GT7 – Transport public /
information voyageur).

Ce document a été validé et publié comme suit :

- travaux de révision : 2024-2025
- date de validation en CN03 : 19 décembre 2025
- date de publication : 6 mars 2026

**Introduction**

Le présent document fait partie du profil France de NeTEx.

NeTEx (CEN/TS 16614 series) propose un format et des
services d'échange de données de description de l'offre de transport
planifiée, basé sur Transmodel (EN 12896 series) et l’ancienne norme IFOPT (EN
28701). NeTEx permet non seulement d'assurer les échanges pour les
systèmes d'information voyageur mais traite aussi de l’ensemble des
concepts nécessaires en entrée et sortie des systèmes de planification
de l'offre (graphiquage, etc.) et des SAE (Systèmes d’Aide à
l’Exploitation).

NeTEx se décompose en six parties:

- Partie 1 : topologie des réseaux (les réseaux, les lignes, les
  parcours commerciaux les missions commerciales, les arrêts et lieux
  d’arrêts, les correspondances et les éléments géographiques en se
  limitant au strict minimum pour l’information voyageur)

- Partie 2 : horaires théoriques (les courses commerciales, les heures
  de passage graphiquées, les jours types associés ainsi que les
  versions des horaires)

- Partie 3 : information tarifaire (uniquement à vocation
  d’information voyageur)

- Partie 4 : profil européen pour l'information voyageur (EPIP)

- Partie 5: nouveaux modes (les véhicules partagés en libre service, les courses
  partagées, etc.)

- Partie 6: profil européen pour l'information voyageur en lien avec
  l'accessibilité (EPIAP)

NeTEx a été développé dans le cadre du CEN/TC278/WG3/SG9 piloté par la France.
Les premières publications de NeTEx datent de 2014 et les plus récentes de mars
2026.

Il faut noter que NeTEx a été l'occasion de renforcer les liens du
CEN/TC278/WG3 avec le secteur ferrovaire, en particulier grâce à la
participation de l'ERA (Agence Européen du Rail, qui a intégré NeTEx
dans la directive Européenne 454/2011 TAP-TSI ) et de l'UIC (Union
International des Chemins de fer).

Les normes, dans leur définition même, sont des « documents établis par
consensus ». Celles du CEN/TC278 sont de plus établies à un niveau
européen, en prenant donc en compte des exigences qui dépassent souvent
le périmètre national.

Il en résulte des normes qui sont relativement volumineuses et dont le
périmètre dépasse souvent largement les besoins d'une utilisation
donnée. Ainsi, à titre d'exemple, SIRI propose toute une série d'options
ou de mécanismes dont la vocation est d'assurer la compatibilité avec
les systèmes développés en Allemagne dans le contexte des VDV 453/454.
De même, SIRI propose des services dédiés à la gestion des
correspondances garanties, services qui, s'ils sont dès aujourd'hui
pertinents en Suisse ou en Allemagne, sont pratiquement inexistants en
France.

De plus, un certain nombre de spécificités locales ou nationales peuvent
amener à préciser l'usage ou la codification qui sera utilisée pour
certaines informations. Par exemple, les Anglais disposant d'un
référentiel national d'identification des points d'arrêts (NaPTAN), ils
imposeront naturellement que cette codification soit utilisée dans les
échanges SIRI, ce que ne feront pas les autres pays européens.

Enfin, certains éléments proposés par ces normes sont facultatifs et il
convient, lors d'une implémentation, de décider si ces éléments seront
ou non implémentés.

L'utilisation des normes liées à l'implémentation de l'interopérabilité
pour le transport en commun passe donc systématiquement par la
définition d'un profil (local agreement, en anglais). Concrètement, le
profil est un document complémentaire à la norme et qui en précise les
règles de mise en œuvre dans un contexte donné. Le profil contient donc
des informations comme :

- détail des services utilisés,

- détails des objets utilisés dans un échange,

- précisions sur les options proposées par la norme,

- précision sur les éléments facultatifs,

- précision sur les codifications à utiliser,

- etc.

Ce document présente la partie Réseaux du profil France de NeTEx, tel que défini
par le Groupe de Travail dédié à l'information voyageur et à l'exploitation des
services de mobilité (GT7) au sein de la Commission Nationale de normalisation
pour le transport public (CN03).

D'autres parties du profil France de NeTEx sont disponibles (arrêts, horaire,
tarif, accessibilité, parking). Ils sont tous complémentaires les uns des autres
(sans recouvrement) et s'appuient tous sur le document:
**NeTEx - Profil France - Éléments communs.** Il conviendra de se référer à ce
document pour tous les éléments utilisés dans le présent document, et dont la
structure n'est pas détaillée.

Ce profil d’échange a pour objectif de décrire et de structurer
précisément les éléments nécessaires à une bonne information de
description des réseaux de transport public de façon :

- à pouvoir les présenter d’une manière homogène et compréhensible à
  l’usager des transports publics sur des supports différents (papier
  ou Internet),

- à pouvoir les échanger entre systèmes d’information (systèmes
  d’information voyageurs et systèmes d’information multimodale,
  systèmes d’aide à l’exploitation, systèmes de planification,
  systèmes billettiques, etc.).

Les éléments présentés ci-dessous couvrent donc l’ensemble des concepts
propres à la description des réseaux.

**NOTE IMPORTANTE** Ce document étant un profil d'échange de NeTEx, il
ne se substitue en aucun cas à NeTEx, et un minimum de connaissance de
NeTEx sera nécessaire à sa bonne compréhension.

# Domaine d'application

Le présent document est un profil de la CEN/TS 16614 (NeTEx) pour
l'échange de données de description des réseaux en France et permet de
décrire les réseaux de transports publics et la manière dont ils
pourront être structurés pour des échanges entre systèmes d'information
ainsi que pour leur présentation aux voyageurs.

C'est la structure du réseau lui-même (sa structure, ses attributs et sa
géographie) qui est prise en compte dans ce contexte, et non son
insertion dans le contexte des services de transport (pas de références
aux horaires, etc.).

# Références normatives

Les documents de référence suivants sont indispensables pour
l'application du présent document. Pour les références datées, seule
l'édition citée s'applique. Pour les références non datées, la dernière
édition du document de référence s'applique (y compris les éventuels
amendements).

CEN/TS 16614-1, Network and Timetable Exchange (NeTEx) — Part 1: Public
transport network topology exchange format

CEN/TS 16614-2, Network and Timetable Exchange (NeTEx) — Part 2: Public
transport scheduled timetables exchange format

EN 12896, Road transport and traffic telematics - Public transport -
Reference data model (Transmodel)

# Termes et définitions

Pour les besoins du présent document, les termes et définitions suivants
s'appliquent. Ils sont directement issus de Transmodel et NeTEx.
L'Error: Reference source not found complète ces définitions par des
explication plus détaillées. Pour une information complète, il
conviendra toutefois de se référer au document normatif.

NOTE Les termes spécifiquement introduits par le profil d’arrêt sont
signalés par le mot *(profil)*, en italique et entre parenthèses. Les
définitions ci-dessous sont des traductions littérales du document
normatif.

NOTE Les définitions ci-dessus sont des traductions littérales du
document CEN.

## **ACCESS MODE** (MODE D’ACCÉS)

Caractérisation de déplacement d’un passager relatif à son mode de
transport en dehors des transports public (piéton, vélo, etc.).

## **AUTHORITY** (AUTORITÉ ORGANISATRICE)

INSTITUTION sous la responsabilité de laquelle l’organisation des
transports est placée pour une zone géographique ou administrative
donnée.

## **BOARDING POSITION** (POSITION D’EMBARQUEMENT)

Position d’une ZONE D’EMBARQUEMENT à partir de laquelle un passager
pourra embarquer, ou vers laquelle il débarquera d’un VÉHICULE

Note: cet objet n’a pas été retenu dans le Modèle d’Arrêt Partagé, mais
il s’y raccroche directement et est donc à considérer comme une
extension du Modèle d’Arrêt Partagé)

## **BOOKING ARRANGEMENT** (CONDITIONS DE RESERVATION)

CONDITIONS DE RÉSERVATION pour une LIGNE FLEXIBLE.

## **COMPOUND TRAIN** (TRAIN COMPOSÉ)

TYPE DE VEHICULE composé d’une séquence d’un ou plusieurs TRAIN.

## **CONNECTION** (CORRESPONDANCE)

Possibilité physique (spatiale) d'un passager de passer d'un véhicule de
transport public vers un autre dans le but de continuer son voyage. Des
temps de parcours différents peuvent être nécessaires en fonction du
type de passager.

## **CONNECTION END** (EXTRÉMITÉ DE CORRESPONDANCE)

Début ou fin d'une CORRESPONDANCE. Il s’agit forcément d’une relation
avec un POINT D’ARRÊT PLANIFIÉ.

## **CONTACT DETAILS** (INFORMATIONS DE CONTACT)

Informations permettant au public de contacter une INSTITUTION.

## **CONTROL CENTRE** (CENTRE DE CONTROL)

UNITÉ ORGANISATIONNELLE composée d’une équipe opérationnelle en charge
des commandes et du contrôle des services d’exploitation.

## **DEAD RUN** (HAUT LE PIED)

PARCOURS associé à un HAUT LE PIED (sans transport des passagers :
retour dépôt, jonction entre ligne, etc.).

## **DEFAULT CONNECTION** (CORRESPONDACE PAR DEFAUT)

Possibilité physique (spatiale) d'un passager de passer d'un véhicule de
transport public vers un autre dans le but de continuer son voyage. Elle
définit le temps par défaut à utiliser pour passer d'un véhicule de
transport à un autre au sein d'une zone (SITE, LIEU TOPOGRAPHIQUE, ZONE
D'ARRÊT). Elle peut être restreinte à des OPERATEURS ou des MODES des
transports particuliers, ou ne s'applique que dans un sens donné (une
correspondance bus vers train peut être différente de train vers bus).

## **DESTINATION DISPLAY** (DESTINATION AFFICHÉE)

Une destination d'un PARCOURS (ou ITINÉRAIRE) particulier, affichée au
public en général sur une girouette ou sur tout autre afficheur
embarqué. Cette information peut évoluer au fur et à mesure de
l'évolution de la course et, en particulier, être mise à jour lors du
franchissement des points VIA.

## **DESTINATION DISPLAY VARIANT** (VARIANTE DE DESTINATION AFFICHÉE)

alternative à la DESTINATION AFFICHÉE, généralement destiné à des média
spécifiques (SMS, type d’afficheur particulier, etc.)

## **DIRECTION** (SENS)

Classification de l'orientation générale des ITINÉRAIREs.

## **FLEXIBLE LINE** (LIGNE FLEXIBLE)

Spécialisation de la LIGNE pour décrire les services flexibles. Tous les
services d'une LIGNE peuvent ne pas être flexibles, la flexibilité
elle-même étant alors décrite au niveau du PARCOURS (cela signifie aussi
qu'il faudra définir des parcours spécifiques pour chaque type de
flexibilité de la LIGNE).

## **FLEXIBLE LINK PROPERTIES** (PROPRIÉTÉ DE TRONÇON FLEXIBLE)

Ensemble de caractéristiques décrivant les éventuelles flexibilités
associées à un lien

Note: la relation est établie par composition pour limiter le recours à
l'héritage multiple.

## **FLEXIBLE POINT PROPERTIES** (PROPRIÉTÉ DE POINT FLEXIBLE)

Ensemble de caractéristiques décrivant les éventuelles flexibilités
associées à un point

Note: la relation est établie par composition pour limiter le recours à
l'héritage multiple.

## **FLEXIBLE ROUTE** (ITINERAIRE FLEXIBLE)

Spécialisation de l'ITINÉRAIRE pour décrire les services flexibles. Il
peut inclure des POINTs et des ZONEs, et des sections parcourues dans un
ordre prédéfini ou non.

## **FLEXIBLE STOP PLACE** (LIEU D’ARRÊT FLEXIBLE)

Spécialisation du LIEU D’ARRÊT décrivant un arrêt d'un service flexible.
Il peut être composé de zones flexibles ou de zones de type « hail and
ride » identifiant les zones de montée ou descente possible des services
flexibles (quand ils utilisent des zones ou des quais flexibles).
Certains services flexibles utilisent aussi des LIEUx D’ARRÊT classiques
pour leurs arrêts. Quand il est assigné à un POINT D'ARRÊT PLANIFIÉ, ce
POINT D'ARRÊT PLANIFIÉ est alors censé être une zone (le centroïd de la
ZONE étant alors considéré comme le POINT D'ARRÊT PLANIFIÉ).

## **GROUP OF LINES** (GROUPE DE LIGNES)

Regroupement de lignes référencées de manière commune relative à un
objectif donné.

## **GROUP OF OPERATOR** (GROUPE D’EXPLOITANTS)

Groupe d’EXPLOITANTs ayant en commun, par exemple, un ensemble de règles
tarifaires et d’information voyageur.

## **JOURNEY PATTERN** (PARCOURS)

Liste ordonnée de POINTs D'ARRÊT PLANIFIÉs et de POINTs HORAIREs sur un
unique ITINÉRAIRE, décrivant le plan de déplacement pour les véhicules
de transport public. Un PARCOURS peut passer par le même POINT plus
d'une fois. Le premier point d'un PARCOURS est l'origine. Le dernier
point est la destination.

## **LINE** (LIGNE)

Groupe d'ITINÉRAIREs (voir plus bas) qui est en général connu du public
par une appellation commune (nom ou numéro, extrémités de ligne, etc.).

## **NETWORK** (RÉSEAU)

Un GROUPE DE LIGNES disposant d'un nom sous lequel un réseau de
transport est connu.

## **OPERATOR** (EXPLOITANT)

Entreprise offrant des services de transport public.

## **PASSENGER STOP ASSIGNMENT** (AFFECTATION D’ARRÊT POUR PASSAGER)

Affection d’un POINT D’ARRÊT PLANIFIÉ à un LIEU D’ARRÊT (ou un de ses
composant de type ZONE D’EMBARQUEMENT ou POSITION D’EMBARQUEMENT) pour
un service passager.

## **POINT IN JOURNEY PATTERN** (POINT SUR PARCOURS)

Un POINT D'ARRÊT PLANIFIÉ ou un POINT HORAIRE dans un PARCOURS indiquant
son rang dans ce PARCOURS.

## **POINT IN TIMING PATTERN** (POINT SUR PARCOURS HORAIRE)

POINT sur PARCOURS qui est un POINT HORAIRE.

## **POINT ON ROUTE** (POINT SUR ITINÉRAIRE)

POINT D'ITINÉRAIRE (accompagné de son rang) qui sert à définir un
ITINÉRAIRE.

## **ROUTE LINK** (TRONÇON D'ITINÉRAIRE)

Tronçon orienté entre deux POINTs D'ITINÉRAIRE permettant une définition
univoque d'un chemin à travers le réseau.

## **ROUTE POINT** (POINT D'ITINÉRAIRE)

POINT permettant de définir la géométrie d'un ITINÉRAIRE à travers le
réseau.

## **ROUTE** (ITINÉRAIRE)

Liste ordonnée de POINTs définissant un seul chemin à travers le réseau
routier (ou ferré). Un ITINÉRAIRE peut passer deux fois par un même
POINT.

## **ROUTING CONSTRAINT ZONE** (ZONE DE CONTRAINTE)

ZONE au sein de laquelle une contrainte d'acheminement s'applique. La
ZONE peut être définie soit par un périmètre géographique, soit par la
liste des POINTs D'ARRÊT PLANIFIÉS qu'elle contient.

## **SCHEDULED STOP POINT** (POINT D'ARRÊT PLANIFIÉ)

POINT où les passagers peuvent monter à bord ou descendre des véhicules.

## **SCHEMATIC MAP** (PLAN SCHÉMATIQUE)

Carte représentant schématiquement la disposition de la structure
topographique des lieux (par exemple, un ensemble de sites) ou le réseau
de transports en commun (un ensemble de lignes). Il peut comprendre une
projection de pixel ou objet de dessin vectoriel vers un ensemble
d'objet transport pour permettre les interactions, services et
hyperliens.

## **SCHEMATIC MAP MEMBER** (COMPOSANT DE PLAN SCHÉMATIQUE)

Projection d’un objet transport sur un PLAN SCHÉMATIQUE.

## **SERVICE JOURNEY PATTERN** (PARCOURS COMMERCIAL)

PARCOURS associé à une COURSE COMMERCIALE (transportant des passagers).

## **SERVICE LINK** (TRONÇON COMMERCIAL)

TRONÇON entre une paire ordonnée de POINTs D'ARRÊT PLANIFIÉS.

## **SERVICE PATTERN** (MISSION COMMERCIALE)

Vue d'un PARCOURS définie uniquement par des POINTs D'ARRÊT SUR
PARCOURS. La MISSION COMMERCIALE se distingue du PARCOURS COMMERCIAL par
le fait qu'elle n'est définie que par une séquence d'arrêts, sans point
intermédiaire.

## **SITE CONNECTION** (CORRESPONDANCE ENTRE SITES)

La possibilité physique (spatiale) d'un passager de continuer son
déplacement déterminé par deux localisations comme des SITEs ou leurs
ENTRÉEs. Des temps de parcours différents peuvent être nécessaires en
fonction du type de passager.

## **STOP ASSIGNMENT** (AFFECTATION D’ARRÊT)

Affection d’un POINT D’ARRÊT PLANIFIÉ à un LIEU D’ARRÊT.

## **STOP POINT IN JOURNEY PATTERN** (POINT D'ARRÊT SUR PARCOURS)

POINT d'un PARCOURS qui est un POINT D'ARRÊT

## **SUBMODE** (SOUS-MODE)

Précision sur le MODE, comme "international" ou "longue distance" (pour
un MODE Rail par exemple). Le SOUS-MODE caractérise très souvent un type
d'exploitation qui vient donc compléter le MODE.

## **TIMING LINK** (TRONÇON HORAIRE)

Paire ordonnée de POINTs HORAIREs qui peut être utilisée pour
l'enregistrement des temps de parcours.

## **TIMING PATTERN** (PARCOURS HORAIRE)

Vue d'un PARCOURS définie uniquement par des POINTs HORAIRE SUR
PARCOURS.

## **TIMING POINT** (POINT HORAIRE)

POINT servant de référence aux données nécessaires à la conception des
horaires. Un POINT HORAIRE peut aussi être un POINT D’ARRÊT PLANIFIÉ
mais cela n’a rien d’obligatoire ou de systématique.

## **TRAIN STOP ASSIGNMENT** (AFFECTATION D’ARRÊT DE TRAIN)

Affection d’un COMPOSANT DE TRAIN à un LIEU D’ARRÊT (ou un de ses
composant de type ZONE D’EMBARQUEMENT ou POSITION D’EMBARQUEMENT) pour
un POINT D’ARRÊT PLANIFIÉ donné.

## **TRANSFER RESTRICTION** (RESTRICTION DE CORRESPONDANCE)

Contrainte qui s’applique aux CORRESPONDANCES (ou CORRESPONDANCES ENTRE
COURSES) entre deux POINTs D’ARRÊT PLANIFIÉs, en limitant voir
interdisant l’usage pour les passagers.

## **TYPE OF LINES** (TYPE DE LIGNES)

Classification pour les lignes

## **VEHICLE MODE** (MODE DE VÉHICULE)

Typologie de l'exploitation suivant le moyen de transport (bus, tramway,
métro, train, ferry, bateau).

## **VIA** (VIA)

POINT utilisé comme POINT D'ITINÉRAIRE et permettant de distinguer deux
cheminements (ITINÉRAIREs) entre une origine et une destination. Il est
généralement défini à des fins d'information voyageur pour par exemple
différentier deux itinéraires sur un afficheur du réseau, ou encore sur
un système de vente.

# Symboles et abréviations

AO

<div class="Definition">

Autorité Organisatrice de Transports

</div>

PMR

<div class="Definition">

Personne à Mobilité Réduite

</div>

# Exigences minimales liées au code des transports et la règlementation européenne

La mise à disposition des données, quand elles existent, est obligatoire et se
conforme aux exigences:

- Au niveau européen, du règlement délégué (UE) 2017/1926 de la Commission du 31
  mai 2017 modifié par le règlement délégué (UE) 2024/490 de la Commission du 29
  novembre 2023 (<https://eur-lex.europa.eu/eli/reg_del/2017/1926/2024-03-04>),
  dit "règlement MMTIS";
- Au niveau français, des articles L. 1115-1 à L. 1115-7, D. 1115-1, R. 1115-2 à
  R. 1115-8 et D. 1115-9 à D. 1115-11 du code du transports, notamment créés ou
  modifiés par les articles 25 et 27 de loi n° 2019-1428 du 24 décembre 2019
  d’orientation des mobilités, dites loi « LOM ». Ces mêmes articles de la LOM
  précise le calendrier de mise à disposition des données.

Le tableau ci-dessous résulte de l’analyse du code des transports et du
règlement MMTIS et fournit la liste des concepts concernés dans le présent
profil correspondant aux données mentionnées dans l’annexe du règlement. Il sera
donc nécessaire de fournir ces données pour être conforme au cadre réglementaire
(il s’agit bien de mettre à disposition toutes les données existantes dans les
SI transport, et non de créer des données qui n’existeraient pas encore sous
forme informatique).

Notez que beaucoup de concepts dépendent des concepts issus de Transmodel/NeTEx
et sont liés entre eux, soit par héritage, soit par relation au sens UML des
termes. Par ailleurs, certains concepts additionnels peuvent relever d’autres
parties du profil France, précisés dans le tableau le cas échéant.

De plus, les noms des catégories (colonnes Catégorie et Détail) ont été
conservés dans la langue originale du document (l’anglais) pour éviter
tout risque de confusion. Pour la même raison, les noms des concepts
concernés sont ceux de la version originale de Transmodel.

Pour certaines catégories de données, il peut arriver que les concepts
correspondants soient multiples, mais aussi qu’ils soient différents
suivant le niveau de précision porté par la donnée. La colonne
« Concepts à minima » correspond alors au minimum à fournir pour
répondre à la catégorie en question et les colonnes « Autres concepts »
décrit des informations complémentaires qui, si elles sont utiles, ne
sont pas indispensables pour répondre à cette catégorie (notez que dans
certains cas, ces concepts additionnels peuvent relever d’autres
profils : ceci est précisé dans le tableau quand c’est le cas). Il faut
toutefois garder à l’esprit que toute information existante est supposée
être mise à disposition (que cela relève de la première ou de la seconde
colonne).

La première colonne reprend la notion de *niveau* tel qu’il est décrit
et utilisé par le règlement européen et a notamment une incidence sur le
calendrier de mise à disposition de la donnée (voir le règlement pour
plus de détails).

Les différents concepts présentés ne sont bien sûr pas détaillés dans ce
tableau, mais dans le profil lui-même. C’est aussi dans la description
du profil que l’on trouvera les détails concernant les attributs
(obligatoire/facultatif, règles de remplissage, codification, etc.).
Pour ce qui est des attributs facultatifs, la règle reste que, pour les
objets ci-dessous, toute information disponible est supposée être
fournie (mais on ne crée pas d’information si elle n’est pas
disponible).

<div class="table-title">Concepts relatifs à la LOM et à la Règlementation Européenne</div>

| Niveau | Catégorie                                                   | Détail                                                                                                                          | Concepts à minima                                                                                                                           | Autres concepts                                                                                                                                                    | Commentaire                                                                                                                                                                                                                                |
| ------ | ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1      | ***Location search (origin/ destination)***                 | Points of interest (related to transport information) to which people may wish to travel                                        | **POI**                                                                                                                                     |                                                                                                                                                                    | Même si le transport en commun n'est probablement pas la meilleure source pour les POI, NeTEx reste néanmoins en mesure de les décrire.                                                                                                    |
| 1      | ***Trip plan computation — scheduled modes transport***     | Connection links where interchanges may be made, default transfer times between modes at interchanges                           | **DEFAUT CONNECTION**                                                                                                                       | <p>**CONNECTION**<br>**SITE CONNECTION**</p><p>*(profil horaire)*</p><p>**INTERCHANGE**</p>                                                                        | <p>DEFAUT CONNECTION peut être utilisé à la place de CONNECTION quand l'information détaillée n'est pas disponible.</p><p>L’INTERCHANGE décrit la correspondance entre deux courses et est, à ce titre, décrit dans le Profil Horaire.</p> |
| 1      | ***Trip plan computation — scheduled modes transport***     | Network topology and routes/lines (topology)                                                                                    | **LINE**<br>**SERVICE PATERN**<br>**SCHEDULED STOP POINT**                                                                                  | <p>**ROUTE**</p><p>**ROUTE POINT**<br>**ROUTE LINK**<br>**SERVICE LINK**<br>**POINT IN JOURNEY PATTERN**<br>**DESTINATION DISPLAY**</p>                            |                                                                                                                                                                                                                                            |
| 2      | ***Trip plans, auxiliary information, availability check*** | Basic common standard fares (all scheduled modes): Fare network data (fare zones/stops and fare stages)                         | **TARIFF ZONE**                                                                                                                             | <p>*(profil tarif)*</p><p>**FARE ZONE**</p><p>**FARE PRODUCT**<br>**SALES OFFER PACKAGE**<br>**DISTRIBUTION CHANNEL**<br>**ACCESS RIGHT PARAMETER ASSIGNMENT**</p> |                                                                                                                                                                                                                                            |
| 3      | ***Trip plans***                                            | Parameters needed to calculate an environmental factor such as carbon per vehicle type or passenger mile or per distance walked | <p>**VEHICLE TYPE**<br>**CONNECTION** *et* **SITE CONNECTION**</p><p>**ROUTE LINK** *(donc ROUTE) ou* **SERVICE LINK** *en alternative*</p> | <p>*(partie accessibilité)*</p><p>**NAVIGATION PATH**</p>                                                                                                          | Les SERVICE LINKs ou ROUTE LINKs impliquent naturellement les POINTs (POINT IN JOURNEY PATTERN, ROUTE POINT, POINT ON ROUTE, etc.) correspondant. Ils permettront d’évaluer la distance parcourue par le véhicule.                         |

# Description du profil d’échange

## Conventions de représentation

### Tableaux d’attributs

NOTE les choix de conventions présentées ici ont pour vocation d'être
cohérents avec ceux réalisés dans le cadre du profil SIRI (IDFM et
CEREMA). De plus tous les profils NeTEx partagent les mêmes conventions.

Les messages constituant ce profil d'échange sont décrits ci-dessous
selon un double formalisme: une description sous forme de diagrammes XSD
(leur compréhension nécessite une connaissance préalable de XSD: XML
Schema Definition) et une description sous forme tabulaire. Les tableaux
proposent ces colonnes:

|                    |         |          |                 |                 |
| ------------------ | ------- | -------- | --------------- | --------------- |
| **Classification** | **Nom** | **Type** | **Cardinalité** | **Description** |

- **Classification** : permet de catégoriser l'attribut. Les
  principales catégories sont:

  - PK (Public Key) que l'on peut interpréter comme Identifiant
    Unique: il permet à lui seul d'identifier l'objet, de façon
    unique, pérenne et non ambiguë. C'est l'identifiant qui sera
    utilisé pour référencer l'objet dans les relations.

  - AK (Alternate Key) est un identifiant secondaire, généralement
    utilisé pour la communication, mais qui ne sera pas utilisé dans
    les relations.

  - FK (Foreign Key) indique que l'attribut contient l'identifiant
    unique (PK) d'un autre objet avec lequel il est en relation.

  - GROUP est un groupe XML nommé (ensemble d'attributs utilisables
    dans différents contextes) (cf:
    <http://www.w3.org/TR/2001/REC-xmlschema-0-20010502/#AttrGroups>
    )

- **Nom** : nom de l'élément ou attribut XSD

- **Type** : type de l'élément ou attribut XSD (pour certains d'entre
  eux, il conviendra de se référer à la XSD NeTEx)

- **Cardinalité** : cardinalité de l'élément ou attribut XSD exprimée
  sous la forme "***minimum:maximum***" ("0:1" pour au plus une
  occurrence; "1:\*" au moins une occurrence et sans limites de nombre
  maximal; "1:1" une et une seule occurrence; etc.).

- Description : texte de description de l'élément ou attribut XSD
  (seul les attributs retenus par le profil ont un texte en français;
  les textes surlignés en jaune indiquent une spécificité du profil
  par rapport à NeTEx).

Les textes surlignés en <mark>Jaune</mark> sont ceux
présentant une particularité (spécialisation) par rapport à NeTEx: une
codification particulière, une restriction d'usage, etc.

La description XSD utilisée est strictement celle de NeTEx, sans aucune
modification (ceci explique notamment que tous les commentaires soient
en anglais).

Les attributs et éléments rendus obligatoires dans le cadre de ce profil
restent facultatifs dans l'XSD (le contrôle de cardinalité devra donc
être réalisé applicativement).

### Valeurs de code de profil

Dans la mesure du possible, le profil sélectionne les valeurs de code à
utiliser pour caractériser des éléments et les limite à un ensemble de
valeurs documentées. NETEX propose plusieurs mécanismes différents pour
spécifier les valeurs de code autorisées :

- Des énumérations fixes définies dans le cadre du schéma XSD NeTEx.
  Le profil impose alors un sous-ensemble des codes NeTEx.

- Des spécialisations de TYPE OF VALUE, utilisées pour définir des
  ensembles de codes ouverts pouvant être ajoutés au fil du temps sans
  modifier le schéma, par exemple, pour enregistrer des
  classifications d'entités héritées. Le profil lui-même utilise le
  mécanisme TYPE OF VALUE dans quelques cas pour spécifier des codes
  normalisés supplémentaires : ceux-ci sont affectés à un CODESPACE
  «FR_IV_metadata» (<https://netex-cen.eu/FR_IV>) indiqué par un préfixe
  «FR_IV». (par exemple, «FR_IV: monomodal».

- Des instances TypeOfFrame: le profil utilise plusieurs TYPES DE
  FRAME pour spécifier l'utilisation de VERSION FRAME dans le profil.

### Indication des classes abstraites

NeTEx, et Transmodel, utilisent largement l'héritage de classe; cela
simplifie considérablement la spécification en évitant les répétitions
puisque les attributs partagés sont déclarés par une superclasse et que
des sous-classes viennent ensuite les spécialiser sans avoir à répéter
ces attributs et en n’ajoutant que ceux qui lui sont spécifiques. La
plupart des superclasses sont «abstraites» - c’est-à-dire qu’il n’
existe aucune instance concrète; seules les sous-classes terminales sont
«concrètes».

Un inconvénient de l'héritage est que si l'on veut comprendre les
propriétés d'une classe concrète unique, il faut également examiner
toutes ses super-classes. Pour cette raison, le profil inclut les
classes abstraites nécessaires pour comprendre les classes concrètes,
même si ces classes concrètes ne sont jamais directement instanciées
dans un document NeTEx.

- Les super-classes sont signalées dans les en-têtes par le suffixe
  «*(abstrait)*»

- Dans les diagrammes UML (comme pour NeTEx et Transmodel), les noms
  des classes abstraites sont indiqués en italique et les classes
  abstraites sont de couleur gris clair.

- Certaines super-classes ne sont techniquement pas abstraites dans
  NeTEx, mais ne sont pas utilisées comme classes concrètes dans le
  profil : elles sont signalées avec la même convention que les
  classes abstraites.

### Classes de sous-composants

Un certain nombre de classes ont des sous-composants qui constituent
leur définition. Celles-ci fournissent des détails auxiliaires (par
exemple, AlternativeText, AlternativeName, TrainComponent) et sont
signalées dans les en-têtes par le suffixe « *(objet inclus)*».

## Structure du réseau

La topologie du réseau décrit les lignes et itinéraires permanent du
réseau de transport, ainsi que les éléments organisationnels qui y sont
rattachés.

![image](media/image1.svg)
*Structure du Réseau – Modèle conceptuel*

Transmodel définit une LIGNE comme un groupe d’ITINERAIREs (ROUTE) qui
est généralement connu du public sous un nom ou un numéro similaire. Ces
ITINERAIREs sont généralement très similaires d’un point de vue
topologique, c’est-à-dire des variantes d’un itinéraire principal avec
quelques écarts seulement sur certaines parties. Deux ITINERAIREs
utilisant la même d’infrastructure (ou des voies parallèles), mais avec
des DIRECTIONS opposées, appartiendront généralement à la même LIGNE.

Une LIGNE est associée à un MODE DE TRANSPORT principal et à un
SOUS-MODE, mais peut également avoir des modes secondaires (par exemple,
une ligne de train qui est exploitée par un bus à certaines heures de la
journée ou dans certaines circonstances).

Une LIGNE est également associée à un OPÉRATEUR principal ou à une
AUTORITÉ (plusieurs opérateurs secondaires sont également autorisés).

Les LIGNEs peuvent être regroupées en groupes de lignes à des fins
particulières, telles que l'harmonisation des tarifs, l'attribution de
types de jours ou pour regrouper certaines catégories de services (bus
de nuit, etc.).

## Les lignes

<div class="table-title">Line – Element</div>

|        | Name                                 | Type                             |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------ | ------------------------------------ | -------------------------------- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                                  | *DataManagedObject*              | ::> | LINE hérite de ***DataManagedObject*** <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|        | ***Name***                           | *MultilingualString*             | 1:1 | Nom de la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|        | ***ShortName***                      | *MultilingualString*             | 0:1 | Nom court de la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|        | ***Description***                    | *MultilingualString*             | 0:1 | Description de la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|        | ***TransportMode***                  | *VehicleModeEnum*                | 0:1 | MODE DE TRANSPORT principal de la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|        | ***TransportSubmode***               | *SubmodeEnum*                    | 0:1 | SOUS-MODE associé à la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|        | ***Url***                            | *any*                            | 0:1 | URL d'information voyageur associée à la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| «AK»   | ***PublicCode***                     | *xsd:normalizedString*           | 0:1 | <p>Identifiant publique de la LIGNE.</p><p><mark>Il s'agit généralement d'un numéro, parfois complété d'une lettre (par exemple 95, ou 27A, etc.). Les ***Name*** et ***ShortName*** porteront généralement une information plus explicite (par exemple la ligne ayant le ***PublicCode*** *95* à Paris s'appelle *"Porte de Vanves / Porte de Montmartre"*).</mark></p><p><mark>On peut considérer que le nom complet de la ligne est une concaténation de son ***PublicCode*** et de son ***Name***.</mark></p>                                                                                                                                                                                                                                                                                                                                                                         |
| «AK»   | ***PrivateCode***                    | *xsd:normalizedString*           | 0:1 | <p>Identifiant secondaire de la LIGNE.</p><p><mark>Il s'agit généralement d'un identifiant propre au fournisseur (transporteur) de l'information.</mark></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        | *Choice*                             |                                  |     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| «FK»   | a : ***AuthorityRef***               | *TransportOperatorRef*           | 0:1 | Réference une AUTORITE                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| «FK»   | b : ***OperatorRef***                | *OperatorRef*                    | 0:1 | Réference un EXPLOITANT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| «cntd» | ***additionalOperators***            | *OperatorRef*                    | 0:* | Réference un EXPLOITANT additionnel pour la LIGNE <mark>(comme pour les RER A et B à Paris, où encore les lignes en "pool")</mark>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|        | ***otherModes***                     | *modeRefs*                       |     | Réference un MODE de transport additionnel pour la LIGNE <mark>(certaines lignes SNCF sont parfois ponctuellement remplacées par des lignes de car par exemple)</mark>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|        | ***TypeOfLineRef***                  | *TypeOfLineRef*                  | 0:1 | <p>TYPE DE LIGNE spécifique.</p><p><mark>Permet une classification particulière de la ligne (ligne saisonnière, ligne de substitution, etc.).</mark></p><p><mark>Deux types prédéfinis sont proposé par le profil : SEASONAL_LINE_TYPE et REPLACEMENT_LINE_TYPE. Pour ce second type on utilisera, par convention, le derivedFromObjectRef (voir le document Profil NeTEx éléments communs) pour effectuer le lien avec la ligne à remplacer, et on renseignera le ValidityTrigger permettant de décrire dans quelle condition le remplacement est activé.</mark></p><p><mark>À ne pas confondre avec une marque commerciale, pour lequel l'attribut Branding est disponible dans le DataManagedObject (voir le document Profil NeTEx éléments communs).</mark></p><p><mark>A définir par un TYPE DE VALEUR spécifique *(voir le document **Profil NeTEx éléments communs**)*.</mark></p> |
|        | ***Monitored***                      | *xsd:boolean*                    | 0:1 | Indique si la ligne dispose d'information voyageur temps réel.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| «cntd» | ***routes***                         | *RouteRef*                       | 0:* | Liste des ITINERAIREs de la LIGNE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| «FK»   | ***<del>RepresentByGroupRef</del>*** |                                  |     | <mark>Le GROUPE DE LIGNES référence les LIGNES, mais on n'utilise pas la relation inverse dans le profil.</mark>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| «cntd» | ***Presentation***                   | *Presentation*                   | 0:1 | Information concernant la représentation graphique de la ligne (couleur, etc.).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|        | ***AccessibilityAssessment***        | *AccessibilityAssessment*        | 0:1 | Information concernant l'accessibilité de la ligne <mark>(voir la partie Accessibilité du profil France)</mark>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| «cntd» | ***allowedDirections***              | *AllowedDirection*               | 0:* | Ensemble des DIRECTIONs de la ligne (attention la DIRECTION est une indication d'ordre générale à ne pas confondre avec la DESTINATION qui est un arrêt terminus de la LIGNE).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|        | ***noticeAssignments***              | *noticeAssignments_RelStructure* | 0:* | <p>NOTEs affectées à la LIGNE.</p><p><mark>*(voir le document **Profil NeTEx éléments communs**).*</mark></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| «cntd» | ***documentLinks***                  | *InfoLinks*                      | 0:* | Document, typiquement PDF, associés à la ligne (généralement plan et horaires).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

### Directions

<div class="table-title">Direction – Element (objet inclus)</div>

| Classification | Name                       | Type                | Cardinalité | Description                                                                                                                                    |
| -------------- | -------------------------- | ------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>            | ::>                        | *TypeOfValue*       | ::>         | DIRECTION hérite de TYPE OF VALUE <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>.                                         |
|                | ***DirectionType***        | *DirectionTypeEnum* | 0:1         | Valeur fixe parmi : ‘*outbound’, ‘inbound’, ‘clockwise’, ‘anticlockwise’* (sortant, entrant, horaire, antihoraire) associée à cette DIRECTION. |
| «FK»           | ***OppositeDirectionRef*** | *DirectionRef*      | 0:1         | Référence à la DIRECTION correspondant au sens opposé.                                                                                         |

## Les groupes de Ligne

<div class="table-title">GroupOfLines – Element</div>

|        | Name                | Type              |     | Description                                                                                                                                                                                                                                                                                      |
| ------ | ------------------- | ----------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ::>    | ::>                 | *GroupOfEntities* | ::> | <p>GROUP OF LINEs hérite de GROUP OF ENTITies <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.</p><p><mark>L'attribut ***PurposeofGroupingRef*** pourra être utilisé pour qualifier les lignes administratives en utilisant la valeur ***"administrativeLine"***.</mark></p> |
| «cntd» | ***members***       | *LineRef*         | 0:* | Références à l'ensemble des LIGNEs du GROUPE DE LIGNES.                                                                                                                                                                                                                                          |
| «FK»   | ***MainLineRef***   | *LineRef*         | 0:1 | LIGNE principale du GROUPE DE LIGNES.                                                                                                                                                                                                                                                            |
|        | ***TransportMode*** | *VehicleModeEnum* | 0:1 | MODE DE TRANSPORT principal du GROUPE DE LIGNES.                                                                                                                                                                                                                                                 |

### Les réseaux

La notion de "réseau" correspond à un regroupement de lignes mis en avant sur le
terrain et visible des voyageurs. Par exemple pour des réseaux urbains, le
réseau TCL pour Lyon et les alentours, TBM pour le réseau de Bordeaux ou Bibus
pour le réseau urbain de Brest.

Cette notion de réseau n'est pas obligatoire, mais très fortement recommandée
pour des exports de structures de réseau ou d'offre horaires. De plus, pour
éviter des différences d'interprétation et de communication, une ligne ne peut
être référencée que par un seul réseau dans un export NeTEx France.

<div class="table-title">Network – Element</div>

| Classification | Name                           | Type                       | Cardinalité | Description                                                              |
| -------------- | ------------------------------ | -------------------------- | ----------- | ------------------------------------------------------------------------ |
| *::>*          | *::>*                          | *GroupOfLines*             | *::>*       | NETWORK hérite de GROUP OF LINEs                                         |
|                | ***TransportOrganisationRef*** | *OrganisationRefStructure* | 0:1         | INSTITUTION (autorité organisatrice ou transporteur) en charge du RÉSEAU |
|                | ***groupsOfLines***            | *groupsOfLinesInFrame*     | 0:\*        | GROUPE DE LIGNES faisant partie du RÉSEAU                                |
|                | ***tariffZones***              | *tariffZoneRefs*           | 0:\*        | ZONEs TARIFAIREs faisant partie du RÉSEAU                                |

Afin de permettre une description complète d'un réseau de transport, la notion
de groupe de lignes peut êgalement être utilisée en complément afin de regrouper
par exemple les lignes de nuit du réseau ou les "lignes fortes". Dans ce cas, la
ligne est référencée par le (ou les) groupe(s) de lignes dont elle fait partie
ET par le réseau global. **Recommandation**: une ligne ne devrait pas être
présente dans plus d'un groupe de lignes à la fois au sein du réseau sauf
situation particulière.

Exemple :

```xml
<Network id="sample-with-lines">
  <Name>Mon Réseau</Name>
  <members>
    <LineRef ref="L1" version="any"/>
    <LineRef ref="L2" version="any"/>
    <LineRef ref="L3" version="any"/>
  </members>
  <groupsOfLines>
    <GroupOfLinesRef ref="G1" version="any"/> 
    <GroupOfLinesRef ref="G2" version="any"/>
  </groupsOfLines>  
</Network>
<!-- avec le groupe de lignes G1 qui contient des références aux lignes L1 et L2, et le groupe de lignes G2 qui contient une référence à la ligne L3. -->
```

## Zone tarifaire

<div class="table-title">TariffZone – Element</div>

| Classification | Name | Type   | Cardinalité | Description                                                                                                                           |
| -------------- | ---- | ------ | ----------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| ::>            | ::>  | *Zone* | ::>         | TARIFF ZONE hérite de ZONE <mark>(*voir le document **Profil NeTEx éléments communs***)</mark> sans y apporter de nouveaux attributs. |

## Les itinéraires

<div class="table-title">Route – Element</div>

| Classification | Name                     | Type                  | Cardinalité | Description                                                                                                                                                 |
| -------------- | ------------------------ | --------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *::>*          | *::>*                    | *LinkSequence*        | *::>*       | ROUTE hérite de LINK SEQUENCE <mark>(voir le document **Profil NeTEx éléments communs***)</mark>.                                                           |
| «FK»           | ***LineRef***            | *LineRef*             | 0:1         | LIGNE à laquelle l'ITINÉRAIRE appartient.                                                                                                                   |
|                | ***DirectionType***      | *TypeOfDirectionEnum* | 0:1         | Type de direction de la ROUTE (***outbound***, ***inbound***, pour aller Retrour et éventuellement ***clockwise*** ou ***anticlockwise*** pour les boucles) |
| «FK»           | ***DirectionRef***       | *DirectionRef*        | 0:1         | Référence la DIRECTION de l'ITINÉRAIRE.                                                                                                                     |
| «cntd»         | ***pointsInSequence***   | *PointOnRoute*        | 2:\*        | Liste des points de l'ITINÉRAIRE.                                                                                                                           |
| «cntd»         | ***sectionsInSequence*** | *SectionLink*         | 0:\*        | Liste des sections de l'ITINÉRAIRE.                                                                                                                         |
|                | ***InverseRouteRef***    | *RouteRef*            | 0:1         | Référence l'éventuel ITINÉRAIRE en sens opposé.                                                                                                             |

### Les Points d'itinéraire

<div class="table-title">RoutePoint – Element</div>

| Classification | Name                 | Type          | Cardinalité | Description                                                                                      |
| -------------- | -------------------- | ------------- | ----------- | ------------------------------------------------------------------------------------------------ |
| *::>*          | *::>*                | *Point*       | *::>*       | ROUTE POINT hérite de POINT <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>. |
|                | ***BorderCrossing*** | *xsd:boolean* | 0:1         | Indique que le point est un point situé à la frontière entre deux pays.                          |

### Les points sur itinéraire

<div class="table-title">PointOnRoute – Element</div>

| Classification                | Name                |                    | Type                  | Cardinalité | Description                                                                                                          |
| ----------------------------- | ------------------- | ------------------ | --------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------- |
| *::>*                         | *::>*               |                    | *PointInLinkSequence* | *::>*       | POINT ON ROUTE hérite de POINT IN LINK SEQUENCE <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>. |
| *Hérité de POINT IN SEQUENCE* |                     | ***~~RouteRef~~*** |                       |             | <mark>Les PointOnRoute seront systématiquement inclus dans les ROUTEs.</mark>                                        |
|                               |                     | ***projections***  | *projections*         | 0:1         | Projection sur la voirie ou les rails <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>.           |
| «FK»                          | ***RoutePointRef*** |                    | *RoutePointRef*       | 1:1         | Référence au POINT D'ITINÉRAIRE correspondant                                                                        |

#### Point sur séquence de tronçon

<div class="table-title">PointInLinkSequence – Element (objet inclus)</div>

| Classification | Name                  | Type                  | Cardinalité | Description                                                                                                                                         |
| -------------- | --------------------- | --------------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| *::>*          | *::>*                 | *PointInSequence*     | *::>*       | POINT IN LINK SEQUENCE hérite de ***PointInSequence*** <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>.                         |
|                | ***order***           | *xsd:positiveInteger* | 0:1         | Numéro d'ordre du point dans la séquence.                                                                                                           |
|                | ***LinkSequenceRef*** | *LinkSequenceRef*     | 0:1         | Référence la SÉQUENCE DE TRONÇONs à laquelle appartient le POINT <mark>(une spécialisation pourra intervenir via un groupe de substitution)</mark>. |
|                | ***projections***     | *projections*         | 0:1         | Projection sur la voirie ou les rails <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>.                                          |

### Les tronçons d'itinéraire

<div class="table-title">RouteLink – Element</div>

| Classification | Name               | Type            | Cardinalité | Description                                                                                                                                                                       |
| -------------- | ------------------ | --------------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| *::>*          | *::>*              | *Link*          | *::>*       | ROUTE LINK hérite de LINK <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>.                                                                                    |
|                | Distance           | DistanceType    | 1:1         | Longueur du ROUTE LINK. Les unités sont telles que spécifiées pour la FRAME (la valeur par défaut est SI mètres).                                                                 |
| «cntd»         | LineString         | gmlLineString   | 0:1         | Géométrie du TRONÇON sous forme d’une linestring GML (la géométrie d’un TRONÇON n’est donc pas limitée à un simple couple de point, mais est décrite par une séquence de points). |
| «FK»           | ***FromPointRef*** | *RoutePointRef* | 1:1         | POINT D'ITINÉRAIRE de début de <mark>TRONÇON</mark>.                                                                                                                              |
| «FK»           | ***ToPointRef***   | *RoutePointRef* | 1:1         | POINT D'ITINÉRAIRE de fin de <mark>TRONÇON</mark>.                                                                                                                                |

Exemple de LineString pour décrire un tracé :

```xml
<gml:LineString gml:id="AB2o"> 
    <gml:pos>53.00 1.00</gml:pos> 
    <gml:pos>53.10 1.10</gml:pos> 
    <gml:pos>53.20 1.20</gml:pos> 
</gml:LineString>
```

## Les affichages de destination

![image](media/image2.svg)
*DESTINATION DISPLAY – Modèle conceptuel*

<div class="table-title">DestinationDisplay – Element</div>

|        | Name                  | Type                     |                                    | Description                                                                                                                                                                                                                                                                                                                                                                                               |
| ------ | --------------------- | ------------------------ | ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                   | *DataManagedObject*      | ::>                                | DESTINATION DISPLAY hérite de ***DataManagedObject*** <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                                                                                                |
|        | ***SideText***        | *MultilingualString*     | 0:1                                | Texte latéral (affiché sur le côté du véhicule) de l'AFFICHAGE DE DESTINATION.                                                                                                                                                                                                                                                                                                                            |
|        | ***FrontText***       | *MultilingualString*     | <del>0:1</del><br><mark>1:1</mark> | <p>Texte frontal (affiché sur le devant du véhicule) de l'AFFICHAGE DE DESTINATION.</p><p><mark>Au niveau du profil, ce texte est considéré comme étant le texte principal et est rendu obligatoire.</mark></p>                                                                                                                                                                                           |
| «AK»   | ***PublicCode***      | *xsd:normalizedString*   | 0:1                                | <p>Code associé à l'AFFICHAGE DE DESTINATION.</p><p><mark>Dans un certain nombre de cas l'AFFICHAGE DE DESTINATION n'est pas un texte mais un code (par exemple pour les RER et Transilen en Ile-de-France avec des codes comme PADO, DEFI ou encore PORO). Ce sont ces codes qui seront indiqué dans ce champ (on réservera les champs ***XxxxText*** pour un texte compréhensible par tous).</mark></p> |
| «cntd» | ***<del>vias</del>*** |                          |                                    | <mark>Les éventuels vias seront intégrés dans le texte de l'AFFICHAGE DE DESTINATION.</mark>                                                                                                                                                                                                                                                                                                              |
| «cntd» | ***variants***        | *DeliveryDisplayVariant* | 0:*                                | Variante de texte AFFICHAGE DE DESTINATION pour s'adapter aux différents types de média.                                                                                                                                                                                                                                                                                                                  |

### Les variantes d'affichages de destination

<div class="table-title">DestinationDisplayVariant – Element (objet inclus)</div>

|     | Name                                     | Type                             |                                    | Description                                                                                                                                                                               |
| --- | ---------------------------------------- | -------------------------------- | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::> | ::>                                      | *DataManagedObject*              | ::>                                | DESTINATION DISPLAY VARIANT hérite de ***DataManagedObject*** <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                        |
|     | ***DestinationDisplayVariantMediaType*** | *DeliveryVariantTypeEnumeration* | 1:1                                | Type (codé) de support auquel est destinée la variante. Les valeurs possibles sont: <ul><li>*Printed*</li><li>*textToSpeech*</li><li>*web*</li><li>*mobile*</li><li>*other*</li></ul>     |
|     | ***FrontText***                          | *MultilingualString*             | <del>0:1</del><br><mark>1:1</mark> | <p>Texte "frontal" de la VARIANTE D'AFFICHAGE DE DESTINATION.</p><p><mark>Au niveau du profil, ce texte est considéré comme étant le texte principal et est rendu obligatoire.</mark></p> |

## La flexibilité des lignes (TAD)

![image](media/image3.svg)
*Flexible Line – Modèle conceptuel*

La plupart des objets de bases utilisés pour la description des lignes
disposent d'une déclinaison dite "flexible" que l'on utilisera en
particulier dans le cadre du transport à la demande (TAD), mais aussi
dans de nombreux autres contextes de nouveaux services de transport
public.

Pour les LIGNEs et les ITINÉRAIREs le mécanisme de groupe de
substitution (substitution group) XML utilisé par NeTEx permet
d'utiliser n'importe que objet "flexible" en lieu et place de la version
non flexible correspondante.

Pour les POINTs et le TRONÇON, c'est un objet supplémentaire
(référençant l'objet "principal") qui apporte les propriétés de
flexibilité.

### Ligne flexible

<div class="table-title">FlexibleLine – Element</div>

|        | Name                      | Type                   |     | Description                                                                                                                                                                                                                                                                                                                                                                                        |
| ------ | ------------------------- | ---------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                       | *Line*                 | ::> | FLEXIBLE LINE hérite de LINE                                                                                                                                                                                                                                                                                                                                                                       |
|        | ***FlexibleLineType***    | *FlexibleLineTypeEnum* | 1:1 | Type de LIGNE FLEXIBLE <mark>(voir le document NeTEx pour le détail des différents types de flexibilité)</mark> : <ul><li>*corridorService*</li><li>*mainRouteWithFlexibleEnds*</li><li>*flexibleAreasOnly*</li><li>*hailAndRideSections*</li><li>*fixedStopAreaWide*</li><li>*freeAreaAreaWide*</li><li>*mixedFlexible*</li><li>*mixedFlexibleAndFixed*</li><li>*fixed*</li><li>*other*</li></ul> |
| «cntd» | ***BookingArrangements*** | *BookingArrangements*  | 0:1 | Information sur les conditions de réservation.                                                                                                                                                                                                                                                                                                                                                     |

<div class="table-title">BookingArrangements – Element (objet inclus)</div>

|        | Name                        | Type                               |     | Description                                                                                                                                                                                                                                                                                                                                            |
| ------ | --------------------------- | ---------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| «cntd» | ***BookingContact***        | *ContactDetails*                   | 0:1 | Informations de contact pour la réservation <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                                                       |
|        | ***BookingMethods***        | *BookingMethodEnum*                | 0:* | Méthode de réservation à utiliser (plusieurs valeurs possibles) : <ul><li>*callDriver* : appeler le conducteur</li><li>*callOffice* : appeler un centre d’appel</li><li>*online* : via Internet</li><li>*other* : autre</li><li>*phoneAtStop* : par téléphone à l’arrêt</li><li>*text* : envoyer un message SMS pour réserver</li><li>*none*</li></ul> |
|        | ***BookingAccess***         | *BookingAccessEnum*                | 0:1 | Précise qui peut faire la réservation : <ul><li>*public* : tout le monde</li><li>*authorisedPublic* : personnes autorisée</li><li>*staff* : le personnel d’exploitation</li><li>*other*</li></ul>                                                                                                                                                      |
|        | ***BookWhen***              | *PurchaseWhenEnumeration*          | 0:1 | Précise quand la reservation peut-être faite <ul><li>*timeOfTravelOnly* : au moment de voyage</li><li>*dayOfTravelOnly* : le jour du voyage</li><li>*untilPreviousDay* : jusqu'au jour précédent le voyage (avant le jour du voyage)</li><li>*advanceAndDayOfTravel* : jusqu'au jour du voyage</li></ul>                                               |
|        | ***BuyWhen***               | *PurchaseMomentListOfEnumerations* | 0:1 | Moment où le paiement doit intervenir : <ul><li>*onReservation* : lors de la réservation</li><li>*beforeBoarding* : avant l'embarquement</li><li>*onBoarding* : au moment de l'embarquement</li><li>*afterBoarding* : après l'embarquement (pendant le voyage)</li><li>*onCheckOut* : à la descente du véhicule</li></ul>                              |
|        | ***LatestBookingTime***     | *MultilingualString*               | 0:1 | <p>Heure au plus tard, dans la journée, où la réservation doit se faire.</p><p><mark>À combiner avec ***BookWhen*** pour exprimer, par exemple *"avant la veille à 18:00"*.</mark></p>                                                                                                                                                                 |
|        | ***MinimumBookingPeriod***  | *xsd:duration*                     | 0:1 | Période, avant le départ, en amont de laquelle la réservation doit être faite. (exemple: 2:00 avant l'heure du départ).                                                                                                                                                                                                                                |
|        | ***<del>BookingUrl</del>*** |                                    |     | <mark>On utilise l'URL de ***BookingContact***</mark>                                                                                                                                                                                                                                                                                                  |
|        | ***BookingNotes***          | *Notice*                           | 0:* | Note concernant les conditions de réservation.                                                                                                                                                                                                                                                                                                         |

### Itinéraire flexible

<div class="table-title">FlexibleRoute – Element</div>

|     | Name                    | Type                    |     | Description                                                                                                                                                                                                 |
| --- | ----------------------- | ----------------------- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::> | ::>                     | *Route*                 | ::> | FLEXIBLE ROUTE hérite ROUTE.                                                                                                                                                                                |
|     | ***FlexibleRouteType*** | *FlexibleRouteTypeEnum* | 1:1 | Type d'ITINÉRAIRE FLEXIBLE <mark>(voir le document NeTEx pour les définitions)</mark> : <ul><li>*flexibleAreasOnly*</li><li>*hailAndRideSections*</li><li>*mixed*</li><li>*fixed*</li><li>*other*</li></ul> |

### Point flexible

***FlexiblePointProperties*** doit toujours être intégré au
***StopPointInPattern*** qu’il précise.

<div class="table-title">FlexiblePointProperties – Element (objet inclus)</div>

|        | Name                        | Type              |     | Description                                                                                                                                                                                                                                                                                                                             |
| ------ | --------------------------- | ----------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                         | *VersionedChild*  | ::> | ***FlexiblePointProperties*** hérite de ***VersionedChild*** <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                       |
| Choice | a : ***PointOnRouteRef***   | *PointOnRouteRef* | 0:1 | POINT SUR ITINÉRAIRE concerné par ces propriétés de flexibilité                                                                                                                                                                                                                                                                         |
|        | ***MayBeSkipped***          | *xsd:boolean*     | 0:1 | L'ITINÉRAIRE peut ne pas passer par ce point                                                                                                                                                                                                                                                                                            |
|        | ***OnMainRoute***           | *xsd:boolean*     | 0:1 | Point sur l'ITINÉRAIRE principal (cas des corridors)                                                                                                                                                                                                                                                                                    |
|        | ***PointStandingForAZone*** | *xsd:boolean*     | 0:1 | <p>Point représentant une ZONE</p><p>Le POINT est alors obligatoirement référencé par une ZONE dont il est le centroïd <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.</p>                                                                                                                                         |
|        | ***ZoneContainingStops***   | *xsd:boolean*     | 0:1 | Dans le cas où ***PointStandingForAZone*** est vrai, cet attribut permet d'indiquer que la zone contient des arrêts (pour différentier le TAD zonal à l'adresse et le TAD zonal à l'arrêt). La ZONE référencée a alors obligatoirement un champ ***members*** référençant les arrêts qu'elle contient (de type POINT D'ARRÊT PLANIFIÉ). |

### Tronçon flexible

<div class="table-title">FlexibleLinkProperties – Element (objet inclus)</div>

|     | Name                   | Type                   |     | Description                                                                                                                      |
| --- | ---------------------- | ---------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------- |
| ::> | ::>                    | *VersionedChild*       | ::> | ***FlexibleLinkProperties*** hérite de ***VersionedChild*** <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>. |
|     | ***LinkRef***          | *LinkRef*              | 0:1 | Tronçon concerné par ces propriétés de flexibilité                                                                               |
|     | ***MayBeSkipped***     | *xsd:boolean*          | 0:1 | L'ITINÉRAIRE peut ne pas passer par ce TRONÇON                                                                                   |
|     | ***OnMainRoute***      | *xsd:boolean*          | 0:1 | TRONÇON sur l'ITINÉRAIRE principal (cas des corridors)                                                                           |
|     | ***UnscheduledPath***  | *xsd:boolean*          | 0:1 | Indique que le cheminement précis sur l'infrastructure routière n'est pas planifié.                                              |
|     | ***FlexibleLinkType*** | *FlexibleLinkTypeEnum* | 0:1 | Type of FLEXIBLE ROUTE LINK : <ul><li>*hailAndRide*</li><li>*onDemand*</li><li>*fixed*</li><li>*other*</li></ul>                 |

## Parcours

![image](media/image4.svg)
*Service Pattern – Modèle Conceptuel*

### Mission commerciale

<div class="table-title">ServiceJourneyPattern – Element</div>

|        | Name                            | Type                                   |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------ | ------------------------------- | -------------------------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                             | *LinkSequence                          | ::> | JOURNEY PATTERN hérite de LINK SEQUENCE <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| «FK»   | ***RouteRef***                  | *RouteRef*                             | 0:1 | ITINÉRAIRE utilisé par la MISSION COMMERCIALE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|        | ***<del>DirectionType</del>***  |                                        |     | <mark>Les informations de directions seront portées par l'ITINÉRAIRE.</mark>                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| «FK»   | ***DirectionRef***              | *DirectionRef*                         | 0:1 | <p>La DIRECTION d’une JOURNEY PATTERN est souvent utilisée pour distinguer des groupes de JOURNEY PATTERN utilisant les mêmes branches (c’est-à-dire des ROUTEs) d’une LIGNE.</p><p><mark>La DIRECTION est disponible à des fins de filtrage exclusivement (par exemple dans une interface utilisateur de calculateur d’itinéraire ou un système d'information sur les horaires), mais ne devra pas être considérée comme une informations descriptive (ce n’est pas une information présentée « spontanément »).</mark></p> |
| «FK»   | ***DestinationDisplayRef***     | *DestinationDisplayRef*                | 0:1 | AFFICHAGE DE DESTINATION associée à la MISSION COMMERCIALE <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                                                                                                                                                                                                              |
| «cntd» | ***pointsInSequence***          | *PointInJourneyPattern*                | 0:* | Liste ordonnée des points sur la MISSION COMMERCIALE (POINT D'ARRÊT SUR PARCOURS, POINT HORAIRE ou POINT SUR PARCOURS).                                                                                                                                                                                                                                                                                                                                                                                                      |
| «cntd» | ***linksInSequence***           | *ServiceLink*                          | 0:* | Liste ordonnée des sections de la MISSION COMMERCIALE (SERVICE LINK). Chaque section décrit la géométrie entre deux points consécutifs (ScheduleStopPoint).                                                                                                                                                                                                                                                                                                                                                                  |
| «FK»   | ***ServiceJourneyPatternType*** | *ServiceJourneyPatternTypeEnumeration* | 0:1 | <p>Type de MISSION COMMERCIALE.</p><mark>Il s'agit d'un type "étendu" qui permet de typer tout PARCOURS présentant un intérêt pour l'information voyageur.</mark> Les valeurs possibles pour ce type sont : <ul><li>*Passenger* : service passager</li><li>*garageRunOut* : sortie de garage/dépôt</li><li>*garageRunIn* : retour de garage/dépôt</li><li>*turningManoeuvre* : manœuvre de retournement (changement de sens en fin de parcours)</li><li>*other* : autre type sans passager</li></ul>                         |

### Haut le pied

Le profil étant dédié à l'information voyageur, on se limitera, pour la
description des hauts le pied, à une bonne utilisation du champ
***ServiceJourneyPatternType*** présenté dans le tableau ci-dessus (ce
champ permet de gérer le haut le pied pour lesquels on souhaite informer
les voyageurs, en indiquant les départ et retour dépôt ou encore les
manœuvre de retournement).

### Point sur parcours

<div class="table-title">PointInJourneyPattern – Element</div>

|      | Name                             | Type                      |     | Description                                                                                                                                                                                                                                                              |
| ---- | -------------------------------- | ------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ::>  | ::>                              | *PointInLinkSequence*     | ::> | <p>POINT IN JOURNEY PATTERN hérite de POINT IN LINK SEQUENCE <mark>(voir )</mark></p><p><mark>On n'utilisera pas le ***LinkSequenceRef*** de cet héritage car, dans le contexte du profil, cet objet sera toujours "à l'intérieur" d'une MISSION COMMERCIALE.</mark></p> |
| «FK» | ***PointRef***                   | *PointRef*                | 0:1 | POINT à placer dans le PARCOURS <mark>(il peut s'agir de n'importe quel type de point)</mark>.                                                                                                                                                                           |
| «FK» | ***DestinationDisplayRef***      | *DestinationDisplayRef*   | 0:1 | <p>DESTINATION DISPLAY associée à ce POINT.</p><p><mark>Cette information, qui sert à changer l'AFFICHAGE DE DESTINATION lorsque le véhicule arrive à ce POINT ne sera renseignée que si ***ChangeOfDestinationDisplay*** est VRAI.</mark></p>                           |
|      | ***FlexiblePointProperties***    | *FlexiblePointProperties* | 0:1 | Information sur l'éventuelle flexibilité du POINT <mark>(voir )</mark>                                                                                                                                                                                                   |
|      | ***ChangeOfDestinationDisplay*** | *xsd:boolean*             | 0:1 | Indique s'il faut changer l'AFFICHAGE DE DESTINATION en arrivant à ce POINT                                                                                                                                                                                              |

### Point d'arrêt sur parcours

<div class="table-title">StopPointInJourneyPattern – Element (objet inclus)</div>

|        | Name                             | Type                          |     | Description                                                                                                                                                                                                                                                                                                                                                     |
| ------ | -------------------------------- | ----------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                              | *TimingPointInJourneyPattern* | ::> | <p>STOP POINT IN JOURNEY PATTERN hérite de POINT IN LINK SEQUENCE <mark>(voir )</mark>.</p><p><mark>On n'utilisera pas le ***LinkSequenceRef*** de cet héritage car, dans le contexte du profil, cet objet sera toujours "à l'intérieur" d'une MISSION COMMERCIALE.</mark></p>                                                                                  |
| «FK»   | ***ScheduledStopPointRef***      | *ScheduledStopPointRef*       | 1:1 | Reference au POINT D'ARRÊT PLANIFIÉ.                                                                                                                                                                                                                                                                                                                            |
|        | ***ForAlighting***               | *xsd:boolean*                 | 0:1 | Indique que l'on peut descendre du véhicule à ce point (vrai par défaut).                                                                                                                                                                                                                                                                                       |
|        | ***ForBoarding***                | *xsd:boolean*                 | 0:1 | Indique que l'on peut embarquer dans le véhicule à ce point (vrai par défaut).                                                                                                                                                                                                                                                                                  |
| Choice | ***DestinationDisplayRef***      | *DestinationDisplayRef*       | 0:1 | <p>DESTINATION DISPLAY associée ce POINT.</p><p><mark>Cette information, qui sert à changer l'AFFICHAGE DE DESTINATION lorsque le véhicule arrive à ce POINT ne sera renseignée que si ***ChangeOfDestinationDisplay*** est VRAI.</mark></p>                                                                                                                    |
|        | ***FlexiblePointProperties***    | *FlexiblePointProperties*     | 0:1 | Information sur l'éventuelle flexibilité du POINT <mark>(voir )</mark>                                                                                                                                                                                                                                                                                          |
|        | ***ChangeOfDestinationDisplay*** | *xsd:boolean*                 | 0:1 | Indique s'il faut changer l'AFFICHAGE DE DESTINATION en arrivant à ce POINT.                                                                                                                                                                                                                                                                                    |
| «cntd» | ***noticeAssignments***          | *NoticeAssignmentView*        | 0:* | NOTE associée au POINT.                                                                                                                                                                                                                                                                                                                                         |
|        | ***RequestStop***                | *xsd:boolean*                 | 0:1 | Indique que l'arrêt doit être demandé <mark>(bouton à l'intérieur du véhicule et faire un signe de la main depuis le quai, ou tout autre dispositif fonctionnellement similaire potentiellement précisé ci-dessous)</mark>.                                                                                                                                     |
|        | ***RequestMethod***              | *RequestMethodTypeEnum*       | 0:1 | Méthode de demander l’arrêt <ul><li>***noneRequired*** : pas de demande nécessaire</li><li>***handSignal*** : signe de main</li><li>***turnOnLight*** : allumage d’une lumière</li><li>***stopButton*** : bouton stop</li><li>***phoneCall*** : appel téléphonique</li><li>***mobileApp*** : application mobile</li><li>***sms***</li><li>***other***</li></ul> |
|        | ***StopUse***                    | *StopUseEnumeration*          | 0:1 | Type d'utilisation du POINT D'ARRÊT PLANIFIÉ dans la MISSION COMMERCIALE (access par défaut) <ul><li>***access*** : accès au transport (montée et/ou descente)</li><li>***interchangeOnly*** : correspondance seulement</li><li>***passthrough*** : passage sans marquer l'arrêt</li><li>***noBoardingOrAlighting*** : arrêt sans montée ni descente</li></ul>  |
|        | ***BookingArrangements***        | *<u>BookingArrangements</u>*  | 0:1 | Conditions de réservation pour cet arrêt quand elles sont différentes du SERVICE JOURNEY.                                                                                                                                                                                                                                                                       |

### Point d'arrêt panifié

<div class="table-title">ScheduledStopPoint – Element</div>

|        | Name                                 | Type                    |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------ | ------------------------------------ | ----------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                                  | *TimingPoint*           | ::> | SCHEDULED STOP POINT hérite de TIMING POINT (voir ci-dessous).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| «cntd» | ***tariffZones***                    | *TariffZoneRef*         | 0:* | ZONE TARIFAIRE à laquelle appartient le POINT D'ARRÊT PLANIFIÉ.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|        | ***ShortName***                      | *MultilingualString*    | 0:1 | <p>Nom abrégé du POINT D'ARRÊT PLANIFIÉ.</p><p><mark>Informations à garder cohérente avec le lieu d'arrêt.</mark></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|        | ***Description***                    | *MultilingualString*    | 0:1 | Description du POINT D'ARRÊT PLANIFIÉ.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| «AK»   | ***PublicCode***                     | *xsd:normalizedString*  | 0:1 | Code publique du POINT D'ARRÊT PLANIFIÉ <mark>(code identifiant utilisé pour les services, par SMS par exemple)</mark>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| «AK»   | ***PrivateCode***                    | *xsd:normalizedString*  | 0:1 | Identifiant technique alternatif du POINT D'ARRÊT PLANIFIÉ.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|        | ***StopType***                       | *StopPlaceTypeEnum*     | 0:1 | <mark>Type de POINT D'ARRÊT PLANIFIÉ. Ce champ n'est retenu que pour fournir une information quand l'affection au LIEU D'ARRÊT n'est pas fournie (le LIEU D'ARRÊT porte cette information de type). Si ***StopType*** est fourni et l'affection au LIEU D'ARRÊT aussi, ces informations devront être cohérente (si ça ne l'est pas, c'est le LIEU D'ARRÊT qui sera pris comme référence).</mark><ul><li>***onstreetBus*** : bus sur voirie</li><li>***onstreetTram*** : tram sur voirie</li><li>***airport*** : aéroport</li><li>***railStation*** : gare</li><li>***metroStation*** : station de métro</li><li>***busStation*** : gare routière</li><li>***coachStation*** : station d’autocars</li><li>***tramStation*** : station de Tram</li><li>***harbourPort*** : port</li><li>***ferryPort*** : port pour ferry</li><li>***ferryStop*** : arrêt de ferry</li><li>***liftStation*** : accès ascenseur ou téléphérique</li><li>***vehicleRailInterchange*** : correspondance rail</li><li>***other***</li></ul> |
|        | ***Presentation***                   | *PresentationStructure* | 0:1 | Eléments de représentation associés au POINT D'ARRÊT PLANIFIÉ.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|        | ***<del>ForAlighting</del>***        |                         |     | <mark>Voir ***StopPointInJourneyPattern***</mark>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|        | ***<del>ForBoarding</del>***         |                         |     | <mark>Voir ***StopPointInJourneyPattern***</mark>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|        | ***<del>RequestStop</del>***         |                         |     | <mark>Voir ***StopPointInJourneyPattern***</mark>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| «FK»   | ***<del>TopographicPlaceRef</del>*** |                         |     | <mark>Ces informations seront portées par le lieu d'arrêt.</mark>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

<mark>**NOTE IMPORTANTE** : Le profil France ne retient pas l'attribut
*Location* du SCHEDULED STOP POINT, l'information est portée par les objets
QUAY ou STOP PLACE.</mark>

### Parcours horaire

Le profil étant dédié à l'information voyageur, on se limitera, pour la
description des parcours horaires, à utiliser la capacité des
***ServiceJourneyPattern*** à intégrer des
***TimingPointInJourneyPattern*** dans sa séquence de points, pour les
point horaire qui ne sont pas des POINT D'ARRÊT PLANIFIÉs, et à
instancier aux codes adéquats les champs ***TimingPointStatus*** et
***AllowedForWaitTime*** des POINT D'ARRÊT PLANIFIÉs (les informations
plus détaillées de ***StopPointInJourneyPattern*** ne sont pas
retenues).

#### Point horaire sur parcours

<div class="table-title">TimingPointInJourneyPattern – Element (objet inclus)</div>

|     | Name                 | Type                    |     | Description                                                                                                                                                                                                                                                                     |
| --- | -------------------- | ----------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::> | ::>                  | *PointInSequence*       | ::> | <p>TIMING POINT IN JOURNEY PATTERN hérite de POINT IN LINK SEQUENCE <mark>(voir )</mark></p><p><mark>On n'utilisera pas le ***LinkSequenceRef*** de cet héritage car, dans le contexte du profil, cet objet sera toujours "à l'intérieur" d'une MISSION COMMERCIALE.</mark></p> |
|     | ***TimingPointRef*** | *ScheduledStopPointRef* | 1:1 | Référence au POINT HORAIRE.                                                                                                                                                                                                                                                     |

#### Point horaire

<div class="table-title">TimingPoint – Element</div>

|     | Name                     | Type                           |     | Description                                                                                                                                                                                                                                                    |
| --- | ------------------------ | ------------------------------ | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::> | ::>                      | *TimingPoint*                  | ::> | TIMING POINT hérite de POINT <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                              |
|     | ***TimingPointStatus***  | *TimingPointStatusEnumeration* | 0:1 | Nature du POINT HORAIRE : <ul><li>***timingPoint*** : POINT HORAIRE utilisé pour la régulation</li><li>***secondaryTimingPoint*** : POINT HORAIRE utilisé pour la construction des horaires mais pas pour la régulation</li><li>***notTimingPoint***</li></ul> |
|     | ***AllowedForWaitTime*** | *xsd:duration*                 | 0:1 | Temps d'attente autorisé pour la régulation.                                                                                                                                                                                                                   |

## Correspondances

La plupart des calculateurs d’itinéraires utilisent les temps de
transfert pour un changement de véhicule de transport. Il peut
éventuellement s’agir d’un temps d'échange par défaut à utiliser pour
toutes les correspondances d'un MODE particulier ou à une station
donnée, mais certains calculateurs permettent d'indiquer les temps de
correspondances entre les quais.

Le modèle NeTEx permet d'échanger un ensemble de correspondance pour la
planification de voyage avec des niveaux de précision dépendant du
contexte (par défaut, pour une station spécifique, pour un couple
d'arrêts spécifique), héritant tous du concept TRANSFER.

![image](media/image5.svg)
*Correspondances – Modèle conceptuel*

### Correspondance entre POINT D'ARRÊT PLANIFIÉs

<div class="table-title">Connection – Element</div>

| Classification | Name       | Type            | Cardinalité | Description                          |
| -------------- | ---------- | --------------- | ----------- | ------------------------------------ |
| ::>            | ::>        | *Transfer*      | ::>         | CONNECTION hérite de TRANSFER.       |
| «cntd»         | ***From*** | *ConnectionEnd* | 1:1         | Point de départ de la CORRESPONDANCE |
| «cntd»         | ***To***   | *ConnectionEnd* | 1:1         | Point de fin de la CORRESPONDANCE    |

<div class="table-title">ConnectionEnd – Element (objet inclus)</div>

|      | Name                        | Type                    |     | Description                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---- | --------------------------- | ----------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|      | ***TransportMode***         | *TransportModeEnum*     | 0:1 | <p>MODE de transport concerné par cette extrémité de correspondance.</p><p><mark>Cet attribut permet de particulariser les correspondances en fonction des modes de transport. Si rien n'est indiqué, tous les modes présents sont concernés. Si le mode est précisé, mais que certain modes présent n'ont pas de correspondance associée, c'est que la correspondance n'est pas possible pour ces modes.</mark></p> |
| «FK» | ***ScheduledStopPointRef*** | *ScheduledStopPointRef* | 0:1 | POINT D'ARRÊT PLANIFIÉ auquel se raccorde la CORRESPONDANCE.                                                                                                                                                                                                                                                                                                                                                         |

#### Transferts

<div class="table-title">Transfer – Element (abstrait)</div>

|        | Name                              | Type                 |     | Description                                                                                                                                                                                                |
| ------ | --------------------------------- | -------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                               | *DataManagedObject*  | ::> | TRANSFER hérite de ***DataManagedObject*** <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                            |
|        | ***Name***                        | *MultilingualString* | 0:1 | Nom du TRANSFERT.                                                                                                                                                                                          |
| «FK»   | ***TypeOfTransferRef***           | *TypeOfTransferRef*  | 0:1 | <p>Type de TRANSFERT.</p><p><mark>Utilisé uniquement avec le code "ADVERTISED" pour signaler que la correspondance doit être affichée sur les média (information à l'arrêt).</mark></p>                    |
|        | ***Description***                 | *MultilingualString* | 0:1 | Description du TRANSFERT.                                                                                                                                                                                  |
|        | ***Distance***                    | *DistanceType*       | 0:1 | Distance totale du TRANSFERT (en mètres).                                                                                                                                                                  |
| «cntd» | ***<del>TransferDuration</del>*** |                      |     | <mark>Temps de correspondance total (marche plus temps d'attentes) : non retenu pour le profil.</mark>                                                                                                     |
| «cntd» | ***WalkTransferDuration***        | *TransferDuration*   | 0:1 | Temps de marche à la correspondance.                                                                                                                                                                       |
|        | ***BothWays***                    | *xsd:boolean*        | 0:1 | Indique si le TRANSFERT est bidirectionnel ou non (oui par défaut).                                                                                                                                        |
| «cntd» | ***(From)***                      | *TransferEnd*        | 1:1 | <p>Origine du TRANSFERT</p><p>Le TRANSFERT étant l'objet de correspondance le plus générique, les extrémités ne sont ici pas typées, elles le seront par contre dans les spécialisations du TRANSFERT.</p> |
| «cntd» | ***(To)***                        | *TransferEnd*        | 1:1 | Fin du TRANSFERT                                                                                                                                                                                           |

<div class="table-title">TransferDuration – Element (objet inclus)</div>

|     | Name                                      | Type           |                                    | Description                                                                                                                                                                                          |
| --- | ----------------------------------------- | -------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     | ***DefaultDuration***                     | *xsd:duration* | <del>0:1</del><br><mark>1:1</mark> | <p>Durée par défaut (à pied)</p><p><mark>Obligatoire dans le contexte du profil.</mark></p>                                                                                                          |
|     | ***FrequentTravellerDuration***           | *xsd:duration* | 0:1                                | Durée pour un voyageur habitué de ce parcours.                                                                                                                                                       |
|     | ***OccasionalTravellerDuration***         | *xsd:duration* | 0:1                                | <p>Durée pour un voyageur découvrant ce parcours.</p><p><mark>Note : on attend naturellement ***FrequentTravellerDuration*** ≤ ***DefaultDuration*** ≤ ***OccasionalTravellerDuration***.</mark></p> |
|     | ***MobilityRestrictedTravellerDuration*** | *xsd:duration* | 0:1                                | Durée pour un voyageur en mobilité réduite (bagages, poussette, handicap, etc.).                                                                                                                     |

#### Informations par défaut sur les correspondances

Les correspondances par défaut sont des objets "racine" (au niveau
***members*** du FRAME) et permettent de valoriser les correspondances
implicites. Elles peuvent être particularisées par MODE ou par
EXPLOITANT ou par LIEU TOPOGRAPHIQUE (ville, arrondissement, etc.).
Cette information est particulièrement importante pour les calculateurs
d'itinéraire.

<mark>Par convention on fournira en général un ***DefaultConnection*** sans
contrainte pour le cas général, et on le particularisera par des versions
spécifiques par MODE ou par EXPLOITANT qui viendront alors "surcharger" la
version sans contrainte (la priorité est aux versions particularisées).</mark>

<div class="table-title">DefaultConnection – Element</div>

| Classification | Name                       | Type                   | Cardinalité | Description                                                                                                                |
| -------------- | -------------------------- | ---------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------- |
| *::>*          | *::>*                      | *Transfer*             | *::>*       | DEFAULT TRANSFER hérite de TRANSFER.                                                                                       |
| «cntd»         | ***From***                 | *DefaultConnectionEnd* | 0:1         | Origine du transfert (MODE / EXPLOITANT).                                                                                  |
| «cntd»         | ***To***                   | *DefaultConnectionEnd* | 0:1         | Fin du transfert (MODE / EXPLOITANT).                                                                                      |
| «FK»           | ***TopographicPlaceView*** | *TopographicPlaceRef*  | 0:\*        | Zone administrative (typiquement une ville ou un groupement de commune) dans laquelle ces valeurs par défaut s’appliquent. |
| «FK»           | ***SiteElementRef***       | *SiteElementRef*       | 0:\*        | Elément de SITE dans lesquels ces valeurs par défaut s’appliquent.                                                         |

<div class="table-title">DefaultConnectionEnd – Element (objet inclus)</div>

| Classification | Name              | Type                | Cardinalité | Description                                                                                       |
| -------------- | ----------------- | ------------------- | ----------- | ------------------------------------------------------------------------------------------------- |
| «FK»           | ***Mode***        | *TransportModeEnum* | 0:1         | MODE associé à l'extrémité du transfert. L’énumération se trouve dans la partie Eléments communs. |
| «FK»           | ***OperatorRef*** | *OperatorRef*       | 0:1         | EXPLOITANT associé à l'extrémité du transfert.                                                    |

#### Correspondance entre sites (LIEUx D'ARRÊT)

Les correspondances entre sites permettent de créer simplement des
relations entre LIEUX D'ARRÊT et les Points Of Interest (POI) sans avoir
à descendre au niveau du NAVIGATION PATH (détail du cheminement piéton,
dont on ne fera ici qu'une description minimale permettant d'indiquer la
présence des principaux équipements, comme les ascenseurs, etc.). La
structure est la même que pour les CORRESPONDANCEs, avec une
spécialisation des extrémités et la possibilité de faire référence à un
NAVIGATION PATH.

Cette structure permet aussi de caractériser de façon un peu plus
détaillée les cheminements accès (STOP PLACE ENTRANCE) vers ZONE
D'EMBARQUEMENT (QUAY).

<div class="table-title">SiteConnection – Element</div>

| Classification | Name                  | Type                | Cardinalité | Description                                                                                                                              |
| -------------- | --------------------- | ------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| ::>            | ::>                   | *Transfer*          | ::>         | SITE CONNECTION hérite de TRANSFER.                                                                                                      |
| «cntd»         | ***From***            | *SiteConnectionEnd* | 0:1         | Origine du lien entre sites                                                                                                              |
| «cntd»         | ***To***              | *SiteConnectionEnd* | 0:1         | Fin du lien entre sites                                                                                                                  |
|                | ***navigationPaths*** | *navigationPaths*   | 0:1         | <p>Description du cheminement utilisé pour cette correspondance.</p><p>(voir la partie accessibilité du profil pour plus de détails)</p> |

<div class="table-title">SiteConnectionEnd – Element (objet inclus)</div>

| Classification | Name                                   | Type                      |     | Description                                                                                                                                                                                                                                                                            |
| -------------- | -------------------------------------- | ------------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                | ***<del>ScheduledStopPointRef</del>*** |                           |     | <p><mark>On limite dans le profil le SITE CONNECTION aux correspondances entre sites (LIEU D'ARRÊT, PARKING, POI) de façon à simplifier l'analyse des données et éviter toute possible confusion sémantique.</mark></p>                                                                |
| Choice         | a : ***StopPlaceRef***                 | *StopPlaceRef*            | 0:1 | Reference to destination STOP PLACE of SITE CONNECTION.                                                                                                                                                                                                                                |
|                | b : ***QuayRef***                      | *QuayRef*                 | 0:1 | Référence à une ZONE D'EMBARGEMENT <mark>(voir profil NeTEx Arrêt)</mark>                                                                                                                                                                                                              |
|                | ***StopPlaceEntranceRef***             | *StopPlaceEntranceRef*    | 0:1 | Référence à une entrée (entrée à utiliser pour cette correspondance) <mark>(voir profil NeTEx Arrêt)</mark>                                                                                                                                                                            |
|                | ***PointOfInterestEndGroup***          | *PointOfInterestEndGroup* | 0:1 | <p>Eléments pour identifier un POI à la l’extrémité d’un SITE CONNECTION.</p><p><mark>On pourra utiliser ***PointOfInterestRef*** avec une référence externe.</mark></p><p><mark>*Note : la valeur de ce champ sera précisée quand on disposera d'un profil pour les POIs.*</mark></p> |
|                | ***ParrkingEndGroup***                 | *ParkingEndGroup*         | 0:1 | <p>Eléments pour identifier un PARKING à l’extrémité d’un SITE CONNECTION.</p><p><mark>On utilisera ***ParkingRef*** avec une référence externe.</mark></p><p><mark>*Note : la valeur de ce champ sera précisée quand on disposera d'un profil pour les PARKINGs.*</mark></p>          |

<u>EXEMPLE XML</u>

L'exemple suivant illustre l'utilisation de références à des POI
externes, la première provenant d'OSM en France et la seconde d'INSPIRE
en Slovaquie. Notez que l'attribut versionRef est obligatoire pour les
objets externes (la valeur peut être "any" si la version est inconnue ou
le numéro de version réel du POI s'il est connu).

```xml
<PointOfInterestRef ref="FR_OSM_Poi:node:55711945" versionRef="any"/>

<PointOfInterestRef ref="SK_INSPIRE_Poi:SK.SOPSK.SKUEV0319" versionRef="any" />
```

##### Point of Interest

Un POINT D'INTÉRÊT (POI) est un type de LIEU vers ou à partir duquel les
passagers peuvent souhaiter se déplacer dans le cadre de leur
déplacement (ce sont fréquemment des points de départ ou d’arrivé
utilisés pour effectuer une requête à un calculateur d’itinéraire, ils
sont aussi utilisés pour interroger la desserte de transport
avoisinante, etc.).

<mark>Dans de nombreux cas, les POIs seront définis dans des
bases de données externes (INSPIRE, OSM, ou jeux de données commerciaux)
et simplement référencés par SITE CONNECTIONs. Toutefois la le
formalisme NeTEx peut aussi permettre d’enrichir l’information issue
d’une autre source (par exemple pour y décrire les service disponible,
l’accessibilité, les équipements du lieu, etc.). Dans ces cas
d’enrichissement, on prendra soin de bien conserver l’identifiant de
l’objet enrichi et on utilisera le codespace adéquat (par exemple
"FR_OSM:PointOfInteres:node:55711945" où 55711945 est bien l’identifiant
OSM, pour enrichir une POI issu d’Open Street Map et permet
au node de qualifier le
type d’objet OSM pour garantir l’unicité de l’identifiant)</mark>

1. PointOfInterest – XML Element

| Classification | Name                        | Type                                                                      |     | Description                                                                                                                                                                                                                                      |
| -------------- | --------------------------- | ------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ::>            | ::>                         | *Site*                                                                    | ::> | POINT OF INTEREST hérite de SITE.                                                                                                                                                                                                                |
| «PK»           | ***id***                    | *PointOfInterestIdType*                                                   | 1:1 | Identifier of: POINT OF INTEREST.                                                                                                                                                                                                                |
| «cntd»         | ***classifications***       | *PointOfInterestClassificationRef* \| *PointOfInterestClassificationView* | 0:* | <p>Classification du POINT OF INTEREST.</p><p><mark>Seul l'attribut Name de PointOfInterestClassificationView sera utilisé pour cette classification. Aucune classification standard n'est prédéfinie ni par NeTEx, ni par le profil.</mark></p> |
| «cntd»         | ***nearTopographicPlaces*** | *TopographicPlaceRef*                                                     | 0:* | TOPOGRAPHIC PLACEs proche du POINT OF INTEREST.                                                                                                                                                                                                  |

##### Cheminement

La description du cheminement est ici limitée à ses caractéristiques
principales (en particulier pour l'accessibilité).

<mark>Note : la partie Accessibilité du profil France fournit
une vue beaucoup plus détaillée du NavigationPath.</mark>

<div class="table-title">NavigationPath – Element</div>

|     | Name                    | Type                 |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --- | ----------------------- | -------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ::> | ::>                     | *LinkSequence*       | ::> | NAVIGATION PATH hérite de LINK SEQUENCE.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     | ***AccessFeatureList*** | *AccessFeatureEnum*  | 0:* | <p>Type d'équipements qui seront rencontrés sur le cheminement (***none*** par défaut).</p> Les valeurs possibles sont : <ul><li>*Lift* : ascenseur</li><li>*Escalator* : escalier mécanique</li><li>*freightElevator* : monte charge</li><li>*travelator* : tapis roulant</li><li>*ramp* : rampe</li><li>*stairs* : escaliers</li><li>*seriesOfStairs* : serie d’escaliers</li><li>*shuttle* : navette</li><li>*crossing* : passage piéton</li><li>*barrier* : barrière</li><li>*narrowEntrance* : passage étroit</li><li>*hall* : hall, couloir</li><li>*concourse* : hall, esplanade</li><li>*confinedSpace* : espace réduit</li><li>*queueManagement* : gestion de queue</li><li>*none* : rine</li><li>*unknown* : inconnu</li><li>*other* : autre</li><li>*openSpace* : espace ouvert</li><li>*street* : rue</li><li>*pavement* : chaussée</li><li>*footpath* : chemin piéton</li><li>*passage* : couloir</li></ul> |
|     | ***NavigationType***    | *NavigationTypeEnum* | 1:1 | Type de cheminement. Les valeurs possibles sont : <ul><li>*hallToQuay* : hall vers quai</li><li>*hallToStreet* : hall vers rue</li><li>*quayToHall* : quai vers hall</li><li>*quayToQuay* : quai vers quai</li><li>*quayToStreet* : quai vers rue</li><li>*streetToHall* : rue vers hall</li><li>*streetToQuay* : rue vers quai</li><li>*streetToSpace* : rue vers esplanade</li><li>*spaceToStreet* : esplanade vers rue</li><li>*spaceToHall* : esplanade vers hall</li><li>*hallToSpace* : hall vers esplanade</li><li>*spaceToSpace* : esplanade vers esplanade</li><li>*other* : autre</li></ul>                                                                                                                                                                                                                                                                                                                    |

## Contraintes et restrictions (ITL, etc.)

![image](media/image6.svg)
*Contraintes et restrictions – Modèle Conceptuel*

### Contraintes de zone

Les contraintes de zone sont particulièrement bien adaptées à la
description des ITL (Interdiction de trafic local).

<div class="table-title">RoutingConstraintZone – Element</div>

|     | Name                  | Type              |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| --- | --------------------- | ----------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::> | ::>                   | *Zone*            | ::> | <p>ROUTING CONSTRAINT ZONE hérite de ZONE <mark>(voir le document **Profil NeTEx éléments communs**)</mark>.</p><p><mark>Note : on définira généralement la zone par la liste des POINTs D'ARRÊT PLANIFIÉs concernés par la contrainte (une ZONE peut en effet être définie par un ensemble de points, par son attribut ***members***). Si la ZONE n'est pas définie par un ensemble de points (et uniquement dans ce cas-là) c'est son périmètre géographique qui sera utilisé (il devra donc impérativement être défini).</mark></p> |
|     | ***ZoneUse***         | *ZoneUseTypeEnum* | 0:1 | Contrainte appliquée à la ZONE : <ul><li>*cannotBoardAndAlightInSameZone* : un voyageur ne peut embarquer puis débarquer au sein de cette ZONE (ITL)</li><li>*mustAlightInZone* : tous les voyageurs présents à l'entrée de la ZONE devront débarquée dans cette ZONE.</li><li>*cannotAlightInZone* : tous les voyageurs présents à l'entrée de la ZONE ne pourront pas débarquer dans cette ZONE.</li><li>*other*</li></ul>                                                                                                           |
|     | ***lines***           | *lineRefs*        | 0:* | Liste des lignes concernées par la restriction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|     | ***GroupOfLinesRef*** | *GroupOfLinesRef* | 0:1 | Groupe de lignes ou réseau concerné par la restriction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|     | ***pointsInPattern*** | *pointsInPattern* |     | <mark>Cette propriété n'est pas retenue dans le profil France. Le champ ***member*** est utilisé, comme indiqué ci-dessus dans l'héritage de Zone.</mark>                                                                                                                                                                                                                                                                                                                                                                              |

### Restriction de correspondance

<div class="table-title">TransferRestriction – Element</div>

|      | Name                  | Type                          |     | Description                                                                                                                                                                                                                                                                                                        |
| ---- | --------------------- | ----------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ::>  | ::>                   | *DataManagedObject*           | ::> | TRANSFER RESTRICTION hérite de DATA MANAGED OBJECT (via ASSIGNMENT) <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                           |
|      | ***Description***     | *MultilingualString*          | 0:1 | Description de la restriction de correspondance (explication/justification de son utilisation).                                                                                                                                                                                                                    |
|      | ***BothWays***        | *boolean*                     | 0:1 | Indique si la restriction n'est que pour le sens direct ou pour les deux sens de correspondance.                                                                                                                                                                                                                   |
|      | ***RestrictionType*** | *TransferRestrictionTypeEnum* | 1:1 | Type de restriction :<ul><li>***cannotTransfer***</li></ul><br><p><mark>Seule l'interdiction de correspondance est retenue dans le profil.</mark></p>                                                                                                                                                              |
| «FK» | ***FromPointRef***    | *ScheduledStopPointRef*       | 0:1 | <p>POINT D'ARRÊT PLANIFIÉ de départ</p><p><mark>Si seul le départ est indiqué, toutes les correspondances partantes sont interdites (et entrante aussi si BothWays=vrai).</mark></p><p><mark>Au moins l'un des deux attributs ***FromPointRef*** ou ***ToPointRef*** doit être valorisé.</mark></p>                    |
| «FK» | ***ToPointRef***      | *ScheduledStopPointRef*       | 0:1 | <p>POINT D'ARRÊT PLANIFIÉ de destination.</p><p><mark>Si seule la destination est indiquée, toutes les correspondances arrivantes sont interdites (et sortantes aussi si BothWays=vrai).</mark></p><p><mark>Au moins l'un des deux attributs ***FromPointRef*** ou ***ToPointRef*** doit être valorisé.</mark></p> |

## Affectation d'arrêt

Cette affection permet de mettre en relation des LIEUx D'ARRÊT ou des
ZONE D'EMBARQUEMENT (voir profil NeTEx Arrêt et modèle d'arrêt partagé
de du ministère des transport) et les POINTs D'ARRÊT PLANIFIÉs.

![image](media/image7.svg)
*Passenger Stop Assignment – Modèle conceptuel*

<div class="table-title">StopAssignment – Element (abstrait)</div>

| Classification | Name                        | Type                    | Cardinalité | Description                                                                                                                         |
| -------------- | --------------------------- | ----------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| ::>            | ::>                         | *DataManagedObject*     | ::>         | STOP ASSIGNMENT hérite de DATA MANAGED OBJECT (via ASSIGNMENT) <mark>(*voir le document **Profil NeTEx éléments communs***)</mark>. |
| «FK»           | ***ScheduledStopPointRef*** | *ScheduledStopPointRef* | 0:1         | Référence au POINT D'ARRÊT PLANIFIÉ.                                                                                                |

<div class="table-title">PassengerStopAssignment – Element</div>

|        | Name                | Type                  |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------ | ------------------- | --------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                 | *StopAssignment*      | ::> | PASSENGER STOP ASSIGNMENT hérite de STOP ASSIGNMENT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| «FK»   | ***StopPlaceRef***  | *StopPlaceRef*        | 1:1 | Référence au LIEU D'ARRÊT associé Référence au POINT D'ARRÊT PLANIFIÉ.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| «FK»   | ***QuayRef***       | *QuayRef*             | 0:1 | Eventuelle référence à la ZONE D'EMBARQUEMENT concernée.                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| «cntd» | ***trainElements*** | *TrainStopAssignment* | 0:* | <p>Références à des affectations détaillées des positions de train (alignement des voitures sur les marques à quai).</p><p><mark>On utilisera ici des objets indépendant (des références et non des inclusions) de façon à permettre une mise à jour de l’affectation de train, sans avoir à modifier l'affectation d'arrêt elle-même. De même on autorise que l'affectation de train référence l'affectation d'arrêt sans que la réciproque ne soit vraie (on pourra donc ne pas remplir le présent élément).</mark></p> |

### Affectation de train à quai

<div class="table-title">TrainStopAssignment – Element</div>

|      | Name                             | Type                          |     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ---- | -------------------------------- | ----------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>  | ::>                              | *StopAssignment*              | ::> | TRAIN STOP ASSIGNMENT hérite de STOP ASSIGNMENT                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| «FK» | ***PassengerStopAssignmentRef*** | *PasssengerStopAssignmentRef* | 0:1 | Référence à l'affectation d'arrêt que l'affectation de train précise.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| «FK» | ***TrainRef***                   | *TrainRef*                    | 0:1 | <p>Identifiant du train concerné.</p><mark>On pourra soit utiliser l'identifiant d'un TRAIN défini par ailleurs, soit directement référencer un numéro de train en utilisant la convention suivante :</mark><ul><li><mark>L'attribut ***nameOfRefClass*** de la référence est positionné à "TrainNumberRef".</mark></li><li><mark>L'attribut ***ref*** de la référence est instancié avec le numéro de train (ex : "9050" pour l'Eurostar Londres-Paris de 19h01).</mark></li></ul>               |
| «FK» | ***TrainComponentRef***          | *TrainComponentRef*           | 0:1 | <p>COMPOSANT DE TRAIN (voiture) concerné par l'affectation de train.</p><mark>On pourra soit utiliser l'identifiant d'un COMPOSANT DE TRAIN défini par ailleurs, soit directement référencer un numéro de voiture en utilisant la convention suivante :</mark><ul><li><mark>L'attribut ***nameOfRefClass*** de la référence est positionné à "TrainComponentRef".</mark></li><li><mark>L'attribut ***ref*** de la référence est instancié avec le numéro de voiture (ex : "12").</mark></li></ul> |
| «FK» | ***BoardingPositionRef***        | *BoardingPositionRef*         | 0:1 | <p>Référence la POSITION D'EMBARQUEMENT avec laquelle le COMPOSANT DE TRAIN s'alignera.</p><mark>La POSITION D'EMBARQUEMENT n'étant pas retenue dans le profil NeTEx Arrêt, on utilisera la convention suivante :</mark><ul><li><mark>L'attribut ***nameOfRefClass*** de la référence est positionné à "BoardingPositionRef".</mark></li><li><mark>L'attribut ***ref*** de la référence est instancié avec le nom de la marque à quay (ex : "W").</mark></li></ul>                                |

### Affectation dynamique (pour affectation « tardive », mais toujours planifiée)

<div class="table-title">DynamicStopAssignment – Element</div>

| Classification | Name                       | Type                           | Cardinalité | Description                                                        |
| -------------- | -------------------------- | ------------------------------ | ----------- | ------------------------------------------------------------------ |
| *::>*          | *::>*                      | *<u>DynamicStopAssignment</u>* | *::>*       | DYNAMIC STOP ASSIGNMENT hérite de PASSENGER STOP ASSIGNMENT.       |
| «PK»           | Id                         | DynamicAssignmentIdType        | 1:1         | Identifiant du DYNAMIC STOP ASSIGNMENT.                            |
| «FK»           | JourneyPatternRef          | *JourneyPatternRef*            | 0:1         | JOURNEY PATTERN à laquelle la DYNAMIC STOP ASSIGNMENT s’applique.  |
| «FK»           | PassengerStopAssignmentRef | *PassengerStopAssignmentRef*   | 0:1         | PASSENGER STOP ASSIGNMENT que le DYNAMIC STOP ASSIGNMENT remplace. |

## Plan schématique

<div class="table-title">SchematicMap – Element</div>

|        | Name                   | Type                 |     | Description                                                                                                                                                                                   |
| ------ | ---------------------- | -------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>    | ::>                    | *DataManagedObject*  | ::> | SCHEMATIC MAP hérite de DATA MANAGED OBJECT <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                              |
|        | ***Name***             | *MultilingualString* | 0:1 | Nom de la carte schématique                                                                                                                                                                   |
|        | ***ImageUri***         | *xsd:anyURI*         | 0:1 | <p>URL d'accès à la carte schématique</p><p><mark>La carte schématique peut être aussi bien une image raster classique (.png, .jpg, etc.), qu'une image vectorielle (.svg, .ai, etc.).</mark></p> |
| «FK»   | ***DepictsObjectRef*** | *ObjectRef*          | 1:1 | Référence de l'objet transport représenté par cette carte (typiquement RESEAU, LIGNE, LIEU D'ARRÊT, etc.)                                                                                     |
| «cntd» | ***members***          | *SchematicMapMember* | 0:* | Objets transports représentés sur la carte schématique.                                                                                                                                       |

<div class="table-title">SchematicMapMember – Element (objet inclus)</div>

|      | Name                     | Type                    |     | Description                                                                                                                                                                                                                                                                                                                                                                                                            |
| ---- | ------------------------ | ----------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ::>  | ::>                      | *GroupMember*           | ::> | SCHEMATIC MAP MEMBER hérite de GROUP MEMBER <mark>*(voir le document **Profil NeTEx éléments communs**)*</mark>.                                                                                                                                                                                                                                                                                                       |
| «FK» | ***VersionOfObjectRef*** | *ObjectRef*             | 0:1 | Référence de l'objet transport (NeTEx) représenté sur la carte.                                                                                                                                                                                                                                                                                                                                                        |
|      | ***InfoLink***           | *InfoLink*              | 0:1 | <p>URL vers l'objet dans la carte schématique :</p><p><mark>On utilisera la syntaxe HTML de référencement par ancre ("anchor", avec la syntaxe `#anchor`, par exemple `http://www.macarte.com/schema.svg#objectId`) pour référencer un objet vectoriel identifié. L'URL de la carte schématique étant fournie par l'attribut ***ImageUri***, on pourra ne fournir que la référence de l'objet (`#objectId`)</mark></p> |
|      | ***x***                  | *GraphicsUnitsTypeType* | 1:1 | Coordonnée (abscisse) de l'objet dans l'environnement de la carte schématique (pixel ou unité graphique suivant le type de carte schématique)                                                                                                                                                                                                                                                                          |
|      | ***y***                  | *GraphicsUnitsTypeType* | 1:1 | Coordonnée (ordonnées) de l'objet dans l'environnement de la carte schématique (pixel ou unité graphique suivant le type de carte schématique)                                                                                                                                                                                                                                                                         |

# Entêtes NeTEx

*Note: les entêtes NeTEx sont présentés dans le document éléments communs.
Seules les spécificités de la partie "description du réseau" sont présentées
ici.*

Deux FRAMEs distinctes sont utilisées pour échanger la description des réseaux:

- Une FRAME de type **NETEX_RESEAU**, utilisée dans le fichier "network.xml"
- Une FRAME de type **NETEX_LIGNE**, utilisée dans le fichier "line_xyz.xml"

Pour rappel, la liste des fichiers d'un export NeTEx profil France est décrite
dans Éléments Communs.

## TypeOfFrame : type spécifique *NETEX_RESEAU*

Lorsqu'une FRAME a pour TypeOfFrame la valeur `NETEX_RESEAU`, seuls les objets
de premier niveau suivants sont autorisés:

- Network
- GroupOfLines
- RoutingContraintZone

Voici un exemple de cadre du fichier `network.xml` :

```xml
<?xml version="1.0" encoding="utf-8"?>
<PublicationDelivery xmlns="http://www.netex.org.uk/netex" version="2.0:FR-NETEX-2.4">
  <PublicationTimestamp>2025-02-27T00:00:00.0Z</PublicationTimestamp>
  <ParticipantRef>Exemple</ParticipantRef>
  <dataObjects>
    <GeneralFrame id="exemple:GeneralFrame:NETEX_RESEAU_1" version="2.0:FR-NETEX-2.4">
      <TypeOfFrameRef ref="FR:TypeOfFrame:NETEX_RESEAU:" />
      <members>
        <!--
          NETWORK
          GROUP OF LINES
          ROUTING CONSTRAINT ZONE
          -->
      </members>
    </GeneralFrame>
  </dataObjects>                  
</PublicationDelivery>
```

## TypeOfFrame : type spécifique *NETEX_LINE* et *NETEX_LIGNE_STRUCTURE*

Lorsqu'une FRAME a pour TypeOfFrame la valeur `NETEX_LINE`, il s'agit un objet
`CompositeFrame`, lui-même composé de:

- Une GeneralFrame de type `NETEX_LIGNE_STRUCTURE` (voir ci-dessous)
- Une GeneralFrame de type `NETEX_HORAIRE`, décrit dans la partie Horaires du
  profil

La Frame de type `NETEX_LIGNE_STRUCTURE` ne contient que les objets de premier
niveau suivants (et les objets qui en héritent):

- Pour la partie de description générale des lignes
  - Line
  - Direction
  - Route
  - RoutePoint
  - PointOnRoute
  - RouteLink
  - FlexibleLine
  - FlexibleRoute
  - Route
- Pour la partie plus précise de la ligne :
  - DestinationDisplay
  - FlexiblePointProperties
  - ServiceJourneyPattern
  - PointInJourneyPattern
  - ScheduledStopPoint
  - TimingPoint
  - TransferRestriction
  - PassengerStopAssignement
  - FlexibleStopAssignment
  - TrainStopAssignment
  - SchematicMap

Voici un exemple de cadre du fichier `line_xyz.xml` :

```xml
<?xml version="1.0" encoding="utf-8"?>
<PublicationDelivery xmlns="http://www.netex.org.uk/netex" version="2.0:FR-NETEX-2.4">
  <PublicationTimestamp>2023-01-01T00:00:00.0Z</PublicationTimestamp>
  <ParticipantRef>Exemple</ParticipantRef>
  <dataObjects>
    <CompositeFrame id="FR:CompositeFrame:NETEX_LIGNE-line_xyz:LOC" version="any">
      <TypeOfFrameRef ref="FR:TypeOfFrame:NETEX_LIGNE:" />
      <frames>
        <GeneralFrame id="FR:GeneralFrame:NETEX_RESEAU-line_xyz:LOC" version="2.0:FR-NETEX-2.4">
          <TypeOfFrameRef ref="FR:TypeOfFrame:NETEX_LIGNE_STRUCTURE:" />
          <members>
            <Line id="sample" version="any">
              <Name>Ligne d'exemple</Name>
            </Line>
            <!--  Partie Ligne
              Peut contenir (chaque objet contiendra ses objets sous-jacents, les éléments listés ici pourront être référencés dans les autres objets)
              LINE 
              DIRECTION
              ROUTE
              ROUTE POINT
              POINT ON ROUTE
              ROUTE LINK
              FLEXIBLE LINE
              FLEXIBLE ROUTE
            -->

            <!--  Partie Reseau
              DESTINATION DISPLAY
              FLEXIBLE POINT PROPERTIES
              FLEXIBLE LINK PROPERTIES
              SERVICE JOURNEY PATTERN
              POINT IN JOURNEY PATTERN
              SCHEDULED STOP POINT
              TIMING POINT
              TRANSFER RESTRICTION
              PASSENGER STOP ASSIGNMENT
              FLEXIBLE STOP ASSIGNMENT
              TRAIN STOP ASSIGNMENT
              SCHEMATIC MAP  
            -->
          </members>
        </GeneralFrame>

        <GeneralFrame id="FR:GeneralFrame:NETEX_HORAIRE-line_xyz:LOC" version="2.0:FR-NETEX-2.4">
          <TypeOfFrameRef ref="FR:TypeOfFrame:NETEX_HORAIRE:" />
          <members>
            <!-- 
              Peut contenir
              SERVICE JOURNEY
              SERVICE LINK
              FLEXIBLE SERVICE PROPERTIES
              TEMPLATE SERVICE JOURNEY
              HEADWAY JOURNEY GROUP
              RHYTHMICAL JOURNEY GROUP
              COUPLED JOURNEY
              JOURNEY PART COUPLE
              JOURNEY PART
              TRAIN
              TRAIN COMPONENT
              COMPOUND TRAIN
              TRAIN NUMBER
              TRAIN COMPONENT LABEL ASSIGNMENT
            -->
          </members>
        </GeneralFrame>
  </dataObjects>
</PublicationDelivery>
```

Bibliographie

EN 15531-1, Public transport - Service interface for real-time
information relating to public transport operations - Part 1: Context
and framework

EN 15531-2, Public transport - Service interface for real-time
information relating to public transport operations - Part 2:
Communications infrastructure3

EN 15531-3, Public transport - Service interface for real-time
information relating to public transport operations - Part 3: Functional
service interfaces4

CEN/TS 15531-4, Public transport - Service interface for real-time
information relating to public transport operations - Part 4: Functional
service interfaces: Facility Monitoring

CEN/TS 15531-5, Public transport - Service interface for real-time
information relating to public transport operations - Part 5: Functional
service interfaces - Situation Exchange
