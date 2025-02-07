---
title: "NeTEx - Profil France - Horaires"
date: 2022-01-13T00:00:00+00:02
draft: false
tags: ["NeTEx"]
autonumbering: true
---

**Avant-propos**

L’harmonisation des pratiques dans l’échange des données relatives aux
offres de transport est essentielle :

-   pour l’usager, aux fins d’une présentation homogène et
    compréhensible de l’offre de transport et de l’engagement
    sous-jacent des organisateurs (autorités organisatrices et
    opérateurs de transports) ;

-   pour les AOT, de manière à fédérer des informations homogènes venant
    de chacun des opérateurs de transports qui travaillent pour elle.
    L’harmonisation des échanges, et en particulier le présent profil,
    pourra le cas échéant être imposé par voie contractuelle. Cette
    homogénéité des formats d’information permet d’envisager la mise en
    place de systèmes d’information multimodaux, produisant une
    information globale de l’offre de transports sur un secteur donné,
    et garantir le fonctionnement des services d’information, en
    particulier des calculateurs d’itinéraires, et la cohérence des
    résultats, que ces services soient directement intégrés dans ces
    systèmes d’information multimodaux ou qu’ils puisent leurs
    informations sur des bases de données réparties ;

-   pour les opérateurs, qui pourront utiliser ce format d’échange pour
    leurs systèmes de planification, les systèmes d’aide à
    l’exploitation, leurs systèmes billettiques et leurs systèmes
    d’information voyageur (information planifiée et information temps
    réel)

-   pour les industriels et développeurs pour pérenniser et fiabiliser
    leurs investissements sur les formats d’échanges implémentés par les
    systèmes qu’ils réalisent, tout en limitant fortement l’effort de
    spécification lié aux formats d’échange

Ce document est le fruit de la collaboration entre les différents
partenaires des autorités organisatrices de transports, opérateurs,
industriels et développeurs de solutions et de systèmes informatiques
ayant pour objet l’aide à l’exploitation du transport public et
l’information des voyageurs. Il a pour objet de présenter le profil
d’échange Profil NeTEx Horaires: "format de référence pour l'échange de
données de description des horaires" (issu des travaux *NeTEx,
Transmodel et IFOPT)* qui aujourd’hui fait consensus dans les groupes de
normalisation (CN03/GT7 – Transport public / information voyageur).

**Introduction**

Le présent format d’échange est un profil de NeTEx.

NeTEx (CEN TS 16614-1, 16614-2 et 16614-3) propose un format et des
services d'échange de données de description de l'offre de transport
planifiée, basé sur Transmodel (EN 12896) et l’ancienne norme IFOPT (EN
28701). NeTEx permet non seulement d'assurer les échanges pour les
systèmes d'information voyageur mais traite aussi l’ensemble des
concepts nécessaires en entrée et sortie des systèmes de planification
de l'offre (graphiquage, etc.) et des SAE (Systèmes d’Aide à
l’Exploitation).

NeTEx se décompose en trois parties:

-   Partie 1 : topologie des réseaux (les réseaux, les lignes, les
    parcours commerciaux les missions commerciales, les arrêts et lieux
    d’arrêts, les correspondances et les éléments géographiques en se
    limitant au strict minimum pour l’information voyageur)



-   Partie 2 : horaires théoriques (les courses commerciales, les heures
    de passage graphiquées, les jours types associés ainsi que les
    versions des horaires)



-   Partie 3 : information tarifaire (uniquement à vocation
    d’information voyageur)

NeTEx a été développé dans le cadre du CEN/TC 278/WG 3/SG 9 piloté par
la France. Les parties 1 et 2 ont été publiées en tant que spécification
technique début 2014. Les travaux pour la partie 3, quant à eux, se
termineront courant 2014sont terminés en 2016.

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

-   détail des services utilisés,



-   détails des objets utilisés dans un échange,



-   précisions sur les options proposées par la norme,



-   précision sur les éléments facultatifs,



-   précision sur les codifications à utiliser,



-   etc.

Les principaux profils actuellement utilisés en France sont NEPTUNE
(profil de TRIDENT) et le profil de SIRI défini par le CEREMA et
Île-de-France Mobilités. Ces deux profils ont une vocation nationale. Le
groupe de travail GT7 (AFNOR BNTRA/CN 03/GT 7) a élaboré une sélection
des concepts Transmodel nécessaire à la description des horaires en
France (à vocation d'information voyageur essentiellement). C'est sur la
base de cette sélection qu'est élaboré le présent profil.

D'autre profils de NeTEx sont disponibles (arrêt, réseau, tarif). Ils
sont tous complémentaires les uns des autres (sans recouvrement) et
s'appuient tous sur un document partagé: **NeTEx - Profil Français de
NETEx: éléments communs.** Il conviendra de se référer à ce document
pour tous les éléments utilisés dans le présent document, et dont la
structure n'est pas détaillée.

Ce profil d’échange a pour objectif de décrire et de structurer
précisément les éléments nécessaires à une bonne information de
description des horaires de transport public de façon :

-   à pouvoir les présenter d’une manière homogène et compréhensible à
    l’usager des transports publics sur des supports différents (papier
    ou Internet),

-   à pouvoir les échanger entre systèmes d’information (systèmes
    d’information voyageurs et systèmes d’information multimodale,
    systèmes d’aide à l’exploitation, systèmes de planification,
    systèmes billettiques, etc.).

Les éléments présentés ci-dessous couvrent donc l’ensemble des concepts
propres à la description des horaires.

NOTE **IMPORTANTE** Ce document étant un profil d'échange de NeTEx, il
ne se substitue en aucun cas à NeTEx, et un minimum de connaissance de
NeTEx sera nécessaire à sa bonne compréhension.

# Domaine d'application

Le présent document est le profil de la CEN/TS  6614 (NeTEx) pour
l'échange de données de description des horaires en France et permet de
décrire les horaires de transports publics et la manière dont ils
pourront être structurés pour des échanges entre systèmes d'information
ainsi que pour leur présentation aux voyageurs.

Ce sont les services de transport et leurs horaires au sens large
(heures de passage, fréquences, jours d'application) qui sont pris en
compte dans ce contexte, et non la structure de l'offre de transport
(voir les profils arrêt et réseau pour cela).

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
explications plus détaillées. Pour une information complète, il
conviendra toutefois de se référer au document normatif.

NOTE Les termes spécifiquement introduits par le profil d’arrêt sont
signalés par le mot *(profil)*, en italique et entre parenthèses. Les
définitions ci-dessus sont des traductions littérales du document
normatif.

## **COUPLED JOURNEY** (COURSE COUPLÉE)

Un voyage complet opéré par un train couplé, composé de deux COURSES, ou
plus, restant couplées tout au long d’un PARCOURS. Une COURSE COUPLÉE
peut être considérée comme une simple COURSE.

## **DATED PASSING TIME** (HEURE DE PASSAGE DATÉE)

HEURE DE PASSAGE pour un JOUR D'EXPLOITATION donné. Cet objet restera
abstrait dans le contexte de ce profil et ne sera utiliséutilisé qu’au
travers de sa spécialisation en HEURE DE PASSAGE COMMANDÉE.

## **DATED VEHICLE JOURNEY** (COURSE DATÉE)

Service service particulier d'un véhicule sur un jour de fonctionnement
particulier, y compris toutes les modifications éventuellement décidées
par le personnel de contrôle. Cet objet restera abstrait dans le
contexte de ce profil et ne sera utilisé qu’au travers de sa
spécialisation en COURSE DATÉE NORMALE.

## **DEAD RUN** (HAUT LE PIED)

Un service voiture haut-le-pied (non commercial).

## **DEFAULT INTERCHANGE** (CORRESPONDANCE PAR DEFAUT)

Paramètre définissant la durée acceptable (maximum autorisée et objectif
de durée standard) pour une correspondance entre deux POINTS D'ARRÊT.

## **FLEXIBLE SERVICE PROPERTIES** (PROPRIÉTÉS DE COURSE FLEXIBLE)

Propriété supplémentaire d'un service permettant de caractériser sa
flexibilité. Un service peut n'être que partiellement flexible.

## **HEADWAY INTERVAL** (INTERVAL)

Intervalle temporel caractérisant un GROUPE DE COURSE À INTERVALLE (par
exemple toutes les 10 minutes ou toutes les 4 à 6 minutes).

## **HEADWAY JOURNEY GROUP** (GROUPE DE COURSES EN FRÉQUENCE)

Groupe de COURSEs suivant le même PARCOURS et dont les départs sont
séparés d'un intervalle temporel fixe au sein d'un créneau horaire donné
(par exemple toutes les 10 minutes entre 8h et 10h30). Cette information
est particulièrement utile dans le cadre de l'information voyageur. Le
créneau horaire est exprimé par l'objet TIME BAND.

## **INTERCHANGE** (CORRESPONDANCE DE COURSES)

Une possibilité théorique de correspondance entre courses intervenant à
un seul POINT D'ARRÊT ou entre différents POINTs D'ARRÊT.

## **JOURNEY FREQUENCY GROUP** (GROUPE DE COURSES EN FRÉQUENCE)

Définit un groupe de COURSEs afin de leur attribuer un comportement
particulier comme un service en fréquence ou un service cadencé (passe
toutes les heures ..h10, ..h25 et ..h45 par exemple).

## **JOURNEY PART** (PARTIE DE COURSE)

Une partie d'une COURSE créée dans un but fonctionnel spécifique,
notamment dans les situations lors de couplage ou de séparation de
véhicule.

## **JOURNEY PART COUPLE** (COUPLE DE PARTIES DE COURSE)

Deux PARTIEs DE COURSEs de différentes COURSES effectuées simultanément
par un train constitué par le couplage de plusieurs véhicules ou rames.

## **NORMAL DATED VEHICLE JOURNEY** (COURSE DATÉE NORMALE)

Une COURSE DATÉE correspondant à la planification du parcours des
véhicules.

## **PASSING TIME** (HEURE DE PASSAGE)

Données temporelles concernant le passage des véhicules de transport
public à un POINT particulier (par exemple heure d'arrivée, heure de
départ, temps d'attente).

## **RHYTMHICAL JOURNEY GROUP** (GROUPE DE COURSES CADENCÉES)

Groupe de COURSEs suivant le même PARCOURS et répétant le même rythme de
départ toutes les heures (passe toutes les heures ..h10, ..h25 et ..h45
par exemple) et ce dans un créneau horaire donnée. Le créneau horaire
est exprimé par l'objet TIME BAND sur le schéma.

## **SERVICE JOURNEY** (COURSE COMMERCIALE)

Une COURSE transportant des passagers prévus pour un JOUR TYPE donné. Le
déroulement est en principe défini par le PARCOURS COMMERCIAL.

## **SERVICE JOURNEY INTERCHANGE** (CORRESPONDANCE DE COURSES COMMERCIALES)

Une possibilité théorique de correspondance entre COURSEs COMMERCIALEs
intervenant à un seul POINT D'ARRÊT ou entre différents POINTs D'ARRÊT.

## **TARGET PASSING TIME** (HEURE DE PASSAGE COMMANDÉE)

Données temporelles indiquant l'objectif à atteindre quant au passage du
véhicule à un POINT SUR PARCOURS particulier pour une COURSE DATÉE afin
de respecter l'horaire en vigueur. Concrètement il s'agit de
l'adaptation des HEUREs DE PASSAGE DATÉEs faite en exploitation pour
prendre en compte les changements de condition d'exploitation en amont
du départ du véhicule (travaux, etc.).

## **TEMPLATE SERVICE JOURNEY** (MODÈLE DE COURCE COMMERCIALE)

COURSE DE RÉFÉRENCE transportant des voyageurs.

## **TEMPLATE VEHICLE JOURNEY** (COURSE DE RÉFÉRENCE)

COURSE modèle dont l'occurrence a été spécifiée au sein d'un GROUPE DE
COURSE À INTERVALLE ou d'un GROUPE DE COURSE CADENCÉ; elle peut donc
représenter un grand nombre de COURSEs.

## **TIMETABLE PASSING TIME** (HEURE DE PASSAGE PLANIFIÉE)

Donnée temporelle théorique relative au passage d'un véhicule de
transport public à un POINT SUR PARCOURS donné sur une COURSE et pour un
JOUR TYPE. On notera qu'il ne s'agit pas d'une simple heure de
franchissement, mais que cette heure de passage est constituée de
l’heure de d’arrivée et de départ ainsi que d’informations associées
(quai, marges d’erreur, etc.).

## **TRAIN** (TRAIN)

Un véhicule composé d'ÉLÉMENTs DE TRAIN dans un certain ordre,
c'est-à-dire de voitures reliées et tirées par une locomotive ou une des
voitures.

## **TRAIN COMPONENT** (COMPOSANT DE TRAIN)

La position d'un ÉLÉMENT DE TRAIN dans un TRAIN.

## **TRAIN COMPONENT LABEL ASSIGNMENT** (AFFECTION DE LABEL DE VOITURE)

L'affectation d'une désignation annoncée pour un véhicule ou un élément
de véhicule pour passagers. Concrètement, cela permet de connaître le
libellé de la voiture (tel qu’indiqué sur la réservation du voyageur).
Ce libellé ne dépend pas que du type de TRAIN mais aussi de la COURSE à
laquelle il est affecté.

## **TRAIN ELEMENT** (ÉLÉMENT DE TRAIN)

Une composante élémentaire d'un TRAIN (par exemple voiture, locomotive).

## **TRAIN IN COMPOUND TRAIN** (TRAIN DANS UN TRAIN COMPOSÉ)

La position d'un TRAIN dans un TRAIN COMPOSÉ.

## **TRAIN NUMBER** (NUMÉRO DE TRAIN)

Spécification spécification des codes attribués à certaines COURSES ou
PARTIE DE COURSE, lorsqu'elles sont réalisées par des TRAINs ou des
TRAINs COMPOSÉs, pour répondre à un objectif fonctionnel (d'information
des passagers, suivi des opérations, etc).

## **TYPE OF FLEXIBLE SERVICE** (TYPE DE COURSE FLEXIBLE)

Classification classification des services flexibles.

## **VEHICLE JOURNEY** (COURSE)

Le mouvement planifié d'un véhicule de transport public effectué un JOUR
TYPE donné, depuis un point début à un point fin d'un PARCOURS sur un
ITINÉRAIRE. La COURSE est donc l'instanciation d'un PARCOURS donné,
auquel on va attribuer des heures de passage aux arrêts et des jours
d'application.

## **VEHICLE MODEL** (MODÈLE DE VEHICULE)

Une classification des véhicules de transport public d'un même TYPE DE
VÉHICULE, par exemple suivant les spécifications relatives aux
équipements ou à la génération du modèle.

## **VEHICLE TYPE** (TYPE DE VEHICULE)

Une classification des véhicules de transport public résultant des
spécifications de la planification des horaires en tenant compte du mode
de transport et de la capacité requise (par exemple bus standard, bus à
étage, …).

# Symboles et abréviations

* **AO** : Autorité Organisatrice de Transports

* **PMR** : Personne à Mobilité Réduite

# Exigences minimum liées à la LOM et la règlementation Européenne

La LOI n° 2019-1428 du 24 décembre 2019 d'orientation des mobilités
(LOM :
<https://www.legifrance.gouv.fr/dossierlegislatif/JORFDOLE000037646678>)
et, au niveau Européen, le Règlement Délégué (UE) 2017/1926 De La
Commission du 31 mai 2017 (complétant la directive 2010/40/UE du
Parlement européen et du Conseil en ce qui concerne la mise à
disposition, dans l'ensemble de l'Union, de services d'informations sur
les déplacements multimodaux) rendent obligatoire la mise à disposition,
quand elles existent, de certains types de données.

Le tableau ci-dessous résulte de l’analyse de la LOM et du règlement
délégué et fournit la liste des concepts concernés dans le présent
profil. Il sera donc nécessaire de fournir ces données pour être
conforme à la législation (il s’agit bien de mettre à disposition toutes
les données existantes dans les SI transport, et non de créer des
données qui n’existeraient pas encore sous forme informatique).

Notez que les concepts présents dans les tableaux sont les ceux qui sont
directement référencés par l’annexe du règlement européen
(<https://eur-lex.europa.eu/legal-content/FR/TXT/HTML/?uri=CELEX:32017R1926&from=FR>),
mais que pour beaucoup d’entre eux, cela impliquera d’autres concepts
(soit par héritage soit par relation, au s sens UML des termes). Ces
éléments d’héritage et de relations sont présentés dans les profils,
mais pas dans ce tableau.

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

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 25%" />
<col style="width: 27%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Niveau</strong></th>
<th><strong>Catégorie</strong></th>
<th><strong>Détail</strong></th>
<th><strong>Concepts à minima</strong></th>
<th><p><strong>Autres</strong></p>
<p><strong>concepts</strong></p></th>
<th><strong>Commentaire</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>2</td>
<td><em><strong>Trip plans, auxiliary information, availability check</strong></em></td>
<td>Vehicle facilities such as classes of carriage, on-board Wi-Fi</td>
<td><strong>VEHICLE TYPE</strong> et <strong>FACILITIES</strong> associées</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>3</td>
<td><em><strong>Trip plans</strong></em></td>
<td>Parameters such as fuel consumption needed to calculate cost</td>
<td><strong>VEHICLE TYPE</strong></td>
<td></td>
<td>Ne fournit qu'une partie de l'information nécessaire pour un véritable calcul de consomation (à partir du VEHICLE TYPE, dautres sources de données devront être utilisées)</td>
</tr>
<tr class="odd">
<td>1</td>
<td><em><strong>Trip plan computation — scheduled modes transport</strong></em></td>
<td>Timetables</td>
<td><strong>SERVICE JOURNEY<br />
TIMETABLE PASSING TIME</strong></td>
<td><strong>JOURNEY FREQUENCY GROUP<br />
HEADWAY JOURNEY GROUP<br />
TEMPLATE SERVICE JOURNEY</strong></td>
<td>Ne pas oublier les calendriers d'application associés (profil éléments communs) et bien sûr tous les éléments cosntitutifs des SERVICE JOURNEY.</td>
</tr>
<tr class="even">
<td>1</td>
<td><em><strong>Trip plan computation — scheduled modes transport</strong></em></td>
<td>Vehicles (low floor; wheelchair accessible.)</td>
<td><strong>VEHICLE TYPE et FACILITIES associées</strong></td>
<td><p><em>(profil Accessibilité)</em></p>
<p><strong>EQUIPMENT</strong></p></td>
<td></td>
</tr>
<tr class="odd">
<td>1</td>
<td><em><strong>Trip plan computation — scheduled modes transport</strong></em></td>
<td>Hours of operation</td>
<td><strong>SERVICE JOURNEY<br />
TIMETABLE PASSING TIME<br />
<br />
AVAILABILITY CONDITIONS</strong></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

# Description du profil d’échange

## Conventions de représentation

### Tableaux d’attributs

NOTE les choix de conventions présentées ici ont pour vocation d'être
cohérents avec ceux réalisés dans le cadre du profil SIRI (Île-de-France
Mobilités et CEREMA). De plus tous les profils NeTEx partagent les mêmes
conventions.

Les messages constituant ce profil d'échange sont décrits ci-dessous
selon un double formalisme: une description sous forme de diagrammes XSD
(leur compréhension nécessite une connaissance préalable de XSD: XML
Schema Definition) et une description sous forme tabulaire. Les tableaux
proposent ces colonnes:

| **Classifi­cation** | **Nom** | **Type** | **Cardin­alité** | **Description** |
|---------------------|---------|----------|------------------|-----------------|

-   **Classification** : permet de catégoriser l'attribut. Les
    principales catégories sont:

    -   PK (Public Key) que l'on peut interpréter comme Identifiant
        Unique: il permet à lui seul d'identifier l'objet, de façon
        unique, pérenne et non ambiguë. C'est l'identifiant qui sera
        utilisé pour référencer l'objet dans les relations.

    

    -   AK (Alternate Key) est un identifiant secondaire, généralement
        utilisé pour la communication, mais qui ne sera pas utilisé dans
        les relations.

    

    -   FK (Foreign Key) indique que l'attribut contient l'identifiant
        unique (PK) d'un autre objet avec lequel il est en relation.

    

    -   GROUP est un groupe XML nommé (ensemble d'attributs utilisables
        dans différents contextes) Voir [ici](http://www.w3.org/TR/2001/REC-xmlschema-0-20010502/#AttrGroups).



-   **Nom** : nom de l'élément ou attribut XSD



-   **Type** : type de l'élément ou attribut XSD (pour certains d'entre
    eux, il conviendra de se référer à la XSD NeTEx)



-   **Cardinalité** : cardinalité de l'élément ou attribut XSD exprimée
    sous la forme "***minimum:maximum***" ("0:1" pour au plus une
    occurrence; "1:\*" au moins une occurrence et sans limites de nombre
    maximal; "1:1" une et une seule occurrence; etc.).



-   Description : texte de description de l'élément ou attribut XSD
    (seul les attributs retenus par le profil ont un texte en français;
    les textes surlignés en jaune indiquent une spécificité du profil
    par rapport à NeTEx).

Les textes surlignés en <span class="hl">Jaune</span> sont ceux
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
spécifier les valeurs de code autorisées:

-   des énumérations fixes définies dans le cadre du schéma XSD NeTEx.
    Le profil impose alors un sous-ensemble des codes NeTEx.

-   des spécialisations de TYPE OF VALUE, utilisées pour définir des
    ensembles de codes ouverts pouvant être ajoutés au fil du temps sans
    modifier le schéma, par exemple, pour enregistrer des
    classifications d'entités héritées. Le profil lui-même utilise le
    mécanisme TYPE OF VALUE dans quelques cas pour spécifier des codes
    normalisés supplémentaires : ceux-ci sont affectés à un CODESPACE
    «FR_IV_metadata» (https://netex-cen.eu/FR_IV) indiqué par un préfixe
    «FR_IV». (par exemple, «FR_IV: monomodal».

-   des instances TypeOfFrame: le profil utilise plusieurs TYPES DE
    FRAME pour spécifier l'utilisation de VERSION FRAME dans le profil.

### Indication des classes abstraites

NeTEx, et Transmodel, utilisent largement l'héritage de classe; cela
simplifie considérablement la spécification en évitant les répétitions
puisque les attributs partagés sont déclarés par une superclasse et que
des sous-classes viennent ensuite les spécialiser sans avoir à répéter
ces attributs et en n’ajoutant que ceux qui lui sont spécifiques. La
plupart des superclasses sont «abstraites» - c’est-à-dire qu’il n’existe
aucune instance concrète; seules les sous-classes terminales sont
«concrètes».

Un inconvénient de l'héritage est que si l'on veut comprendre les
propriétés d'une classe concrète unique, il faut également examiner
toutes ses super-classes. Pour cette raison, le profil inclut les
classes abstraites nécessaires pour comprendre les classes concrètes,
même si ces classes concrètes ne sont jamais directement instanciées
dans un document NeTEx.

-   Les super-classes sont signalées dans les en-têtes par le suffixe
    «*(abstrait)*»

-   Dans les diagrammes UML (comme pour NeTEx et Transmodel), les noms
    des classes abstraites sont indiqués en italique et les classes
    abstraites sont de couleur gris clair.

-   Certaines super-classes ne sont techniquement pas abstraites dans
    NeTEx, mais ne sont pas utilisées comme classes concrètes dans le
    profil : elles sont signalées avec la même convention que les
    classes abstraites.

### Classes de sous-composants

Un certain nombre de classes ont des sous-composants qui constituent
leur définition. Celles-ci fournissent des détails auxiliaires (par
exemple, AlternativeText, AlternativeName, TrainComponent) et sont
signalées dans les en-têtes par le suffixe « *(objet inclus)* ».

## Les Courses

![image](media/image1.svg)
*Service Journey – Modèle conceptuel*

Une COURSE (SERVICE JOURNEY) est le mouvement défini d'un véhicule
utilisant un PARCOURS (JOURNEY PATTERN) spécifiée. Elle défini pour un
TYPE DE JOUR donné.

Le profil ne concerne que les COURSEs dans lequel les passagers seront
autorisés à monter à bord ou à descendre du véhicule aux arrêts.

<div class="table-title">ServiceJourney – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 6%" />
<col style="width: 11%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td colspan="2"><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td colspan="2"><em>::></em></td>
<td><em>Journey</em></td>
<td><em>::></em></td>
<td>SERVICE JOURNEY hérite de JOURNEYet intègre un certain nombre d'éléments de VEHICLE JOURNEY</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>ServiceAlteration</strong></em></td>
<td><em>ServiceAlterationEnumeration</em></td>
<td>0:1</td>
<td><p>Indique si la course est planifiée (valeur par défaut), si elle est annulée ou si c’est une course additionnelle.</p>
<p><span class="hl">Ce champ n’est à utiliser que pour les mises à jour tardives dans les cas où cette information n’est pas diffusée avec SIRI (service Producion Timetable)</span></p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"><em><strong>DepartureTime</strong></em></td>
<td><em>xsd:time</em></td>
<td>0:1</td>
<td>Heure de départ de la COURSE</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>DepartureDayOffset</strong></em></td>
<td><em>DayOffsetType</em></td>
<td>0:1</td>
<td>Décalage de jour si le jour de départ du VEHICLE JOURNEY est différent de l’OPERATING DAY courant (typiquement -1 pour « <em>la veille</em> »)..</td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td colspan="2"><em><strong><del>Frequency</del></strong></em></td>
<td></td>
<td></td>
<td><span class="hl">L'information de fréquence est fournie par la COURSE MODÈLE (voir </span><em><strong><span class="hl">frequencyGroups</span></strong></em><span class="hl"> de </span><em><strong><span class="hl">TemplateVehicleJourney</span></strong></em><span class="hl">)</span></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>JourneyDuration</strong></em></td>
<td><em>xsd:duration</em></td>
<td>0:1</td>
<td>Durée totale de la course.</td>
</tr>
<tr class="even">
<td>«FK»</td>
<td colspan="2"><em><strong>DayTypeRef</strong></em></td>
<td><em>DayTypeRef</em></td>
<td>1:*</td>
<td>TYPE DE JOUR correspondant aux jours d'application de la course. Voir Elements communs pour les précisions sur l'utilisation.</td>
</tr>
<tr class="odd">
<td>«FK»</td>
<td colspan="2"><em><strong><del>RouteRef</del></strong></em></td>
<td></td>
<td></td>
<td><span class="hl">Voir le PARCOURS</span></td>
</tr>
<tr class="even">
<td>«FK»</td>
<td colspan="2"><em><strong>JourneyPattern­Ref</strong></em></td>
<td><em>JourneyPatternRef</em></td>
<td>0:1</td>
<td>PARCOURS suivi par la COURSE</td>
</tr>
<tr class="even">
<td>«FK»</td>
<td colspan="2"><em><strong>VehicleTypeRef</strong></em></td>
<td><em>VehicleTypeRef</em></td>
<td>0:1</td>
<td>TYPE DE VEHICULE utilisé pour la course.</td>
</tr>
<tr class="odd">
<td></td>
<td><em>choice</em></td>
<td><em><strong>OperatorRef</strong></em></td>
<td>OperatorRef</td>
<td>0:1</td>
<td><p>Référence l'EXPLOITANT opérant cette course.</p>
<p><span class="hl">Il n'est indiqué que s’il est différent de celui de la ligne.</span></p></td>
</tr>
<tr class="odd">
<td>«EV»</td>
<td><em>choice</em></td>
<td><em><strong>LineRef</strong></em></td>
<td>LineRef</td>
<td>0:1</td>
<td>Référence la LIGNE à laquelle appartient la COURSE <span class="hl">(pour simplifier la navigation COURSE->PARCOURS->ITINERAIRE->LIGNE). Il peut naturellement s'agir d'une LIGNE FLEXIBLE.</span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td><em><strong>FlexibleLineView</strong></em></td>
<td>FlexibleLineView</td>
<td>0:1</td>
<td>Permet de décrire les éléments de flexibilité (typiquement TAD - Transport à la Demande) spécifiques à cette course</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"><em><strong>trainNumbers</strong></em></td>
<td><em>trainNumberRefs</em></td>
<td>0:*</td>
<td><p>Référence le numéro de train associé.</p>
<p><span class="hl">Note: le NUMERO DE TRAIN est un objet indépendant, qui est ici référencé.</span></p></td>
</tr>
<tr class="odd">
<td>«cntd»</td>
<td colspan="2">Origin</td>
<td></td>
<td></td>
<td><span class="hl">Voir le PARCOURS.</span></td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td colspan="2">Destination</td>
<td></td>
<td></td>
<td><span class="hl">Voir le PARCOURS.</span></td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td colspan="2"><em><strong>passingTimes</strong></em></td>
<td><em>TimetabledPassingTime</em></td>
<td>0:*</td>
<td>Heures de passages planifiées aux arrêts (<em><strong>scheduledStopPoint</strong>)</em>.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>parts</strong></em></td>
<td><em>journeyParts</em></td>
<td>0:*</td>
<td><p>Références à des parties de COURSE (JOURNEY PART) constituant la COURSE.</p>
<p><span class="hl">Utilisé pour un certain nombre de situations du mode ferré (changement de parité ou de numéro de train) ainsi que pour des situations comme le changement d'exploitant en cours de course sur les RER A et B.</span></p>
<p><span class="hl">Contrairement à la règle générale dans les profils NeTEx, et afin de pouvoir être réutilisées, les JOURNEY PARTs seront systématiquement définies indépendamment (à la racine de l'élément </span><em><strong><span class="hl">members</span></strong></em><span class="hl"> du FRAME) et simplement référencées ici (et non incluse, même si le modèle l'autorise).</span></p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>facilities</strong></em></td>
<td><em>serviceFacilitySets_RelStructure</em></td>
<td>0:*</td>
<td>Services disponibles pour cette course (voir le profil accessibilité pour plus de détails).</td>
</tr>

<tr class="odd">
<td></td>
<td colspan="2"><em><strong>TrainSize</strong></em></td>
<td>TrainSizeStructure</td>
<td>0:1</td>
<td>Information sur la taille du train (long/court). <span class="hl">Peut aussi servir pour identifier les bus articulés ou couplés.</span></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">FlexibleServiceProperties</td>
<td>FlexibleServiceProperties</td>
<td>0:1</td>
<td><p>Information de flexibilité de la COURSE.</p>
<p>Les informations de flexibilité sont fournies ici que si elles ne sont pas globales pour la LIGNE.</p></td>
</tr>
</tbody>
</table>

Pour ***TrainSize*** voir *6.10.1-Train.*

<div class="table-title">Journey – Element (abstrait)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 3%" />
<col style="width: 14%" />
<col style="width: 23%" />
<col style="width: 8%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td colspan="2"><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td colspan="2"><em>::></em></td>
<td><em>LinkSequence</em></td>
<td><em>::></em></td>
<td>JOURNEY hérite de LINK SEQUENCE <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Descriptionde JOURNEY.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"><em><strong>TransportMode</strong></em></td>
<td><em>VehicleModeEnum</em></td>
<td>0:1</td>
<td><p>Transport MODE de JOURNEY.</p>
<p><span class="hl">Le mode n'est précisé que s'il est différent de celui de la ligne (exemple: bus de substitution SNCF)</span>.</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>TransportSubmode</strong></em></td>
<td><em>TransportSubmode</em></td>
<td>0:1</td>
<td><p>SOUS MODE de transport de JOURNEY.</p>
<p><span class="hl">Le sous-mode n'est précisé que s'il est différent de celui de la ligne.</span></p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong><del>Monitored</del></strong></em></td>
<td></td>
<td></td>
<td><span class="hl">Fourni au niveau LIGNE.</span></td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td colspan="2"><em><strong><del>journeyAccountings</del></strong></em></td>
<td></td>
<td></td>
<td><span class="hl">Le profil étant dédié à l'information voyageur, les notions de comptabilité ne sont pas prises en compte, mais pourraient être nécessaires dans d'autres contextes.</span></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>noticeAssignments</strong></em></td>
<td><em>noticeAssignments</em></td>
<td>0:*</td>
<td>NOTEs associées à la COURSE.</td>
</tr>
</tbody>
</table>

### Les heures de passage

![image](media/image2.svg)
*Vehicle Journey, Passing Times et Interchanges – Modèle conceptuel*

<div class="table-title">PassingTime – Element (objet inclus)</div>

|                     |                           |                        |                  |                                                                                                                                                                                                                                                                                                                 |
|---------------------|---------------------------|------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Classifi­cation** | **Name**                  | **Type**               | **Cardin­ality** | **Description**                                                                                                                                                                                                                                                                                                 |
| *::>*               | *::>*                     | *VersionedChild*       | *::>*            | PASSING TIME hérite de VERSIONED CHILD <span class="hl">(non utilisé dans le profil)</span>                                                                                                                                                                                                                   |
|                     |                           |                        |                  |                                                                                                                                                                                                                                                                                                                 |
|                     |                           |                        |                  |                                                                                                                                                                                                                                                                                                                 |
| «FK»                | PointInJourney­PatternRef | PointInLinkSequenceRef | 0:1              | Référence les POINT D'ARRÊT PLANIFIÉ pour lequel on fournit les heures de passage. Ce point peut aussi, de façon plus exceptionnel être un POINT HORAIRE uniquement.                                                                                                                                            |
|                     | ***DayOffset***           | *xsd:integer*          | 0:1              | Nombre de jour de décalage par rapport au jour de début de course (permet de gérer les courses à cheval sur plusieurs jours).                                                                                                                                                                                   |
|                     | ArrivalTime               | xsd:time               | 0:1              | Heure d'arrivée.                                                                                                                                                                                                                                                                                                |
|                     | DepartureTime             | xsd:time               | 0:1              | Heure de départ.                                                                                                                                                                                                                                                                                                |
|                     |                           |                        |                  |                                                                                                                                                                                                                                                                                                                 |
|                     | Headway                   | HeadwayInterval        | 0:1              | Temps d'attente moyen avant le prochain passage d'une COURSE empruntant le même PARCOURS.                                                                                                                                                                                                                       |
|                     | EarliestDeparture­Time    | xsd:time               | 0:1              | Heure de départ au plus tôt <span class="hl">(il s'agit là de l'engagement de service du transporteur ou de l'AOT; il permettra notamment de sécuriser les correspondances; il permet aussi d'indiquer la précision de l'heure de passage, en particuliers aux points ou l'horaire est interpolé).</span>     |
|                     | LatestArrivalTime         | xsd:time               | 0:1              | Heure de d'arrivée au plus tard <span class="hl">(il s'agit là de l'engagement de service du transporteur ou de l'AOT; il permettra notamment de sécuriser les correspondances; il permet aussi d'indiquer la précision de l'heure de passage, en particuliers aux points ou l'horaire est interpolé).</span> |

*<span class="hl">Note: pour les courses en fréquence, les nécessaires
temps de parcours (pour le calcul d'itinéraire) seront calculés à partir
des heures de passage de la COURSE MODÈLE (la fourniture explicite des
temps de parcours, ou RUN TIME, nécessite la définition des TIMING
LINKs, alourdissant sensiblement l'échange sans pour autant
véritablement apporter une information supplémentaire dans un contexte
d'information voyageur). Le calcul du temps de parcours sera réalisé par
simple différence des heures de départs (DepartureTime) aux différents
arrêts.</span>*

### Propriétés de course flexible

<div class="table-title">FlexibleServiceProperties – Element (objet inclus)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classification</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>cardinality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em>DataManagedObject</em></td>
<td><em>::></em></td>
<td><p>FLEXIBLE SERVICE PROPERTIES hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</p>
<p><span class="hl">Non utilisé ici</span>.</p></td>
</tr>

<tr class="even">
<td>«cntd»</td>
<td><em><strong>Booking­Arrangements</strong></em></td>
<td><em>BookingArrangements</em></td>
<td>0:1</td>
<td>Informations de contact pour les services flexibles <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx réseau</span></strong></em><span class="hl">)</span>.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>FlexibleService­Type</strong></em></td>
<td><em>FlexibleServiceTypeEnum</em></td>
<td>0:1</td>
<td><p>Type de flexibilité mise en œuvre sur la course</p>
<ul>
<li><p><em>dynamicPassingTimes</em>: heure de passage fixée dynamiquement (en fonction de la demande)</p></li>
<li><p><em>fixedHeadwayFrequency</em>: fréquence de passage fixe (par exemple toute les 30 minutes) mais maintenue uniquement s'il y a une demande (réservation)</p></li>
<li><p><em>fixedPassingTimes</em>: heures de passage aux arrêts fixes (planifiées) mais maintenue uniquement s'il y a une demande (réservation)</p></li>
<li><p><em>notFlexible</em>: service régulier</p></li>
<li><p><em>other</em>: autre type de flexibilité <span class="hl">(associer une NOTE à la course)</span></p></li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>Cancellation­Possible</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td>Indique si une annulation du service est possible (même après une réservation).</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>ChangeOfTime­Possible</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td>Indique que l'horaire peut être modifié (même après une réservation).</td>
</tr>
</tbody>
</table>

## Groupes de courses

Un groupement de COURSEs, est particulièrement utile pour organiser des
séries de voyages similaires à présenter sous forme de tableau ou dans
les systèmes d’information voyageur, par exemple «*Tous les services au
départ pour la ligne 2 en semaine*».

<div class="table-title">GroupOfServices – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classification</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardinality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em><u>GroupOfEntities</u></em></td>
<td><em>::></em></td>
<td>GROUP OF SERVICES hérite de GROUP OF ENTITIES.</td>
</tr>
<tr class="odd">
<td>«PK»</td>
<td>id</td>
<td>GroupOfServicesIdType</td>
<td>1:1</td>
<td>Identifiant du GROUP OF SERVICEs.</td>
</tr>



<tr class="odd">
<td></td>
<td><em><strong>origin</strong></em></td>
<td><em>EndPoint_DerivedView</em></td>
<td></td>
<td>Origine des courses du groupe<br />
Par exemple : <em><strong>ScheduledStopPointRef, Name, StopType, etc</strong></em></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>destination</strong></em></td>
<td><em>EndPoint_DerivedView</em></td>
<td></td>
<td>Destination des courses du groupe<br />
Par exemple : <em><strong>ScheduledStopPointRef, Name, StopType, etc</strong></em></td>
</tr>
<tr class="odd">
<td>«cntd»</td>
<td><em><strong>destinationDisplays</strong></em></td>
<td><em><u>DestinationDisplay</u></em></td>
<td>0:*</td>
<td>DESTINATION DISPLAYs associés au groupe</td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td>members</td>
<td>VehicleJourneyRef</td>
<td>0:*</td>
<td>COURSEs faisant partie du GROUP OF SERVICEs.</td>
</tr>
<tr class="odd">
<td>«cntd»</td>
<td><em><strong>noticeAssignments</strong></em></td>
<td>NoticeAssignmentView</td>
<td>0:*</td>
<td>Note associée au GROUP OF SERVICEs.</td>
</tr>
</tbody>
</table>

## Les parties de course

![image](media/image3.svg)
*Journey Parts et Trains – Modèle conceptuel*

Les PARTIEs DE COURSE seront généralement spécifiques au mode ferré.

<div class="table-title">JourneyPart – Element (objet inclus)</div>

| **Classification** | **Name** | **Type** | **cardinality** | **Description** |
|-|-|-|-|-|
| *::>* | *::>* | *DataManagedObject* | *::>* | JOURNEY PART hérite de DATA MANAGED OBJECT <span class="hl">(</span>*<span class="hl">voir le document </span>**<span class="hl">Profil NeTEx éléments communs</span>***<span class="hl">)</span>. |
| | ***Description*** | *MultilingualString* | 0:1 | Description de la PARTIE DE COURSE. |
| «FK» | ***ParentJourneyRef*** | *VehicleJourneyRef* | 0:1 | COURSE à laquelle appartient cette PARTIE DE COURSE. |
| «FK» | ***MainPartRef*** | *JourneyPartCoupleRef* | 1:1 | Référence à la PARTIE DE COURSE principale (l'une des différentes PARTIE DE COURSE doit être déclarée comme principale). |
| «FK» | ***JourneyPart­CoupleRef*** | *JourneyPartCoupleRef* | 0:1 | Référence à l'éventuelle COURSE COUPLÉE à laquelle la PARTIE DE COURSE appartient. |
| «FK» | ***TrainNumberRef*** | *TrainNumberRef* | 0:1 | Référence au NUMÉRO DE TRAIN de la PARTIE DE COURSE. |
| «FK» | ***FromStopPointRef*** | *ScheduledStopPointRef* | 0:1 | Arrêt de départ de la PARTIE DE COURSE. |
| «FK» | ***ToStopPointRef*** | *ScheduledStopPointRef* | 0:1 | Arrêt de fin de la PARTIE DE COURSE. |
| | ***StartTime*** | *xsd:time* | 1:1 | Arrêt de départ de la PARTIE DE COURSE (à l'arrêt de départ). |
| | ***StartTimeDayOffset*** | *DayOffsetType* | 0:1 | Nombre de jours de décalage par rapport au jour de départ de la COURSE. |
| | ***EndTime*** | *xsd:time* | 1:1 | Arrêt de fin de la PARTIE DE COURSE (à l'arrêt de fin). |
| | ***EndTimeDayOffset*** | *DayOffsetType* | 0:1 | Nombre de jours de décalage par rapport au jour de départ de la COURSE. |
| «cntd» | ***facilities*** | *ServiceFacilitySet* | 0:\* | Service spécifique à cette PARTIE DE COURSE. |
| «cntd» | ***journeyPartPositions*** | *<u>JourneyPartPosition</u>* | 0:\* | Positions dans la séquence de PARTIE DE COURSE. |

JOURNEY PART POSITION décrit la position relative dans le train d'un
JOURNEY PART à partir d'un arrêt donné. Cela peut changer en cours de
route car les composants du train sont couplés et découplés.

<div class="table-title">JourneyPartPosition – Element (objet inclus)</div>

| **Classification** | **Name**                     | **Type**                   | **Cardinality** | **Description**                                             |
|--------------------|------------------------------|----------------------------|-----------------|-------------------------------------------------------------|
| *::>*              | *::>*                        | *VersionedChild*           | *::>*           | JOURNEY PART POSITION hérite de VERSIONED CHILD.            |
| «PK»               | id                           | JourneyPartPosition­IdType | 1:1             | Identifiant de JOURNEY PART POSITION.                       |
|                    |                              |                            |                 |                                                             |
| «FK»               | ***ScheduledStopPoint­Ref*** | *ScheduledStopPointRef*    | 0:1             | SCHEDULED STOP POINT pour lequel cette position est valide. |
|                    | ***PositionInTrain***        | *xsd:integer*              | 0:\*            | Position du JOURNEY PART à partir du SCHEDULED STOP POINT.  |

## Numéro de train

<div class="table-title">TrainNumber – Element (objet inclus)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em>DataManagedObject</em></td>
<td><em>::></em></td>
<td><p>TRAIN NUMBER hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</p>
<p>Le champ <em><strong>Id</strong></em> est naturellement l'identifiant du NUMÉRO DE TRAIN (c'est le numéro de train lui-même).</p></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Texte descriptif associé au NUMÉRO DE TRAIN <span class="hl">et à utiliser pour l'information voyageur (devra figurer en complément du numéro de train).</span></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>ForAdvertisement</strong></em></td>
<td><em>xsd:normalizedString</em></td>
<td>0:1</td>
<td>NUMÉRO DE TRAIN utilisé pour la communication au public <span class="hl">(parfois différent du numéro technique: si ce champ est présent il sera systématiquement utilisé pour l'information voyageur).</span></td>
</tr>

</tbody>
</table>

## Les courses en fréquence

### Course modèle

Les courses modèles sont des courses de référence utilisées pour décrire
les services en fréquence (on ne décrit alors qu'une course qui sera
répétée à intervalle régulier) ou en cadences (on décrit alors toutes
les courses passant dans un créneau d'une heure).

![image](media/image4.svg)
*Template Service Journey – Modèle conceptuel*

<span class="hl">Pour les courses en fréquence le calcul du temps de
parcours sera réalisé par simple différence des heures de départs
(DepartureTime) aux différents arrêts de la course modèle. Par
convention, la course modèle pour les services en fréquence sera, en
termes d'horaire de passage, la première course de la tranche horaire
décrite (avec généralement un calage au premier arrêt sur l'heure de
début de la tranche horaire).</span>

<span class="hl">Pour les courses en cadence on prendra comme
convention de n'indiquer que les minutes des horaires de passage
(l'heure sera donc fixe, à 0, un arrêt desservi toutes les heures dix,
vingt-cinq et cinquante, aura donc des horaire 0:10, 0:25 et 0:50). Il
ne s'agit là que d'une convention, dans tous les cas, la partie heure de
l'horaire de passage peut être ignorée dans le cadre des
cadences.</span>

<div class="table-title">TemplateVehicleJourney – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 23%" />
<col style="width: 8%" />
<col style="width: 42%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em>ServiceJourney</em></td>
<td><em>::></em></td>
<td>TEMPLATE SERVICE JOURNEY hérite de SERVICE JOURNEY.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>TemplateVehicle­JourneyType</strong></em></td>
<td><em>TemplateVehicle­JourneyTypeEnum</em></td>
<td>0:1</td>
<td><p>Type de COURSE MODÈLE (avec voyageur). Ce type est codifié de la façon suivante:</p>
<ul>
<li><p><em>Headway :</em> course en fréquence</p></li>
</ul>
<blockquote>
<p><em>Rhythmic :</em> course cadencée</p>
</blockquote></td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td><em><strong>frequencyGroups</strong></em></td>
<td><em>JourneyFrequencyGroup</em></td>
<td>0:*</td>
<td><p>Référence à la description du service en fréquence ou en cadence que la COURSE MODÈLE décrit.</p>
<p><span class="hl">Seules les références </span><em><strong><span class="hl">xxxxRef</span></strong></em><span class="hl"> (</span><em><strong><span class="hl">HeadwayJourneyGroupRef</span></strong></em><span class="hl"> pour les services en fréquence ou </span><em><strong><span class="hl">RhythmicalJourneyGroupRef</span></strong></em><span class="hl"> pour les services en cadence) seront utilisées dans le cadre du profil.</span></p></td>
</tr>
</tbody>
</table>

### Course en fréquence

<div class="table-title">HeadwayJourneyGroup – Element</div>


| **Classifi­cation** | **Name**                        | **Type**                | **Cardin­ality** | **Description**                                                             |
|---------------------|---------------------------------|-------------------------|------------------|-----------------------------------------------------------------------------|
| *::>*               | *::>*                           | *JourneyFrequencyGroup* | *::>*            | HEADWAY JOURNEY GROUP hérite de JOURNEY FREQUENCY GROUP.                    |
|                     | ***Scheduled­HeadwayInterval*** | *xsd:duration*          | 0:1              | INTERVAL DE PASSAGE planifié (temps prévu entre deux passages de véhicule). |
|                     | ***Description***               | *MultilingualString*    | 0:1              | Description du service en fréquence                                         |

<div class="table-title">JourneyFrequencyGroup – Element (abstrait)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em>GroupOfEntities</em></td>
<td><em>::></em></td>
<td>JOURNEY FREQUENCY GROUP hérite de GROUP OF ENTITies <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>FirstDeparture­Time</strong></em></td>
<td><em>xsd:time</em></td>
<td>1:1</td>
<td><p>Heure du premier départ dans le GROUPE DE FRÉQUENCE.</p>
<p>Il s'agit là de l'heure de passage du premier départ au premier arrêt de la course.</p>
<p><span class="hl">S'il n'y a pas de régulation des heures de premier départ dans les tranches horaires, on indiquera uniquement l'heure de début de tranche horaire (pour un bus toute les 10 minutes de 8h00 à 9h30 on indiquera donc 8h00 même s'il n'y a pas de garantie d'un départ à 8h00).</span></p></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>LastDeparture­Time</strong></em></td>
<td><em>xsd:time</em></td>
<td>0:1</td>
<td><p>Heure du dernier départ dans le GROUPE DE FRÉQUENCE.</p>
<p>Il s'agit là de l'heure de passage du dernier départ au premier arrêt de la course.</p>
<p><span class="hl">S'il n'y a pas de régulation des heures de dernier départ dans les tranches horaires, on indiquera uniquement l'heure de fin de tranche horaire (pour un bus toute les 10 minutes de 8h00 à 9h30 on indiquera donc 9h30 même s'il n'y a pas de garantie d'un départ à 9h30).</span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>DayOffset</strong></em></td>
<td><em>xsd:integer</em></td>
<td>0:1</td>
<td>Éventuel décalage de jour pour l'heure de dernier départ (si la plage horaire est à cheval sur plusieurs jours).</td>
</tr>

<tr class="odd">
<td>«cntd»</td>
<td><em><strong>journeys</strong></em></td>
<td><em>VehicleJourneyRef</em></td>
<td>0:*</td>
<td><p>Liste des courses constituant ce GROUPE DE FRÉQUENCE. Cette relation permet d'avoir en même temps une description globale du service en fréquence complété par la liste de toutes les courses (et horaires associées) qui vont effectivement réaliser ce service.</p>
<p>Seul le <em><strong>ServiceJourneyRef</strong></em> est utilisé par le profil.</p></td>
</tr>
</tbody>
</table>

### Course en cadence

<div class="table-title">RhythmicalJourneyGroup – Element</div>

| **Classifi­cation** | **Name**  | **Type**                | **Cardin­ality** | **Description**                                                                                                 |
|---------------------|-----------|-------------------------|------------------|-----------------------------------------------------------------------------------------------------------------|
| *::>*               | *::>*     | *JourneyFrequencyGroup* | *::>*            | RHYTHMICAL JOURNEY GROUP hérite de JOURNEY FREQUENCY GROUP.                                                     |
| «cntd»              | timebands |                         |                  | <span class="hl">On utilisera uniquement les COURSEs MODÈLEs pour décrire les services en cadencement.</span> |

## Les Courses couplées

![image](media/image5.svg)
*Courses coupléed – Modèle conceptuel*

<div class="table-title">CoupledJourney – Element</div>

| **Classifi­cation** | **Name**          | **Type**             | **Cardin­ality** | **Description**                                                                                                                                                                                               |
|---------------------|-------------------|----------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *::>*               | *::>*             | *DataManagedObject*  | *::>*            | COUPLED JOURNEY hérite de DATA MANAGED OBJECT <span class="hl">(</span>*<span class="hl">voir le document </span>**<span class="hl">Profil NeTEx éléments communs</span>***<span class="hl">)</span>. |
|                     | ***Description*** | *MultilingualString* | 0:1              | Description de la COURSE COUPLÉE <span class="hl">(texte utilisable pour l'information voyageur)</span>.                                                                                                    |
| «cntd»              | ***journeys***    | *VehicleJourney*     | 0:\*             | Référence vers les COURSEs qui sont associées ensemble.                                                                                                                                                       |

### Parties de courses couplées

<div class="table-title">JourneyPartCouple – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em>DataManagedObject</em></td>
<td><em>::></em></td>
<td>JOURNEY PART COUPLE hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Description of JOURNEY PART COUPLE.</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>StartTime</strong></em></td>
<td><em>xsd:time</em></td>
<td>1:1</td>
<td>Heure de début du couplage <span class="hl">(heure de départ au point de départ)</span></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>StartTimeDayOffset</strong></em></td>
<td><em>DayOffsetType</em></td>
<td>0:1</td>
<td>Nombre de jours de décalage par rapport au jour de départ de la COURSE.</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>EndTime</strong></em></td>
<td><em>xsd:time</em></td>
<td>1:1</td>
<td><p>Heure de fin du couplage.</p>
<p><span class="hl">Il s'agit de l'heure d'arrivée au point de d'arrivé, ou à défaut de l'heure de premier départ du point d'arrivée (première des courses couplées à quitter le point d'arrivée).</span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>EndTimeDayOffset</strong></em></td>
<td><em>DayOffsetType</em></td>
<td>0:1</td>
<td>Nombre de jours de décalage par rapport au jour de départ de la COURSE.</td>
</tr>
<tr class="even">
<td>«FK»</td>
<td><em><strong>FromPointRef</strong></em></td>
<td><em>ScheduledStopPointRef</em></td>
<td>1:1</td>
<td>POINT D'ARRÊT PLANIFIÉ où débute le couplage.</td>
</tr>
<tr class="odd">
<td>«FK»</td>
<td><em><strong>ToPointRef</strong></em></td>
<td><em>ScheduledStopPointRef</em></td>
<td>1:1</td>
<td>POINT D'ARRÊT PLANIFIÉ où se termine le couplage.</td>
</tr>
<tr class="even">
<td>«FK»</td>
<td><em><strong>MainPartRef</strong></em></td>
<td><em>JourneyPartRef</em></td>
<td>1:1</td>
<td>PARTIE DE COURSE principale (à référencer pour l'information voyageur en particulier).</td>
</tr>
<tr class="odd">
<td>«cntd»</td>
<td><em><strong>joinedParts</strong></em></td>
<td><em>JourneyPartRef</em></td>
<td>0:*</td>
<td>PARTIEs DE COURSEs jointes à la PARTIE DE COURSE principale.</td>
</tr>
<tr class="even">
<td>«FK»</td>
<td><em><strong>TrainNumberRef</strong></em></td>
<td><em>TrainNumberRef</em></td>
<td>0:1</td>
<td>Numéro de train associé à la partie de courses couplées.</td>
</tr>
</tbody>
</table>

## Les correspondances entre course

<div class="table-title">ServiceJourneyInterchange – Element</div>

| **Classifi­cation** | **Name**                  | **Type**                | **Cardin­ality** | **Description**                                                                                                                                         |
|---------------------|---------------------------|-------------------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| *::>*               | *::>*                     | *Interchange*           | *::>*            | SERVICE JOURNEY INTERCHANGE hérite de INTERCHANGE.                                                                                                      |
| «FK»                | ***FromPointRef***        | *ScheduledStopPointRef* | 1:1              | POINT D'ARRÊT planifié au départ de la correspondance.                                                                                                  |
|                     | ***~~FromVisitNumber~~*** |                         |                  | <span class="hl">On utilisera les horaires de passage et de correspondance pour distinguer deux passages au même point d'arrêt, si nécessaire.</span> |
| «FK»                | ***ToPointRef***          | *ScheduledStopPointRef* | 1:1              | POINT D'ARRÊT planifié auquel donne accès la correspondance.                                                                                            |
|                     | ***~~ToVisitNumber~~***   |                         |                  | <span class="hl">On utilisera les horaires de passage et de correspondance pour distinguer deux passages au même point d'arrêt, si nécessaire.</span> |
| «FK»                | ***FromJourneyRef***      | *ServiceJourneyRef*     | 1:1              | COURSE de départ.                                                                                                                                       |
| «FK»                | ***ToJourneyRef***        | *ServiceJourneyRef*     | 1:1              | COURSE à laquelle donne accès la correspondance.                                                                                                        |

<div class="table-title">Interchange – Element (abstrait)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><em>::></em></td>
<td><em>::></em></td>
<td><em>DataManagedObject</em></td>
<td><em>::></em></td>
<td>INTERCHANGE hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>




<tr class="odd">
<td>«FK»</td>
<td><em><strong>ConnectionRef</strong></em></td>
<td><em>ConnectionRef</em></td>
<td>0:1</td>
<td>Lien avec la CORRESPONDANCE physique sur laquelle s'opère la CORRESPONDANCE ENTRE COURSEs <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx Réseau</span></strong></em><span class="hl">)</span>.</td>
</tr>

<tr class="odd">
<td></td>
<td><em><strong>StaySeated</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td><p>Permet d'indiquer que la course en correspondance est assurée par le même véhicule que la course amenante et que le passager peut simplement rester dans le véhicule et n'a donc pas besoin de descendre.</p>
<p><span class="hl">Cela sera utile pour les lignes en boucle par exemple, ou encore si l'on décide de modéliser un changement d'exploitant par des courses distinctes (cas des RER A et B en région parisienne par exemple).</span></p></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>CrossBorder</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td>Indique que l’INTERCHANGE implique le franchissement d’une frontière nationale.</td>
</tr>




<tr class="odd">
<td>«cntd»</td>
<td><em><strong>Interchange­TimesGroup</strong></em></td>
<td><em>InterchangeTimesGroup</em></td>
<td>0:*</td>
<td>Information horaire de la correspondance.</td>
</tr>

<tr class="odd">
<td>«cntd»</td>
<td><em><strong>notice­Assignments</strong></em></td>
<td><em>NoticeAssignmentView</em></td>
<td>0:*</td>
<td>NOTE associé à la correspondance <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>
</tbody>
</table>

<div class="table-title">InterchangeTimesGroup – Element (objet inclus)</div>

<table style="width:100%;">
<colgroup>
<col style="width: 8%" />
<col style="width: 23%" />
<col style="width: 16%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>



<tr class="odd">
<td></td>
<td><em><strong>StandardTransferTime</strong></em></td>
<td><em>xsd:duration</em></td>
<td><p>0:1</p>
<p><span class="hl">1:1</span></p></td>
<td><p>Temps de correspondance moyen (entre l'arrivée de l'amenant et le départ du partant)</p>
<p><span class="hl">Obligatoire dans le cadre du profil.</span></p>
<p><span class="hl">Voir la CORRESPONDANCE physique pour les détails de temps de parcours de la correspondance (temps de marche, etc.) (</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx Réseau</span></strong></em><span class="hl">)</span><span class="hl">.</span></p></td>
</tr>



</tbody>
</table>

## Position d'arrêt pour une course

Cette information complète l'**Affectation de train à quai** <span
class="hl">(</span>*<span class="hl">voir le document </span>**<span
class="hl">Profil NeTEx Réseau</span>***<span
class="hl">)</span><span class="hl"> </span>dans le cas où
l'identification des voitures est variable d'une course à l'autre.

<div class="table-title">TrainComponentLabelAssignment – Element</div>

| **Classifi­cation** | **Name**                | **Type**             | **Cardin­ality** | **Description**                                                                                                                                                                                                                |
|---------------------|-------------------------|----------------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *::>*               | *::>*                   | *DataManagedObject*  | *::>*            | TRAIN COMPONENT LABEL ASSIGNMENT hérite de DATA MANAGED OBJECT <span class="hl">(</span>*<span class="hl">voir le document </span>**<span class="hl">Profil NeTEx éléments communs</span>***<span class="hl">)</span>. |
|                     | ***Name***              | *MultilingualString* | 0:1              | Nom associé au COMPOSANT DE TRAIN (voiture) pour la course <span class="hl">(il s'agit du nom de la voiture tel qu'il figurera sur le billet du voyageur).</span>                                                            |
| «AK»                | ***VehicleJourneyRef*** | *VehicleJourneyRef*  | 0:1              | Référence de la course concernée.                                                                                                                                                                                              |
| «FK»                | ***TrainComponentRef*** | *TrainComponentRef*  | 0:1              | Référence du COMPOSANT DE TRAIN (voiture) concernée.                                                                                                                                                                           |

## Type de véhicule

![image](media/image6.svg)
*Type de Vehicule et Trains – Modèle Conceptuel*

<div class="table-title">VehicleType – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 24%" />
<col style="width: 8%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>::></td>
<td>::></td>
<td><em>DataManagedObject</em></td>
<td>::></td>
<td>VEHICLE TYPE hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>Name</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Nom du TYPE DE VEHICULE.</td>
</tr>

<tr class="odd">
<td></td>
<td><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Description du TYPE DE VEHICULE.</td>
</tr>


<tr class="even">
<td></td>
<td><em><strong>SelfPropelled</strong></em></td>
<td><em>boolean</em></td>
<td>0:1</td>
<td>Indique si le TYPE DE VEHICULE est autonome, ou s'il nécessite une motrice ou un véhicule tracteur.</td>
</tr>

<tr class="even">
<td></td>
<td><em><strong>TypeOfFuel</strong></em></td>
<td><em>TypeOfFuelEnum</em></td>
<td>0:1</td>
<td><p>Type de carburant du TYPE DE VEHICULE:</p>
<ul>
<li><p><em>petrol :</em> essence</p></li>
<li><p><em>diesel:</em> diesel</p></li>
<li><p><em>naturalGas :</em> gaz</p></li>
<li><p><em>biodiesel :</em> diesel bio</p></li>
<li><p><em>electricity :</em> électrique</p></li>
<li><p><em>other :</em> autre</p></li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>EuroClass</strong></em></td>
<td><em>xsd:normalizedString</em></td>
<td>0:1</td>
<td>Euroclasse du TYPE DE VEHICULE (normes européennes d'émission: <a href="http://fr.wikipedia.org/wiki/Normes_européennes_d&#39;émission">http://fr.wikipedia.org/wiki/Normes_europ%C3%A9ennes_d%27%C3%A9mission</a>).</td>
</tr>

<tr class="odd">
<td></td>
<td><em><strong>capacities</strong></em></td>
<td><em>PassengerCapacity</em></td>
<td>0:*</td>
<td><p>Capacité en passager (par classe tarifaire).</p>
<p><span class="hl">On utilisera directement les </span><em><strong><span class="hl">PassengerCapacity</span></strong></em><span class="hl"> (et non les références) dont on n'utilisera pas les champs issu de l'héritage DATA MANAGED OBJECT.</span></p></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>LowFloor</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td>Indique un plancher bas (pour l'accessibilité).</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>HasLiftOrRamp</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td>Indique que le TYPE DE VEHICULE est équipé d'une rampe ou d'une palette pour l'accès PMR</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>HasHoist</strong></em></td>
<td><em>xsd:boolean</em></td>
<td>0:1</td>
<td>Indique que le TYPE DE VEHICULE est équipé d'un monte-charge pour l'accès PMR</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>Length</strong></em></td>
<td><em>LengthType</em></td>
<td>0:1</td>
<td>Longueur du TYPE DE VEHICULE.</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>Width</strong></em></td>
<td><em>LengthType</em></td>
<td>0:1</td>
<td>Largeur du TYPE DE VEHICULE.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>Height</strong></em></td>
<td><em>LengthType</em></td>
<td>0:1</td>
<td>Hauteur du TYPE DE VEHICULE.</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>Weight</strong></em></td>
<td><em>WeightType</em></td>
<td>0:1</td>
<td>Poids du TYPE DE VEHICULE.</td>
</tr>

<tr class="even">
<td>«FK»</td>
<td><em><strong><del>ClassifiedAsRef</del></strong></em></td>
<td></td>
<td></td>
<td><span class="hl">On utilise le champ Brand de l'héritage DATA MANAGED OBJECT pour éventuellement indiquer la marque et/ou le modèle du véhicule.</span></td>
</tr>




</tbody>
</table>

<div class="table-title">PassengerCapacity – Element (objet inclus)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 21%" />
<col style="width: 20%" />
<col style="width: 5%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>::></td>
<td>::></td>
<td><em>DataManagedObject</em></td>
<td>::></td>
<td><p>PASSENGER CAPACITY hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span></p>
<p><span class="hl">Champs non utilisés dans le cadre du profil.</span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>FareClass</strong></em></td>
<td><em>FareClassEnum</em></td>
<td>0:1</td>
<td><p>Classe pour laquelle on indique la CAPACITÉ EN PASSAGERS:</p>
<ul>
<li><p><em>firstClass (première classe)</em></p></li>
<li><p><em>secondClass (seconde classe)</em></p></li>
<li><p><em>premiumClass (classe pemium)</em></p></li>
<li><p><em>businessClass</em></p></li>
<li><p><em>standardClass (classe normale)</em></p></li>
<li><p><em>economyClass (classe économique)</em></p></li>
<li><p><em>any (toutes)</em></p></li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>TotalCapacity</strong></em></td>
<td><em>NumberOfPassengers</em></td>
<td>0:1</td>
<td>Capacité totale.</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>SeatingCapacity</strong></em></td>
<td><em>NumberOfPassengers</em></td>
<td>0:1</td>
<td>Nombre de places assises.</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>StandingCapacity</strong></em></td>
<td><em>NumberOf­Passengers</em></td>
<td>0:1</td>
<td>Nombre de places debout.</td>
</tr>


<tr class="odd">
<td></td>
<td><em><strong>WheelchairPlace­Capacity</strong></em></td>
<td><em>NumberOf­Passengers</em></td>
<td>0:1</td>
<td>Nombre de places PMR</td>
</tr>
</tbody>
</table>

### Train

<div class="table-title">Train – Element</div>

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 16%" />
<col style="width: 21%" />
<col style="width: 8%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>::></td>
<td>::></td>
<td><em>VehicleType</em></td>
<td>::></td>
<td>TRAIN hérite de VEHICLE TYPE</td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>TrainSize</strong></em></td>
<td><em>TrainSizeStructure</em></td>
<td>0:1</td>
<td>Taille du train.</td>
</tr>
<tr class="even">
<td>«cntd»</td>
<td><em><strong>components</strong></em></td>
<td><em>TrainComponent</em></td>
<td>0:*</td>
<td><p>Ensemble des composants du train.</p>
<p><span class="hl">On utilisera directement les </span><em><strong><span class="hl">TrainComponent</span></strong></em><span class="hl"> (et non les références) dont on n'utilisera pas les champs issus de l'héritage de DATA MANAGED OBJECT (à l'exception de l'identifiant, indispensable si l'on souhaite préciser les alignements de voiture sur les quais).</span></p></td>
</tr>
</tbody>
</table>

<div class="table-title">TrainSize – Structure (objet inclus)</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 23%" />
<col style="width: 8%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>NumberOfCars</strong></em></td>
<td><em>xsd:nonNegativeInteger</em></td>
<td>0:1</td>
<td>Nombre de voitures <span class="hl">(voiture ou éventuellement bus couplé; par convention on indiquera 2 pour un véhicule articulé à 2 éléments).</span></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>TrainSizeType</strong></em></td>
<td><em>TrainSizeEnumeration</em></td>
<td>0:1</td>
<td><p>Type de taille du véhicule</p>
<ul>
<li><p><em>Normal</em></p></li>
<li><p><em>Short</em></p></li>
<li><p><em>Long</em></p></li>
</ul></td>
</tr>
</tbody>
</table>

<div class="table-title">TrainComponent – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 2%" />
<col style="width: 15%" />
<col style="width: 22%" />
<col style="width: 8%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td colspan="2"><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>::></td>
<td colspan="2">::></td>
<td><em>VersionedChild</em></td>
<td>::></td>
<td>TRAIN COMPONENT hérite de VERSIONED CHILD <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"><em><strong>Label</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Label du COMPOSANT DE TRAIN (s'il est fixe, on utilisera <em><strong>TrainComponentLabelAssignment</strong></em> sinon).</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Description du COMPOSANT DE TRAIN.</td>
</tr>
<tr class="odd">
<td>«FK»</td>
<td colspan="2"><em><strong><del>TrainRef</del></strong></em></td>
<td></td>
<td></td>
<td><span class="hl">Non utilisé car implicite du fait de l'imbrication XML, dans le contexte du profil.</span></td>
</tr>
<tr class="odd">
<td></td>
<td>b</td>
<td><em><strong>TrainElement</strong></em></td>
<td><em><strong>TrainElement</strong></em></td>
<td>1:1</td>
<td><p>ELEMENT DE TRAIN associé au COMPOSANT DE TRAIN.</p>
<p><span class="hl">On utilisera directement les </span><em><strong><span class="hl">TrainElement</span></strong></em><span class="hl"> (et non les références) dont on n'utilisera pas les champs issus de l'héritage DATA MANAGED OBJECT.</span></p></td>
</tr>
</tbody>
</table>

<div class="table-title">TrainElement – Element</div>

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 17%" />
<col style="width: 24%" />
<col style="width: 6%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Classifi­cation</strong></td>
<td><strong>Name</strong></td>
<td><strong>Type</strong></td>
<td><strong>Cardin­ality</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td>::></td>
<td>::></td>
<td><em>DataManagedObject</em></td>
<td>::></td>
<td><p>TRAIN ELEMENT hérite de DATA MANAGED OBJECT <span class="hl">(</span><em><span class="hl">voir le document </span><strong><span class="hl">Profil NeTEx éléments communs</span></strong></em><span class="hl">)</span>.</p>
<p><span class="hl">Champs non utilisés dans le cadre du profil.</span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><em><strong>Name</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Nom du TRAIN ELEMENT.</td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>0:1</td>
<td>Description du TRAIN ELEMENT.</td>
</tr>
<tr class="odd">
<td>«FK»</td>
<td><em><strong>TrainElement­Type</strong></em></td>
<td><em>TypeOfTrainElementEnum</em></td>
<td>1:1</td>
<td><p>Classification de l'ÉLÉMENT DE TRAIN:</p>
<ul>
<li><p><em>buffetCar :</em> voiture bar</p></li>
<li><p><em>carriage :</em> voiture passager</p></li>
<li><p><em>engine :</em> motrice</p></li>
<li><p><em>carTransporter :</em> transport de véhicule</p></li>
<li><p><em>sleeperCarriage :</em> voiture couchette</p></li>
<li><p><em>luggageVan :</em> voiture/compartiment à bagage</p></li>
<li><p><em>restaurantCarriage:</em> voiture restaurant</p></li>
<li><p><em>other:</em> autre</p></li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>FareClasses</strong></em></td>
<td><em>FareClassEnum</em></td>
<td>0:*</td>
<td><p>Classe associé à l'ÉLÉMENT DE TRAIN:</p>
<ul>
<li><p><em>firstClass (première classe)</em></p></li>
<li><p><em>secondClass (seconde classe)</em></p></li>
<li><p><em>premiumClass (classe pemium)</em></p></li>
<li><p><em>businessClass</em></p></li>
<li><p><em>standardClass (classe normale)</em></p></li>
<li><p><em>economyClass (classe économique)</em></p></li>
<li><p><em>any (toutes)</em></p></li>
</ul></td>
</tr>





</tbody>
</table>

### Train composé

<div class="table-title">CompoundTrain – Element</div>

| **Classifi­cation** | **Name**         | **Type**               | **Cardin­ality** | **Description**                                                                                                                              |
|---------------------|------------------|------------------------|------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| ::>                 | ::>              | *VehicleType*          | ::>              | COMPOUND TRAIN hérite de VEHICLE TYPE                                                                                                        |
|                     | ***components*** | *TRainInCompoundTrain* | 1:\*             | Références aux TRAINs constituant le TRAIN composé. C'est une liste ordonnée (en commençant par la tête de train dans le sens de la marche). |

# Entêtes NeTEx

*Note: les entêtes NeTEx sont présentés dans le document éléments
communs. Seules les spécificités du profil NETEX_HORAIRE sont présentées
ici.*

## TypeOfFrame : type spécifique *NETEX_HORAIRE*

Le présent profil utilise un *TypeOfFrame* spécifique, identifié
***NETEX_HORAIRE***. Il apparaitra systématiquement et explicitement
dans les éléments ***members*** du ***GeneralFrame***.

<div class="table-title">TypeOfFrame – Element</div>

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 17%" />
<col style="width: 19%" />
<col style="width: 12%" />
<col style="width: 41%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Classifi­cation</strong></th>
<th><strong>Nom</strong></th>
<th><strong>Type</strong></th>
<th></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>::></td>
<td>::></td>
<td><em>TypeOfValueDataManagedObject</em></td>
<td><em>::>::></em></td>
<td><p>TYPE OF FRAME hérite de TYPE OF VALUE.</p>
<p><span class="hl">L'Id est imposé à NETEX_HORAIRE</span></p></td>
</tr>


<tr class="even">
<td>«cntd»</td>
<td><em><strong>classes</strong></em></td>
<td><em>ClassInContextRef</em></td>
<td>0:*</td>
<td><p>Liste des classes pouvant être contenu dans ce TYPE OF FRAME.</p>
<p><span class="hl">La liste est fixe pour NETEX_ HORAIRE:</span></p>
<ul>
<li><p><span class="hl">SERVICE JOURNEY</span></p></li>
</ul>
<ul>
<li><p><span class="hl">FLEXIBLE SERVICE PROPERTIES</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TEMPLATE SERVICE JOURNEY</span></p></li>
</ul>
<ul>
<li><p><span class="hl">HEADWAY JOURNEY GROUP</span></p></li>
</ul>
<ul>
<li><p><span class="hl">RHYTHMICAL JOURNEY GROUP</span></p></li>
</ul>
<ul>
<li><p><span class="hl">SERVICE JOURNEY INTERCHANGE</span></p></li>
</ul>
<ul>
<li><p><span class="hl">VEHICLE TYPE</span></p></li>
</ul>
<ul>
<li><p><span class="hl">COUPLED JOURNEY</span></p></li>
</ul>
<ul>
<li><p><span class="hl">JOURNEY PART COUPLE</span></p></li>
</ul>
<ul>
<li><p><span class="hl">JOURNEY PART</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN COMPONENT</span></p></li>
</ul>
<ul>
<li><p><span class="hl">COMPOUND TRAIN</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN NUMBER</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN COMPONENT LABEL ASSIGNMENT</span></p>
<p><span class="hl">Il faut noter que certains éléments ne seront utilisés que pour les descriptions des services ferrés (généralement longue distance, sauf pour TRAIN NUMBER et TRAIN). Il s'agit de :</span></p></li>
</ul>
<ul>
<li><p><span class="hl">COUPLED JOURNEY</span></p></li>
</ul>
<ul>
<li><p><span class="hl">JOURNEY PART COUPLE</span></p></li>
</ul>
<ul>
<li><p><span class="hl">JOURNEY PART</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN COMPONENT</span></p></li>
</ul>
<ul>
<li><p><span class="hl">COMPOUND TRAIN</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN NUMBER</span></p></li>
</ul>
<ul>
<li><p><span class="hl">TRAIN COMPONENT LABEL ASSIGNMENT</span></p></li>
</ul></td>
</tr>


</tbody>
</table>

<div class="table-title">TypeOfValue (pour le TypeOfFrame NETEX\_ HORAIRE) – Element</div>

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 12%" />
<col style="width: 14%" />
<col style="width: 8%" />
<col style="width: 29%" />
<col style="width: 29%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Classifi­cation</strong></th>
<th><strong>Name</strong></th>
<th><strong>Type</strong></th>
<th></th>
<th><strong>Description</strong></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>::></td>
<td>::></td>
<td><em>DataManagedObject</em></td>
<td>::></td>
<td><p>TYPE OF VALUE hérite de DATA MANAGED OBJECT.</p>
<p><span class="hl">L’attribut </span><em><strong><span class="hl">version</span></strong></em><span class="hl"> portera la version du profil</span>.</p>
<p><span class="hl">L'Identifiant du TYPE OF VALUE est imposé à NETEX_ HORAIRE</span>.</p></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>Name</strong></em></td>
<td><em>MultilingualString</em></td>
<td>1:1</td>
<td><p>Nom du TYPE OF VALUE.</p>
<p><span class="hl">Imposé à « NETEX HORAIRE»</span>.</p></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td><em><strong>Description</strong></em></td>
<td><em>MultilingualString</em></td>
<td>1:1</td>
<td><p>Description du TYPE OF VALUE.</p>
<p><span class="hl">Imposé à « Profil d’échange français NETEX HORAIRE»</span>.</p></td>
<td></td>
</tr>
</tbody>
</table>

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
