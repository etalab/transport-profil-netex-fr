---
title: "SIRI"
date: 2021-09-09T13:21:16+02:00
draft: false
tags: ["elixir"]
---

CN03

Date: 2019-03

Nom_fichier

T

Secretariat: xxxx

Service Interface for Real-time information (SIRI) – Profil National
France

Einführendes Element — Haupt-Element — Ergänzendes Element

Élément introductif — Élément central — Élément complémentaire

ICS:

|                                                      |
| ---------------------------------------------------- |
| CCMC will prepare and attach the official title page |

Table des matières Page

[Avant-propos 6](#__RefHeading___Toc26889577)

[Introduction 8](#__RefHeading___Toc26889578)

[1 Domaine d’application 9](#domaine-dapplication)

[1.1 Profils 9](#profils)

[1.2 Qualité & Cohérence des données 9](#qualité-cohérence-des-données)

[1.3 Références Normatives 10](#références-normatives)

[1.4 Autres documents 10](#autres-documents)

[2 Termes et définitions 11](#termes-et-définitions)

[2.1 Cas général 11](#cas-général)

[2.2 Définition de la structure LEADER
11](#définition-de-la-structure-leader)

[2.3 Référentiel théorique 12](#référentiel-théorique)

[3 Description du profil d’échange 12](#description-du-profil-déchange)

[3.1 Règles de gestion du profil 12](#règles-de-gestion-du-profil)

[3.2 Conventions & Représention des messages
12](#conventions-représention-des-messages)

[4 Partie I - Description du cadre 15](#partie-i---description-du-cadre)

[4.1 Définition des concepts fondamentaux
15](#définition-des-concepts-fondamentaux)

[4.2 Cas d’usage 15](#cas-dusage)

[5 Partie II - Application du Profil SIRI France
22](#partie-ii---application-du-profil-siri-france)

[5.1 Modalités d’application 22](#modalités-dapplication)

[5.2 Implémentations locales: éléments à préciser dans les protocoles
d’accord
22](#implémentations-locales-éléments-à-préciser-dans-les-protocoles-daccord)

[5.3 Référentiels de données 23](#référentiels-de-données)

[5.4 Gestion des Identifiants 26](#gestion-des-identifiants)

[5.5 Gestion des abonnements 32](#gestion-des-abonnements)

[5.6 Service SIRI Discovery 41](#service-siri-discovery)

[5.7 Gestion des versions du profil SIRI FR
49](#gestion-des-versions-du-profil-siri-fr)

[6 Partie III. Description détaillée des messages
51](#partie-iii.-description-détaillée-des-messages)

[6.1 Estimated Timetable 51](#estimated-timetable)

[6.2 Stop Monitoring 65](#stop-monitoring)

[6.3 Connection Monitoring 97](#connection-monitoring)

[6.4 Vehicle Monitoring 108](#vehicle-monitoring)

[6.5 General Message 113](#general-message)

[7 Eléments techniques des messages
124](#eléments-techniques-des-messages)

[7.1 En-têtes des requêtes 124](#en-têtes-des-requêtes)

[7.2 En-têtes des réponses 128](#en-têtes-des-réponses)

[7.3 Abonnement 132](#abonnement)

[7.4 Vérification de l’état des partenaires (service Check Status)
139](#vérification-de-létat-des-partenaires-service-check-status)

[Annex A Termes et définitions 143](#__RefHeading___Toc26889615)

[Annex B (informative) Service SIRI Situation Exchange
147](#__RefHeading___Toc26889616)

[Annex C (informative) SIRI Facility Monitoring
192](#__RefHeading___Toc26889694)

[Annex D (informative) Production TimeTable
203](#__RefHeading___Toc26889704)

[Bibliographie 213](#__RefHeading___Toc26889712)

<span id="__RefHeading___Toc26889577" class="anchor"></span>Avant-propos

Ce document présente de façon détaillée le profil SIRI National France
(également appelé « local agreement SIRI France »), soit la déclinaison
de la norme SIRI aux besoins métiers France. Il contient tous les
éléments nécessaires à sa compréhension, mais ne propose ni une
réécriture ni une traduction de l'ensemble des documents normatifs SIRI
:

-   Le lecteur devra donc se référer à la norme quand cela sera
    nécessaire, en particulier au niveau technique avant d'envisager
    toute implémentation de SIRI.

D'autre part, l'ensemble de la terminologie utilisée dans ce document
est celle de SIRI, et par voie de conséquence de TRANSMODEL version 6.0
.

-   Le lecteur est donc invité à se référer au document TRANSMODEL pour
    de plus amples précisions sur la terminologie, les concepts ou
    modèles de données sous-jacents.

Plus généralement, les notions manipulées dans ce document sont décrites
par l’ensemble de documents normatifs suivants :

-   SIRI : Service Interface for Real-time Information relating to
    public transport operations (EN 15531- 1 to 3 and CEN/TS 15531-4
    and 5)

    -   Part 1: Context and framework

    -   Part 2: Communications infrastructure

    -   Part 3: Functional service interfaces

    -   Part 4: Functional service interfaces - Facility Management

    -   Part 5: Functional service interfaces - Situation Exchange

-   TRANSMODEL : CEN EN 12896, Transmodel (version 6.0), Reference Data
    Model for Public Transport et Transmodel in UML (projet SITP
    2,version 0.1 04/09/2003)

-   NEPTUNE : Norme AFNOR - PR NF P99-506 Décembre 2009

Dans le document, les règles propres au profil sont présentées sur fond
gris. Les autres règles ont plus un rôle d'explication, d'accompagnement
ou de recommandation.

Ce document est structuré en trois parties :

-   Partie 1 : Contexte

Cette partie présente la démarche de construction du profil SIRIFrance,
les cas d’utilisation constatés ou présentés à titre d’exemple, et la
liste des services SIRI retenus, en se basant sur ces cas d’utilisation.

-   Partie 2 : Présentation des concepts fondamentaux du Profil

Cette partie présente les particularités et les options du profil SIRI
France : concepts fondamentaux, modélisation de cas spécifiques,
référentiels de données, modalités techniques d’échange.

-   Partie 3 : Description du profil d’échange

Cette partie décrit les conventions et les règles utilisées pour la
rédaction de ce profil.

-   Partie 4 : Description détaillée des messages

Cette partie présente le format des messages SIRI et les choix effectués
dans le contexte National France (utilisation ou non des champs,
cardinalités, …). Elle constitue à ce titre une description technique et
essentiellement un cadre fonctionnel à destination des développeurs et
intégrateurs.

Le lecteur dispose en annexe au présent document d’un glossaire composé
des définitions et autres acronymes.

*<u>A noter</u>* : les extraits de normes figurant dans cet ouvrage sont
reproduits avec l’accord de l’AFNOR. Seul le texte original et complet
de la norme telle que diffusée par l'AFNOR – accessible via le site
Internet www.afnor.fr – possède une valeur normative.

<span id="__RefHeading___Toc26889578" class="anchor"></span>Introduction

La norme SIRI (Service Interface for Real time Information) définit le
protocole d’échange de l’information Temps Réel pour les transports
collectifs (format XML). SIRI se base sur le modèle de données de
référence du transport public : TRANSMODEL. SIRI a été élaborée avec la
participation initiale de la France, l’Allemagne ( Verband Deutscher
Verkehrsunternehmen ), en Scandinavie et au Royaume-Uni ( UK Real Time
Interest Group ).

Le groupe de travail français, CN03/GT7 (miroir du groupe européen CEN
TC278 / WG3 / SG7) a adopté le format d’échanges NEPTUNE (sous-ensemble,
ou profil, du format TRIDENT issu d'un projet Européen) comme base pour
les échanges de données de transport en commun. Le standard NEPTUNE,
aborde essentiellement les aspects référentiels des données échangées.
Il est normalisé à l’AFNOR sous le nom NEPTUNE, PR NF P99-506

Afin de fournir aux transporteurs et aux industriels un cadre normalisé
pour l’échange de données concernant l’information temps réel, le CEN
TC278 / WG3 / SG7 a décidé de lancer le projet **SIRI** (**S**ervice
**I**nterface for **R**ealtime **I**nformation) dès 2004.

Aujourd’hui, la norme SIRI version 2.0 peut servir de base à toute
implémentation des échanges de données temps réel, elle assure une
compatibilité ascendante avec la version 1.0 qu'elle précise et lui
ajoute quelques fonctions et attributs issus des retours d'expérience de
mise en œuvre de la version 1.0.

Le présent document contient le profil d’utilisation de cette
spécification technique dans un contexte national francais.

Il est complété par un ensemble de documents d’accompagnement : Se
reporter au paragraphe Error: Reference source not found du présent
document.

# Domaine d’application

Le profil objet du present document s’applique à la spécification
technique SIRI (documents \[R5\] à \[R9\] §2). Les objectifs de ce
profil sont rappelés dans la suite de ce paragraphe.

## Profils

La mise en place d’un profil normatif répond au constat suivant :

-   Les normes sont par nature et définition des documents consensuels,
    en particulier pour les documents de normalisations publiés par le
    CEN, définis dans un contexte international. Cela signifie que d'une
    part elles prennent en compte de très nombreux besoins car elles ont
    été établies à un niveau européen, et d'autre part elles n'imposent
    pas une implémentation exhaustive immédiate, mais permettent une
    implémentation progressive et qui peut être limitée à un besoin bien
    identifié.

Ces normes prennent en compte des besoins d’implémentation qui vont
au-delà des besoins nationaux.

-   La contrepartie de cette ouverture est que l'on peut facilement
    aboutir à des systèmes SIRI incompatibles alors même qu'ils
    respectent la norme : par exemple, pour peu qu'ils n'implémentent
    pas les mêmes services.

-   Les documents normatifs sont bien souvent très détaillés et
    volumineux, rendant leur consultation et lecture difficiles.

-   Des éléments proposés par la norme sont optionnels, lors de
    l’implémentation d’une application conforme à la norme il doit être
    décidé si ils sont ou non utilisés.

-   Les spécifications techniques SIRI sont issues de ces processus de
    normalisation internationaux et intègrent des mécanismes répondant à
    des besoins Allemands ou Suisse par exemple y sont aussi intégrés
    des mécanismes pour faciliter la compatibilité avec la norme
    française NEPTUNE, Britannique TransXChange, NOPTIS suédoise, …

La norme SIRI recommande donc l'établissement d'un « Local Agreement »
ou profil SIRI, qui permettra de contraindre et restreindre son
implémentation dans le cadre d'un échange donné – ici, dans le cas
présent, au niveau national France.

De plus, la norme SIRI fournit un guide pour l'établissement de ce
profil.

## Qualité & Cohérence des données

Un des objectifs du profil est de simplifier et améliorer
l’interopérabilité. L’interopérabilité ne peut être atteinte uniquement
sur la base de la conformité au profil sans s’assurer de la qualité des
données véhiculées : Cohérence des données, conforme au format et
decrivant la réalité.

En conséquence le profil doit être accompagné d’un ensemble de règles de
cohérence et de qualité spécifiquement concues pour la mise en œuvre du
profil SIRI. Le respect des règles ne garantie cependant pas à 100% la
qualité d’un jeu de données mais va permettre de minimiser les problèmes
de cohérence.

## Références Normatives

Les documents de référence suivants sont indispensables pour
l'application du présent document. Pour les références datées, seule
l'édition citée s'applique. Pour les références non datées, la dernière
édition du document de référence s'applique (y compris les éventuels
amendements).

\[R1\] EN12896 Public Transport Reference Data Model Part 1 à Part 4

-   Part 1 : Common Concepts (corresponds to
    [NeTEx](http://www.transmodel-cen.eu/standards/netex/) Part 1
    -Framework)

-   Part 2: Public Transport Network Topology (corresponds to
    [NeTEx](http://www.transmodel-cen.eu/standards/netex/) Part 1-
    Topology)

-   Part 3 : Timing Information and Vehicle Scheduling (corresponds to
    [NeTEx](http://www.transmodel-cen.eu/standards/netex/) Part 2)

\[R2\] CEN/TS 16614-1 Network and Timetable Exchange (NeTEx) - Network
description

\[R3\] CEN/TS 16614-2 Network and Timetable Exchange (NeTEx) - Timing
information

\[R4\] CEN/TS 16614-3 Network and Timetable Exchange (NeTEx) - Fare
description

\[R5\] EN 15531-1, Public transport - Service interface for real-time
information relating to public transport operations - Part 1: Context
and framework

\[R6\] EN 15531-2, Public transport - Service interface for real-time
information relating to public transport operations - Part 2:
Communications infrastructure

\[R7\] EN 15531-3, Public transport - Service interface for real-time
information relating to public transport operations - Part 3: Functional
service interfaces

\[R8\] CEN/TS 15531-4, Public transport - Service interface for
real-time information relating to public transport operations - Part 4:
Functional service interfaces: Facility Monitoring

\[R9\] CEN/TS 15531-5, Public transport - Service interface for
real-time information relating to public transport operations - Part 5:
Functional service interfaces - Situation Exchange

## Autres documents

Profil Netex France : Arrêts

\[R10\] T1 Éléments communs aux profils d'échange pour les informations
planifiées du transport en commun

\[T10.1\] T2 NeTEx - Profil Français de NETEx: éléments communs

\[T10.2\] T2 NeTEx - Profil Français pour les Arrêts

\[T10.3\] T2 NeTEx - Profil Français pour les horaires \[T10.4\] T2
NeTEx - Profil Français pour les réseaux

# Termes et définitions

## Cas général

Dans le cadre de ce document, les termes et definitions applicables sont
ceux définis par les normes

-   EN 12896 (Transmodel V6) \[R1\]

-   CEN/TS 16614 (NeTEx) \[R2\]\[R3\]\[R4\]

-   CEN/TS 15531 (SIRI).\[R5\]\[R6\]\[R7\]\[R8\]\[R9\]

##  Définition de la structure LEADER

La description des services SIRI fait référence à une structure LEADER.

|        |     |     |              |                       |
| ------ | --- | --- | ------------ | --------------------- |
| LEADER | ::: | 1:1 | xxx­Delivery | voir xxx**Delivery**. |

Le Leader est (indirectement) défini dans la spécification SIRI
\[R6\]par les attributs suivants

|                       |                         |                                |     |                                       |                          |                   |                                                                                                                |                                                                                                                                                                                                          |                                                                                                      |
| --------------------- | ----------------------- | ------------------------------ | --- | ------------------------------------- | ------------------------ | ----------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| xxxDelivery           |                         |                                |     |                                       | +Structure               |                   | Delivery for xxx Service                                                                                       |                                                                                                                                                                                                          |                                                                                                      |
| Log                   | Response­Timestamp      |                                | 1:1 |                                       | xsd:dateTime             |                   | Time individual response element was created.                                                                  |                                                                                                                                                                                                          |                                                                                                      |
| End­point prop­erties | RequestMessageRef       |                                | 0:1 |                                       | Message­Qualifier       |                   |                                                                                                                | For direct requests, Identifier of request that this Delivery satisfies.                                                                                                                                 |                                                                                                      |
|                       | SubscriberRef           |                                | 0:1 |                                       | Participant­Code        |                   |                                                                                                                | Required if Delivery is for a Subscription, Participant Reference of Subscriber.                                                                                                                         |                                                                                                      |
|                       | Subscription­FilterRef  |                                | 0:1 |                                       | SubcriptionFilterCode   |                   |                                                                                                                | Unique identifier of Subscription filter to which this subscription is assigned. If there is only a single filter, then can be omitted.                                                                  |                                                                                                      |
|                       | Subscription­Ref        |                                | 1:1 |                                       | Subscript­ion­Qualifier |                   |                                                                                                                | Required if Delivery is for a Subscription, Identifier of Subscription issued by Requestor. Unique within Subscriber (i.e. within ***ParticipantRef*** of Subscriber), and SIRI Functional Service type. |                                                                                                      |
| Deleg­ation           | DelegatorAddress        |                                | 0:1 |                                       | Xsd:anyURI               |                   | Address of original Consumer, i.e. requesting system to which delegating response is to be returned. +SIRI 2.0 |                                                                                                                                                                                                          |                                                                                                      |
|                       | DelegatorRef            |                                | 0:1 |                                       | Participant­Code        |                   |                                                                                                                | Identifier of delegating system that originated message. +SIRI 2.0                                                                                                                                       |                                                                                                      |
| Stat­us               | Status                  |                                | 0:1 |                                       | xsd:boolean              |                   |                                                                                                                | Whether the complete request could be processed successfully or not. Default is true. If any of the individual requests within the delivery failed, should be set to *false*.                            |                                                                                                      |
|                       | ErrorCondition          |                                | 0:1 |                                       | +Structure               |                   |                                                                                                                | Description of any error or warning conditions that apply to the specific functional request or response.                                                                                                |                                                                                                      |
|                       |                         |                                |     |                                       | choice                   |                   |                                                                                                                | One of the following Error codes.                                                                                                                                                                        |                                                                                                      |
|                       | a                       | Capability­Not­Supported­Error |     | -1:1                                  |                          | \+ Error          |                                                                                                                |                                                                                                                                                                                                          | Error: Capability not supported.                                                                     |
|                       | b                       |                                |     | AccessNot­Allowed­Error               |                          | +Error            |                                                                                                                |                                                                                                                                                                                                          | Error: Requestor is not authorised to the service or data requested.                                 |
|                       | c                       |                                |     | NoInfoFor­TopicError                  |                          | +Error            |                                                                                                                |                                                                                                                                                                                                          | Error: Valid request was made but service does not hold any data for the requested topic expression. |
|                       | d                       |                                |     | Allowed­Resource­Usage­Exceeded­Error |                          | +Error            |                                                                                                                |                                                                                                                                                                                                          | Error: Valid request was made but request would exceed the permitted resource usage of the client.   |
|                       | e                       |                                |     | OtherError                            |                          | +Error            |                                                                                                                |                                                                                                                                                                                                          | Error other than a well-defined category.                                                            |
|                       |                         | Description                    |     | 0:1                                   |                          | ErrorDescription |                                                                                                                |                                                                                                                                                                                                          | Description of Error.                                                                                |
|                       | ValidUntil              |                                | 0:1 |                                       | xsd:dateTime             |                   |                                                                                                                | End of data horizon of the data producer.                                                                                                                                                                |                                                                                                      |
|                       | Shortest­Possible­Cycle |                                | 0:1 |                                       | Positive­Duration­Type   |                   |                                                                                                                | Minimum interval at which updates can be sent.                                                                                                                                                           |                                                                                                      |
|                       | DefaultLanguage         |                                |     |                                       | Xsd:language             |                   |                                                                                                                | Default language for text elements.                                                                                                                                                                      |                                                                                                      |

## Référentiel théorique

Le référentiel théorique est l’objet d’un accord entre les parties.

Il repose sur des échanges :

-   non définis par le présent profil (NeTEx par exemple)

-   ou à base de service Discovery (cf paragraphe 5.6).

# Description du profil d’échange

## Règles de gestion du profil

Le present profil contient un ensemble de règles de gestion applicables.
Ces règles de gestion sont présentées sous forme tabulaire et
numérotées.

|        |                      |
| ------ | -------------------- |
| Numéro | Intitulé de la règle |

Des textes explicatifs viennent compléter les règles d’application du
profil FR

## Conventions & Représention des messages

Les messages constituant ce profil d'échange sont décrits en adoptant un
formalisme tabulaire. Les tableaux proposent ces colonnes:

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 17%" />
<col style="width: 11%" />
<col style="width: 39%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Organisational Group</td>
<td>Name of Element</td>
<td>Min :<br />
Max</td>
<td>Data Type</td>
<td>Description</td>
</tr>
</tbody>
</table>

La structure des tableaux présentée ici est exactement la même que celle
des tableaux des documents SIRI de référence ceci afin de simplifier le
passage d'un document à l'autre.

Les tableaux sont simplement complétés et enrichis des informations
propres au profil SIRI France.

Une description détaillée de la structure de ces tableaux est présentée
dans le document « **SIRI-part 1**-**4.3-Notation for XML model
structures of SIRI messages »**.

Pour mémoire les principaux éléments présentés sont les suivants :

-   Dans la documentation SIRI, les structures sont présentées sous
    forme tabulaire. L'en-tête des colonnes est supposé connu et n'est
    donc pas systématiquement répété.

-   Les tableaux utilisent un ensemble de conventions pour les éléments
    XML et leurs contraintes.

Les éléments constitutifs de ces tableaux sont présentés ci-dessous.

### Classification (Organisational Group label)

Cette première colonne précise la catégorie de l'élément, par exemple
‘*Payload’* (qui se traduit littéralement par « charge utile », et
correspond à la description de l'objet lui-même indépendamment de toute
donnée d'accompagnement, et autres en-têtes).

Par exemple :

-   Attributes

-   Log

-   Endpoint

-   Status

-   Payload

### Nom de l'élément (*Element Name*)

Cet élément correspond naturellement au nom de l'élément présenté. Si
l'élément appartient à une structure complexe, le nom de l'élément père
(ou racine) est présenté en haut du tableau.

Element names are shown in bold italics in the second column e.g.
**VehicleJourneyRef.** The parent element for which the table shows the
structure name is shown in the top left of the table.

La notation « :: » fait référence à un groupe d'éléments défini à un
autre endroit du document (la colonne Type de Données permettra de
retrouver cette définition)

Dans les cas d'éléments composés, une indication « voir ci-dessous »
figure dans la colonne type et les sous-éléments sont présentés en
dessous avec une indentation (c'est le cas de ***ErrorCondition*** dans
l'exemple ci-dessous).

### Cardinalité et choix(Multiplicity & Choice (Min:Max))

Cette colonne précise la cardinalité de l'élément sous la forme :

-   \[nombre minimal d'occurrences\]:\[nombre maximal d'occurrences\]

-   Un nombre d'occurrence valant « \* » signifie « nombre non limité ».

Si cet indicateur est préfixé d'un tiret (par exemple « **–1:1** ») cela
signifie qu'il faut choisir un élément (ou plusieurs) parmi une liste
indiquée (***choice*** au niveau XSD).

Si la cardinalité SIRI est précisée pour le profil SIRI France, cela
sera aussi noté, en complément dans cette colonne et surligné en gris.

Les différentes possibilités d'exprimer la cardinalité sont donc les
suivantes :

-   En noir sur fond blanc : la cardinalité est celle spécifiée par le
    document normatif SIRI (en particulier, toutes les notations de type
    « 1:1 » ou « 1:\* » signifient que le champ est obligatoire)

-   En noir surligné en gris: la cardinalité du document normatif SIRI
    est précisée par le profil SIRI France (pour rendre un champ
    facultatif obligatoire en Île-de-France par exemple). C'est alors la
    version surlignée en gris qui s'applique.

-   En noir surligné en vert : la cardinalité du document normatif SIRI
    est précisée par le profil SIRI France pour la mise en place des
    concentrateurs (pour les interfaces entre le concentrateur et le
    relais). En effet, les concentrateurs ont des spécificités, en
    particulier en terme de volumétrie et de mise en cohérence de
    données multi-sources qui nécessitent certaines adaptations par
    rapport au cas général. Les commentaires y attenant seront aussi
    surlignés en vert.

-   Il n’y a pas de cardinalité texte masqué : les champs en texte
    masqué sont les champs non retenus par le profil SIRI France, leur
    cardinalité d'origine est « 0:1 » ou « 0:\* » mais ils ne sont pas
    utilisés en France (techniquement ils ne sont pas interdits, et leur
    présence ne doit pas poser de problème d'interopérabilité, mais
    s'ils sont présents ils seront à priori ignorés).

### Type de données (*Data Type*)

Cette colonne indique le type de l'élément:

-   soit un type simple (SIRI ou XSD) comme *Positive­DurationType* ou
    *xsd:dateTime*

-   soit un type structuré, signalé par +*Structure* (la définition de
    la structure porte alors le nom de l'élément suffixé par le terme
    **Structure**)

-   les références (par identifiant) sont signalées, sous la forme
    *OperatorCode* (référence à un opérateur, dont on fournit le code ou
    identifiant, dans ce cas)

-   dans le cas des énumérations, la liste des valeurs est indiquée
    (éléments séparés par une barre verticale : « **\|** »)

-   Pour les types les plus classiques, l'abréviation est autorisée
    quand le nom est long (*NLString* pour *NaturalLanguageString* ou
    *Error* pour *ErrorStructure*).

### Description (Description)

On trouve dans cette colonne la description textuelle de l'élément.

Le tableau ci-dessous est un exemple de tableau SIRI (non traduit pour
celui-ci, étant donné que son contenu n'a pas d'importance).

# Partie I - Description du cadre

## Définition des concepts fondamentaux

Le présent profil s’appuie sur les concepts définis dans Transmodel
\[R1\]

## Cas d’usage

Les principaux cas d’usage SIRI, dans un environnement national France,
sont synthétisés dans la suite de ce paragraphe. Ils sont détaillées
dans le document d’accompagnement \[A1\].

Cette liste des cas d’usage ne se veut **pas exhaustive** et peut être
complétée localement pour répondre à des besoins spécifiques

Pour chaque cas d’usage, une **préconisation** de services SIRI à
implémenter est présentée en conclusion du paragraphe. Les
préconisations s’appuient sur les ‘bonnes pratiques’ d’implémentation
SIRI \[A3\].

Dans ce cadre chaque service SIRI d’un cas d’Usage est qualifié
‘Indispensable’ ou ‘Facultatif’.

-   Indispensable : indique que, pour le cas d’usage identifié, le
    respect des bonnes pratiques d’implémentation tend à l’utilisation
    de ce service. Dans le cas ou un autre service SIRI serait retenu,
    l’implémentation sortirait du contexte d’utilisation et
    correspondrait alors un autre cas d’usage.

-   La non implémentation d’un service Indispensable ne veut pas dire
    que cette implémentation n’est pas conforme au profil SIRI FR, seule
    la conformité aux règles de gestion et aux règles d’implémentation
    des services le sont.

-   Facultatif : indique que le service SIRI peut être utilisé en
    complément du ou des services SIRI obligatoires mais que le cas
    d’usage peut être respecté sans son implémnetation.

### Diffusion inter systemes

Ce cas d’usage doit permettre de communiquer à différents systèmes de
transport d’échanger des flux d’information relatifs à l’information
voyageur pour leur permettre de réaliser des traitements de cette
information independamment les uns des autres et en parfaite cohérence.

Dans ce cadre, SIRI permet l’échange d’information multimodale et multi
opérateurs. Ces flux ne sont pas à destination directe des usagers.

Les systèmes concernés peuvent être des SAE, des SIV, des Systèmes
d’affichage, …

Cet alignement repose sur un échange préalable de données théoriques
(Topologie et offre de transport) qui sont mises à jour entre les
différents systèmes interconnectés via SIRI.

Ces échanges s’appuient sur le protocole de communication SIRI définis
dans le partie 2 de la psécification

La description de ce cas d’usage est définie dans le document
d’accompagnement

### Diffusion Terminaux legers

Il s'agit ici de permettre à un utilisateur d'accéder aux informations
horaires temps réel (prochains passages avec indications de ligne, de
direction, ainsi que les éventuels messages) pour n’importe quel point
d’arrêt, indépendamment du transporteur, et ce à partir d'un terminal
mobile de type téléphone portable.

Ce service pourra ainsi être utilisé sur le réseau (à l'arrêt dans le
cas où il n'y aurait pas d'afficheur, permettant ainsi à l'exploitant de
mettre le service à disposition sans que les coûts ne soient trop
importants, autorisant ainsi plus facilement la couverture de ligne ou
zones à faible fréquentation) ou hors réseau (pour synchroniser son
départ avec l'arrivée du train ou du bus par exemple).

SIRI est ici utilisé pour permettre au système de présentation qui gère
le dialogue avec les terminaux mobiles d'accéder aux informations
horaires temps réel de prochain passage.

Ce cas d'utilisation peut être généralisé à un accès avec tout autre
type de terminal, en particulier via un accès de type Web, pour diffuser
les informations horaires et les informations de perturbation.

A noter que pour ce cas d’usage les protocoles de communications SIRI
light sont à privilégier.

La description de ce cas d’usage est définie dans le document
d’accompagnement

### Centrale de mobilité

Les centrales de mobilité prennent en compte les transports en commun
sur une échelle relativement large, impliquant ainsi quasi
systématiquement plusieurs transporteurs.

L'un des services clés de ce type de centrale de mobilité est souvent le
calcul d’itinéraires, qui de plus e plus ne se limite pas à la prise en
compte les horaires théoriques (pour cause d’indisponibilité des
données, et non pour des raisons techniques).

La prise en compte des informations temps réel est un besoin qui, dans
ce contexte, s'exprime à deux niveaux:

1.  la prise en compte des perturbations (prévues, c'est-à-dire connues
    plus ou moins longtemps avant le départ, ou inopinées) pour, d'une
    part, les signaler à l'usager et, d'autre part, lui proposer des
    solutions alternatives lui permettant de « sécuriser » son trajet,

2.  la prise en compte des informations horaires temps réel pour
    optimiser le déplacement (le train que l'on ne pensait pas pouvoir
    prendre à une correspondance devient disponible suite à un léger
    retard ou encore un retard trop important impliquant une
    modification de l'itinéraire, etc..).

L'apport de la norme SIRI est ici clairement de permettre aux SAE de
diffuser vers la centrale de mobilité l'ensemble des informations temps
réel nécessaires pour la mise en place des services.

La description de ce cas d’usage est définie dans le document
d’accompagnement

### Gestion des perturbations

La prise en compte des perturbations telle qu'elle est souvent mise en
oeuvre dans les systèmes actuels se limite souvent à un message textuel
libre ou pré-formaté et associé à un arrêt, une ligne, un itinéraire ou
une mission. La norme SIRI permet de transmettre la perturbation de
manière codifiée ; Elle permet :

-   de décrire finement la cause de la perturbation,

-   de lister les conséquences liées à cette perturbation,

-   de permettre une prise en compte par un calculateur d’itinéraires,

-   de générer automatiquement des messages, avec prise en compte du
    type de périphérique (petits messages pour les SMS, longs messages
    pour le Web, etc.) ou de générer ces messages en plusieurs langues
    (il ne s’agit naturellement pas d’une fonction de SIRI mais d’une
    fonction qui pourra être mise en œuvre par l’émetteur ou par le
    récepteur sur la base des données structurées),

<!-- -->

-   d'associer la perturbation à un tronçon de ligne,

-   de gérer des périodes de validité complexe (i.e. : du lundi au
    vendredi de 8 h à 18 h...),

-   de mettre à jour le « fil de perturbation » en ayant la possibilité
    d’identifier les mises à jour d'une perturbation.

La description de ce cas d’usage est définie dans le document
d’accompagnement

### Information PMR

Informer les PMR ou toute personne ayant des besoins particuliers (on
pensera en particulier aux handicaps auditifs, visuels, moteurs, etc.,
mais aussi à tous les besoins particuliers comme « utilisation d'une
poussette », « lourdement chargé en bagage », « jambe dans le plâtre »,
etc.) est aussi un besoin avéré.

Ce type de besoin comporte une composante temps réel afin de pouvoir
informer sur l'état des équipements et des services (i.e. :
disponibilité ou non d'un ascenseur, d'un escalier mécanique, d'une
palette, d'un dispositif visuel, etc.).

Sur la base des services SIRI des systèmes d'acquisition et de
supervision ou des systèmes impliquant une saisie par un opérateur (la
vérification d'état des équipements est aujourd'hui réalisée de façon
manuelle dans de très nombreux cas) peuvent diffuser leurs informations
de perturbation.

La description de ce cas d’usage est définie dans le document
d’accompagnement

### Concentrateur

Les concentrateurs permettent de rassembler au sein d’un même système un
ensemble d’informations voyageur d’origine et de formes diverses dans un
format pivot (en principe conforme aux concepts transmodel) pour les
mettre à disposition de systèmes Clients.

Le flux entrant et sortant du concentrateur peuvent s’appuyer sur SIRI.
En general les systèmes historiques peuvent fournir aux concentrateurs
les informations dans des formats autres, le concentrateur redistribuant
les données en utilisant SIRI.

-   les centrales de mobilité,

-   les systèmes pour les agents sur le terrain,

-   les afficheurs,

-   des terminaux dédiés (système prévu spécifiquement pour gérer un
    type de handicap),

-   etc.

### Conformité Directive EU

ACU

### Services SIRI applicables

<table style="width:100%;">
<colgroup>
<col style="width: 17%" />
<col style="width: 9%" />
<col style="width: 11%" />
<col style="width: 8%" />
<col style="width: 9%" />
<col style="width: 11%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 10%" />
</colgroup>
<thead>
<tr class="header">
<th>Service</th>
<th>Diffusion Inter Systèmes</th>
<th>Diffusion Terminaux Legers</th>
<th>Centrale de Mobilité</th>
<th>Diffusion dans les vehicules</th>
<th>Gestion des perturbations</th>
<th>Information PMR</th>
<th>Concentrateur</th>
<th>Directive EU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Horaires planifiés</p>
<p>Production Timetable</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Horaires calculés</p>
<p>Estimated Timetable</p></td>
<td>Indispensable</td>
<td></td>
<td>Indispensable</td>
<td></td>
<td></td>
<td></td>
<td>Indispensable</td>
<td>Indispensable <sup>1</sup></td>
</tr>
<tr class="odd">
<td><p>Horaires planifiés à l’arrêt</p>
<p>Stop Timetable</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Discovery Line</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>Facultatif<a href="#fn1" class="footnote-ref" id="fnref1" role="doc-noteref"><sup>1</sup></a></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Horaires calculés à l’arrêt</p>
<p>Stop Monitoring</p></td>
<td></td>
<td>Indispensable</td>
<td></td>
<td>Facultatif</td>
<td></td>
<td></td>
<td>Facultatif</td>
<td>Indispensable <sup>1</sup></td>
</tr>
<tr class="even">
<td>Discovery Stop</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>Facultatif<a href="#fn2" class="footnote-ref" id="fnref2" role="doc-noteref"><sup>2</sup></a></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Supervision des véhicules</p>
<p>Vehicle Monitoring</p></td>
<td></td>
<td></td>
<td></td>
<td>Indispensable</td>
<td></td>
<td></td>
<td>facultatif</td>
<td></td>
</tr>
<tr class="even">
<td><p>Correspondances planifiées</p>
<p>Connection Timetable</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Correspondances calculées</p>
<p>Connection Monitoring</p></td>
<td></td>
<td></td>
<td></td>
<td>Facultatif</td>
<td></td>
<td></td>
<td></td>
<td>Indispensable</td>
</tr>
<tr class="even">
<td><p>Messagerie</p>
<p>General Messaging</p></td>
<td>Facultatif</td>
<td>Facultatif</td>
<td>Facultatif</td>
<td>Indispensable</td>
<td>Facultatif</td>
<td>Facultatif</td>
<td>Indispensable</td>
<td>Indispensable</td>
</tr>
<tr class="odd">
<td><p>Gestion des événements</p>
<p>Situation Exchange</p></td>
<td></td>
<td></td>
<td>Indispensable</td>
<td>Facultatif</td>
<td>Indispensable</td>
<td>Indispensable</td>
<td>facultatif</td>
<td>Indispensable</td>
</tr>
<tr class="even">
<td><p>Etat des équipements</p>
<p>Facility Monitoring</p></td>
<td></td>
<td></td>
<td>Facultatif</td>
<td></td>
<td></td>
<td>Indispensable</td>
<td></td>
<td>Indispensable</td>
</tr>
</tbody>
</table>
<section class="footnotes" role="doc-endnotes">
<hr />
<ol>
<li id="fn1" role="doc-endnote"><p>En complément du Service ET<a href="#fnref1" class="footnote-back" role="doc-backlink">↩︎</a></p></li>
<li id="fn2" role="doc-endnote"><p>En complement du Service SM<a href="#fnref2" class="footnote-back" role="doc-backlink">↩︎</a></p></li>
</ol>
</section>

Règles de gestion

<table>
<colgroup>
<col style="width: 4%" />
<col style="width: 95%" />
</colgroup>
<tbody>
<tr class="odd">
<td>CU-1</td>
<td>Si le service SX est disponible, toute information diffusée via GM doit aussi l’être en SX</td>
</tr>
<tr class="even">
<td>CU-2</td>
<td><p>Si le service SIRI SX est implémenté, GM ne devient qu'un service pour compatibilité avec les systèmes ne sachant pas recevoir du SX.</p>
<p>SX devient la référence pour les informations circonstancielles et doit donc contenir toutes les informations.</p></td>
</tr>
</tbody>
</table>

# Partie II - Application du Profil SIRI France

## Modalités d’application

Après avoir retenu les services SIRI pour les cas d’utilisation
identifiés (Partie 1), les principales actions à effectuer sont les
suivantes:

Identifier les données de référence, objet de la partie 2 de ce
document :

-   Participants,

-   Identifiants des Lignes, des itinéraires et des missions,

-   Identifiants des Points d’Arrêt (et type de point d’arrêt…),

-   Identifiants des Correspondances,

-   Préciser les listes de valeurs supportées (*ServiceCategory*,
    *ProductCategory*, *VehicleFeature*)

1.  Définir le profil technique lui-même :

-   Type d’abonnement (1 ou 2 phases),

-   Support de la segmentation des messages,

-   Confirmation ou non, des notifications,

-   Filtres simples ou multiples,

-   Supervision de la disponibilité des partenaires,

-   Signification des champs fonctionnels,

-   …

2.  Préciser l’utilisation des champs facultatifs dans les messages des
    services retenus (un champ facultatif dans la norme peut être
    supprimé, devenir obligatoire ou rester facultatif dans le profil…)

3.  Définir éventuellement des extensions (ajout de champs non
    normalisés) propres à l’implémentation locale.

## Implémentations locales: éléments à préciser dans les protocoles d’accord

Le paragraphe suivant présente les aspects techniques à traiter pour
l’implémentation, il est à noter que ces aspects ne font pas partie
intégrante du local agreement SIRI France et sont présentés ci-dessous à
titre indicatif.

Le profil ne peut en effet pas définir tous les aspects nécessaires à la
mise en place d’un échange. Ces éléments devront donc être définis dans
le cadre des protocoles locaux établis entre les différents acteurs des
échanges.

1.  L'identification des infrastructures d’alimentation (et processus
    correspondant) : à définir spécifiquement pour chaque implémentation
    (par exemple le mode de connexion de l’interface SIRI au SAE…)

2.  Le choix d’utilisation des champs laissés facultatifs par le profil
    France dans les messages et services retenus (un champ facultatif
    peut être supprimé, devenir obligatoire ou rester facultatif), sans
    que la WSDL SIRI France ne soit modifiée. 

3.  Des préconisations pour la gestion et l'organisation des
    systèmes (annexe recommandée par la norme SIRI, à traiter dans le
    contexte de chaque protocole d’accord local) :

-   Contacts et responsables opérationnels,

-   Surveillance des services,

-   Période d’interruption des services,

-   Identification/gestion des anomalies.

## Référentiels de données

### Présentation du besoin

La mise en place d'un échange de données implique que les systèmes mis
en relation puissent identifier de façon non ambiguë les objets auxquels
ils font référence.

Cela est particulièrement vrai pour SIRI qui, de par sa vocation à
échanger des informations temps réel, ne re-décrit pas le référentiel
sous-jacent et le suppose donc connu:

Il sera donc indispensable, pour demander les prochains horaires de
passage à un arrêt, de connaître l'identifiant de l'arrêt en question.
Cela concerne tout un ensemble d'objets listés ci-dessous.

Il faut rappeler que l'identification de l'objet est une chose, mais que
le concept sous-jacent en est une autre:

La cohérence doit porter sur ces deux aspects. Les principaux concepts
utiles ont été évoqués au chapitre précédent. Pour les autres,
TRANSMODEL fait référence.

<u>Note</u>: le nom des objets est donné en Français et en Anglais, de
façon à simplifier une éventuelle recherche complémentaire dans les
documents normatifs.

### Références utilisées dans le cadre du profil SIRI France

<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 71%" />
</colgroup>
<thead>
<tr class="header">
<th>Donnée de référence</th>
<th>Référence adoptée pour le profil SIRI France</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Date et Heure</p>
<p>(Date &amp; Time)</p></td>
<td>ISO 8601</td>
</tr>
<tr class="even">
<td><p>Langue</p>
<p>(Language)</p></td>
<td>ISO 639-1</td>
</tr>
<tr class="odd">
<td><p>Localisation géographique</p>
<p>(Location)</p></td>
<td>WGS84 / gml (GML permettra d'échanger les localisations géographiques dans des référentiels projetés comme Lambert 2 étendu...)</td>
</tr>
<tr class="even">
<td><p>Fournisseur d'information</p>
<p>(Information Provider)</p></td>
<td><p>Voir le paragraphe correspondant (5.4.4-Error: Reference source not found)</p>
<p>Notion à mettre en relation avec le groupement ou le transporteur qui délivre l’information.</p></td>
</tr>
<tr class="odd">
<td><p>Point d'arrêt</p>
<p>(Stop Point)</p></td>
<td><p>Voir le paragraphe correspondant (5.4.2)</p>
<p>Dans l'état actuel des choses, il n'existe aucun référentiel global des points d’arrêt en France.</p></td>
</tr>
<tr class="even">
<td><p>Correspondance</p>
<p>(Connection)</p></td>
<td><p>Dans l'état actuel des choses, il n'existe aucun référentiel global des correspondances en France.</p>
<p>Dans un premier temps, l'identification des correspondances devra donc être réalisée au cas par cas, et définie entre les acteurs avant de débuter un échange. L'identification devra dans ce cas porter une indication signalant qu'elle est spécifique à un échange local.</p>
<p>Cela concernera uniquement les cas où l'on souhaite gérer une correspondance et où l'on souhaitera être informé du fait qu'elle n'est plus possible (le Bus signale qu'il décide de ne pas attendre le Train, par exemple).</p></td>
</tr>
<tr class="odd">
<td><p>Véhicule supervisé</p>
<p>(VehicleActivity)</p></td>
<td><p>Dans le cadre du profil SIRI France, cette donnée ne peut être utile que pour permettre d'identifier la position d’un véhicule.</p>
<p>Si l’on souhaite connaître l'état des services dans le véhicule (état de fonctionnement de la palette par exemple), il sera alors plus simple de passer par l'identification de la course que par celle du véhicule.</p></td>
</tr>
<tr class="even">
<td><p>Course</p>
<p>(Vehicle Journey )</p></td>
<td>L'identification des courses devra donc être réalisée au cas par cas, et définie entre les acteurs avant de débuter un échange. L'identification devra dans ce cas porter une indication signalant qu'elle est spécifique à un échange local.</td>
</tr>
<tr class="odd">
<td><p>Numéro de passage à un Point d'arrêt sur une mission</p>
<p>(Stop Visit In Pattern)</p></td>
<td>Parmi les solutions proposées par SIRI, le profil SIRI France retient celle qui consiste à attribuer un numéro d'ordre dans la mission à chacun des arrêts.</td>
</tr>
<tr class="even">
<td><p>Ligne</p>
<p>(Line )</p></td>
<td>L'identification des lignes devra donc être réalisée au cas par cas, et définie entre les acteurs avant de débuter un échange. L'identification devra dans ce cas porter une indication signalant qu'elle est spécifique à un échange local.</td>
</tr>
<tr class="odd">
<td><p>Itinéraire</p>
<p>(Route)</p></td>
<td>L'identification des itinéraires devra donc être réalisée au cas par cas, et définie entre les acteurs avant de débuter un échange. L'identification devra dans ce cas porter une indication signalant qu'elle est spécifique à un échange local.</td>
</tr>
<tr class="even">
<td><p>Mission</p>
<p>(Journey pattern)</p></td>
<td>L'identification des Missions devra donc être réalisée au cas par cas, et définie entre les acteurs avant de débuter un échange. L'identification devra dans ce cas porter une indication signalant qu'elle est spécifique à un échange local.</td>
</tr>
<tr class="odd">
<td><p>Direction</p>
<p>(Direction)</p></td>
<td>Cette notion a été introduite par SIRI pour pallier les cas où la notion d’itinéraires n'est pas formalisée.</td>
</tr>
<tr class="even">
<td><p>Destination</p>
<p>(Destination)</p></td>
<td><p>Cette notion a été introduite par SIRI pour pallier les cas ou la notion de mission n'est pas formalisée.</p>
<p>Dans le cadre du profil SIRI France, les Destinations seront systématiquement les extrémités des missions, et donc leur dernier point d'arrêt (dont on utilisera l'identifiant).</p></td>
</tr>
<tr class="odd">
<td><p>Version des horaires théoriques</p>
<p>(Schedule Version)</p></td>
<td><p>Cette notion permet de référencer la version des données horaires théoriques sous-jacente.</p>
<p>L'identification de version du référentiel devra donc être réalisée au cas par cas, et défini entre les acteurs avant de débuter un échange. L'identification devra dans ce cas porter une indication signalant qu'elle est spécifique à un échange local.</p>
<p>Pour mémoire, son principal usage est de permettre d'identifier une éventuelle désynchronisation entre les référentiels (horaires et réseaux) qui pourrait amener à ce que, par exemple, un point d'arrêt connu par l'une des parties de l'échange ne le soit pas de l'autre.</p></td>
</tr>
<tr class="even">
<td><p>Mode et sous-mode de transport</p>
<p>(Product Category)</p></td>
<td><p>L'ensemble des valeurs proposées par SIRI est retenu pour le profil SIRI France.</p>
<p>Voir 3.3.11.3 dans le document SIRI-Part 1</p>
<p>Cette liste est très détaillée (issue de la norme TPEG) mais permet d'être certain de ne pas avoir à la compléter à l'avenir.</p></td>
</tr>
<tr class="odd">
<td><p>Identification du véhicule, type de véhicule</p>
<p>(Vehicle Feature)</p></td>
<td><p>L'ensemble des valeurs proposées par SIRI est retenu pour le profil SIRI France.</p>
<p>Voir 3.3.13 dans le document SIRI-Part 1 et sa mise à jour pour le service <em>Facility Monitoring</em></p>
<p>Cette liste est très détaillée (issue de la norme TPEG, entre autres) mais permet d'être certain de ne pas avoir à la compléter à l'avenir.</p></td>
</tr>
<tr class="even">
<td><p>Type de service</p>
<p>(Service Feature)</p></td>
<td><p>L'ensemble des valeurs proposées par SIRI est retenu pour le profil SIRI France.</p>
<p>Voir 3.3.13 dans le document « SIRI-Part 1 » et sa mise à jour pour le service <em>Facility Monitoring</em></p>
<p>Cette liste est très détaillée (issue de la norme TPEG, entre autres) mais permet d'être certain de ne pas avoir à la compléter à l'avenir.</p></td>
</tr>
</tbody>
</table>

<u>Note</u> : Il faut rappeler que, d’une façon générale, pour des
échanges locaux, il n’est pas indispensable de disposer d’un référentiel
complet pour échanger les données temps réel (notamment mission, course,
…). Le sous-ensemble d’objets ci-dessus peut en effet suffir, tout
dépendra du cas d’utilisation mis en œuvre.

## Gestion des Identifiants

### Structure des identifiants

Dans le cadre du profil SIRI France, l'identification sera conforme à la
structure suivante :

\[Fournisseur\]:\[type
d'objet\]:\[typeObjetDétaillé\]:\[identifiantTechnique\]:LOC

Ou

\[Fournisseur\]:\[type
d'objet\]:\[typeObjetDétaillé\]:\[identifiantTechnique\]:

Ou

\[Fournisseur\]:\[type
d'objet\]:\[typeObjetDétaillé\]:\[identifiantTechnique\]:\[Nom
attributaire\]

*<u>Note</u>* : il est convenu de conserver fixe le nombre de séparateur
":" : ainsi, même si l'une des valeurs encadrée est vide, le ":" autour
seront conservés (par exemple
***800INFOTRANSTN:JourneyPattern::ZECO:LOC***)

La signification des différents champs est la suivante :

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 13%" />
<col style="width: 11%" />
<col style="width: 54%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Champ</td>
<td>Obligatoire</td>
<td>Type</td>
<td>Description</td>
</tr>
<tr class="even">
<td>[Fournisseur]</td>
<td>oui</td>
<td><p>Alpha-</p>
<p>numérique</p></td>
<td><p>Identifie le système fournisseur de la donnée : en l'occurrence, il s'agira soit :</p>
<ol type="1">
<li><p>Dans les leaders : le nom du système qui transmet la donnée, qui est soit le nom du relais, soit le nom du concentrateur, soit le nom du SAEIV</p></li>
<li><p>Dans les deliveries : le nom du système qui produit la donnée,</p></li>
</ol>
<p>Dans le cas où l’objet identifié serait rattaché à plusieurs transporteurs ACU</p></td>
</tr>
<tr class="odd">
<td>[type d'objet]</td>
<td>oui</td>
<td><p>Caractères</p>
<p>codés</p></td>
<td><p>Contient le nom du type d'objet identifié. Les valeurs possibles pour SIRI -, (la liste est un peu plus longue pour TRIDENT) - sont:</p>
<ul>
<li><p>StopPoint</p></li>
<li><p>StopArea</p></li>
<li><p>Line</p></li>
<li><p>Route</p></li>
<li><p>JourneyPattern</p></li>
<li><p>VehicleJourney</p></li>
<li><p>Stop Place</p></li>
</ul></td>
</tr>
<tr class="even">
<td>[typeObjetDétaillé]</td>
<td>non</td>
<td>Caractères codés</td>
<td><p>Ce champ est facultatif et ne sert que pour les points d'arrêt. On pourra toutefois envisager de l'utiliser à terme aussi pour les lignes notamment pour gérer la notion de sous-lignes.</p>
<p>Le « typeObjetDétaillé » pourra être omis, mais un type détaillé par défaut sera alors associé (lieu d'arrêt pour les points d'arrêt).</p>
<p>Les valeurs possibles pour les arrêts sont les suivantes:</p>
<ul>
<li><p>SP (Stop Place) : correspond à une Zone de Lieu (ZDL), à un Lieu d'Arrêt (LDA) ou à un Groupe de Lieux (GDL)</p></li>
<li><p>BP (Boarding Point) : correspond à une Zone d'Embarquement (ZDE)</p></li>
<li><p>Q (Quay) : correspond à une Zone d'Embarquement (ZDE)</p></li>
</ul>
<p>Pour les autres objets il pourra être possibile depréciser le contexte d’utilisation par les valeurs suivantes :</p>
<ul>
<li><p>Monomodal</p></li>
<li><p>Multimodal</p></li>
</ul></td>
</tr>
<tr class="odd">
<td>[identifiantTechnique]</td>
<td>oui</td>
<td><p>Alpha-</p>
<p>numérique</p></td>
<td><p>C'est l'identifiant technique de l'objet. Il peut être constitué de lettres et de chiffres. L'objectif est que cet identifiant devienne pérenne dans le temps.</p>
<p>Pour les identifiants non pérennes, chaque producteur en précisera le format dans sa spécification technique.</p></td>
</tr>
<tr class="even">
<td>LOC</td>
<td>oui si applicable</td>
<td>Fixe</td>
<td>Ce champ permet de préciser que l'identifiant a été défini de façon locale entre les parties engagées dans l'échange, et qu'il ne fait donc pas partie du référentiel régional. L'utilisation de ce champ est obligatoire quand l'identifiant est local.</td>
</tr>
<tr class="odd">
<td>Identifiant Attributaire</td>
<td>Non</td>
<td>Alpha numérique</td>
<td>Ce champ permet d’indiquer que l’identifiant est défini par « l’attributaire ».</td>
</tr>
</tbody>
</table>

### Ajout d’identifiants alternatifs

Un mécanisme permet optionnellement de typer les identifiants (KeyList).
L’implentation des KeyList s’appuie sur une nouvelle structure de la
table extensions de SIRI (Part2) présentée ci-dessous.

#### KeyList

Une Keylist est un ensemble de couples clé-valeur utilisé pour décrire
les identifiants secondaires de l'objet (LIGNE, LIEU D'ARRÊT, ZONE
D'EMBARQUEMENT, POINT D’ARRET PLANIFIÉ, COURSE, etc.): c’est-à-dire tel
qu'il peut être identifié dans des systèmes tiers: billettique,
information voyageur, etc. La clé permet de nommer l'identifiant (et
donc de faire référence au système tiers), la valeur étant l'identifiant
lui même.

Cette identification servira principalement d'identification croisée,
permettant au fournisseur de retrouver facilement, dans ses systèmes,
l'origine de l'objet.

La liste des identifiants secondaires est spécifique à chaque
fournisseur. Voir aussi PrivateCode du GroupOfEntities pour les
identifiants alternatifs:

|      |                                                                                                                                                                                                                   |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| KL-1 | Les KeyList ne sont à utiliser que s'il y a plusieurs identifiants alternatifs, et si elles sont utilisées, le PrivateCode doit impérativement être aussi renseigné.                                              |
| KL-2 | Il est interdit, dans le profil, d’utiliser le système de clé/valeur pour décrire des informations qui pourraient être fournies avec des attributs SIRI existants (même s’ils ne sont pas retenus par le profil). |

#### Structure Extension

|            |         |      |            |                                  |
| ---------- | ------- | ---- | ---------- | -------------------------------- |
| Extensions |         |      | +Structure | Placeholder for user extensions. |
|            | KeyList | 0:1  | +Structure | Set of KEY VALUE pairs.          |
|            | …       | 0:\* | xsd:any\*  | Any user defined content.        |
|            |         |      |            |                                  |

#### Structure KeyList

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 4%" />
<col style="width: 13%" />
<col style="width: 5%" />
<col style="width: 21%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">KeyList</td>
<td>+Structure</td>
<td>Set of arbitrary key value pairs. Provides an extension mechanism. Each KEY VALUE pair must be unique.</td>
</tr>
<tr class="even">
<td rowspan="4"></td>
<td colspan="2">KeyValue</td>
<td>1:*</td>
<td>+Structure</td>
<td>An arbitrary key value pair.</td>
</tr>
<tr class="odd">
<td rowspan="3"></td>
<td>TypeOfKey</td>
<td>0:1</td>
<td>xsd:normalizedString</td>
<td><p><strong>Attribute</strong> that specifies the type / purpose of the KEY VALUE pair.</p>
<p>Type de clé</p>
<p>Seule la valeur "ALTERNATE_IDENTIFIER"</p>
<p>est reconnue dans le cadre du profil. Tout autre</p>
<p>type de type de clé devra être ignoré (sans</p>
<p>toutefois générer d'erreur).</p></td>
</tr>
<tr class="even">
<td>Key</td>
<td>1:1</td>
<td>xsd:normalizedString</td>
<td>Key of KEY VALUE.</td>
</tr>
<tr class="odd">
<td>Value</td>
<td>1:1</td>
<td>xsd:normalizedString</td>
<td>Value of KEY VALUE.</td>
</tr>
</tbody>
</table>

### Identifiant des arrêts

Pour mémoire, dans SIRI les identifiants sont des NMTOKEN et doivent
donc en respecter la syntaxe (cf:
<https://www.w3.org/TR/xmlschema11-2/#NMTOKEN>), c’est-à-dire ne
contenir que des lettres, des chiffres, des points \[ . \] , des tirets
\[ - \], des soulignés \[ \_ \] et des deux-points \[ : \] (pas
d'espace).

A terme l’utilisation d’identifiant d’arrêt nationaux devra être la
règle. Dans l’attente de la mise en place de ce reférentiel, si des
identifiants internes doivent être utilisés, il conviendra de les
suffixer par l’extension « LOC » (pour LOCal, précisant ainsi qu’il ne
s’agit pas d’un identifiant commun, voire d'un identifiant interne, et
non d’un objet issu du référentiel national).

L'utlisation d’identifiants locaux est toutefois interdite dans les
échanges entre les concentrateurs et le relais (sauf dans le cas
ci-dessous).

Le tableau ci-dessous présente la mise en correspondance des différents
types d'arrêt définis dans le profil NeTEx France des arrêts et la
formation des identifiants correspondants. Pour rappel les arrêts
respectent la structure suivante :

![image](media/image1.png)

Les identifiants associés à chacun de ces composants respectent les
patterns suivants :

<table>
<colgroup>
<col style="width: 26%" />
<col style="width: 48%" />
<col style="width: 24%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Concept NeTex</td>
<td>Forme de l’Identifiant</td>
<td>Remarque</td>
</tr>
<tr class="even">
<td>Groupe de lieu</td>
<td rowspan="4">[Fournisseur]: StopPlace:SP:[identifiantTechnique]:LOC</td>
<td></td>
</tr>
<tr class="odd">
<td>Lieu d’arrêt Multimodal</td>
<td></td>
</tr>
<tr class="even">
<td>Lieu d’arrêt monomodal</td>
<td></td>
</tr>
<tr class="odd">
<td>Pole Monomodal</td>
<td></td>
</tr>
<tr class="even">
<td>Zone d’embarquement</td>
<td><p>[Fournisseur]:StopPoint:Q:[identifiantTechnique]:LOC</p>
<p>[Fournisseur]:StopPoint:BP:[identifiantTechnique]:LOC</p></td>
<td></td>
</tr>
</tbody>
</table>

### Identifiant des systèmes en communication

Dans un échange informatique comme celui proposé par SIRI, il est
important que chaque système informatique puisse s'identifier vis-à-vis
des autres.

Cela permet de mettre en place des mécanismes de contrôle d'accès, mais
aussi de bien gérer les mécanismes d'abonnement ou encore d'identifier
la provenance d'une information.

Dans le cadre du profil SIRI France, les systèmes s'identifieront de la
façon suivante:

\[Code Transporteur\]:\[Nom Transporteur\]

Où \[Code Transporteur\]

Dans le cas general e code transporteur, est fourni par l’AOT si cen’est
pas le cas le numero SIRET peut être envisagé

Dans le cas où l’objet identifié est rattaché à plusieurs transporteurs
(un groupement), le code transporteur sera remplacé par XXX, et le code
du système portera l’ensemble de la qualification du fournisseur.Le code
complémentaire du code transporteur sera précisé dans les protocoles
d’accord engageant les participants de l’échange.

Le nom du transporteur \[*Nom Transporteur*\] se présente sous la forme
d'une chaîne de caractères (bien que cela ne soit pas une contrainte -
il est recommandé d'utiliser un nom court, 20 caractères maximum et sans
espace).

### Identifiants SIRI

Cette liste non exhaustive devra être complétée si nécessaire lors des
développements. Ces identifiants pourront aussi évoluer si nécessaire
(ex : cas de doublon pour deux identifiants). Des précisions sur ces
format d'identifiant pourront être apportées dans les spécifications
d'interface de chancun des systèmes.

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 70%" />
</colgroup>
<thead>
<tr class="header">
<th>Champ SIRI</th>
<th>Identifiant SIRI</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>DataFrameRef</td>
<td>[Fournisseur]:DataFrame::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="even">
<td>DatedVehicleJourneyRef</td>
<td><p>[Fournisseur]:VehicleJourney::<em>[identifiantTechnique]</em>:[LOC]</p>
<p>Note: <strong>DatedVehicleJourneyRef</strong> est le champ de la structure <strong>FramedVehicleJourneyRef</strong> contenant la référence à la course datée elle-même.</p></td>
</tr>
<tr class="odd">
<td>DestinationRef</td>
<td>Comme un identifiant d'arrêt</td>
</tr>
<tr class="even">
<td>DirectionRef</td>
<td><em><strong>DirectionRef</strong></em> est un code (code ouvert, limité à "<em>aller</em>" ou "<em>retour</em>" ou vide, sans format particulier donc). Normalement non retenu par le profil SIRI France, mais parfois obligatoire dans SIRI</td>
</tr>
<tr class="odd">
<td>formatRef</td>
<td>Utilisé pour General Message ; le format est spécifique au contexte France et doit contenir la valeur fixe « France » (valeur sans format particulier)</td>
</tr>
<tr class="even">
<td>FramedVehicleJourneyRef</td>
<td><strong>FramedVehicleJourneyRef</strong> est une structure, la référence elle-même est portée par contenant la référence à la course datée elle-même <strong>DatedVehicleJourneyRef</strong> décrit plus haut.La course étant spécifique d'un SAE, on complétera autant que possible le code Opérateur de [Fournisseur] par un code permettant d'identifier le SAE producteur.</td>
</tr>
<tr class="odd">
<td>InfoChannelRef</td>
<td>C'est un code technique seul qui est utilisé pour l'<em><strong>InfoChannelRef</strong>.</em> Il peut valoir "<em>Perturbation</em>", "<em>Information</em>" ou "<em>Commercial</em>" (valeur sans format particulier).</td>
</tr>
<tr class="even">
<td>InfoMessageIdentifier</td>
<td>[Fournisseur]:InfoMessage::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="odd">
<td>ItemIdentifier</td>
<td><p>[Fournisseur]:Item::[identifiant Unique de l'Information]:[LOC]</p>
<p>La partie [identifiant Unique de l'Information] pourra etre construite en s'appuyant sur l'identifiant de véhicule pour Vehicle Monitoring, et sur le Info­Message­Identifier pour General Message.</p>
<p>Pour les passages à l'arrêt (StopMonitoring en particulier), la forme est la suivante:</p>
<p>[Fournisseur]:Item::[identifiantTechnique du couple Arrêt – Course]:[LOC]</p></td>
</tr>
<tr class="even">
<td>ItemRef</td>
<td>[Fournisseur]:Item::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="odd">
<td>JourneyPatternRef</td>
<td>[Fournisseur]:JourneyPattern::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="even">
<td>LineRef</td>
<td>[Fournisseur]:Line::[identifiantTechnique]:</td>
</tr>
<tr class="odd">
<td>MessageIdentifier</td>
<td>[Fournisseur]:Message::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="even">
<td>MonitoringRef</td>
<td>Comme pour les arrêts</td>
</tr>
<tr class="odd">
<td>OperatorRef</td>
<td>[Fournisseur]:Operator::<em>[identifiantTechnique]</em>:</td>
</tr>
<tr class="even">
<td>OriginRef</td>
<td>Comme pour les arrêts</td>
</tr>
<tr class="odd">
<td>PlaceRef</td>
<td><p>Cet identifiant a la particularité de pouvoir identifier un lieu quelconque, pouvant en particulier être un arrêt (pour mémoire, dans Transmodel, le STOP PLACE hérite bien de PLACE).</p>
<p>La forme générale de l'identifiant de place est [Fournisseur]:Place::<em>[identifiantTechnique]</em>:LOC</p>
<p>Mais s'il s'agit d'un arrêt on utilisera la forme spécifique des identifiant d'arrêt (voir 5.4.2 - Error: Reference source not found)</p>
<p>Note: Si un référentiel national est mis en place, le LOC devrait être supprimé.</p></td>
</tr>
<tr class="even">
<td>ProducerRef</td>
<td>[Fournisseur]</td>
</tr>
<tr class="odd">
<td>RequestMessageRef</td>
<td>[Fournisseur]:Message::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="even">
<td>RequestorRef</td>
<td>[Fournisseur]</td>
</tr>
<tr class="odd">
<td>ResponseMessageIdentifier</td>
<td>[Fournisseur]:ResponseMessage::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="even">
<td>RouteRef</td>
<td>[Fournisseur]:Route::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="odd">
<td>SituationSimpleRef</td>
<td>[Fournisseur]:Situation::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
<tr class="even">
<td>StopPointRef</td>
<td>Comme pour les arrêts</td>
</tr>
<tr class="odd">
<td>SubscriberRef</td>
<td>[Fournisseur]</td>
</tr>
<tr class="even">
<td><p>SubscriptionRef</p>
<p>et</p>
<p>SubscriptionIdentifier </p></td>
<td>[Fournisseur]:Subscription::<em>[identifiantTechnique]</em>:[LOC]</td>
</tr>
</tbody>
</table>

## Gestion des abonnements

La spécification SIRI propose une couche de communication très complète
(décrite dans le document « part-2: Communications infrastructure »),
mais qui, comme le reste de la spécification, est ouverte et nécessite
un certain nombre de précisions dans le cadre du profil France.

Ainsi, la norme SIRI propose deux méthodes pour accéder à l'information:

1.  Les **requêtes directes**, générant immédiatement une, et une seule,
    réponse portant les informations demandées ;

2.  Un mécanisme d'abonnement où la même requête est soumise, mais pour
    laquelle on recevra régulièrement des mises à jour des informations
    au fur et à mesure de leur évolution.

3.  Ce mécanisme d'abonnement propose lui-même deux variantes:

<!-- -->

1.  un mécanisme de notification à deux phases (fetched delivery) : lors
    d'une évolution des données on reçoit une indication de « mise à
    jour disponible » et on peut alors aller chercher les données en
    question auprès du serveur, via une nouvelle requête ;

2.  un mécanisme de notification à une phase (direct delivery) : lors
    d'une évolution des données on reçoit directement les données mises
    à jour

|     |                                                                                                                                                                                                                                                                                                                 |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R1  | Dans le cadre du profil SIRI France, tout système implémentant SIRI devra impérativement implémenter le <u>mécanisme de requête directe</u>.                                                                                                                                                                    |
| R2  | De même, tout nouveau système (en particulier les concentrateurs) devra proposer un service d’abonnement                                                                                                                                                                                                        |
| R3  | Ce mécanisme d'abonnement sera mis en oeuvre en implémentant impérativement le mécanisme de notification à une phase (moins consommateur en bande passante réseau, et plus simple à mettre en oeuvre que le mécanisme à deux phases).                                                                           |
| R4  | De plus, dans les cadres des abonnements, SIRI propose une gestion des confirmations de réception (lorsque l'on reçoit une notification, on répond avec un acquittement pour confirmer au serveur que les données ont bien été reçues) : cette **possibilité n'est pas retenue** dans le cadre du profil France |

En effet les protocoles de transport permettent aujourd’hui de s’assurer
qu’une requête a bien été transmise, ce qui supprime tout besoin
d’acquittement (il suffit donc de tester le code retour de l’appel
fonctionnel SOAP).

Enfin, la meilleure raison pour ne pas utiliser les confirmations est
que les protocoles de transport permettent aujourd’hui de s’assurer
qu’une requête a bien été transmise, ce qui supprime tout besoin
d’acquittement (il suffit de tester le code retour de l’appel
fonctionnel SOAP).

La figure ci-dessous est extraite de SIRI et présente le mécanisme
d'abonnement retenu (voir les documents SIRI, en particulier le
document « part 2 », pour plus de précisions) :

### Gestion de la segmentation des messages

La spécification SIRI offre la possibilité de segmenter les messages
(découper un grand message en un ensemble de messages plus petits, qu'il
faudra ré-assembler).

|     |                                                                                                                                                                                                                                        |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R5  | La segmentation des messages peut être intéressante si les échanges sont réalisés sur des réseaux de communication fortement contraints, mais ne présente pas d'intérêt dans le cadre du profil France, et n'est donc **pas retenue**. |

### Vérification de la disponibilité des partenaires

Lors d'un échange, il est important de savoir si le système avec lequel
on « dialogue » est disponible ou non. Cela est particulièrement
important si un mécanisme d'abonnement est mis en place de façon à
pouvoir faire la différence entre le fait de ne pas recevoir de mise à
jour parce qu'il n'y a pas d'évolution des données, et le fait de ne pas
recevoir de mises à jour parce que le système distant est « en panne »
(ou qu'il y a un problème réseau... ou toute autre défaillance).

Pour ce faire, la spécification SIRI propose deux mécanismes afin
d’assurer cette surveillance :

1.  La requête de vérification d'état : une requête spécifique permet de
    demander au système distant, quand on le souhaite, s’il est bien
    disponible. On déclare le système distant indisponible si l'on ne
    reçoit pas de réponse ou si l'on reçoit une erreur en réponse (ce
    mécanisme est similaire au « ping » classiquement utilisé sur les
    réseaux IP).

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 93%" />
</colgroup>
<tbody>
<tr class="odd">
<td>R6</td>
<td><p>Dans le cadre du profil SIRI France, le <u>mécanisme de requête de vérification d'état</u> (service CheckStatus) est retenu. Tout serveur SIRI devra donc implémenter ce mécanisme.</p>
<p>Par contre cela n’est pas une obligation pour les clients : cela pourra toutefois être envisagé dans la cadre de la gestion d’abonnement pour vérifier la disponibilité d’un abonné.</p></td>
</tr>
<tr class="even">
<td>R8</td>
<td>Les implémentations devront toutefois s'engager à appeler régulièrement la requête de vérification d'état, au moins dès qu'elles n'ont plus eu d’échange avec le système distant depuis un certain temps (fixé par défaut à cinq minutes).</td>
</tr>
</tbody>
</table>

Structure du CheckStatus

Dans le cadre du profil SIRI France :

|     |                                                                                                                                                                                                                                                                                                                                |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| R9  | Le champ facultatif au niveau SIRI «Status» sera toujours présent, dans le profil France, et égal à « true » si le système est parfaitement opérationnel, et à « false » s’il est en mesure de recevoir les requêtes, mais dans l'impossibilité d'y apporter une réponse (contact avec le gestionnaire de données perdu, etc.) |
| R10 | Le champ facultatif au niveau «ErrorCondition» reste facultatif, au niveau du profil France, si aucune erreur n’est détectée, mais devra obligatoirement être présent et instancié à chaque fois qu'une erreur sera détectée.                                                                                                  |
| R11 | Les champs facultatifs de «SuccessInfoGroup» restent facultatifs                                                                                                                                                                                                                                                               |
| R12 | Le champ facultatif au niveau SIRI «ServiceStartedTime» sera toujours présent dans le profil France, et instancié avec l'heure du dernier démarrage du système                                                                                                                                                                 |

### 

### SIRI propose une formalisation des requêtes et des réponses sous forme de structures XML (avec une modélisation XSD), mais n'impose pas de protocole de transport particulier pour son l'implémentation. Il suggère, toutefois une utilisation de XML sur HTTP et dans ce cadre propose, une implémentation SOAP.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<tbody>
<tr class="odd">
<td><h3 id="section-1"></h3></td>
<td><h3 id="section-2"></h3></td>
</tr>
<tr class="even">
<td><h3 id="section-3"></h3></td>
<td><h3 id="section-4"></h3></td>
</tr>
</tbody>
</table>

### 

### 

### Utilisation des WSDL

Les WSDL introduites ci-dessus, permettent de décrire complètement
l'interface des services SIRI dans le contexte de Web Service de type
SOAP.

|     |                                                                                                                 |
| --- | --------------------------------------------------------------------------------------------------------------- |
| R15 | Dans le cadre du profil France, seuls les encodages *RPC-Literal* et *Document-Literal-Wrapped* sont supportés. |

### Gestion des filtres multiples

Lors de la constitution d'une requête, les différents paramètres
permettent, entre autres, de définir un filtre pour que le client puisse
ne recevoir que les données qui lui sont utiles (« les 3 prochains
passages à l'arrêt AAA dans la direction DDD», « le prochain passage à
l'arrêt BBB », « toutes les informations temps réel pour la ligne LLL »,
etc.).

La gestion d’abonnement utilise le même mécanisme.

Le cas des abonnements est un peu particulier car on peut, par exemple,
souhaiter être abonné avec plusieurs paramètres de filtrage:

« les 2 prochains passages à l'arrêt AAA dans la direction DDD»

et

« le prochain passage à l'arrêt BBB ».

Pour limiter les échanges sur le réseau ainsi que la surcharge de
traitement (overhead) pour la gestion de données, la norme SIRI propose
un mécanisme de filtres multiples permettant aux clients de recevoir,
dans une unique notification, les informations issues de l'ensemble des
abonnements : c'est le mécanisme de filtres multiples sur un abonnement.

|     |                                                                                                                                                                                                                                                                                                                                                                |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R16 | En cohérence avec le choix des notifications à une phase, le profil SIRI France retient ce <u>mécanisme de filtres multiples</u> qui devra donc être mis en œuvre à chaque fois que les services d'abonnement seront retenus (cela permettra de recevoir plusieurs informations dans une même réponse ou notification, et donc limiter le nombre de messages). |

### Structuration XML

La spécification SIRI propose, ~~à la demande des représentants
allemands du groupe de travail,~~ la possibilité de « déstructurer »
l'arborescence XML pour la rendre « plate » (« flat XML »), et ce, afin
de simplifier la compatibilité avec certains systèmes existants.

|     |                                                                                                  |
| --- | ------------------------------------------------------------------------------------------------ |
| R17 | Cette option de XML à plat (« flat XML ») n'est pas retenue dans le cadre du profil SIRI France. |

### Identification de la version de SIRI

|     |                                                                                     |
| --- | ----------------------------------------------------------------------------------- |
| R18 | La version de SIRI utilisée dans le cadre du profil SIRI France est la version 2.0. |

### Réseau et sécurité

La gestion de la sécurité et du contrôle d'accès n'est pas à proprement
parler du ressort de SIRI, mais repose sur la couche de transport réseau
retenue.

SIRI étant un protocole inter-systèmes, la sécurité est plus facile à
maîtriser.

|     |                                                                                                                                                               |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R19 | A minima, la mise en place de filtres sur les adresses IP (ou des plages d'adresses IP), complétés par l'utilisation d'un canal crypté HTTPS, est recommandé. |

Cette solution est peu coûteuse et simple à mettre en oeuvre, car elle
ne repose que sur une configuration du serveur HTTP.

En complément de ces éléments, on retrouve tous les éléments de sécurité
classique du monde du Web : firewall, architecture avec DMZ, etc.
Cependant ces éléments n'ont pas d’impact sur les échanges SIRI
eux-mêmes et sont du ressort de chaque intervenant (points sur lesquels
ils auront une parfaite autonomie).

|     |                                                                                                                                                                                                                                                                                                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R20 | Par contre, dans tous les cas, les services SIRI France seront accessibles à partir d'une liaison Web classique et ne nécessiteront donc pas la mise en place de liaisons spécialisées, d'abonnement à un gestionnaire de réseau spécifique, ni d'utilisation de réseaux point à point (RTC, etc.). |

Ces recommandations valent de façon générale pour tous les accès SIRI
indépendamment des cas d'utilisation : il est souhaitable que le mode
d'accès soit toujours le même, et sans lien avec l'usage qui sera fait
des données.

Si certains systèmes disposent déjà de mécanismes de gestion des accès
sécurisés et ne correspondent pas à la description ci-dessus (type VPN
par exemple), ils pourront être utilisés dans un premier temps de façon
à ne pas pénaliser les temps de développement (puisque cela n’entraîne
pas d’impact fonctionnel).

### Contrôle d'accès (niveau applicatif)

La norme SIRI impose que tous les messages échangés contiennent
l'identifiant de celui qui l'a émis (voir ***Identification des systèmes
en communication***).

Cet identifiant peut être utilisé pour réaliser un contrôle d'accès
pour, par exemple, ne permettre à un système distant de n'accéder qu'à
certaines lignes ou certains arrêts.

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 93%" />
</colgroup>
<tbody>
<tr class="odd">
<td>R21</td>
<td><p>Dans le cadre du profil France, un tel contrôle sera possible, mais ne pourra porter que :</p>
<ul>
<li><p>sur des <strong>arrêts</strong> identifiés,</p></li>
<li><p>des <strong>lignes</strong> identifiées,</p></li>
<li><p>des <strong>exploitants</strong> identifiés (accès à toutes les informations fournies par un exploitant donné pour les cas où le système SIRI propose des informations issues de plusieurs exploitants).</p></li>
</ul></td>
</tr>
</tbody>
</table>

Les éventuelles informations de restrictions devront être communiquées
aux personnes en charge de la gestion et de l'exploitation du système
client concerné.

|     |                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R22 | Toutefois, cet échange sera réalisé par courrier ou par mail, mais sans utiliser les structures d'autorisation (« ***permission structures »***) proposées par SIRI et dont l'implémentation ne correspond pas à un besoin exprimé en France (pour mémoire les « ***permission structures »*** permettent à un client de demander **dynamiquement** « quelles sont les informations auxquelles j'ai droit » ...). |

### Gestion des erreurs

La gestion des erreurs constitue un point important, auquel SIRI apporte
une réponse claire et précise.

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 93%" />
</colgroup>
<tbody>
<tr class="odd">
<td>R23</td>
<td><p>Toute anomalie détectée par le serveur devra donner lieu à la génération d'un message d’erreur précisant le problème (« service SIRI non implémenté », « accès non autorisé », « service temporairement indisponible », etc.).</p>
<p>De façon à être précise, toute réponse à une requête devra indiquer si elle a pu être traitée normalement ou si une quelconque erreur a été rencontrée</p></td>
</tr>
</tbody>
</table>

Le tableau ci-dessous détaille chacun des codes d'erreur proposés par
SIRI :

<table>
<colgroup>
<col style="width: 26%" />
<col style="width: 60%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>Erreur SIRI</th>
<th>Description</th>
<th><p>Disponibilité</p>
<p>(version SIRI)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>AccessNotAllowedError</td>
<td>Le demandeur n'a pas les droits lui permettant d'accéder à ce service ou à ces données.</td>
<td></td>
</tr>
<tr class="even">
<td>AllowedResourceUsage­ExceededError</td>
<td>La requête est valide mais nécessite une charge trop importante pour pouvoir être traitée.</td>
<td></td>
</tr>
<tr class="odd">
<td>BeyondDataHorizon</td>
<td>Les données ne sont pas disponibles pour la période demandée.</td>
<td></td>
</tr>
<tr class="even">
<td>CapabilityNotSupportedError</td>
<td><p>Le serveur ne supporte pas la fonctionnalité demandée.</p>
<p>Le champ « CapabilityNotSupportedError » signalera une erreur si un service optionnel non implémenté est sollicité.</p></td>
<td></td>
</tr>
<tr class="odd">
<td>EndpointDeniedAccessError</td>
<td>Le client refuse l'accés à un message de notification.</td>
<td></td>
</tr>
<tr class="even">
<td>EndpointNotAvailable­AccessError</td>
<td><p>Le destinataire du message (requête ou notification) n'est pas disponible.</p>
<p><em><u>Note</u></em>: cette erreur fait echo à la capacité de relais de requête introduite par SIRI 2.</p></td>
<td></td>
</tr>
<tr class="odd">
<td>InvalidDataReferencesError</td>
<td>La requête contient des identifiants qui sont inconnus.</td>
<td></td>
</tr>
<tr class="even">
<td>NoInfoForTopicError</td>
<td>La requête est valide, mais aucune donnée correspondante n'est disponible sur le serveur.</td>
<td></td>
</tr>
<tr class="odd">
<td>OtherError</td>
<td>Erreur autre que celles qui sont prédéfinies.</td>
<td></td>
</tr>
<tr class="even">
<td>ParametersIgnoredError</td>
<td>La requête contient des paramètres qui ne sont pas supportés par le serveur : une réponse a été fournie, mais les paramètres non supportés n'ont pas été pris en compte.</td>
<td></td>
</tr>
<tr class="odd">
<td>ServiceNotAvailableError</td>
<td>Le service est indisponible (mais toutefois capable de fournir cette réponse …).</td>
<td></td>
</tr>
<tr class="even">
<td>UnknownEndpointError</td>
<td><p>Le destinataire du message (notification) est inconnu.</p>
<p><em><u>Note</u></em>: cette erreur fait echo à la capacité de relais de requête introduite par SIRI 2.</p></td>
<td></td>
</tr>
<tr class="odd">
<td>UnknownExtensionsError</td>
<td>La requête contient des extensions qui ne sont pas supportées par le serveur : une réponse a bien été fournie mais sans tenir compte de ces extensions.</td>
<td></td>
</tr>
<tr class="even">
<td>UnknownParticipantError</td>
<td><p>Le destinataire du message (requête) est inconnu.</p>
<p><em><u>Note</u></em>: cette erreur fait echo à la capacité de relais de requête introduite par SIRI 2.</p></td>
<td></td>
</tr>
<tr class="odd">
<td>UnknownSubscriberError</td>
<td>Abonné inconnu.</td>
<td></td>
</tr>
<tr class="even">
<td>UnknownSubscriptionError</td>
<td>Abonnement inconnu.</td>
<td></td>
</tr>
<tr class="odd">
<td>UnapprovedKeyAccessError</td>
<td>Clé d'authentification invalide.</td>
<td></td>
</tr>
</tbody>
</table>

<u>Note</u>: la liste des erreurs proposées par SIRI a été fortement
étendue lors du passage à la version SIRI 2.

Dans le cadre du profil SIRI France :

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 93%" />
</colgroup>
<tbody>
<tr class="odd">
<td>R24</td>
<td><p>Pour les services fonctionnels, le champ facultatif « <strong>Status</strong> » (dans le <em><strong>DeliveryStatusGroup</strong></em> défini par la structure <em><strong>AbstractServiceDeliveryStructure</strong></em> utilisée pour les réponses de chacun des services) sera :</p>
<ul>
<li><p>toujours présent et égal à « <strong>true »</strong> (valeur par défaut) si la requête a été traitée normalement</p></li>
<li><p>et à « <strong>false »</strong> sinon (dans le cas des abonnements, un éventuel problème détecté, comme une indisponibilité temporaire, donnera lieu à l'émission d'une notification sans données, mais signalant le problème).</p></li>
</ul></td>
</tr>
</tbody>
</table>

Ce champ signale qu'un problème a été rencontré, et non qu'il n'y a pas
de réponse : il peut donc être positionné à « **false »** alors qu'une
information est bien retournée.

Plus particulièrement dans le cas de la réponse à un GetSiri, on obtient
un « **Status** » au niveau de l'entête global de la réponse (dans le
***ServiceDeliveryRequestStatusGroup***) et un autre pour chacune des
réponses aux requêtes élémentaires (typiquement quand on a utilisé
GetSiri pour effectuer une interrogation sur toute une liste d'arrêts.
Dans ce cas aussi, un « **Status** » à « **false »** dans l'entête
signifie qu'il y a une des réponses portant une erreur, et non qu'il n'y
a pas de réponse.

|     |                                                                                                                                                       |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| R25 | Le champ facultatif « **ErrorCondition** » reste facultatif, mais devra être présent et instancié à chaque fois qu'une erreur sera détectée           |
| R26 | La liste des codes erreur à supporter dans le cadre du profil France est détaillée dans le tableau ci-dessous                                         |
| R27 | s'il ne s'agit pas d'un service optionnel non implémenté, le champ « **OtherError** » précisera sous forme textuelle la nature de l'erreur rencontrée |

|     |                                                                                                                                                                                                                                                                                                                                                    |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R28 | Le champ facultatif « Description » reste facultatif et permettra juste de préciser l'erreur (les éléments fondamentaux étant précisés dans l'un des deux champs précédents). Il devra contenir une description de l’erreur ainsi que le champ incriminé, par exemple : "Erreur \[nom du champ\] : \[Raison de l’erreur avec valorisation reçue\]" |
| R29 | De façon à systématiser les messages d'erreur, le champ « **OtherError** » sera structuré en débutant par un code prédéfini entre crochets, suivi d'un texte explicatif.                                                                                                                                                                           |

La liste des codes prédéfinis est la suivante :

-   **\[BAD_REQUEST\]** : impossible de décoder la requête.

-   **\[BAD_PARAMETER\]** : la requête contient un paramètre
    inutilisable (le texte devra alors préciser le paramètre posant
    problème).

-   **\[INTERNAL_ERROR\] :** erreur non identifiée, mais empêchant la
    fourniture d'un résultat.

-   

|     |                                                                                                                                |
| --- | ------------------------------------------------------------------------------------------------------------------------------ |
| R30 | De façon à assurer une homogénéité de comportement dans le traitement des erreurs, il est convenu des comportements suivants : |

|                                   |                                                                                                                                                 |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Erreur                            | Comportement                                                                                                                                    |
| \[BAD_REQUEST\]                   | rejet complet de la requête, réponse erreur uniquement                                                                                          |
| InvalidDataReferencesError        | rejet de la requête ; en cas de multiples requêtes, rejet de la seule requête en erreur                                                         |
| \[BAD_PARAMETER\]                 | rejet complet de la requête, réponse erreur uniquement                                                                                          |
| ParametersIgnoredError            | Réponse en ignorant le paramètre inciminé                                                                                                       |
| NoInfoForTopicError               | Réponse uniquement sur la base des informations effectivement disponibles (pas de réponse autre que l'erreur si aucune donnée n'est disponible) |
| ServiceNotAvailableError          | rejet complet de la requête, réponse erreur uniquement                                                                                          |
| AccessNotAllowedError             | rejet complet de la requête, réponse erreur uniquement                                                                                          |
| \[INTERNAL_ERROR\]                | réponse erreur uniquement                                                                                                                       |
| AllowedResourceUsageExceededError | réponse erreur uniquement                                                                                                                       |
| BeyondDataHorizon                 | réponse erreur uniquement                                                                                                                       |
| UnknownExtensionsError            | Réponse uniquement sur la base des paramètres effectivement reconnus                                                                            |

Il n'y a pas d'obligation pour un système d'être en mesure de remonter
chacune de ces erreurs.

|     |                                                                                                                                                                                                                                                                                                                          |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| R31 | Toutefois, en cas d'anomalie, les systèmes devront s'astreindre à utiliser le code correspondant au problème rencontré pour le signaler (et ce en rapport avec leurs capacités et limitations de détection d'anomalie, ce qui signifie qu'ils ne sont pas tenus de remonter une erreur qu'ils ne savent pas identifier). |
| R32 | Les erreurs rencontrées devront de plus être conservées dans des fichiers (fichier type « log ») tant au niveau des systèmes serveurs que des systèmes clients, de façon à permettre une analyse « post-mortem » et d’envisager d'éventuels correctifs ultérieurs.                                                       |
| R33 | La durée minimale de conservation des fichiers « log » sera définie dans le cadre des projets ; on peut toutefois considérer que **3** mois est une valeur acceptable et **1** an une valeur maximale.                                                                                                                   |

La remontée d'erreur n'a en effet d'intérêt que si on l’utilise pour
comprendre et corriger les causes des anomalies. Cela implique que ces
erreurs soient reçues et traitées par les équipes d’exploitation puis
dispatchées, après une première analyse, vers les partenaires, les
industriels ou tout intervenant susceptible d’y apporter un remède.

|     |                                                                                                                                                                                                                                                                                                                                                                                                    |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R34 | Dans le cas ou une requête ne reçoit pas de réponse, une erreur pourra être déclarée. Cette anomalie sera mentionnée dans le « log » d'erreur du client. Le délai d'attente (« timeout » avant identification d'une panne) est fixé par défaut à une minute (cette valeur « par défaut » pourra être ajustée localement, notamment au regard du délai « normal » de rafraîchissement des données). |
| R35 | *ATTENTION* : il est tout à fait possible que la réponse arrive finalement, mais après le délai imparti, le système client pourra alors décider de la prendre en compte ou de l'ignorer (à définir localement dans l'implémentation du système).                                                                                                                                                   |

### Identification des services disponibles

La norme SIRI offre la possibilité de demander à un système la liste des
services qu'il implémente (ceux qu’ils doivent normalement implémenter,
indépendamment des éventuelles pannes), ce qui peut s'avérer utile du
fait du caractère facultif d'implémentation de certains services (se
référer à la partie 1 pour la liste des services à caractère obligatoire
ou facultatif).

Il peut être utile pour des systèmes concentrateurs ~~comme la *Base
Communautaire*~~ de pouvoir demander à un système distant les services
qu'il implémente et ainsi se configurer automatiquement pour la gestion
de l'échange.

Toutefois, cela peut aussi être réalisé au travers d'un simple mécanisme
de configuration du serveur, qui sera de toute façon indispensable pour
identifier la liste des serveurs SIRI à contacter (il suffit alors, pour
chaque serveur, de préciser la liste des services disponibles).

|     |                                                                                                                                                                                                                                                                                                                         |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R36 | De façon à ne pas alourdir le développement des systèmes la possibilité de « **Capability Checking** » proposée par SIRI n'est pas retenue, au profit d'un système non dynamique basé sur des fichiers de configuration (l'aspect dynamique et automatique ne présente pas d'intérêt particulier dans le cadre France). |

### Compression

<table>
<colgroup>
<col style="width: 6%" />
<col style="width: 93%" />
</colgroup>
<tbody>
<tr class="odd">
<td>R37</td>
<td><p>De façon à limiter la taille des messages, une compression de type Gzip (proposée par SIRI) sera utilisée.</p>
<p>Dans le contexte de l'utilisation de SOAP sur le protocole HTTP, elle sera mise en œuvre par les serveurs HTTP généralement par simple configuration.</p></td>
</tr>
</tbody>
</table>

### Encodage des caractères

|     |                                                                                                                                                                                                                           |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R38 | Les différentes chaines de caractères présentent dans les données XML seront encodées exclusivement en UTF-8 (abréviation de l’anglais Universal Character Set Transformation Format - 8 bits sans Bit-Order-Mark (BOM)). |

Tehchniquement cela se traduira, si l'on souhaite être explicite, par un
" **\<?xml version="1.0" encoding="UTF-8**"**?>** " en entête du
document. Mais cela n'est pas indispensable car l'UTF-8 est la valeur
par défaut quand l'encodage n'est pas précisé.

Voir <https://fr.wikipedia.org/wiki/UTF-8> pour plus de détail sur
UTF-8.

## Service SIRI Discovery

SIRI propose des services qui permettent d’effectuer l’échange de
données référentielles (Discovery Services). Le tableau ci-dessous
présente les services disponibles et ceux qui sont retenus pour le
profil SIRI France :

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 70%" />
</colgroup>
<thead>
<tr class="header">
<th>Requête d'identification du référentiel</th>
<th>Commentaire</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>StopPointsRequest</td>
<td><p>Requête retenue pour le profil France. L'utilisation de ce service devra donc reposer sur des informations cohérentes d’identifiant des arrêts.</p>
<p>Cette requête permet d'obtenir la liste de tous les points d'arrêts connus du système (voir la structure retournée, ci-dessous)</p></td>
</tr>
<tr class="even">
<td>LinesRequest</td>
<td><p>Requête retenue pour le profil France</p>
<p>Cette requête permet d'obtenir la liste de toutes les lignes connues du système (voir la structure retournée, ci-dessous)</p></td>
</tr>
<tr class="odd">
<td>ServiceFeaturesRequest</td>
<td>Requête non retenue pour le profil France (utilisation de la totalité de la liste proposée)</td>
</tr>
<tr class="even">
<td>ProductCategoriesRequest</td>
<td>Requête non retenue pour le profil France (utilisation de la totalité de la liste proposée)</td>
</tr>
<tr class="odd">
<td>VehicleFeaturesRequest</td>
<td>Requête non retenue pour le profil France (utilisation de la totalité de la liste proposée)</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 70%" />
</colgroup>
<tbody>
<tr class="odd">
<td>InfoChannelRequest</td>
<td><p>Requête retenue pour le profil France</p>
<p>Cette requête permet d'obtenir la liste de tous les canaux de messagerie proposés (voir la structure retournée, ci-dessous)</p>
<p>Dans le cadre du profil IDF, seules les valeurs suivantes seront utilisées pour identifier les canaux:</p>
<p>1. « Perturbation »</p>
<p>2. « Information »</p>
<p>3. « Commercial »</p>
<p>NB : même il ne s'agit pas ici d'une donnée du référentiel cette information est traitée ici, car elle fait partie du « Discovery Service » proposé par SIRI.</p></td>
</tr>
<tr class="even">
<td>FacilityRequest</td>
<td><p>Requête retenue pour le profil France</p>
<p>Cette requête permet d'obtenir la liste de tous les équipements et services connus du système (voir la structure retournée, ci-dessous)</p>
<p>Note: ce service n'est pas encore disponible dans la version actuelle de SIRI, mais fait partie des nouveaux services en cours de définition.</p></td>
</tr>
</tbody>
</table>

Ces requêtes ne seront déployées que dans les cas où un référentiel
théorique n’aura pas pu être identifié : leur implémentation est donc
facultative et devra, autant que faire se peut, être temporaire.

Les services retenus sont donc : *StopPointsRequest*, *LinesRequest*,
*InfoChannelRequest* et *FacilityRequest*. Les identifiants ainsi
obtenus pourront être utilisés avec tous les Services SIRI disponibles
sur le système les ayant fournis. On utilisera, par exemple, un même
identifiant d’arrêt pour consulter les horaires à l’arrêt (avec le
service « Stop Monitoring »), ou les informations de perturbation
(service « Situation Exchange » et/ou « General Message »).

Les informations qu'ils procurent sont présentées ci-dessous :

Note: les services de découvertes SIRI permettent de connaître les noms
des arrêts et lignes et l'appartenance des arrêts aux lignes mais en
aucun cas la structure (itinéraire-Route, mission-Journey pattern et à
fortiori course-vehicle Journey).Il conviendra donc de se tourner vers
les données de référence de l'offre et unréférentiel d'arrêt R pour
obtenir une information proprement structurée.

### Discovery StopPoint

#### Requête StopPointsRequest

<u>Note</u>: Voir 3.2 pour les explications détaillées de lecture des
tableaux qui suivent (codes couleurs, etc.).

|                            |                       |            |     |                             |                                                                                                                                      |
| -------------------------- | --------------------- | ---------- | --- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| StopPointsDiscoveryRequest |                       |            |     | +Structure                  | Requête d'accès à la liste des arrêts                                                                                                |
| log                        | Request­Timestamp     |            | 1:1 | xsd:dateTime                | Date d’émission de la requête.                                                                                                       |
| Auth                       | AccountId             |            | 0:1 | +Structure                  | Account Identifier. May be used to attribute requests to a specific user account for authentication or reporting purposes +SIRI v2.0 |
|                            | AccountKey            |            | 0:1 | +Structure                  | Authentication key for request. May be used to authenticate the request to ensure the user is a registered client. +SIRI v2.0        |
| Endpoint Properties        | Address               |            | 0:1 | Endpoint­Address            | Adresse réseau de destination de la réponse (ici une URL étant donné le choix d’implémentation SOAP).                                |
|                            | Requestor­Ref         |            | 1:1 | Participant­Code            | Identifiant du demandeur (reprendre la structure \[*fournisseur*\] des identifiants).                                                |
|                            | Message­Identifier    |            | 0:1 | Message­Qualifier           | Identifiant unique de ce message.                                                                                                    |
| Topic                      | BoundingBox           |            | 0:1 |                             | Filtre permettant de n'obtenir que les arrêts situés à l'intérieur d'un rectangle englobant +SIRI v2.0                               |
|                            |                       | UpperLeft  | 0:1 | LocationStructure           | Coin supérieur gauche du rectangle englobant                                                                                         |
|                            |                       | LowerRight | 0:1 | LocationStructure           | Coin inférieur droit du rectangle englobant                                                                                          |
|                            | Circle                |            | 0:1 | LocationStructure           | Circle containing stops be returned. Point indicates centre, precision indicates radius (+SIRI v2.0)                                 |
|                            | PlaceRef              |            | 0:1 | xsd:normalizedString        | Filter the results to include only stops associated with the PLACE . (+SIRI v2.0)                                                    |
|                            | OperatorRef           |            | 0:1 | Operator­Code               | Filtre permettant de n'obtenir que les arrêts utilisés par un opérateur donné.                                                       |
|                            | LineRef               |            | 0:1 | LineCode                    | Filtre permettant de n'obtenir que les arrêts utilisés par une ligne donnée.                                                         |
| Policy                     | Language              |            | 0:1 | xsd:language                | Preferred language in which to return text values. +SIRI v2.0                                                                        |
|                            | StopPointsDetailLevel |            | 0:1 | StopPointsDetailEnumeration | Level of detail to include in response. Default is 'normal'. +SIRI v2.0                                                              |

#### Réponses aux StopPointsRequest

La structure ci-dessous présente la description d'un arrêt tel que
retourné par le sevice (mais sans les entêtes génériques de réponse
SIRI).

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 2%" />
<col style="width: 13%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">AnnotatedStopPointStructure</td>
<td>+Structure</td>
<td>Description simplifiée d'un arrêt</td>
</tr>
<tr class="even">
<td rowspan="11">Stop Identity</td>
<td colspan="2">Stop­Point­Ref</td>
<td>1:1</td>
<td>StopPoint­Code</td>
<td><p>Identifiant du Point d'arrêt. Cf 5.4</p>
<p>Il convient d'utiliser ici un identifiant d'objet de référence de REFLEX.</p></td>
</tr>
<tr class="odd">
<td colspan="2">TimingPoint</td>
<td></td>
<td>xsd:boolean</td>
<td>Whether the stop is a TIMING POINT. Times for stops that are not timing points are sometimes interpolated crudely from the timing points, and may represent a lower level of accuracy. Default is 'true'</td>
</tr>
<tr class="even">
<td colspan="2">Monitored</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether real-time data is available for the stop. Default is 'true'. Detail level is 'normal'.</td>
</tr>
<tr class="odd">
<td colspan="2">StopName</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>NaturalLanguageStringStructure</td>
<td>le champ«StopName» sera toujours présent et renseigné conformément au paragraphe 5.4.</td>
</tr>
<tr class="even">
<td colspan="2">StopAreaRef</td>
<td>0:1</td>
<td>StopAreaCode</td>
<td>Identifer of the sSTOP AREA to which SCHEDULED STOP POINT belongs. +SIRI.v2.0</td>
</tr>
<tr class="odd">
<td colspan="2">Features</td>
<td>0:*</td>
<td>Structure</td>
<td>Service features of stop. Detail level is 'full'</td>
</tr>
<tr class="even">
<td colspan="2">Lines</td>
<td>0:*</td>
<td></td>
<td>Liste des lignes passant à l'arrêt</td>
</tr>
<tr class="odd">
<td></td>
<td>LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Identifiant d'une ligne (issu du référentiel des lignes)</td>
</tr>
<tr class="even">
<td></td>
<td>LineDirection</td>
<td>0:1</td>
<td>LineDirectionStructure</td>
<td>Reference to a LINE that calls at stop. and its direction</td>
</tr>
<tr class="odd">
<td colspan="2">Location</td>
<td>0:1</td>
<td>LocationStructure</td>
<td><p>Localisation géographique de l'arrêt</p>
<p>+SIRI V2.0</p></td>
</tr>
<tr class="even">
<td colspan="2">Url</td>
<td>0:1</td>
<td>xsd:anyURI</td>
<td>Web page associated with Stop. Detail level is 'full'+SIRI.v2.0</td>
</tr>
</tbody>
</table>

### Discovery Line

#### Requête LinesRequest

|                       |                       |            |     |                             |                                                                                                                                      |
| --------------------- | --------------------- | ---------- | --- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| LinesDiscoveryRequest |                       |            |     | +Structure                  | Requête d'accès à la liste des lignes                                                                                                |
| log                   | Request­Timestamp     |            | 1:1 | xsd:dateTime                | Date d’émission de la requête.                                                                                                       |
| Auth                  | AccountId             |            | 0:1 | +Structure                  | Account Identifier. May be used to attribute requests to a specific user account for authentication or reporting purposes +SIRI v2.0 |
|                       | AccountKey            |            | 0:1 | +Structure                  | Authentication key for request. May be used to authenticate the request to ensure the user is a registered client. +SIRI v2.0        |
| Endpoint Properties   | Address               |            | 0:1 | Endpoint­Address            | Adresse réseau de destination de la réponse (ici une URL étant donné le choix d’implémentation SOAP).                                |
|                       | Requestor­Ref         |            | 1:1 | Participant­Code            | Identifiant du demandeur (reprendre la structure \[*fournisseur*\] des identifiants).                                                |
|                       | Message­Identifier    |            | 0:1 | Message­Qualifier           | Identifiant unique de ce message.                                                                                                    |
| Topic                 | BoundingBox           |            | 0:1 |                             | Filtre permettant de n'obtenir que les lignes situées à l'intérieur d'un rectangle englobant +SIRI v2.0                              |
|                       |                       | UpperLeft  | 0:1 | LocationStructure           | Coin supérieur gauche du rectangle englobant                                                                                         |
|                       |                       | LowerRight | 0:1 | LocationStructure           | Coin inférieur droit du rectangle englobant                                                                                          |
|                       | OperatorRef           |            | 0:1 | Operator­Code               | Filtre permettant de n'obtenir que les lignes exploitées par un opérateur donné.                                                     |
| Policy                | Language              |            | 0:1 | xsd:language                | Preferred language in which to return text values. +SIRI v2.0                                                                        |
|                       | StopPointsDetailLevel |            | 0:1 | StopPointsDetailEnumeration | Level of detail to include in response. Default is 'normal'. +SIRI v2.0                                                              |

#### Réponses aux LinesRequest

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">AnnotatedLineStructure</td>
<td>+Structure</td>
<td>Description simplifiée d'une ligne</td>
</tr>
<tr class="even">
<td rowspan="6">Line Identity</td>
<td>LineRef</td>
<td>1:1</td>
<td>LineCode</td>
<td>Identifiant de la ligne (issu du référentientiel des lignes)</td>
</tr>
<tr class="odd">
<td>LineName</td>
<td>1:1</td>
<td>NaturalLanguageStringStructure</td>
<td>Nom de la ligne (issu du référentientiel des lignes)</td>
</tr>
<tr class="even">
<td>Monitored</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>le champ obligatoire « Monitored » sera toujours égal à « true » indiquant ainsi que l’on dispose bien d’information temps réel à ce point (inutile de traiter les arrêts et lignes pour lesquels on n’a pas d'information temps réel)</td>
</tr>
<tr class="odd">
<td>Destinations</td>
<td>0:*</td>
<td>AnnotatedDestinationStructure</td>
<td>Le champ facultatif « Destinations » reste facultatif et permettra d’indiquer, en plus des extrémités de la ligne, si elle est composée de plus de deux itinéraires (aller et retour)</td>
</tr>
<tr class="even">
<td>Directions</td>
<td>0:*</td>
<td>RouteDirectionStructure</td>
<td>DIRECTIONs and Stops for the LINE. 'normal'</td>
</tr>
<tr class="odd">
<td>Extensions</td>
<td>0:1</td>
<td><ul>
<li><p>any</p></li>
</ul></td>
<td>Extensions to schema. (Wrapper tag used to avoid problems with handling of optional 'any' by some validators).</td>
</tr>
</tbody>
</table>

### Discovery InfoChannel & Facility

#### Requêtes

Les requêtes - quant à elles - ont toutes la même forme (l'exemple de la
*StopPointsRequest* est fourni ci-dessous).

Dans le cadre du profil France :

-   Le champ facultatif «**address**» ne sera jamais présent

-   Le champ facultatif «**MessageIdentifier**» sera toujours présent et
    instancié (utilisé en particulier pour la gestion des cas d'erreur).

<u>Note</u>: l'attribut « version » référence la version de SIRI
utilisée (afin de permettre une gestion « sereine » des futures
versions, voir Error: Reference source not found).

La mise à jour des données de référence devra être réalisée
périodiquement de façon à garantir la synchronisation des référentiels
des différents systèmes. On pourra envisager différents modes de
synchronisation :

-   Des synchronisations à heures fixes (quotidiennement la nuit ou en
    milieu de journée pour les réseaux nocturnes),

-   Des synchronisations à dates fixes (hebdomadaires, mensuelles,
    etc.),

-   Des synchronisations manuelles.

Il est difficile d’envisager ici tous les cas et modes de
synchronisation, car l’objectif traité dans ces paragraphes n’est pas de
préconiser « comment faire » mais de s’adapter aux systèmes existants.

Il faudra donc envisager des adaptations au cas par cas, à formaliser
dans le cadre de la contractualisation entre les intervenants. Il est
important de rappeler que ces accords particuliers devront traiter de
façon explicite et détaillée les différents cas d’erreur qui pourront
intervenir :

-   Impossibilité de consulter les référentiels à la date et/ou l’heure
    prévue

-   Identification d’une incohérence de référentiel en exploitation,
    alors que le système est utilisé,

-   Modification tardive du référentiel par l’exploitant,

-   Etc.

Un tel mécanisme peut sembler attrayant, et il peut être tentant de le
pérenniser. Il faut toutefois bien garder à l'esprit que s'il est
pertinent pour deux systèmes en communication, il est beaucoup plus
délicat à mettre en place pour un grand nombre de systèmes du fait de la
problématique de mise à jour et de synchronisation qu'il implique: on a
en effet un nombre d'échanges à prévoir égal à N\*(N-1) où N est le
nombre de systèmes (donc 20 synchronisations quotidiennes pour 5
systèmes...).

Et, même si l’on a qu’un fournisseur et N clients, il est clair que la
mise en place d’un référentiel spécifique à l’information temps réel ne
permettra pas la mise en place de systèmes d’information complets
permettant à l’utilisateur de passer sans difficulté de l’information
théorique à l’information temps réel.

La convergence vers un référentiel commun reste donc importante.

#### Réponses aux InfoChannelRequest

Tous les champs étant obligatoires, il n'y a pas d'adaptation au cadre
du profil France (on définit tout de même les codes possibles : «
Perturbation », « Information » ou « Commercial »).

On peut toutefois noter que le champ «** icon **» pourra souvent rester
vide.

*<u>Note</u>*: voir la description du service de messagerie pour plus de
précisions.

#### Réponses aux FacilityRequest

Dans le cadre du profil France :

-   le champ facultatif « Monitored » sera toujours présent et égal à
    « true » (inutile de traiter les équipements pour lesquels on n’a
    pas d'information temps réel ou au moins mis à jour quotidiennement.

-   Le champ facultatif «Facility» sera toujours présent

    -   Le champ facultatif «**FacilityRef**» ne sera jamais présent
        (déjà disponible au niveau supérieur)

    -   Le champ facultatif «**Description**» reste facultatif

    -   Le champ facultatif «**FacilityClass**» reste facultatif

    -   Le champ facultatif «**Feature**» sera toujours présent et
        instancié

    -   Le champ facultatif «**FacilityLocation**» sera toujours présent
        et instancié

    -   Les champs facultatifs «**SuitableFor**» et «**NotSuitableFor**»
        restent facultatifs

    -   Le champ facultatif «**Extension**» ne sera jamais présent

Les valeurs possibles pour ces différents champs seront celles proposées
par SIRI, mais pourront être réduites aux valeurs jugées pertinentes
dans le contexte France lors de l’implémentation du service , par
exemple pour «**SuitableFor**» et «**NotSuitableFor**» on trouvera des
possibilités comme :

-   auditory,

-   wheelChair

-   motorizedWheelChair

-   mobility

-   visual

-   cognitive

-   psychiatric

-   incapacitingdisease

-   youngPassenger

-   luggageEncumbered

-   stroller

-   elderly

-   otherSpecificNeed

## Gestion des versions du profil SIRI FR

L’évolution des normes et du profil SIRI France dans le temps necessite
de définir les règles permettant d’identifier la version d’un profil
France SIRI.

A un instant t, il existera plusieurs versions du profil qui
s'appuieront sur différentes versions de SIRI.

Une compatibilité ascendante devra être assurée entre les versions du
profil. Il n'y a par contre aucune garantie de compatibilité
"descendante" : on peut assurer qu'un client de version antérieure
puisse toujours s'adresser à un serveur de version postérieure, mais
l'inverse ne peut être réalisé.

Le profil SIRI France intègre un mécanisme de gestion de version qui a
plusieurs objectifs:

-   Permettre à un serveur de savoir suivant quel profil il doit
    répondre à une requête client (en supportant plusieurs versions ou
    en redirigeant les requêtes et donc sans contraindre tout les
    clients à changer de version en même temps que lui) ;

-   Permettre à un serveur de signaler à un client qu'il ne supporte pas
    la version demandée (plutôt que de lui répondre avec une erreur) ;

-   Permettre à un client de gérer les réponses d'un serveur d'une
    version antérieure.

Le principe de gestion de version est simple : il s'appuie sur les
identifiants de version proposés par SIRI dans les en-têtes de toutes
les requêtes de service (ce champ est disponible pour chacune des
***xxxxRequestStructure*** sous la forme d'un attribut nommé
***Version***) ainsi que de chacune des réponses correspondantes (ce
champs est disponible pour chacune des ***xxxxDeliveryStructure,*** là
aussi sous la forme d'un attribut nommé ***Version***).

<u>Note**:**</u> il s'agit bien ici de l'attribut **Version** au niveau
des services et non de l'attribut que l'on trouve sur la racine **Siri**
du schéma, cette dernière n'étant pas accessible dans le cadre des
échanges SOAP.

La codification de version proposée par SIRI est de la forme x.y :

-   x constitue le numéro de version majeure, soit en l'occurrence la
    version de la norme (TS précédemment),

-   y constitue le numéro de version mineure: il est potentiellement
    suivi d'une lettre (la lettre est facultative précise éventuellement
    la version de l'XSD utilisée, on aura par exemple une version
    ***2.0n*** pour indiquer la version ***2.0*** de Siri et la version
    ***n*** de l'XSD correspondant.

Par exemple pour SIRI 1, les versions 1.0, 1.2, 1.3 et 1.4, et pour SIRI
2, seule la version 2.0 est actuellement disponible.

La codification de la version de profil se fait de la façon suivante :
***x.y:FR-a.b-c-d*** (par exemple "*2.0:FR-1.0*").

-   ***x.y*** étant la version de SIRI (obligatoire): le **x** est un
    entier et les **y** est un entier potentiellement suivi d'une
    lettre.

-   ***:*** est un délimiteur obligatoire

-   ***FR*** le digramme de la France (ISO 3166-1
    [alpha-2](http://fr.wikipedia.org/wiki/ISO_3166-1_alpha-2))
    (obligatoire)

-   ***-*** est un délimiteur obligatoire

-   ***a.b*** est la version du profil (obligatoire). ***a*** et ***b***
    sont des chiffres entiers.

-   ***-*** est un délimiteur facultatif (doit être omis si ni **c** ni
    **d** ne sont présents, obligatoire sinon)

-   **c** est le numéro de version du service concerné (facultatif). Il
    est constitué d'un ou deux caractères numériques. Il permettra
    d'identifier des possibles ajustements futurs spécifiques à ce
    service.

-   ***-*** est un délimiteur facultatif (doit être omis si **d** n'est
    pas présent, mais est impératif si **d** est présent)

-   **d** est le numéro de version le l'implémentation locale (numéro de
    version logicielle du serveur SNCF, Transdev, RATP, Keolis, du
    relais, etc.). **d** est constitué de chiffres et de "." uniquement.

Les exemples ci-dessous sont valides au titre de cette codification :

-   2.0:FR-1.0

-   2.0:FR-1.0-1

### Modalité d'utilisation des versions

Les principales règles d'utilisation des versions sont les suivantes.
Soit deux versions de profil N et N+ (N+ étant une version postérieure à
N).

-   Un client N peut s'adresser à un serveur N+. Le serveur N+ peut
    alors :

    -   (*solution non recommandée*) Indiquer qu'il ne supporte pas
        cette version en utilisant le code d'erreur
        ***CapabilityNotSupportedError*** en précisant dans le champ
        ***CapabilityRef*** le numéro de version qui a été demandé (donc
        N ici)

    -   adapter sa réponse pour la rendre conforme à la version N

    -   Transférer la requête à un serveur en version N (le "transfert"
        peut, techniquement, être réalisé de différentes façons, comme
        l'*URL Forwarding*, mais ceci relève du choix d'implémentation
        technique).

-   Un client N+ ne peut pas s'adresser à un serveur N en demandant la
    version N+ (le serveur ne supportant pas cette version N+). Si
    toutefois cela se produisait et que le serveur soit en mesure de
    décoder la requête sans générer d'erreur, il est recommandé de
    répondre qu'il ne supporte pas cette version en utilisant le code
    d'erreur ***CapabilityNotSupportedError*** en précisant dans le
    champ ***CapabilityRef*** le numéro de version qui a été demandé
    (donc N+ ici)

-   Un client N+ peut s'adresser à un serveur N en demandant la
    version N. La réponse lui est alors retournée en version N.

*<u>Note</u>*: Cette gestion de version n'est en rien incompatible avec
l'insertion d'un numéro de version dans l'URL d'accès au service (avec
éventuellement plusieurs URL si plusieurs versions sont disponibles). Ce
type de gestion des versions à travers les URL est à négocier entre les
partenaires impliqués dans l'échange.

# Partie III. Description détaillée des messages

Les paragraphes ci-dessous présentent, de façon détaillée, tous les
services retenus dans le cadre du profil SIRI France d’un point de vue
« description technique des messages ».

Le principe de ces services a déjà été présenté en amont dans ce
document, ce qui est présenté ici correspond aux tableaux détaillés des
services que l'on trouve dans le document « SIRI-Part 3 », traduit en
Français (seules les descriptions sont traduites, les noms des éléments
et leurs types restent en anglais, car c'est ainsi qu'on les retrouvera
dans l'échange XML) et précisant l'utilisation des différents champs, le
maintien ou non de leur caractère facultatif, etc.

Les éléments retenus pour le profil sont surlignés en Gris.

Les éléments non retenus pour le profil sont en texte masqué

L’ensemble des services présentés s’appuie sur la norme SIRI en version
2.0.

Des mises à jour de version de SIRI pourront être envisagées, au fur et
à mesure des évolutions et corrections de SIRI. Toutefois, la prise en
compte d’une nouvelle version de SIRI ne pourra être réalisée que si
elle a été validée par une mise à jour du présent document.

## Estimated Timetable

~~:~~ La norme SIRI ne pose aucune hypothèse ni aucune limite sur la
durée exacte des journée d’exploitation (possibilité de passer minuit),
les informations pourront donc être remontées indépendamment de la durée
de la journée d’exploitation.

*<u>Note</u>* : Les mécanismes de datation SIRI sont normalisés ISO. Un
changement de jour se traduit par un incrément du jour et
l’initialisation des heures, minutes et secondes.

Par contre si un système s’attend à recevoir des données après minuit et
que le fournisseur n’est pas en mesure de les produire, cela peut poser
problème : ce point sera donc à qualifier, si nécessaire, dans le cadre
des protocoles d’accord en tre AOT et OTP.

### Requête d’informations horaires calculées sur la ligne

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 2%" />
<col style="width: 11%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">EstimatedTimetable­Request</td>
<td>+Structure</td>
<td>Requête d’informations horaires calculées sur la ligne</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td colspan="2">Version</td>
<td>1:1</td>
<td>VersionString</td>
<td>Version du service “ Estimated Timetable”, intégrant le numéro de version de profil (voir 5.7) par exemple.. ‘2.0:FR-1.0’</td>
</tr>
<tr class="odd">
<td rowspan="2">Endpoint Properties</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date d'émission de la requête.</td>
</tr>
<tr class="even">
<td colspan="2">Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>MessageQualifier</td>
<td>Numéro d'identification du message</td>
</tr>
<tr class="odd">
<td>Topic</td>
<td colspan="2">Preview­Interval</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td>Si ce paramètre est présent, il indique que l'on souhaite recevoir des informations sur toute course proposant au moins une arrivée ou un départ intervenant dans la durée indiquée (à partir de l’heure de réception de la requête). S’il n’est pas présent, toutes les informations disponibles sur la journée d'exploitation sont remontées.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Timetable­VersionRef</td>
<td>0:1</td>
<td>xsd:string</td>
<td>Version du référenciel théorique connue : seuls les écarts par rapport à ce référentiel seront transmis.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Operator­Ref</td>
<td>0:1</td>
<td>Operator­Code</td>
<td>Identifie l’exploitant pour lequel on souhaite obtenir des informations<em>.</em></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Lines</td>
<td>0:*</td>
<td>LineDirection</td>
<td>Liste des lignes contenant les courses pour lesquelles on souhaite des informations.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>LineRef</td>
<td>0:1</td>
<td>Line­Code</td>
<td>Identifie la ligne pour laquelle on souhaite obtenir des informations.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Direction­Ref</td>
<td>0:1</td>
<td>Direction­Code</td>
<td><p>Filter the results to include only Stop Visits for vehicles running in a specific relative direction, for example, "inbound" or "outbound". (Direction does not specify a destination.)</p>
<p>Optional SIRI capability: TopicFiltering / ByDirection.</p></td>
</tr>
<tr class="odd">
<td>Policy</td>
<td colspan="2">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td>Au niveau des échanges inter-systèmes, les textes restent en français. Les éventuelles traductions seront prises en charge par les systèmes de présentation.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Include­Translations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the producer should include any available translations of NLString text elements into multiple languages. If false elements only one value per text element will be provided. +SIRI.2.0</p>
<p>Default is false.</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">EstimatedTimetableDetailLevel</td>
<td>0:1</td>
<td>EstimatedTimetableDetailLevelEnum</td>
<td><p>Level of detail to include in response. minimum | basic | normal | calls | full</p>
<p>Default is ‘normal’.</p>
<p>Optional SIRI capability: DetailLevel (if absent, must support normal).</p>
<p>+SIRI.2.0</p></td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2"></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

### Abonnement aux horaires calculés sur la ligne

Les notifications sont gérées de façons très légèrement différentes en
EstimatedTimetable et StopMonitoring (du fait des différences
structurelles des services).

Le tableau ci-dessous précise les conditions de notification pour
EstimatedTimetable.

|                                                                                                                                                                                                |                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| Condition de notification                                                                                                                                                                      | Commentaire                                                                                                                |
| Changement (incluant une première inscription dans le champ) d'une des heures de passage d'une valeur supérieure ou égale à ***ChangeBeforeUpdate*** par rapport à la précédente notification. | Notification différentielle (uniquement des ***Call*** concernés par ces changements) similaire à celle de StopMonitoring. |
| Lorsque le véhicule quitte l'arrêt (sauf pour le dernier arrêt)                                                                                                                                | Notification en positionnant le champ ***DepartureStatus*** à "*departed"*.                                                |
| A minima pour le dernier arrêt (et si possible pour tous les arrêts), lorsque le véhicule arrive à l'arrêt                                                                                     | Notification en positionnant le champ ***VehicleAtStop*** à *VRAI*                                                         |
| En cas de changement de quai                                                                                                                                                                   | Notification en positionnant les informations relatives au quai.                                                           |

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 19%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">EstimatedTimetable­SubscriptionRequest</td>
<td>+Structure</td>
<td>Requête d’abonnement aux horaires calculés sur la ligne</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td>Subscriber­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du système demandeur (voir SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.)</td>
</tr>
<tr class="odd">
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant de l'abonnement pour le système demandeur.</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td>Date et heure de fin de l'abonnement : un abonnement a forcément une date et heure de fin (les partenaires pourront décider de limiter la durée maximale d’un abonnement).</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>Estimated­Timetable­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>voir EstimatedTimetable­Request.</td>
</tr>
<tr class="even">
<td>Policy</td>
<td>Change­Before­Update</td>
<td>1:1</td>
<td>Positive­Duration­Type</td>
<td><p>Permet d'indiquer un écart de temps en dessous duquel on ne souhaite pas être notifié (si l'on demande un seuil de 5mn et qu'un horaire de départ change de 2mn, on ne sera pas notifié, évitant ainsi des flux d'information inutiles).</p>
<p>Si ce champ n'est pas présent, une valeur de <strong>5mn</strong> est prise par défaut.C’est une valeur « par défaut », qui est volontairement haute pour ne pas surcharger les échanges : dans le cas nominal elle devra être précisée avec une valeur plus faible (mais tous les systèmes ne fonctionnent pas à la minute, surtout côté client).</p>
<p>Dans le cadre des échanges avec un concentrateur la valeur par défaut est de <strong>1mn</strong>.</p>
<p>De plus il est important de noter que l'abonnement à Estimated Timetable fonctionne exclusivement en mode <strong>incrémental</strong> : ce service est en effet conçu pour les échanges en volume, et ne pas utiliser le mode incrémental serait complètement contreproductif par rapport à l'objectif de limiter les volumes d'échange.</p></td>
</tr>
</tbody>
</table>

### Réponse aux requêtes d’horaires calculés sur la ligne

|                              |                              |      |                |                                                                                                                                                      |
| ---------------------------- | ---------------------------- | ---- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Estimated­Timetable­Delivery |                              |      | +Structure     | Décrit une *Dated Timetables*. (horaire pour un jour d’application donné)                                                                            |
| Attributes                   | version                      | 1:1  | Version­String | Numéro de version du service *Estimated Timetable*, intégrant le numéro de version de profil (voir Error: Reference source not found) (valeur fixe). |
| LEADER                       | :::                          | 1:1  | xxx­Delivery   | voir xxx**Delivery**.                                                                                                                                |
| Payload                      | EstimatedJourneyVersionFrame | 0:\* | +Structure     | voir EstimatedJourneyVersionFrame element.                                                                                                           |
| any                          | Extensions                   | 0:1  | +Structure     | Voir paragraphe 5.4.2.2                                                                                                                              |

### Structure EstimatedJourneyVersionFrame

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 17%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">EstimatedJourneyVersionFrame</td>
<td>+Structure</td>
<td>Fournit les horaires attendus pour un itinéraire (ligne+direction) donné</td>
</tr>
<tr class="even">
<td>Log</td>
<td>Recorded­AtTime</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure à laquelles ces données ont été produites.</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>VersionRef</td>
<td>0:1</td>
<td>VersionCode</td>
<td><p>Contexte d'identification de la course (SAE pour le jour d'exploitation, version du référentiel de données, etc.).</p>
<p>Ce champ permet de qualifier la version de donnée de référence ie version du référentiel théorique (voir 2.3).)..</p></td>
</tr>
<tr class="even">
<td>Journeys</td>
<td>Estimated­Vehicle­Journey</td>
<td>1:*</td>
<td>+Structure</td>
<td><p>Description des courses sur l’itinéraire.</p>
<p>Voir EstimatedVehicleJourney element.</p></td>
</tr>
<tr class="odd">
<td>Connections</td>
<td>EstimatedServiceJourneyInterchange</td>
<td>0:*</td>
<td>+Structure</td>
<td>Connection parameters for a monitored SERVICE JOURNEY INTERCHANGE between a feeder and distributor journey. SIRI 2.0</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

### Structure EstimatedVehicleJourney

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 0%" />
<col style="width: 2%" />
<col style="width: 0%" />
<col style="width: 1%" />
<col style="width: 2%" />
<col style="width: 10%" />
<col style="width: 0%" />
<col style="width: 7%" />
<col style="width: 0%" />
<col style="width: 15%" />
<col style="width: 0%" />
<col style="width: 0%" />
<col style="width: 45%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="10">EstimatedVehicleJourney</td>
<td colspan="2">+Structure</td>
<td colspan="3">Description d’une course.</td>
</tr>
<tr class="even">
<td rowspan="9">Vehicle Journey Identity</td>
<td colspan="7">LineRef</td>
<td colspan="2">1:1</td>
<td colspan="2">LineCode</td>
<td colspan="3">Identifiant de la ligne.</td>
</tr>
<tr class="odd">
<td colspan="7">DirectionRef</td>
<td colspan="2">1:1</td>
<td colspan="2">Direction­Code</td>
<td colspan="3"><p>Identifie la direction (typiquement Aller/Retour).</p>
<p>La sélection de ce champ n’est pas dans la logique du reste du profil (plutôt porté sur Destination, voir plus bas) mais est maintenu du fait de la cardinalité imposée par SIRI (le champ est obligatoire dans la description XSD de SIRI et doit donc être maintenu, il pourra toutefois être laissé vide, sans que cela ne pose problème…)</p></td>
</tr>
<tr class="even">
<td colspan="7"></td>
<td colspan="2"></td>
<td colspan="2">choice</td>
<td colspan="3">Seul le choix <em>a, b</em> ou <em>c</em> est possible …</td>
</tr>
<tr class="odd">
<td colspan="2">a</td>
<td colspan="5">Dated­Vehicle­Journey­Ref</td>
<td colspan="2" rowspan="2">–1:1</td>
<td colspan="3">DatedVehicle­Journey­Code</td>
<td colspan="2"><p>Identifie la course.</p>
<p>Cette information est obligatoire dans le cadre des échanges avec un concentrateur.</p></td>
</tr>
<tr class="even">
<td colspan="2" rowspan="5">b</td>
<td colspan="5">Dated­Vehicle­Journey­Indirect­Ref</td>
<td colspan="3">+Structure</td>
<td colspan="2">Si les systèmes en communication n’ont pas de référentiel commun pour identifier les courses, la structure ci-dessous permet de la décrire succinctement.</td>
</tr>
<tr class="odd">
<td colspan="3" rowspan="4"></td>
<td colspan="2">Origin­Ref</td>
<td colspan="2">1:1</td>
<td colspan="3">StopPoint­Code</td>
<td colspan="2">Identifiant du premier point d’arrêt de la course.</td>
</tr>
<tr class="even">
<td colspan="2">Aimed­Departure­Time</td>
<td colspan="2">1:1</td>
<td colspan="3">xsd:dateTime</td>
<td colspan="2">Heure de depart (théorique) au premier point d’arrêt.</td>
</tr>
<tr class="odd">
<td colspan="2">Destination­Ref</td>
<td colspan="2">1:1</td>
<td colspan="3">StopPoint­Code</td>
<td colspan="2">Identifiant du dernier point d’arrêt de la course.</td>
</tr>
<tr class="even">
<td colspan="2">Aimed­Arrival­Time</td>
<td colspan="2">1:1</td>
<td colspan="3">xsd:dateTime</td>
<td colspan="2">Heure d’arrivée (théorique) au dernier point d’arrêt.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">c</td>
<td colspan="5">Estimated­Vehicle­Journey­Code</td>
<td colspan="2">1:1</td>
<td colspan="3">Estimated­Vehicle­Journey­Code</td>
<td colspan="2"><p>Permet d’identifier une nouvelle course (course ajoutée par rapport aux horaires théoriques).</p>
<p>Si ce champ est présent,. <em><strong>ExtraJourney</strong></em> doit être positionné à ‘true’ (et réciproquement…).</p>
<p>Cette information est obligatoire (si une course a été ajoutée) dans le cadre des échanges avec un concentrateur. Dans le cas ou l'adjonction de course ne peut être détectée, la structure <em><strong>Dated­Vehicle­Journey­Ref</strong></em> sera remplie comme pour les autres courses.</p></td>
</tr>
<tr class="even">
<td rowspan="2">Change</td>
<td colspan="7">ExtraJourney</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:boolean</td>
<td colspan="3"><p>Signale qu’il s’agit d’une nouvelle course, ajoutée par rapport aux horaires théoriques.</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="odd">
<td colspan="7">Cancellation</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:boolean</td>
<td colspan="3"><p>Signale la suppression de la course identifiée.</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="even">
<td>Journey­Pattern Info</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">Journey­Pattern­Info­Group</td>
<td colspan="3">Voir Journey­Pattern­Info­Group.</td>
</tr>
<tr class="odd">
<td>JourneyEndNames</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">JourneyEndNamesGroup</td>
<td colspan="3">Voir JourneyEndNamesGroup</td>
</tr>
<tr class="even">
<td>VehicleJourneyInfo</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">VehicleJourneyInfoGroup</td>
<td colspan="3">Voir VehicleJourneyInfoGroup</td>
</tr>
<tr class="odd">
<td>Service Info</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">Service­Info­Group</td>
<td colspan="3">Voir Service­Info­Group.</td>
</tr>
<tr class="even">
<td rowspan="8">Journey Info</td>
<td colspan="7">Vehicle­Journey­Name</td>
<td colspan="2">0:1</td>
<td colspan="2">NLString</td>
<td colspan="3">Nom commercial de la course.</td>
</tr>
<tr class="odd">
<td colspan="7">JourneyNote</td>
<td colspan="2">0:*</td>
<td colspan="2">NLString</td>
<td colspan="3">Texte complémentaire décrivant la course.</td>
</tr>
<tr class="even">
<td colspan="7">PublicContact</td>
<td colspan="2">0:1</td>
<td colspan="2">+Structure</td>
<td colspan="3">Contact details for use by members of public. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="6">PhoneNumber</td>
<td colspan="2">0:1</td>
<td colspan="2">PhoneType</td>
<td colspan="3">Phone number for Public to contact OPERATOR of journey. +SIRI v2.0</td>
</tr>
<tr class="even">
<td colspan="6"></td>
<td>Url</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:anyUri</td>
<td colspan="3">Public URL to contact OPERATOR of journey. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td colspan="7">OperationsContact</td>
<td colspan="2">0:1</td>
<td colspan="2">+Structure</td>
<td colspan="3">Contact details for use by operational staff. +SIRI v2.0</td>
</tr>
<tr class="even">
<td></td>
<td colspan="6">PhoneNumber</td>
<td colspan="2">0:1</td>
<td colspan="2">PhoneType</td>
<td colspan="3">Phone number for operational contact. Not for Public use. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td colspan="6"></td>
<td>Url</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:anyUri</td>
<td colspan="3">URL number for operational contact. Not for Public use. +SIRI v2.0</td>
</tr>
<tr class="even">
<td>Estimated­Info</td>
<td colspan="7">Headway­Service</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:boolean</td>
<td colspan="3"><p>Indique si la course est gérée dans un contexte d’exploitation (ou d’information seulement) en fréquence.</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="7">Origin­Aimed­Departure­Time</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:date­Time</td>
<td colspan="3">Heure théorique de départ de la course à son point de départ.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="7">Destination­Aimed­Arrival­Time</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:date­Time</td>
<td colspan="3">Heure théorique d'arrivée de la course à son point de d'arrivée.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="7">FirstOrLastJourney</td>
<td colspan="2">0:1</td>
<td colspan="2">FirstOrLastJourneyEnum</td>
<td colspan="3"><p>Indique s'il s'agit de la première ou de la dernière course de la journée d'exploitation sur la ligne, et pour une destination donnée. L'interprétation comme "première ou dernière course pour une mission donnée" est acceptable, mais devra être précisée dans les spécifications d'interface du serveur (et le JourneyPatterInfoGroup devra alors être renseigné).</p>
<p>(firstServiceOfDay | lastServiceOfDay | otherService | unspecified).</p>
<p>+SIRI v2.0.</p></td>
</tr>
<tr class="even">
<td>Disruption­Group</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">Disrupt­ion­Group</td>
<td colspan="3">Voir Disruption­Group..</td>
</tr>
<tr class="odd">
<td>Journey­Progress­Info</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">Journey­Progresss­Info­Group</td>
<td colspan="3"><p>voir Journey­Progress­Info­Group.</p>
<p>DetailLevel: normal.</p></td>
</tr>
<tr class="even">
<td rowspan="4">Train­Block­Part</td>
<td colspan="7">TrainBlock­Part</td>
<td colspan="2">0:1</td>
<td colspan="2">TrainBlock­Part­Structure</td>
<td colspan="3">Associates Stop Visit with a part of a train: for use when trains split or merge.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="6">NumberOf­BlockParts</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:positive­Integer</td>
<td colspan="3">Total number of block parts making up the train of which this is part.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="6">TrainPart­Ref</td>
<td colspan="2">0:1</td>
<td colspan="2">TrainPartCode</td>
<td colspan="3">Identifier of train block part.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="6">PositionOf­ TrainBlock­Part</td>
<td colspan="2">0:1</td>
<td colspan="2">NLString</td>
<td colspan="3">Description of position of TrainBlockPart within Train to guide passengers where to find it. E.g. 'Front four coaches'</td>
</tr>
<tr class="even">
<td rowspan="8">Opera­tional­Info</td>
<td colspan="7">:::</td>
<td colspan="2">0:1</td>
<td colspan="2">Operational­Info­Group</td>
<td colspan="3"><p>Voir SIRI Part 2 OperationalInfo­Group.</p>
<p>BlockRef &amp; CourseOfJourney­Ref:</p></td>
</tr>
<tr class="odd">
<td colspan="7">TrainNumber</td>
<td colspan="2">0:*</td>
<td colspan="2">sequence</td>
<td colspan="3"><p>Séquence de numéro de train (l'utilisation d'une sequence permet notament de gérer les trains couples)</p>
<p>+SIRI v2.0</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="6">TrainNumberRef</td>
<td colspan="2">1:1</td>
<td colspan="2">TrainNumber</td>
<td colspan="3"><p>Numéro de train</p>
<p>On utilisera en priorité la codification de code primaire UE 454/2011 ou le numéro de train UIC</p>
<p>+SIRI v2.0</p></td>
</tr>
<tr class="odd">
<td colspan="7">JourneyParts</td>
<td colspan="2">0:*</td>
<td colspan="2">sequence</td>
<td colspan="3"><p>Liste des parties de course concernée par les Call ci-dessous.</p>
<p>Dans le cadre du profil France on utilisera ces sous-ensembles de course exclusivement pour porter la parité des trains (avec possibilité de changer de parité en cours de course).</p>
<p>+SIRI v2.0</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="6">JourneyPart­Info</td>
<td colspan="2">1:1</td>
<td colspan="2">+Structure</td>
<td colspan="3"><p>Information sur les parties de course</p>
<p>+SIRI v2.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3"></td>
<td colspan="3">Journey­PartRef</td>
<td colspan="2">0:1</td>
<td colspan="2">JourneyPart­Code</td>
<td colspan="3"><p>Dans le cadre du profil France ce champ permettra d'identifier les portions de courses exploitées par des opérateurs différents : les valeurs d'identification des JourneyPart sont des données de référence qui devront être fixées en amont de l'échange.</p>
<p>Exemple de Ile de France : cas du RER, les portions de courses exploitées par la RATP et celles exploitées par la SNCF</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="3"></td>
<td colspan="3">Train­NumberRef</td>
<td colspan="2">0:1</td>
<td colspan="2">TrainNumbere</td>
<td colspan="3"><p>Dans le cadre du profil France ce champ sera suffixé, pour la SNCF, des code suivants:</p>
<ul>
<li><p>:2 pour les trains de parité paire</p></li>
<li><p>:1 pour les trains de parité impaire</p></li>
</ul>
<p>L'association à une JourneyPart permet de gérer les changements de parité en cours de course. Si la parité est invariable, une seule JourneyPart sera définie.</p>
<p>Si le numéro de train n'est pas connu mais que la parité doit tout de même être échangée, ce champ contiendra "<em><strong>unknown:1</strong></em>" ou "<em><strong>unknown:2</strong></em>".</p>
<p>Si les identifiants de JourneyPart n'ont pas été échangés mais que la parité doit tout de même être échangée, le champ précédent (JourneyPartRef, qui est obligatoire) prendra la valeur arbitraire de "<em><strong>unknown</strong></em>".</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3"></td>
<td colspan="3">Operator­Ref</td>
<td colspan="2">0:1</td>
<td colspan="2">Operator­Code</td>
<td colspan="3">Reference to OPERATOR of a JOURNEY PART.</td>
</tr>
<tr class="even">
<td rowspan="3">Calls</td>
<td colspan="7">RecordedCall</td>
<td colspan="2">0:1</td>
<td colspan="2">+Structure</td>
<td colspan="3">Observed call times for that art of the journey that has already been completed.</td>
</tr>
<tr class="odd">
<td rowspan="2">a</td>
<td colspan="7">Estimated­Calls</td>
<td colspan="2">0:1</td>
<td colspan="3">+Structure</td>
<td>Description ordonnée des arrêts et heures de passage.</td>
</tr>
<tr class="even">
<td colspan="2"></td>
<td colspan="5">Estimated­Call</td>
<td colspan="2">1:*</td>
<td colspan="3">+Structure</td>
<td>Voir EstimatedCall.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="7">IsComplete­Stop­Sequence</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:boolean</td>
<td colspan="3"><p>Indique si la liste des arrêts est complète ou non.</p>
<p>Dans le cadre du profil France, en mode requête-réponse, elle sera toujours complète - le champ vaudra donc ‘true’ (on remonte l'ensemble des passages non encore échus).</p>
<p>En mode abonnement, le mode différentiel étant appliqué, la séquence d'arrêt sera régulièrement incomplète.</p>
<p>Il faut noter que cette indication ne concerne que les passages à échoir et non les passages déjà échus.</p></td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="7">Extensions</td>
<td colspan="2">0:1</td>
<td colspan="2">any</td>
<td colspan="3">Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

### Structure EstimatedCall

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 2%" />
<col style="width: 12%" />
<col style="width: 7%" />
<col style="width: 15%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">EstimatedCall</td>
<td>+­Structure</td>
<td>Description d’un arrêt prévu, avec ses informations horaires</td>
</tr>
<tr class="even">
<td rowspan="4">Stop Identity</td>
<td colspan="2">Stop­Point­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>StopPoint­Code</td>
<td>Identifiant du Point d'arrêt (cet identifiant est à rapprocher de l’attribut <em>MonitoringRef</em> de la structure <em>MonitoredStopVisit</em>, mais restreint à ce cas de point d’arrêt là ou le <em>MonitoringRef</em> peut aussi, dans le contexte général de SIRI, <del>,</del> référencer un afficheur, par exemple).</td>
</tr>
<tr class="odd">
<td colspan="2">Visit­Number</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the <strong>VisitNumber</strong> count is used to distinguish each separate visit. If not specified, default is ‘1’.</td>
</tr>
<tr class="even">
<td colspan="2">Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission.</td>
</tr>
<tr class="odd">
<td colspan="2">Stop­Point­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom du point d'arrêt.</td>
</tr>
<tr class="even">
<td rowspan="2">Change</td>
<td colspan="2">ExtraCall</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Signale si cet arrêt a été ajouté sur la course (par rapport aux horaires théoriques).</td>
</tr>
<tr class="odd">
<td colspan="2">Cancellation</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>La valeur « true » signale que, contrairement à ce que prévoyaient les horaires théoriques, cet arrêt n’est plus desservi.</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="even">
<td rowspan="2">Real time Info</td>
<td colspan="2">Prediction­Inaccurate</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the vehicle is in congestion. If not, present, not known. Inheritable.</p>
<p>On utilisera les attributs au niveau de la course.</p></td>
</tr>
<tr class="odd">
<td colspan="2">Occupancy</td>
<td>0:1</td>
<td>full | seats­Available | standing­Available</td>
<td><p>How full the vehicle is at the stop. Enumeration. If omitted: <strong>Occupancy</strong> is as for journey. Enumeration.</p>
<p>On utilisera les attributs au niveau de la course.</p></td>
</tr>
<tr class="even">
<td rowspan="2">Call Realtime Group</td>
<td colspan="2">VehicleAt­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indicateur “Véhicule à l’arrêt”.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="odd">
<td colspan="2">VehicleLocationAtStop</td>
<td>0:1</td>
<td>LocationStructure</td>
<td>Exact location that VEHICLE will take up / or has taken at STOP POINT.</td>
</tr>
<tr class="even">
<td rowspan="3">Call Rail Group</td>
<td colspan="2">Reverses­At­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether vehicle reverses at stop. Default is false.</td>
</tr>
<tr class="odd">
<td colspan="2">Platform­Traversal</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>La valeur « true » permet de signaler le passage d'un train sans arrêt (et de demander au voyageur de s'écarter des voies)</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="even">
<td colspan="2">Signal­Status</td>
<td>0:1</td>
<td>xsd:NMTOKEN</td>
<td>Status of signal clearance for train. This may affect the presentation emphasis given to arrival or departures on displays – e.g. cleared trains appear first, flashing in green.</td>
</tr>
<tr class="odd">
<td rowspan="4">Call Property</td>
<td colspan="2">TimingPoint</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the stop is a timing point. Times for stops that are not timing points are sometimes interpolated crudely from the timing points, and may represent a lower level of accuracy. Default is true.</td>
</tr>
<tr class="even">
<td colspan="2">Boarding­Stretch</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether this is a Hail and Ride Stop. Default is false.</td>
</tr>
<tr class="odd">
<td colspan="2">Request­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether Vehicle stops only if requested explicitly by passenger. Default is false.</td>
</tr>
<tr class="even">
<td colspan="2">Destination­Display</td>
<td>0:1</td>
<td>NLString</td>
<td>Destination telle qu'elle est affichée sur la girouette du véhicule à cet arrêt (ou sur l’afficheur local).</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">CallNote</td>
<td>0:*</td>
<td>NLString</td>
<td>Text annotation that applies to this call.</td>
</tr>
<tr class="even">
<td>Disruption­Group</td>
<td colspan="2">:::</td>
<td>0:1</td>
<td>Disrupt­ion­Group</td>
<td>Voir Disruption­Group.</td>
</tr>
<tr class="odd">
<td rowspan="11">Arrival</td>
<td colspan="2">Aimed­Arrival­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure d'arrivée théorique (ou commandée).</td>
</tr>
<tr class="even">
<td colspan="2">Expected­Arrival­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure d'arrivée estimée par le SAE.</td>
</tr>
<tr class="odd">
<td colspan="2">Arrival­Status</td>
<td>0:1</td>
<td>onTime | missed | arrived | notExpected | | delayed | early | cancelled | noReport</td>
<td><p>Caractérisation de l'horaire d'arrivée attendu (ou mesuré si le véhicule est à quai).</p>
<p>Valeur par défaut : « onTime »</p></td>
</tr>
<tr class="even">
<td colspan="2">ArrivalProximity­Text</td>
<td>0:*</td>
<td>NLString</td>
<td>Texte libre à présenter quand le véhicule est proche, par exemple "à l'approche".</td>
</tr>
<tr class="odd">
<td colspan="2">Arrival­PlatformName</td>
<td>0:1</td>
<td>NLString</td>
<td>Identification ou nom du quai d'arrivée.</td>
</tr>
<tr class="even">
<td colspan="2">Arrival­Boarding­Activity</td>
<td>0:1</td>
<td>alighting | noAlighting | passThru</td>
<td><p>Type of boarding and alighting allowed at stop. Default is Alighting.</p>
<p>On utilisera le <em><strong>Departure­Boarding­Activity</strong></em> dans le profil France</p></td>
</tr>
<tr class="odd">
<td colspan="2">ArrivalStopAssignment</td>
<td>0:1</td>
<td>+Structure</td>
<td>Affectation du point d'arrêt planifié à un quay</td>
</tr>
<tr class="even">
<td></td>
<td>Aimed­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the planned timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td>Aimed­­QuayName</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Indication de la voie d'arrivée (en complément de Platform)<em>.</em></p>
<p>Ce champ permet de remplacer l'extension PlateformType introduite par le profil 2.3 et abondonnée en version 2.4 au profit des champs normalisés.</p></td>
</tr>
<tr class="even">
<td></td>
<td>Expected­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the real-time prediction. <del>+SIRI v2.0</del></td>
</tr>
<tr class="odd">
<td></td>
<td>Actual­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY actually used<del>.</del></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">ArrivalOperatorRefs</td>
<td>0:1</td>
<td>OperatorRefStructure</td>
<td>OPERATORs of othe service up until arrival.. May change for departure.</td>
</tr>
<tr class="odd">
<td rowspan="7">Departure</td>
<td colspan="2">Aimed­Departure­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure de départ théorique (ou commandée).</td>
</tr>
<tr class="even">
<td colspan="2">Expected­Departure­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure de départ estimée par le SAE.</td>
</tr>
<tr class="odd">
<td colspan="2">ProvisionalExpectedDepartureTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Estimated departure time of VEHICLE without waiting time due to operational actions. For people at stop this would normally be shown if different from Expected departure time.</td>
</tr>
<tr class="even">
<td colspan="2">EarliestExpected­DepartureTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Earliest time at which VEHICLE may leave the stop. Used to secure connections. Used for passenger announcements. Passengers must be at boarding point by this time to be sure of catching VEHICLE.</td>
</tr>
<tr class="odd">
<td colspan="2">ExpectedDeparture­PredictionQuality</td>
<td>0:1</td>
<td>+Prediction­Quality</td>
<td><p>Prediction quality, either as approximate confidence level or as a more quantitative percentile range of predictions that will fall within a given range of times<del>.</del></p>
<p>If not defined for some CALLs, an Extrapolation Rule can be applied.</p></td>
</tr>
<tr class="even">
<td colspan="2">AimedLatestPassengerAccessTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Target Latest time at which a PASSENGER should aim to arrive at the STOP PLACE containing the stop. This time may be earlier than the VEHICLE departure times as itmay include time for processes such as checkin, security, etc.(As specified by CHECK CONSTRAINT DELAYs in the underlying data) If absent assume to be the same as Earliest expected departure time,</td>
</tr>
<tr class="odd">
<td colspan="2">ExpectedLatestPassengerAccessTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Expected Latest time at which a PASSENGER should aim to arrive at the STOP PLACE containing the stop. This time may be earlier than the VEHICLE departure times as it may include time for processes such as checkin, security, etc.(As specified by CHECK CONSTRAINT DELAYs in the underlying data) If absent assume to be the same as Earliest expected departure time,</td>
</tr>
<tr class="even">
<td>Departure Status</td>
<td colspan="2">Departure­Status</td>
<td>0:1</td>
<td>onTime | early | delayed | cancelled | arrived |departed | notExpected | noReport</td>
<td><p>Caractérisation de l'horaire de départ attendu (ou mesuré si le véhicule est à quai).</p>
<p>Valeur par défaut : « onTime »</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Departure­ProximityText</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Arbitrary text string to show to indicate the proximity status of the departure of the VEHICLE, for example, “Boarding”, “GatesClosed”.</p>
<p>One per language</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Departure­Platform­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Identification ou nom du quai de départ.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Departure­Boarding­Activity</td>
<td>0:1</td>
<td>boarding | noBoarding | passThru</td>
<td><p>Caractérisation de l'horaire de départ attendu (ou mesuré si le véhicule est à quai).</p>
<p>Valeur par défaut : « boarding »</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">DepartureStop­Assignment</td>
<td>0:1</td>
<td>+Structure</td>
<td>Assignments of departure platform for SCHEDULED STOP POINT to a physical QUAY<del>.</del>.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Aimed­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the planned timetable.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Aimed­­QuayName</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Scheduled QUAY (Platform) name. Can be used to indicate a platform change.</p>
<p>One per language</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Expected­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the real-time prediction.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Actual­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) actually used.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">DepartureOperatorRefs</td>
<td>0:1</td>
<td>OperatorRefStructure</td>
<td>OPERATORs of the service for departure and onwards.. May change from that for arrival.</td>
</tr>
<tr class="even">
<td rowspan="2"></td>
<td colspan="2">Aimed­Headway­Interval</td>
<td>0:1</td>
<td>Positive­Duration</td>
<td>Fréquence de passage théorique (ou commandée).</td>
</tr>
<tr class="odd">
<td colspan="2">Estimated­Headway­Interval</td>
<td>0:1</td>
<td>Positive­Duration</td>
<td>Fréquence de passage estimée par le SAE.</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

Il faut noter que le document SIRI donne des indications nombreuses et
précises sur cette structure, en particulier en « part 3 : 6.6 Handling
of Predictions in the Estimated Timetable Service »

## Stop Monitoring

|      |                                                                                                                                 |
| ---- | ------------------------------------------------------------------------------------------------------------------------------- |
| SM-1 | La notion de «niveau de détail » (Detail Level) proposée pour ce service par SIRI n'est pas retenue pour le profil SIRI France. |

### Capability Matrix

|      |                                                                   |
| ---- | ----------------------------------------------------------------- |
| SM-2 | Cette matrice n'est pas échangée dans le cadre du profil France : |

Cette,matrice est présentée ici pour indiquer les principales fonctions
retenues pour le service (les explications ne sont pas traduites dans ce
tableau, mais on retrouve les traductions dans les tableaux qui
suivent).

|                |                         |     |
| -------------- | ----------------------- | --- |
| TopicFiltering |                         |     |
|                | DefaultPreview­Interval | Oui |
|                | FilterByMonitoring­Ref  | Oui |
|                | FilterByLineRef         | Oui |
|                | FilterByDirectionRef    | Non |
|                | FilterByDestination     | Oui |
|                | FilterByVisitType       | Non |

|                    |                               |     |
| ------------------ | ----------------------------- | --- |
| RequestPolicy      |                               |     |
|                    | Language                      | Non |
| a                  | GmlCoordinateFormat           | Oui |
| b                  | WgsDecimalDegrees             | Non |
|                    | UseReferences                 | Oui |
|                    | UseNames                      | Oui |
|                    | HasDetailLevel                | Non |
|                    | DefaultDetailLevel            | Non |
|                    | HasMaximumVisits              | Non |
|                    | HasMinimum­StopVisits­PerLine | Oui |
|                    | HasNumberOf­OnwardsCalls      | Oui |
|                    | HasNumberOf­PreviousCalls     | Non |
| SubscriptionPolicy |                               |     |
|                    | HasIncremental­Updates        | Oui |
|                    | HasChangeSensitivity          | Oui |
| AccessControl      |                               |     |
|                    | RequestChecking               | Non |
|                    | CheckOperatorRef              | Non |
|                    | CheckLineRef                  | Non |
|                    | CheckMonitoringRef            | Non |
| ResponseFeatures   |                               |     |
|                    | HasLineNotice                 | Non |
| Extensions         |                               | Non |

### Requête d'information temps réel au point d'arrêt

*<u>Note importante</u>* : Il est possible d’effectuer une requête sur
un ensemble de points d’arrêt. On constatera, ci-dessous, que le champ
« MonitoringRef », qui caractérise le point d’arrêt, a une cardinalité
1:1, cela vient du fait que c’est l’ensemble du bloc
« StopMonitoringRequest » qui doit être répété au sein de la structure
« ServiceRequest ». Cela se justifie par le fait que, dans un certain
nombre de cas, la désignation du simple « MonitoringRef » peut s’avérer
insuffisante (s‘il s’agit d’un ‘Lieu d’arrêt (multimodal), on pourra,
par exemple, être amené à préciser la ligne et la destination en plus du
« MonitoringRef »…).

Note concernant la granularité des objets interrogés :

Le « MonitoringRef » peut aussi bien référencer :

-   Un Groupe de Lieux

-   Un lieu d’arrêt multimodal

-   Un pole monomodal

-   Un lieu d’arrêt monomodal

-   un Lieu d'Arrêt

-   une Zone de Lieu

-   une Zone d'Embarquement ~~REFLEX~~

|      |                                                                                                                                                                                                                                                          |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SM-3 | Toutefois il n'y a pas d'obligation pour un serveur de supporter tous ces niveaux (sauf pour les concentrateurs pour lesquels le Lieu d’arrêt est obligatoire): il conviendra donc de s'assurer que le serveur sollicité reconnait bien le niveau requis |

Note concernant les heures de passage :

SIRI propose plusieurs niveaux d'information sur les heures de passage:

-   *Aimed(Departure/Arrival)Time* : Heure d'arrivée ou de départ
    théorique. Il s'agit là de l'heure planifiée (figurant dans les
    fichiers horaires). Il peut aussi s'agir de l'horaire replanifié du
    matin s’il est disponible (horaire commandé).

-   *Actual(Departure/Arrival)Time* : Heure d'arrivée ou de départ
    effectivement mesurée (et donc disponible uniquement après le départ
    ou l’arrivée du véhicule).

-   *Expected(Departure/Arrival)Time* : Heure d'arrivée ou de départ
    calculée par le SAE sur la base de la progression du véhicule et du
    commandé (ou modifié en cours d'exploitation).

|      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SM-4 | Par contre il n'est pas obligatoire de diffuser avant le départ du véhicule l'horaire théorique modifié du jour même ou modifié en cours d'exploitation suite à une régulation. Cette information peut par contre être renseignée dans l' «Expected(Departure/Arrival)Time», le champ étant par la suite mis à jour en fonction de l'avancement du véhicule.                                                                                                                                                                                                                                                |
| SM-4 | En mode requête classique, les heures de passage à l'arrêt ne sont fournies que tant que le véhicule est en amont de l’arrêt ou à l’arrêt ; dès lors qu’il a quitté l’arrêt, aucune information concernant ce véhicule à cet arrêt n'est plus fournie (dans la limite ci-dessous).                                                                                                                                                                                                                                                                                                                          |
| SM-5 | En mode abonnement, une notification est envoyée lorsque le véhicule a quitté l’arrêt, en utilisant la structure « MonitoredStopVisitCancellation ». Ceci permet de signaler aux diffuseurs que le prochain passage en question doit être retiré des medias de diffusion (on utilisera donc pas le champ "ActualDepartureTime" à cet effet). En complément, une notification est aussi réalisée lors de l'arrivée au dernier arrêt (il n'y aura en effet pas de notification de départ dans ce cas: on notifiera alors un « MonitoredStopVisitCancellation » au moment de l'arrivée du véhicule à l'arrêt). |
| SM-6 | En situation perturbée il peut arriver qu'une information «Expected(Departure/Arrival)Time» soit antérieure à l’heure courante. Toutefois il est précisé qu'en tout état de cause, un temps d’attente inférieur ou égal à 0, induit par une telle information, doit être diffusé comme un temps d’attente égal à 0 (et probablement accompagné d'une indication de retard).                                                                                                                                                                                                                                 |

Note concernant les statuts (avance, retard, etc.):

SIRI propose des statuts de départ et d'arrivée pour qualifier l'horaire
calculé par rapport à l'horaire planifié. Le tableau ci-dessous précise
l'usage des différentes valeurs de statuts.

|              |                                                                                                                                                                                            |                 |                                                                                                                                                                                            |     |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- |
| Statuts      | ArrivalStatus                                                                                                                                                                              | DepartureStatus |                                                                                                                                                                                            |     |
| onTime       | A l’heure ; la notion peut être précisée à la discrétion du producteur selon un seuil à préciser dans les spécifications d’interface à titre informatif.                                   |                 | A l’heure ; la notion peut être précisée à la discrétion du producteur selon un seuil à préciser dans les spécifications d’interface à titre informatif.                                   |     |
| Early        | En avance par rapport à l’horaire théorique ; la notion peut être précisée à la discrétion du producteur selon un seuil à préciser dans les spécifications d’interface à titre informatif. |                 | En avance par rapport à l’horaire théorique ; la notion peut être précisée à la discrétion du producteur selon un seuil à préciser dans les spécifications d’interface à titre informatif. |     |
| Delayed      | En retard par rapport à l’horaire théorique ; la notion peut être précisée à la discrétion du producteur selon un seuil à préciser dans les spécifications d’interface à titre informatif. |                 | En retard par rapport à l’horaire théorique ; la notion peut être précisée à la discrétion du producteur selon un seuil à préciser dans les spécifications d’interface à titre informatif. |     |
| Cancelled    | Passage annulé                                                                                                                                                                             |                 | Passage annulé (note: ce passage annulé reste comptabilisé dans le nombre de passages utilisé dans les filtres de requêtes).                                                               |     |
| Arrived      | Non utilisé dans le cadre du profil Île-de-France                                                                                                                                          |                 | Non utilisé dans le cadre du profil France                                                                                                                                                 |     |
| Departed     | Non utilisé dans le cadre du profil France                                                                                                                                                 |                 | Le véhicule a déjà quitté l'arrêt                                                                                                                                                          |     |
| Not Expected | Non utilisé dans le cadre du profil France                                                                                                                                                 |                 | Non utilisé dans le cadre du profil France                                                                                                                                                 |     |
| noReport     | Pas d’information « ExpectedArrivalTime » disponible (par contre le « AimededArrivalTime » peut être fourni)                                                                               |                 | Pas d’information disponible                                                                                                                                                               |     |

Note concernant les derniers arrêts de course:

Il existe plusieurs façons d'identifier le dernier arrêt d'une course :

-   La plus fiable consiste à faire la distinction des terminus par
    constat d'égalité dans le VehicleJourneyInfoGroup entre l'arrêt
    courant et l'arrêt de destination de la course.

-   Toutefois, cela peut aussi être fait en constatant que l'on a un
    ArrivalTime mais pas de DepartureTime

-   ou encore, quand cela est possible, en demandant des informations
    sur les arrêts suivants (onwardCall, en demandant au moins un arrêt)
    et en constatant qu'il n'y en a pas.

Note concernant les cas ou il n'y a pas ou plus d'information:

|      |                                                                                                                                                                                                                                                                                                                                                                                    |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SM-7 | S'il n'y a de réponse à une requête « Stop monitoring » car elle intervient après le dernier passage de la journée, le producteur doit dans la mesure du possible fournir une information via le service « General message ». Il est donc recommandé que le client, s'il n'obtient pas de réponse au « Stop monitoring », fasse dans la foulée une requête au « General message ». |
| SM-8 | Dans le cas des déviations : pour les arrêts non desservis, il conviendra aussi de fournir une information via le service « General message » ou « Situation Exchange » (la réponse à « Stop monitoring n'est toutefois pas forcément vide si la déviation est temporaire »).                                                                                                      |

Note concernant les annulations de passage :

Concernant les informations permettant d'indiquer l'annulation d'un
passage il est précisé que:

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 92%" />
</colgroup>
<tbody>
<tr class="odd">
<td>SM-9</td>
<td><p>Mode requête</p>
<ul>
<li><p>La réponse positionne à « Cancelled » le champ « ArrivalStatus » et/ou « DepartureStatus » dans « MonitoredCall » jusqu’à l’heure d’arrivée théorique</p></li>
<li><p>Puis aucune information n'est plus fournie pour cette course</p></li>
</ul></td>
</tr>
<tr class="even">
<td>SM-10</td>
<td><p>Mode abonnement</p>
<ul>
<li><p>Une (unique) notification est faite en positionnant à « Cancelled » le champ « ArrivalStatus » et/ou « DepartureStatus » dans « MonitoredCall »</p></li>
</ul></td>
</tr>
</tbody>
</table>

Note concernant les MonitoredCall, OnwardCall et PreviousCall :

L'utilisation des « OnwardCall » et « PreviousCall » mérite d'être
précisée car elle est légèrement différente suivant qu'on les utilise
dans le service StopMonitoring ou le service VehicleMonitoring.

|       |                                                                                                                                                                                                                                                                                                                    |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| SM-11 | Le « PreviousCall » n'a pas été retenu par le profil France et ne doit donc pas être utilisé.                                                                                                                                                                                                                      |
| SM-12 | ~~Dans le cas du service StopMonitoring le~~ Le « MonitoredCall» correspond à l'arrêt pour lequel on a fait l'interrogation (et n'est donc en aucun cas lié à la position du véhicule). Les « OnwardCall » correspondent alors à tous les arrêts suivant ce « MonitoredCall» dans le cadre des courses concernées. |

Dans le cas du service VehicleMonitoring le « MonitoredCall» correspond
au dernier arrêt marqué ou à l'arrêt où se trouve le véhicule s'il est à
l'arrêt. Les « OnwardCall » correspondent alors à tous les arrêts
suivants pour ce véhicule dans le cadre de sa course.

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 2%" />
<col style="width: 3%" />
<col style="width: 9%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 53%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="5">StopMonitoringRequest</td>
<td>+Structure</td>
<td>Requête pour obtenir des informations temps réel sur les heures d'arrivée et de départ à un point d'arrêt</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td colspan="3">Version</td>
<td>1:1</td>
<td>Version­String</td>
<td>Version du service “Stop Monitoring”, , intégrant le numéro de version de profil par exemple. ‘2.0:FR-1.0’</td>
</tr>
<tr class="odd">
<td rowspan="2">Endpoint Properties</td>
<td colspan="3">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date d'émission de la requête</td>
</tr>
<tr class="even">
<td colspan="3">Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Numéro d'identification du message</td>
</tr>
<tr class="odd">
<td rowspan="6">Topic</td>
<td colspan="3">Preview­Interval</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Si ce paramètre est présent, il indique que l'on souhaite recevoir des informations sur toute arrivée et tout départ intervenant dans la durée indiquée (comptée à partir de l'heure indiquée par le paramètre suivant: <em><strong>StartTime</strong></em> ... si le paramètre <em><strong>StartTime</strong></em> n'est pas présent, l'heure courante sera utilisée).</td>
</tr>
<tr class="even">
<td colspan="3">StartTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure à partir de laquelle doit être compté le <em><strong>Preview­Interval</strong></em></td>
</tr>
<tr class="odd">
<td colspan="3">Monitoring­Ref</td>
<td>1:1</td>
<td>Monitoring­Code</td>
<td><p>Identifiant du point d'arrêt concerné par la requête.</p>
<p>Il convient d'utiliser ici un identifiant d'objets (arrêt) de référence (Zone d'Embarquement, Lieu d’arrêt multi ou mono modal ou Groupe de Lieux), et non d'objet particulier.</p></td>
</tr>
<tr class="even">
<td colspan="3">LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Filtre permettant de n'obtenir que les départs et arrivées pour une ligne donnée (dont on fournit l'identifiant)</td>
</tr>
<tr class="odd">
<td colspan="3">DirectionRef</td>
<td>0:1</td>
<td>Direction­Code</td>
<td></td>
</tr>
<tr class="even">
<td colspan="3">Destination­Ref</td>
<td>0:1</td>
<td>StopPoint­Code</td>
<td>Filtre permettant de n'obtenir que les départs et arrivées ayant une destination donnée (dont on fournit l'identifiant de point d'arrêt)</td>
</tr>
<tr class="odd">
<td rowspan="2"></td>
<td colspan="3">OperatorRef</td>
<td>0:1</td>
<td>Operator­Code</td>
<td><p>Filtre permettant de n'obtenir que les départs et arrivées pour un exploitant donné (dont on fournit l'identifiant)</p>
<p>Filtre particulièrement utile pour les pôles d'échange</p></td>
</tr>
<tr class="even">
<td colspan="3">StopVisit­Types</td>
<td>0:1</td>
<td>all | departures | arrivals</td>
<td><p>Indique si l'on souhaite avoir les départs, les arrivées ou les deux.</p>
<p>Seule la valeur «<em> <strong>departures</strong> </em>» est obligatoire (pour tous les arrêts sauf, naturellement, le dernier de la mission) pour le profil FR, les autres sont optionnelles (à préciser pour chaque implémentation).</p>
<p>Si le champ n’est pas renseigné, la valeur par défaut est « <em><strong>all</strong></em> ».</p>
<p>Quelques règles de gestion sont précisées:</p>
<ul>
<li><p>dans le cas du <strong>StopVisitTypes</strong> = <em><strong>all</strong></em> ou <em><strong>departures</strong></em>, si l’heure de départ n'est pas connue (pour les SAEIV bus notament) alors l'heure de départ sera renseignée égale à l'heure d’arrivée et les 2 champs sont renseignés</p></li>
<li><p>Inversement (pour la SNCF notament), dans le cas du <strong>StopVisitTypes</strong> = <em><strong>all</strong></em> ou <em><strong>arrivals</strong></em>, si l’heure d’arrivée n'est pas connue alors l'heure d’arrivée prend la valeur de l'heure de départ et les 2 champs sont renseignés</p></li>
</ul>
<p>Il faut noter que, pour la gestion des correspondances, l’heure d’arrivée sera particulièrement utile …</p>
<p>Ce champ est facultatif (sauf dans le cas des échange avec les concentrateurs: <em>voir ci-dessous</em>), toutefois l'XSD lui définit une valeur par défaut qui est "<em>all</em>". S'il n'est pas présent il faut donc le géré comme s'il était positionné à "<em>all</em>".</p>
<p>Dans le cas des échanges avec les concentrateurs, ce filtre ne sera jamais présent et c'est donc avec la valeur par défaut <em><strong>all</strong></em> qu'il faudra l'interpréter.</p></td>
</tr>
<tr class="odd">
<td>Request Policy</td>
<td colspan="3">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td>Au niveau des échanges inter-systèmes, les textes restent en français. Les éventuelles traductions seront prises en charge par les systèmes de présentation.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">Include­Translations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the producer should include any available translations of NLString text elements into multiple languages. If false elements only one value per text element will be provided. +SIRI.2.0</p>
<p>Default is false.</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">Maximum­StopVisits</td>
<td>0:1</td>
<td>xsd:nonNegativeInteger</td>
<td><p>Nombre maximal d'informations de départ ou d'arrivée que l'on souhaite recevoir sur l’arrêt requêté. Si aucune valeur n’est fournie, toutes les informations disponibles seront remontées.</p>
<p>De plus « 0 » est une valeur interdite pour ce champ (erreur).</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2" rowspan="2">choix</td>
<td>Minimum­StopVisits­PerLine</td>
<td>0:1</td>
<td>xsd:nonNegativeInteger</td>
<td><p>Ce paramètre permet de demander un nombre minimum de réponses par ligne passant à l'arrêt. Cela permet d'éviter que pour un arrêt où passent 2 lignes et pour lesquels on a demandé les quatre prochains passages, on ait bien quatre indications mais sur une seule des deux lignes (les passages sur la seconde ligne intervenant après).</p>
<p>Dans ce cas, si ce paramètre est fixé à 2 on obtiendra les deux prochains passages sur chacune des lignes.</p>
<p>Ces passages doivent toutefois rester dans le <em><strong>Preview­Interval</strong></em></p>
<p>Il est recommandé de ne pas utiliser simultanément <em><strong>Maximum­StopVisits</strong></em> et <em><strong>Minimum­StopVisits­PerLine</strong></em> : si toutefois cela arrivait, le <em><strong>Maximum­StopVisits</strong></em> serait dominé par le <em><strong>Minimum­StopVisits­PerLine</strong></em> et la liste des informations disponibles pourrait être plus importante que stipulé par <em><strong>Maximum­StopVisits</strong></em>.</p></td>
</tr>
<tr class="odd">
<td></td>
<td>MinimumStop­Visits­PerLine­Via</td>
<td>0:1</td>
<td>xsd:nonNegative­Integer</td>
<td><p>Ce paramètre permet de demander un nombre minimum de réponses (de passage) par couple Ligne+Via (et donc pour chaque itinéraire identifiable). Ce paramètre est très similaire à MinimumStopVisitsPerLine mais propose une granularité plus fine (au niveau itinéraire). La notion d'itinéraire n'étant pas toujours explicitement présente dans les systèmes, on pourra interpréter ce paramètre comme une demande de nombre minimum de réponses par itinéraire possible (et par ligne).</p>
<p><u>Note</u>: ce filtre étant à comprendre comme "nombre de passage pour tous les VIA possibles", les VIA ne sont naturellement pas à préciser.</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">Maximum­Text­Length</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Pas de limite</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">Stop­Visit­DetailLevel</td>
<td>0:1</td>
<td>minimum | basic | normal | calls | full</td>
<td>Non utilisé</td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">Include­Situations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether any related SITUATIONs should be included in the ServiceDelivery. Default is 'false'. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">Maximum­Number­Of­Calls</td>
<td>0:1</td>
<td>+Structure</td>
<td>Structure permettant de préciser combien d’arrêts suivants ou précédents on souhaite obtenir au maximum (sous réserve de leur disponibilité). Si cette structure facultative n'est pas présente, aucun arrêt suivant ou précédent ne sera retourné.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td colspan="2">Previous</td>
<td>0:1</td>
<td>xsd:nonNegativeInteger</td>
<td>Nombre d'arrêts précédents souhaités (on aura donc des heures de passage constatées pour ces arrêts).</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td colspan="2">Onwards</td>
<td>0:1</td>
<td>xsd:nonNegativeInteger</td>
<td><p>Nombre maximal d'arrêts suivants souhaités (pour une course donnée). Si le paramètre est présent et vaut 0, tous les arrêts seront retournés. S’il n’est pas fourni et que la balise <em><strong>&lt;MaximumNumberOfCalls&gt;</strong></em> est présente, tous les arrêts seront remontés. S'il n'y a pas de balise <em><strong>&lt;MaximumNumberOfCalls&gt;</strong></em> aucune information relative aux OnwardCalls n'est remontée.</p>
<p>Précisions : ces informations ne sont pas comptabilisées pour le traitement des paramètres <em><strong>Maximum­StopVisits</strong></em> et <em><strong>Minimum­StopVisits­PerLine qui ne concernent que l'arrêt requêté.</strong></em></p></td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="3">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

### Requête multiple d'information temps réel au point d'arrêt en utilisant SOAP

|       |                                                                                                                                                                                                                                                                                              |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SM-13 | Il existe plusieurs façons de réaliser des requêtes d'information temps réel pour plusieurs points d'arrêt. Toutefois seule la solution ***GetSiri*** (voir ci-dessous) est recommandée par le profil FR, les autres solutions ne pouvant être maintenues que pour compatibilité ascendante. |

Le service SOAP ***GetSiri*** *(introduit par SIRI 2)* est celui qui
doit être utilisé pour les requêtes multiples d'information temps réel
au point d'arrêt ~~à partir du profil 2.4~~. ce point d'accès
fonctionnel est générique et permet de solliciter n'importe quel service
SIRI avec une cardinalité de requête illimitée. ~~La figure ci-dessous
en fournit l'interface de requête en faisant plus particulièrement
apparaître le cas du StopMonitoring (encadré en rouge) et sa
cardinalité. On notera bien que ce service peut être utilisé pour
solliciter de façon multiple n'importe quel service SIRI.~~

### Abonnement aux informations temps réel au point d'arrêt

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 55%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">StopMonitoringSubscription</td>
<td>+Structure</td>
<td>Requête d'abonnement pour obtenir des informations temps réel sur les heures d'arrivée et de départ à un point d'arrêt</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td>Subscriber­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du système demandeur (voir SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.)</td>
</tr>
<tr class="odd">
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant de l'abonnement pour le système demandeur.</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td>Date et heure de fin de l'abonnement : un abonnement a forcément une date et heure de fin (les partenaires pourront décider de limiter la durée maximale d’un abonnement)</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>Stop­Monitoring­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>voir StopMonitoringRequest (ci-dessus)</td>
</tr>
<tr class="even">
<td rowspan="2">Policy</td>
<td>Incremental­Updates</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indique s’il faut notifier uniquement les changements d'information ou s’il faut systématiquement renvoyer toutes les informations si l'une d'elles change.</p>
<p>Valeur par défaut : « true » (mise à jour incrémentale)</p>
<p>Dans le cadre des échanges avec un concentrateur seul le mode incrémental est supporté.</p></td>
</tr>
<tr class="odd">
<td>Change­Before­Updates</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td><p>Permet d'indiquer un écart de temps en dessous duquel on ne souhaite pas être notifié (si l'on demande un seuil de 5mn et qu'un horaire de départ ou d'arrivée change de 2mn, on ne sera pas notifié, évitant ainsi des flux d'information inutiles).</p>
<p>Si ce champ n'est pas présent, une valeur de <strong>5mn</strong> est prise par défaut.</p>
<p>Dans le cadre des échanges avec un concentrateur la valeur par défaut est de <strong>1mn</strong>.</p>
<p>C’est une valeur « par défaut », qui est volontairement haute pour ne pas surcharger les échanges : dans le cas nominal elle devra être précisée avec une valeur plus faible (mais tous les systèmes ne fonctionnent pas à la minute, surtout côté client).</p>
<p>Ce champ est facultatif car son implémentation peut s'avérer délicate pour certains systèmes : s'il n'est pas disponible, les spécifications d'interface du serveur SIRI devront préciser les valeurs et comportements implémentés.</p></td>
</tr>
</tbody>
</table>

Les données sont réputées avoir changé et doivent donc être notifiées
dès que :

-   La valeur d'une des heures de passage (planifiée, mesurée ou
    constatée) est modifiée d'une valeur supérieure ou égale au seuil
    demandé (***ChangeBeforeUpdates***) ;

-   Le véhicule quitte l'arrêt (ou arrive au dernier arrêt de la
    copurse);

-   Un changement de quai intervient.

### Résultat de la requête d'information temps réel au point d'arrêt

|                 |                          |      |                      |                                           |
| --------------- | ------------------------ | ---- | -------------------- | ----------------------------------------- |
| ServiceDelivery |                          |      | +Structure           | voir SIRI Part 7.2***ServiceDelivery***   |
| HEADER          | :::                      | 1:1  | Voir ServiceDelivery |                                           |
| Payload         | Stop­Monitoring­Delivery | 0:\* | +Structure           | Voir StopMonitoring­Delivery ci- dessous. |

#### Attributs temps réel du point d'arrêt

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 14%" />
<col style="width: 47%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">StopMonitoringDelivery</td>
<td>+Structure</td>
<td>Delivery for Stop Monitoring Service.</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td>version</td>
<td>1:1</td>
<td>Version­String</td>
<td>Numéro de version du service <em>Stop Monitoring</em>, intégrant le numéro de version de profil (voir Error: Reference source not found).</td>
</tr>
<tr class="odd">
<td>LEADER</td>
<td>:::</td>
<td>:::</td>
<td>xxx­Delivery</td>
<td>Voir paragraphe 2.2</td>
</tr>
<tr class="even">
<td rowspan="10">Pay­load</td>
<td>MonitoringRef</td>
<td><p>0:*</p>
<p>1:1</p></td>
<td>Monitoring­Code</td>
<td><p>Identifiant du point d'arrêt concerné par la requête.</p>
<p>Il convient d'utiliser ici un identifiant d'objets (arrêt) de référence (Zone d'Embarquement, , Lieu d'Arrêt ou Groupe de Lieux), et non d'objet particulier.</p></td>
</tr>
<tr class="odd">
<td>MonitoringName</td>
<td>0:*</td>
<td>NaturalLanguageStringStructure</td>
<td>Name to use to describe monitoring point (Stop or display). Normally Consumer will already have access to this in its reference data but may be included to increase utility of delivery data i to devices that do not hold reference data, e.g. for SIRI LITE services(+SIRI v2.0).</td>
</tr>
<tr class="even">
<td>Monitored­Stop­Visit</td>
<td>0:*</td>
<td>+Structure</td>
<td>Description des passages à l'arrêt</td>
</tr>
<tr class="odd">
<td>Monitored­Stop­Visit­Cancellation</td>
<td>0:*</td>
<td>+Structure</td>
<td>Indication qu'un passage précédemment signalé ne doit plus être affiché (indique généralement que le véhicule a franchi l'arrêt).</td>
</tr>
<tr class="even">
<td>Stop­Line­Notice</td>
<td>0:*</td>
<td>+Structure</td>
<td>Non utilisé pour le profil IDF (le service General Message sera utilisé pour ce type de service)</td>
</tr>
<tr class="odd">
<td>Stop­Line­Notice­Cancellation</td>
<td>0:*</td>
<td>+Structure</td>
<td>Non utilisé pour le profil IDF (le service General Message sera utilisé pour ce type de service)</td>
</tr>
<tr class="even">
<td>Stop­Notice</td>
<td>0:*</td>
<td>+Structure</td>
<td>Notice for stop. (SIRI 2.0++)</td>
</tr>
<tr class="odd">
<td>Stop­Notice­Cancellation</td>
<td>0:*</td>
<td>+Structure</td>
<td>Reference to an previously communicated Notice which should now be removed from the arrival/departure board for the stop. (SIRI 2.0++)</td>
</tr>
<tr class="even">
<td>ServiceException</td>
<td>0:*</td>
<td>+Structure</td>
<td><p>Information about why data is unavailable for the functional service. (+SIRI v2.0)</p>
<p>DetailLevel: basic.</p></td>
</tr>
<tr class="odd">
<td>Note</td>
<td>0:*</td>
<td>NLString</td>
<td>Message associated with delivery.</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

#### Description d'un arrêt (ou point d'arrêt indiqué) sur une course

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 2%" />
<col style="width: 13%" />
<col style="width: 6%" />
<col style="width: 19%" />
<col style="width: 42%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">MonitoredStopVisit</td>
<td>+Structure</td>
<td>Description du passage d'un véhicule à un arrêt (dans le cadre d'une course)</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Recorded­At­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Heure à laquelle la donnée a été mise à jour</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td colspan="2">Item­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>ItemIdentifier</td>
<td><p>Identifie cette information : cela correspond en fait à une identification du couple arrêt-course, et permettra par la suite une éventuelle annulation (cas où l’arrêt n’est plus desservi).</p>
<p>Il doit être unique et pérenne et bien identifier le passage à l'arrêt.</p></td>
</tr>
<tr class="even">
<td>Currency</td>
<td colspan="2">ValidUntilTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td><p>Time until which data is valid. (+SIRI v2.0).</p>
<p>This allows an override at the individual VISIT level of the value at the delivery level.</p></td>
</tr>
<tr class="odd">
<td rowspan="3">Stop­Visit­Reference</td>
<td colspan="2">Monitoring­Ref</td>
<td>1:1</td>
<td>Monitoring­Code</td>
<td>Référence du point d'arrêt</td>
</tr>
<tr class="even">
<td colspan="2">Monitoring­Name</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Name to use to describe monitoring point (SCHEDULED STOP POINT or (LOGICAL DISPLAY)). Normally Consumer will already have access to this in its reference data, but may be included to increase usability of SIRI LITE services (+SIRI v2.0).</p>
<p>One per language</p></td>
</tr>
<tr class="odd">
<td colspan="2">Clear­Down­Ref</td>
<td>0:1</td>
<td>ClearDown­Code</td>
<td>Identifier associated with MonitoredStopVisit for use in direct wireless communication between vehicle and stop display. Cleardown codes are short arbitrary identifiers suitable for radio transmission. Their scope may be transient, that is, they may be unique only to a day and sector.</td>
</tr>
<tr class="even">
<td>Journey­Info</td>
<td>a</td>
<td>Monitored­Vehicle­Journey</td>
<td>-1:1</td>
<td>Monitored­Vehicle­Journey­Structure</td>
<td>Description de la course</td>
</tr>
<tr class="odd">
<td>Message</td>
<td colspan="2">StopVisit­Note</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Message associated with delivery.</p>
<p>DetailLevel: basic.</p></td>
</tr>
<tr class="even">
<td>Facility</td>
<td colspan="2">StopFacility</td>
<td>0:1</td>
<td>Facility­Code</td>
<td>Facility associated with stop visit. SIRI 1.3</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

#### Attributs temps réel de la course

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 2%" />
<col style="width: 11%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="5">MonitoredVehicleJourney</td>
<td>+Structure</td>
<td>Description de la course</td>
</tr>
<tr class="even">
<td rowspan="3">Vehicle Journey Identity</td>
<td colspan="3">LineRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>LineCode</td>
<td>Identifiant de la ligne</td>
</tr>
<tr class="odd">
<td colspan="3">DirectionRef</td>
<td>0:1</td>
<td>Direction­Code</td>
<td>Identifier of the relative direction the vehicle is running along the line, for example, "in" or "out", “clockwise”. Distinct from a destination.</td>
</tr>
<tr class="even">
<td colspan="3">Framed­Vehicle­JourneyRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>+Framed­Vehicle­JourneyRef­Structure</td>
<td><p>Identification de la course</p>
<p>Champ obligatoire pour les échanges avec les concentrateurs : ce champ n'est pas forcément le reflet d'une valeur d'identifiant planifié et peut être construit localement par l'émetteur, mais il sera important pour une bonne gestion des abonnements en mode différentiel (en particulier pour le service Estimated Timetable).</p></td>
</tr>
<tr class="odd">
<td>Journey­Pattern­Info</td>
<td colspan="3">:::</td>
<td>0:1</td>
<td>Journey­Pattern­Info­Group</td>
<td>Voir Journey­Pattern­Info­Group.</td>
</tr>
<tr class="even">
<td>Vehicle­Journey­Info</td>
<td colspan="3">:::</td>
<td>0:1</td>
<td>Vehicle­JourneyInfo­Group</td>
<td>Voir Vehicle­JourneyInfo­Group</td>
</tr>
<tr class="odd">
<td>Disruption­Group</td>
<td colspan="3">:::</td>
<td>0:1</td>
<td>Disruption­Group</td>
<td>Voir Disruption­Group.</td>
</tr>
<tr class="even">
<td>Journey­Progress­Info</td>
<td colspan="3">:::</td>
<td>0:1</td>
<td>Journey­Progresss­Info­Group</td>
<td><p>voir Journey­Progress­Info­Group.</p>
<p>DetailLevel: normal.</p></td>
</tr>
<tr class="odd">
<td rowspan="4">Train­Block­Part</td>
<td colspan="3">TrainBlock­Part</td>
<td>0:1</td>
<td>TrainBlock­Part­Structure</td>
<td>Associates Stop Visit with a part of a train: for use when trains split or merge.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">![image](media/image2.jpeg) NumberOf­BlockParts</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Total number of block parts making up the train of which this is part.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">TrainPart­Ref</td>
<td>0:1</td>
<td>TrainPartCode</td>
<td>Identifier of train block part.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">PositionOf­ TrainBlock­Part</td>
<td>0:1</td>
<td>NLString</td>
<td>Description of position of TrainBlockPart within Train to guide passengers where to find it. E.g. 'Front four coaches'</td>
</tr>
<tr class="odd">
<td rowspan="8">Opera­tional­Info</td>
<td colspan="3">:::</td>
<td>0:1</td>
<td>Operational­Info­Group</td>
<td><p>Voir SIRI Part 2 OperationalInfo­Group.</p>
<p>BlockRef &amp; CourseOfJourney­Ref:</p></td>
</tr>
<tr class="even">
<td colspan="3">TrainNumber</td>
<td>0:*</td>
<td>sequence</td>
<td>Séquence de numéro de train (l'utilisation d'une sequence permet notament de gérer les trains couples)</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">TrainNumberRef</td>
<td>1:1</td>
<td>TrainNumber</td>
<td><p>Numéro de train</p>
<p>On utilisera en priorité la codification de code primaire UE 454/2011 ou le numéro de train UIC +<em>SIRI v2.0</em></p></td>
</tr>
<tr class="even">
<td colspan="3">JourneyParts</td>
<td>0:*</td>
<td>sequence</td>
<td><p>Liste des parties de course concernée par les Call ci-dessous.</p>
<p>Dans le cadre du profil France on utilisera ces sous-ensembles de course exclusivement pour porter la parité des trains (avec possibilité de changer de parité en cours de course).</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">JourneyPart­Info</td>
<td>1:1</td>
<td>+Structure</td>
<td>Information sur les parties de course</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Journey­PartRef</td>
<td>1:1</td>
<td>JourneyPart­Code</td>
<td>Dans le cadre du profil France ce champ permettra d'identifier, en particulier dans le contexte du RER, les portions de courses exploitées par la RATP et celles exploitées par la SNCF (les valeurs d'identification des JourneyPart sont des données de référence qui devront être fixes en amont de l'échange).</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Train­NumberRef</td>
<td>0:1</td>
<td>TrainNumbere</td>
<td><p>Dans le cadre du profil France ce champ sera suffixé, pour la SNCF, des code suivants:</p>
<ul>
<li><p>:2 pour les trains de parité paire</p></li>
<li><p>:1 pour les trains de parité impaire</p></li>
</ul>
<p>L'association à une JourneyPart permet de gérer les changements de parité en cours de course. Si la parité est invariable, une seule JourneyPart sera définie.</p>
<p>Si le numéro de train n'est pas connu mais que la parité doit tout de même être échangée, ce champ contiendra "<em><strong>unknown:1</strong></em>" ou "<em><strong>unknown:2</strong></em>".</p>
<p>Si les identifiants de JourneyPart n'ont pas été échangés mais que la parité doit tout de même être échangée, le champ précédent (JourneyPartRef, qui est obligatoire) prendra la valeur arbitraire de "<em><strong>unknown</strong></em>".</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Operator­Ref</td>
<td>0:1</td>
<td>Operator­Code</td>
<td>Reference to OPERATOR of a JOURNEY PART.</td>
</tr>
<tr class="odd">
<td rowspan="6">Calling Pattern</td>
<td colspan="3">Previous­Calls</td>
<td>0:1</td>
<td>+Structure</td>
<td>Information on stops called at previously, the origin stop and all intermediate stops up to but not including the current stop.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Previous­Call</td>
<td>0:*</td>
<td>+Structure</td>
<td>Information on a stop called at previously. See PreviousCall element.</td>
</tr>
<tr class="odd">
<td colspan="3">Monitored­Call</td>
<td>0:1</td>
<td>+Structure</td>
<td>Informations horaires concernant l'arrêt considéré</td>
</tr>
<tr class="even">
<td colspan="3">Onward­Calls</td>
<td>0:1</td>
<td>+Structure</td>
<td>Informations horaires concernant les arrêts suivants</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Onward­Call</td>
<td>0:*</td>
<td>+Structure</td>
<td>Informations horaires pour l'un des arrêts suivants</td>
</tr>
<tr class="even">
<td colspan="3">IsComplete­Stop­Sequence</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the call sequence is simple, i.e. represents every call of the route and so can be used to replace a previous call sequence. Default is false.</td>
</tr>
</tbody>
</table>

#### L'arrêt 

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 13%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 49%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">MonitoredCall</td>
<td>+Structure</td>
<td>Informations horaires pour l'arrêt.</td>
</tr>
<tr class="even">
<td rowspan="4">Stop Identity</td>
<td colspan="2">Stop­Point­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>StopPoint­Code</td>
<td><p>Identifiant du Point d'arrêt (cet identifiant est à rapprocher de l’attribut <em>MonitoringRef</em> de la structure <em>MonitoredStopVisit</em>, mais restreint à ce cas de point d’arrêt, là ou le <em>MonitoringRef</em> peut aussi, dans le contexte général de SIRI, mais pas celui du profil France, référencer un afficheur, par exemple).</p>
<p>Il convient d'utiliser ici un identifiant d'objet du referentiel théorique.</p>
<p>- Si MonitoringRef est un lieu d’arrêt, ou un groupe de lieux, StopPointRef est une zone d'embarquement, si l'émetteur est capable de la fournir.</p>
<p>- Sinon, StopPointRef estun lieu d’arrêt (granularité la plus fine possible dans tous les cas)</p>
<p>Champ obligatoire pour les échanges avec les concentrateurs</p></td>
</tr>
<tr class="odd">
<td colspan="2">VisitNumber</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the VisitNumber is used to distinguish each separate visit. DetailLevel: minimum.</td>
</tr>
<tr class="even">
<td colspan="2">Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission</td>
</tr>
<tr class="odd">
<td colspan="2">Stop­Point­Name</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>NLString</td>
<td><p>Nom du point d'arrêt.</p>
<p>Si plusieurs noms sont disponibles chez le producteur, le nom le plus détaillé sera utilisé en priorité.</p></td>
</tr>
<tr class="even">
<td>Call Real-time</td>
<td colspan="2">Vehicle­At­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>La Valeur «true » indique que le véhicule est à l'arrêt</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Vehicle­Location­At­Stop</td>
<td>0:1</td>
<td>Location­Structure</td>
<td>Location that vehicle will take up at stop point.</td>
</tr>
<tr class="even">
<td rowspan="3">Call Rail</td>
<td colspan="2">Reverses­At­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether vehicle reverses at stop. Default is false.</td>
</tr>
<tr class="odd">
<td colspan="2">Platform­Traversal</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>La valeur « true » permet de signaler le passage d'un train sans arrêt (et de demander au voyageur de s'écarter des voies)</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="even">
<td colspan="2">Signal­Status</td>
<td>0:1</td>
<td>xsd:NMTOKEN</td>
<td>Status of signal clearance for train. This may affect the presentation emphasis given to arrival or departures on displays – e.g. cleared trains appear first, flashing in green.</td>
</tr>
<tr class="odd">
<td rowspan="4">Call Property</td>
<td colspan="2">TimingPoint</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the stop is a timing point, i.e. times are measured at it. In Some systems this is a measure of data quality as non-timing points are interpolated.</td>
</tr>
<tr class="even">
<td colspan="2">Boarding­Stretch</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether this is a Hail and Ride Stop. Default is false.</td>
</tr>
<tr class="odd">
<td colspan="2">Request­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether Vehicle stops only if requested explicitly by passenger. Default is false.</td>
</tr>
<tr class="even">
<td colspan="2">Destination­Display</td>
<td>0:1</td>
<td>NLString</td>
<td>Destination telle qu'elle est affichée sur la girouette du véhicule à cet arrêt (ou sur l’afficheur local).</td>
</tr>
<tr class="odd">
<td>Call Note</td>
<td colspan="2">CallNote</td>
<td>0:*</td>
<td>NLString</td>
<td>Text annotation that applies to this call..</td>
</tr>
<tr class="even">
<td>Disruption­Group</td>
<td colspan="2">:::</td>
<td>0:1</td>
<td>Disruption­Group</td>
<td>Voir Disruption­Group.</td>
</tr>
<tr class="odd">
<td>Arrival</td>
<td colspan="2">Aimed­Arrival­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure d'arrivée théorique (ou commandée)</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Actual­Arrival­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure d'arrivée effectivement mesurée.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Expected­Arrival­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure d'arrivée estimée par le SAE.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">LatestExpectedArrival­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Latest expected time at which a VEHICLE will arrive at stop. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td rowspan="9">Arrival Status</td>
<td colspan="2">Arrival­Status</td>
<td>0:1</td>
<td><p>onTime | early | delayed | cancelled |</p>
<p>missed | arrived | notExpected | noReport</p></td>
<td><p>Caractérisation de l'horaire d'arrivée attendu (ou mesuré si le véhicule est à quai)</p>
<p>Valeur par défaut : « onTime »</p>
<p>Note: SIRI 2 ajoute les codes:</p>
<ul>
<li><p><em>missed</em> : le vehicule n'a pas marqué l'arrêt alors qu'il aurait du, mais la course continue.</p></li>
<li><p><em>notExpected</em> : départ ou arrivée non planifié(e) (cas de TAD non encore déclenché)</p></li>
</ul></td>
</tr>
<tr class="even">
<td colspan="2">ArrivalProximity­Text</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Texte libre à présenter quand le véhicule est proche, par exemple "à l'approche". Ce texte peut dépendre de règles propres à l'exploitant ou à l'AO, autant par son contenu que par les règles d'affichage qui le concernent (distance à partir de laquelle on l'affiche, etc.). Ces règles peuvent aussi être différentes suivant le lieu d'affichage de l'information (à quai, sur smartphone, dans un hall d'attente, etc.). Ces règles sont échangées en amont de façon contractuelle.</p>
<p>+SIRI v2.0.</p></td>
</tr>
<tr class="odd">
<td colspan="2">Arrival­Platform­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Identification ou nom du quai d'arrivée</td>
</tr>
<tr class="even">
<td colspan="2">Arrival­Boarding­Activity</td>
<td>0:1</td>
<td>alighting | noAlighting | passthru</td>
<td><p>Indique si l'on peut monter dans le véhicule ou si c'est un passage sans arrêt ou avec montée interdite.</p>
<p>On utilisera le <em><strong>Departure­Boarding­Activity</strong></em> dans le profil FR</p></td>
</tr>
<tr class="odd">
<td colspan="2">ArrivalStop­Assignment</td>
<td>0:1</td>
<td>+Structure</td>
<td>Assignment of arrival of Scheduled STOP POINT to a physical QUAY (platform). If not given, assume same as for departure <del>+SIRI v2.0.</del></td>
</tr>
<tr class="even">
<td></td>
<td>Aimed­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the planned timetable. <del>+SIRI v2.0</del></td>
</tr>
<tr class="odd">
<td></td>
<td>Aimed­­QuayName</td>
<td>0:1</td>
<td>NLString</td>
<td>Indication de la voie d'arrivée (en complément de Platform)<em>.</em></td>
</tr>
<tr class="even">
<td></td>
<td>Expected­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the real-time prediction. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td></td>
<td>Actual­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY actually used. +SIRI v2.0.</td>
</tr>
<tr class="even">
<td rowspan="6">Departure</td>
<td colspan="2">Aimed­Departure­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure de départ théorique (ou commandée).</td>
</tr>
<tr class="odd">
<td colspan="2">Actual­Departure­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure de départ effectivement mesurée.</td>
</tr>
<tr class="even">
<td colspan="2">Expected­Departure­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure de départ estimée par le SAE.</td>
</tr>
<tr class="odd">
<td colspan="2">Provisional­Expected­DepartureTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Estimated departure time of VEHICLE without waiting time due to operational actions. This would normally be shown to teh public at a stop if different from the Expected Departure time. +SIRI v2.0.</td>
</tr>
<tr class="even">
<td colspan="2">EarliestExpected­DepartureTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Earliest time at which VEHICLE may leave the stop. Used to secure connections. Passengers must be at boarding point by this time to be sure of catching VEHICLE. +SIRI v2.0.</td>
</tr>
<tr class="odd">
<td colspan="2">Expected­Departure­PredictionQuality</td>
<td>0:1</td>
<td>+Prediction­Quality</td>
<td><p>Prediction quality, either as approximate confidence level or as a more quantitative percentile range of predictions that will fall within a given range of times. See below ExpectedDeparturePredictionQuality +SIRI v2.0.</p>
<p>If not defined for some calls, an Extrapolation Rule has to be applied, see.</p></td>
</tr>
<tr class="even">
<td rowspan="2">Passenger­Times</td>
<td colspan="2">AimedLatest­Passenger­AccessTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Target latest time at which a PASSENGER should aim to arrive at the STOP PLACE containing the stop. This time may be earlier than the VEHICLE departure times and may include time for processes such as check-in, security, etc. (As specified by CHECK CONSTRAINT DELAYs in the underlying data) If absent assume to be the same as Earliest expected departure time. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td colspan="2">ExpectedLatest­Passenger­AccessTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Expected latest time at which a PASSENGER should aim to arrive at the STOP PLACE containing the stop. This time may be earlier than the VEHICLE departure times and may include time for processes such as check-in, security, etc. (As specified by CHECK CONSTRAINT DELAYs in the underlying data) If absent assumed to be the same as Earliest expected departure time. +SIRI v2.0</td>
</tr>
<tr class="even">
<td rowspan="4">Departure Status</td>
<td colspan="2">Departure­Status</td>
<td>0:1</td>
<td>onTime | early | delayed | cancelled | arrived |departed | notExpected | noReport</td>
<td><p>Caractérisation de l'horaire de départ attendu (ou mesuré si le véhicule est à quai).</p>
<p>Valeur par défaut : « onTime »</p></td>
</tr>
<tr class="odd">
<td colspan="2">Departure­ProximityText</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Arbitrary text string to show to indicate the proximity status of the departure of the VEHICLE, for example, “Boarding”, “GatesClosed”.</p>
<p>One per language</p></td>
</tr>
<tr class="even">
<td colspan="2">Departure­Platform­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Identification ou nom du quai de départ.</td>
</tr>
<tr class="odd">
<td colspan="2">Departure­Boarding­Activity</td>
<td>0:1</td>
<td>boarding | noBoarding | passthru</td>
<td><p>Indique si l'on peut monter dans le véhicule ou si c'est un passage sans arrêt ou avec montée interdite.</p>
<p>Valeur par défaut : « boarding»</p></td>
</tr>
<tr class="even">
<td rowspan="5">Departure Stop Assignment</td>
<td colspan="2">DepartureStop­Assignment</td>
<td>0:1</td>
<td>+Structure</td>
<td>Assignments of departure platform for SCHEDULED STOP POINT to a physical QUAY.</td>
</tr>
<tr class="odd">
<td></td>
<td>Aimed­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the planned timetable.</td>
</tr>
<tr class="even">
<td></td>
<td>Aimed­­QuayName</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Scheduled QUAY (Platform) name. Can be used to indicate a platform change.</p>
<p>One per language</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Expected­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the real-time prediction.</td>
</tr>
<tr class="even">
<td></td>
<td>Actual­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) actually used<del>.</del></td>
</tr>
<tr class="odd">
<td>Frequency</td>
<td colspan="2">Aimed­Headway­Interval</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td>Fréquence de passage théorique (ou commandée).</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Expected­Headway­Interval</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td>Fréquence de passage estimée par le SAE.</td>
</tr>
<tr class="odd">
<td rowspan="2">Stop Proximity Group</td>
<td colspan="2">DistanceFrom­Stop</td>
<td>0:1</td>
<td>DistanceType</td>
<td>Distance qui sépare le vehicule de l'arrêt. Une valeur positive indique que le véhicule est en amont de l'arrêt.</td>
</tr>
<tr class="even">
<td colspan="2">NumberOf­StopsAway</td>
<td>0:1</td>
<td>nonNegative­Integer</td>
<td>Indique le nombre d'arrêts à marquer entre la position courante du vehicule et l'arrêt considéré.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">KeyList</td>
<td>0:1</td>
<td>Keylist</td>
<td></td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td></td>
</tr>
</tbody>
</table>

#### Arrêts suivants

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 2%" />
<col style="width: 0%" />
<col style="width: 16%" />
<col style="width: 7%" />
<col style="width: 0%" />
<col style="width: 16%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="5">OnwardCall</td>
<td colspan="2">+Structure</td>
<td>Information sur les arrêts suivants de la course.</td>
</tr>
<tr class="even">
<td rowspan="4">Stop Identity</td>
<td colspan="3">Stop­Point­Ref</td>
<td colspan="2"><p>0:1</p>
<p>1:1</p></td>
<td>StopPoint­Code</td>
<td><p>Identifiant du point d'arrêt.</p>
<p>Il convient d'utiliser ici un identifiant d'objet de référence de (zone d'embarquement ou lieu d’arrêt : granularité la plus fine possible dans tous les cas).</p></td>
</tr>
<tr class="odd">
<td colspan="3">Visit­Number</td>
<td colspan="2">0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the <strong>VisitNumber</strong> is used to distinguish each separate visit.</td>
</tr>
<tr class="even">
<td colspan="3">Order</td>
<td colspan="2">0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission.</td>
</tr>
<tr class="odd">
<td colspan="3">Stop­Point­Name</td>
<td colspan="2"><p>0:1</p>
<p>1:1</p></td>
<td>NLString</td>
<td>Nom du point d'arrêt.</td>
</tr>
<tr class="even">
<td rowspan="2">Pro­gress</td>
<td colspan="3">Vehicle­At­Stop</td>
<td colspan="2">0:1</td>
<td>xsd:boolean</td>
<td><p>La Valeur «true » indique que le véhicule est à l'arrêt.</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="odd">
<td colspan="3">Timing­Point</td>
<td colspan="2">0:1</td>
<td>xsd:boolean</td>
<td>Whether the stop is a timing point, i.e. times are measured at it. In Some systems this is a measure of data quality as non-timing points are interpolated..</td>
</tr>
<tr class="even">
<td>Arrival</td>
<td colspan="3">Aimed­Arrival­Time</td>
<td colspan="2">0:1</td>
<td>xsd:dateTime</td>
<td>Heure d'arrivée théorique (ou commandée).</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">Expected­Arrival­Time</td>
<td colspan="2">0:1</td>
<td>xsd:dateTime</td>
<td>Heure d'arrivée estimée par le SAE.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">ExpectedArrival­PredictionQuality</td>
<td colspan="2">0:1</td>
<td>+Prediction­Quality</td>
<td><p>Prediction quality, either as approximate confidence level or as a more quantitative percentile range of predictions that will fall within a given range of times.</p>
<p>Compare below ExpectedDeparturePredictionQuality +SIRI v2.0.</p></td>
</tr>
<tr class="odd">
<td rowspan="2">Arrival Status</td>
<td colspan="3">Arrival­Status</td>
<td colspan="2">0:1</td>
<td>onTime | early | delayed | cancelled | missed | arrived | notExpected | | noReport</td>
<td><p>Caractérisation de l'horaire d'arrivée attendu.</p>
<p>Valeur par défaut : « onTime »</p></td>
</tr>
<tr class="even">
<td colspan="3">ArrivalProximity­Text</td>
<td colspan="2">0:*</td>
<td>NLString</td>
<td>Texte libre à présenter quand le véhicule est proche, par exemple "à l'approche". Ce texte peut dépendre de règles propres à l'exploitant ou à l'AO, autant par son contenu que par les règles d'affichage qui le concernent (distance à partir de laquelle on l'affiche, etc.). Ces règles peuvent aussi être différentes suivant le lieu d'affichage de l'information (à quai, sur smartphone, dans un hall d'attente, etc.). Ces règles sont échangées en amont de façon contractuelle.</td>
</tr>
<tr class="odd">
<td rowspan="7"></td>
<td colspan="3">Arrival­Platform­Name</td>
<td colspan="2">0:1</td>
<td>NLString</td>
<td>Identification du quai d'arrivée.</td>
</tr>
<tr class="even">
<td colspan="3">Arrival­Boarding­Activity</td>
<td colspan="2">0:1</td>
<td>alighting | noAlighting | passthru</td>
<td><p>Indique si l'on peut monter dans le véhicule ou si c'est un passage sans arrêt ou avec montée interdite.</p>
<p>On utilisera le <strong>Departure­Boarding­Activity</strong> dans le profil FR</p></td>
</tr>
<tr class="odd">
<td colspan="3">ArrivalStop­Assignment</td>
<td colspan="2">0:1</td>
<td>+Structure</td>
<td>Assignment of arrival of Scheduled STOP POINT to a physical QUAY (platform). If not given, assume same as for departure</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Aimed­­QuayRef</td>
<td colspan="2">0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the planned timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Aimed­­QuayName</td>
<td colspan="2">0:1</td>
<td>NLString</td>
<td>Scheduled Platform name. Can be used to indicate a platform change.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Expected­­QuayRef</td>
<td colspan="2">0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the real-time prediction.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Actual­­QuayRef</td>
<td colspan="2">0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY actually used.</td>
</tr>
<tr class="even">
<td>Depar­ture</td>
<td colspan="3">Aimed­Departure­Time</td>
<td colspan="2">0:1</td>
<td>xsd:dateTime</td>
<td>Heure de départ théorique (ou commandée).</td>
</tr>
<tr class="odd">
<td rowspan="4"></td>
<td colspan="3">Expected­Departure­Time</td>
<td colspan="2">0:1</td>
<td>xsd:dateTime</td>
<td>Heure de départ estimée par le SAE.</td>
</tr>
<tr class="even">
<td colspan="3">ProvisionalExpectedDepartureTime</td>
<td colspan="2">0:1</td>
<td>xsd:dateTime</td>
<td>Estimated departure time of VEHICLE without waiting time due to operational actions. For people at stop this would normally be shown if different from Expected departure time.</td>
</tr>
<tr class="odd">
<td colspan="3">EarliestExpected­DepartureTime</td>
<td colspan="2">0:1</td>
<td>xsd:dateTime</td>
<td>Earliest time at which VEHICLE may leave the stop. Used to secure connections. Used for passenger announcements. Passengers must be at boarding point by this time to be sure of catching VEHICLE.</td>
</tr>
<tr class="even">
<td colspan="3">ExpectedDeparture­PredictionQuality</td>
<td colspan="2">0:1</td>
<td>+Prediction­Quality</td>
<td>Prediction quality, either as approximate confidence level or as a more quantitative percentile range of predictions that will fall within a given range of times.</td>
</tr>
<tr class="odd">
<td>Departure Status</td>
<td colspan="3">Departure­Status</td>
<td colspan="2">0:1</td>
<td>onTime | early | delayed | cancelled | arrived |departed | notExpected | noReport</td>
<td><p>Caractérisation de l'horaire de départ attendu.</p>
<p>Valeur par défaut : « onTime »</p></td>
</tr>
<tr class="even">
<td rowspan="3"></td>
<td colspan="3">Departure­ProximityText</td>
<td colspan="2">0:*</td>
<td>NLString</td>
<td><p>Arbitrary text string to show to indicate the proximity status of the departure of the VEHICLE, for example, “Boarding”, “GatesClosed”.</p>
<p>One per language</p></td>
</tr>
<tr class="odd">
<td colspan="3">Departure­Platform­Name</td>
<td colspan="2">0:1</td>
<td>NLString</td>
<td>Identification du quai de départ.</td>
</tr>
<tr class="even">
<td colspan="3">Departure­Boarding­Activity</td>
<td colspan="2">0:1</td>
<td>boarding | noBoarding | passthru</td>
<td><p>Indique si l'on peut monter dans le véhicule ou si c'est un passage sans arrêt ou avec montée interdite.</p>
<p>Valeur par défaut : « boarding »</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">DepartureStop­Assignment</td>
<td colspan="2">0:1</td>
<td>+Structure</td>
<td>Assignments of departure platform for SCHEDULED STOP POINT to a physical QUAY.</td>
</tr>
<tr class="even">
<td rowspan="4"></td>
<td colspan="2"></td>
<td>Aimed­­QuayRef</td>
<td colspan="2">0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the planned timetable.</td>
</tr>
<tr class="odd">
<td colspan="2"></td>
<td>Aimed­­QuayName</td>
<td colspan="2">0:*</td>
<td>NLString</td>
<td><p>Scheduled QUAY (Platform) name. Can be used to indicate a platform change.</p>
<p>One per language</p></td>
</tr>
<tr class="even">
<td colspan="2"></td>
<td>Expected­­QuayRef</td>
<td colspan="2">0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the real-time prediction. 0</td>
</tr>
<tr class="odd">
<td colspan="2"></td>
<td>Actual­­QuayRef</td>
<td colspan="2">0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) actually used.</td>
</tr>
<tr class="even">
<td>Pro­gress Status</td>
<td colspan="3">Aimed­­Head­Way­Interval</td>
<td colspan="2">0:1</td>
<td>Positive­DurationType</td>
<td>Fréquence de passage théorique (ou commandée).</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">Expected­Headway­­Interval</td>
<td colspan="2">0:1</td>
<td>Positive­DurationType</td>
<td>Fréquence de passage estimée par le SAE.</td>
</tr>
<tr class="even">
<td>Stop Proximity Group</td>
<td colspan="3">DistanceFrom­Stop</td>
<td colspan="2">0:1</td>
<td>DistanceType</td>
<td>Distance qui sépare le vehicule de l'arrêt. Une valeur positive indique que le véhicule est en amont de l'arrêt.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">NumberOf­StopsAway</td>
<td colspan="2">0:1</td>
<td>nonNegative­Integer</td>
<td>Indique le nombre d'arrêts à marquer entre la position courante du vehicule et l'arrêt considéré.</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="3">Extensions</td>
<td colspan="2">0:1</td>
<td>any</td>
<td>Extension</td>
</tr>
</tbody>
</table>

#### Annulation d'arrêts

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 17%" />
<col style="width: 7%" />
<col style="width: 15%" />
<col style="width: 47%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">MonitoredStopVisit­Cancellation</td>
<td>+Structure</td>
<td><p>Indication qu'un passage précédemment signalé ne doit plus être affiché (indique généralement que le véhicule a franchi l'arrêt).</p>
<p><u>Note</u>: A ne pas confondre avec une annulation de course.</p></td>
</tr>
<tr class="even">
<td>Log</td>
<td>Recorded­At­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Heure à laquelle l'annulation de passage a été signalée/publiée.</td>
</tr>
<tr class="odd">
<td>Event­Identity</td>
<td>ItemRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>ItemIdentifier</td>
<td><p>Identifiant de l'arrêt annulé (voir ItemRef plus haut).</p>
<p>Champ obligatoire pour les échanges avec les concentrateurs (il doit être unique et pérenne, dans le cadre d'une journée d'exploitation, et bien permettre une annulation de passage à l'arrêt).</p></td>
</tr>
<tr class="even">
<td></td>
<td>Monitoring­Ref</td>
<td>1:1</td>
<td>Monitoring­Code</td>
<td>Identifiant du point d'arrêt.</td>
</tr>
<tr class="odd">
<td></td>
<td>VisitNumber</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the VisitNumber is used to distinguish each separate visit.</td>
</tr>
<tr class="even">
<td></td>
<td>Clear­Down­Ref</td>
<td>0:1</td>
<td>ClearDown­Code</td>
<td>Identifier associated with StopVisit for use in direct wireless communication between vehicle and stop display. Cleardown codes are short arbitrary identifiers suitable for radio transmission.</td>
</tr>
<tr class="odd">
<td></td>
<td>LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Identifiant de la ligne (celle de la course pour laquelle le passage à l'arrêt est annulé, la course elle-même peut être identifiée par le paramètre <em>FramedVehicleJourneyRef</em> ).</td>
</tr>
<tr class="even">
<td></td>
<td>DirectionRef</td>
<td>0:1</td>
<td>Direction­Code</td>
<td>Identifier of <strong>Direction</strong> of journey that is being deleted.</td>
</tr>
<tr class="odd">
<td></td>
<td>Vehicle­JourneyRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>+Structure (FramedVehicleJourneyRefStructure)</td>
<td><p>Identification de la course concernée<em>.</em></p>
<p>Champ obligatoire pour les échanges avec les concentrateurs</p></td>
</tr>
<tr class="even">
<td>Journey­Pattern­Info</td>
<td>:::</td>
<td>0:1</td>
<td>Journey­Pattern­Info­Group</td>
<td>Voir Journey­Pattern­Info­Group.</td>
</tr>
<tr class="odd">
<td>Message</td>
<td>Reason</td>
<td>0:1</td>
<td>NLString</td>
<td>Message expliquant la cause de l'annulation.</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

#### FramedVehicleJourneyRef

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 54%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="2">Framed­Vehicle­JourneyRef</td>
<td>0:1</td>
<td>+Structure</td>
<td>Identification d'une course.</td>
</tr>
<tr class="even">
<td></td>
<td>Data­Frame­Ref</td>
<td>1:1</td>
<td>DataFrame­Qualifier</td>
<td><p>Contexte d'identification de la course (SAE pour le jour d'exploitation, version du référentiel de données, etc.).</p>
<p>Ce champ permet de qualifier la version de donnée de référence, si cela est applicable</p>
<p>Utiliser la valeur "<em><strong>any</strong></em>" si ce champ n'est pas applicable.</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Dated­Vehicle­Journey­Ref</td>
<td>1:1</td>
<td>Dated­Vehicle­Journey­Code</td>
<td>Identifiant de la course elle-même.</td>
</tr>
</tbody>
</table>

#### VehicleJourneyInfoGroup

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 2%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 45%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">VehicleJourneyInfo­Group</td>
<td></td>
<td></td>
<td>Description de la course</td>
</tr>
<tr class="even">
<td>Service­Info</td>
<td colspan="2">:::</td>
<td>0:1</td>
<td>Service­Info­Group</td>
<td>Voir Service­Info­Group.</td>
</tr>
<tr class="odd">
<td>JourneyEndNames</td>
<td colspan="2">:::</td>
<td>0:1</td>
<td>JourneyEndNamesGroup</td>
<td>Voir JourneyEndNamesGroup.</td>
</tr>
<tr class="even">
<td>JourneyInfo</td>
<td colspan="2">Vehicle­Journey­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom de la course.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Journey­Note</td>
<td>0:1</td>
<td>NLString</td>
<td>Texte complémentaire décrivant la course.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">PublicContact</td>
<td>0:1</td>
<td>+Structure</td>
<td>Contact details for use by members of public.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>PhoneNumber</td>
<td>0:1</td>
<td>PhoneType</td>
<td>Phone number for Public to contact OPERATOR of journey.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Url</td>
<td>0:1</td>
<td>xsd:anyUri</td>
<td>Public URL to contact OPERATOR of journey.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">OperationsContact</td>
<td>0:1</td>
<td>+Structure</td>
<td>Contact details for use by operational staff.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>PhoneNumber</td>
<td>0:1</td>
<td>PhoneType</td>
<td>Phone number for operational contact. Not for Public use.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Url</td>
<td>0:1</td>
<td>xsd:anyUri</td>
<td>URL number for operational contact. Not for Public use.</td>
</tr>
<tr class="even">
<td rowspan="3">End Times</td>
<td colspan="2">Headway­Service</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>La valeur « true » permet de signaler que la course est gérée en fréquence (interval), et que les informations horaires seront fournies en conséquence…</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="odd">
<td colspan="2">Origin­Aimed­Departure­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure théorique de départ de la course à son point de départ.</td>
</tr>
<tr class="even">
<td colspan="2">Destination­Aimed­Arrival­Time</td>
<td>0:1</td>
<td>xsd:date­Time</td>
<td>Heure théorique d'arrivée de la course à son point d'arrivée.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">FirstOrLastJourney</td>
<td>0:1</td>
<td>FirstOrLast­Journey­Enumeration</td>
<td><p>Indique s'il s'agit de la première ou de la dernière course de la journée d'exploitation sur la ligne, et pour une destination donnée. L'interprétation comme "première ou dernière course pour une mission donnée" est acceptable, mais devra être précisée dans les spécifications d'interface du serveur (et le JourneyPatterInfoGroup devra alors être renseigné).</p>
<p>(firstServiceOfDay | lastServiceOfDay | otherService | unspecified).</p></td>
</tr>
</tbody>
</table>

#### ServiceInfoGroup

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 19%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Service Info</td>
<td>OperatorRef</td>
<td>0:1</td>
<td>OperatorCode</td>
<td>Identifiant de l'exploitant.</td>
</tr>
<tr class="even">
<td></td>
<td>Product­Category­Ref</td>
<td>0:1</td>
<td>Product­Category­Code</td>
<td>Mode de transport détaillé (voir l’énumération complète dans le XSD SIRI).</td>
</tr>
<tr class="odd">
<td></td>
<td>Service­Feature­Ref</td>
<td>0:*</td>
<td>Service­Feature­Code</td>
<td>Classification du type de service (“bus scolaire”, etc.).</td>
</tr>
<tr class="even">
<td></td>
<td>Vehicle­Feature­Ref</td>
<td>0:*</td>
<td>Vehicle­Feature­Code</td>
<td><p>Service spécifique disponible dans le véhicule (plancher bas, etc.).</p>
<p>Dans le cadre du profil France <del>(à partir de la version 2.4)</del> deux valeurs sont ajoutées par rapport à la liste recommandée par la norme (<em>voir SIRI 2 Partie 1 paragraphe 3.3.14.1</em>) pour signaler les trains courts et les trains longs. Les codes retenus sont:</p>
<ul>
<li><p><em><strong>shortTrain</strong></em> : Train court</p></li>
<li><p><em><strong>longTrain</strong></em> : Train long</p></li>
</ul></td>
</tr>
</tbody>
</table>

#### JourneyEndNamesGroup

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 2%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 45%" />
</colgroup>
<tbody>
<tr class="odd">
<td rowspan="13">ServiceEnd Names</td>
<td colspan="2">OriginRef</td>
<td>0:1</td>
<td>Journey­PlaceCode</td>
<td>Identifiant de l'arrêt de départ de la course.</td>
</tr>
<tr class="even">
<td colspan="2">Origin­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom de l'arrêt de départ (si l'identifiant OriginRef est fourni, le nom doit l'être aussi).</td>
</tr>
<tr class="odd">
<td colspan="2">Origin­Short­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>The short name of the origin of the journey; used to help identify the vehicle to the public.</td>
</tr>
<tr class="even">
<td colspan="2">DestinationDisplayAtOrigin</td>
<td>0:*</td>
<td>NLString</td>
<td><p>DESTINATION DISPLAY name shown for journey at the origin. +SIRI v2.0.</p>
<p>(One per language).</p></td>
</tr>
<tr class="odd">
<td colspan="2">Via</td>
<td><p>0:*</p>
<p>0:1</p></td>
<td>+Structure</td>
<td><p>Description d'un via sur la course.</p>
<p>La cardinalité est limitée à 1 dans le cadre du profil. Ceci permet notament de simplifer la gestion de compatibilité avec les versions antérieures de SIRI <del>et du Profil.</del></p></td>
</tr>
<tr class="even">
<td></td>
<td>PlaceRef</td>
<td>0:1</td>
<td>Journey­PlaceCode</td>
<td>Identifiant de l'arrêt via (ou d'un lieu via).</td>
</tr>
<tr class="odd">
<td></td>
<td>PlaceName</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom du via (si l'identifiant PlaceRef est fourni, le nom doit l'être aussi, si c'est un arrêt le nom doit naturellement être celui de l'arrêt</td>
</tr>
<tr class="even">
<td></td>
<td>PlaceShort­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Short name of a via point of the journey, used to help identify the line.</td>
</tr>
<tr class="odd">
<td></td>
<td>ViaPriority</td>
<td>0:1</td>
<td>xsd:integer</td>
<td>Relative priority to give to VIA name in displays. 1=high. Default is 2. +SIRI v2.0.</td>
</tr>
<tr class="even">
<td colspan="2">DestinationRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Journey­PlaceCode</td>
<td>Identifiant du dernier arrêt de la course.</td>
</tr>
<tr class="odd">
<td colspan="2">Destination­Name</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>NLString</td>
<td>Nom de l'arrêt de destination (si l'identifiant DestinationRef est fourni, le nom doit l'être aussi).</td>
</tr>
<tr class="even">
<td colspan="2">Destination­ShortName</td>
<td>0:1</td>
<td>NLString</td>
<td>The name of the destination of the journey; used to help identify the vehicle to the public.</td>
</tr>
<tr class="odd">
<td colspan="2">OriginDisplayAtDestination</td>
<td>0:1</td>
<td>NLString</td>
<td>Origin name shown for journey at the destination +SIRI v2.0</td>
</tr>
</tbody>
</table>

#### JourneyPatternInfoGroup

<table>
<colgroup>
<col style="width: 18%" />
<col style="width: 18%" />
<col style="width: 7%" />
<col style="width: 14%" />
<col style="width: 40%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="2">JourneyPatternInfoGroup</td>
<td></td>
<td></td>
<td>Groupe d'attributs pour la description des missions</td>
</tr>
<tr class="even">
<td>Journey Pattern Info</td>
<td>Journey­PatternRef</td>
<td>0:1</td>
<td>Journey­PatternCode</td>
<td>Identifiant de la mission.</td>
</tr>
<tr class="odd">
<td></td>
<td>JourneyPatternName</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Nom ou numero de course présenté au public.</p>
<p>Exemple : Dans le cas de la SNCF et du RER, cet identifiant est le code à 4 lettres qui désigne la mission (RER et Transilien).</p></td>
</tr>
<tr class="even">
<td></td>
<td>Vehicle­Mode</td>
<td>0:1</td>
<td>air | bus | coach | ferry | metro | rail | tram | under­ground</td>
<td><p>Mode de transport pour cette mission (il s’agit ici d’un mode « générique », tous les avions par exemple seront air, et c’est le <em>ProductCategory</em>, dans <em>ServiceInfoGroup</em>, qui donnera plus de précisions, comme : <em>internationalFlight, intercontinentalFlight, domesticScheduledFlight, shuttleFlight …</em></p>
<p>Valeur par défaut : « bus »</p></td>
</tr>
<tr class="odd">
<td></td>
<td>RouteRef</td>
<td>0:1</td>
<td>RouteCode</td>
<td>Identifiant de l'itinéraire suivi.</td>
</tr>
<tr class="even">
<td></td>
<td>Published­LineName</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>NLString</td>
<td>Nom de la ligne.</td>
</tr>
<tr class="odd">
<td></td>
<td>Direction­Name</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Nom de la direction de la mission.</p>
<p>Ce nom peut par exemple contenir des informations comme "A" ou "R" (Aller ou Retour) pour les lignes qui utilisent ces informations.</p></td>
</tr>
<tr class="even">
<td></td>
<td>External­Line­Ref</td>
<td>0:1</td>
<td>LineCode</td>
<td>Alternative Identifier of Line that an external system may associate with journey.</td>
</tr>
</tbody>
</table>

#### DisruptionGroup

Ce groupe de paramètres fait partie des éléments qui vont être étendus
dans le cadre des services « *Facility Monitoring* » et « *Situation
Exchange* ».

|       |                                                                                                                                                                                                         |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SM-14 | Seule la référence à un événement sera retenue, les informations complémentaires pour l'état des équipements et les perturbations seront déterminées dans le cadre du service « *Situation Exchange* ». |

|                 |                 |                        |                   |            |      |                                      |                                                                                                                                                                     |
| --------------- | --------------- | ---------------------- | ----------------- | ---------- | ---- | ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Situa­tion      | SituationRef    |                        |                   |            | 0:\* | SituationCode                        | Identifiant (externe) de l'événement qui est la cause des modifications horaires indiquées                                                                          |
| Facility­Change | FacilityChanget |                        |                   |            | 0:1  | +Structure                           | Information about a change of Equipment availability at stop that may affect access or use.                                                                         |
|                 |                 | Equipment­Availability |                   |            | 0:1  | +Structure                           | Availability change for Equipment item.                                                                                                                             |
|                 |                 |                        | Equipment­Ref     |            | 0:1  | Equipment­Code                       | Identifier of the equipment.                                                                                                                                        |
|                 |                 |                        | Description       |            | 0:1  | NLString                             | Description of equipment.                                                                                                                                           |
|                 |                 |                        | Equipment­Status  |            | 1:1  | unknown \| available \| notAvailable | Status of the equipment available. Enumeration. Default is ‘*notAvailable’*.                                                                                        |
|                 |                 |                        | Validity­Period   |            | 0:1  | +Structure                           | Period for which Status Change applies. If omitted, indefinite period.                                                                                              |
|                 |                 |                        |                   | Start­Time | 1:1  | xsd:dateTime                         | The (inclusive) start time stamp.                                                                                                                                   |
|                 |                 |                        |                   | EndTime    | 0:1  | xsd:dateTime                         | The (inclusive) end time stamp. If omitted, the range end is open-ended, that is, it should be interpreted as "forever".                                            |
|                 |                 |                        | Equipment­TypeRef |            | 0:1  | Equipment­TypeCode                   | Reference to Equipment type identifier.                                                                                                                             |
|                 |                 |                        | Features          |            | 0:1  | +Structure                           | Service Features associated with equipment.                                                                                                                         |
|                 |                 |                        |                   | Feature    | 1:\* | ServiceFeature                       | Service or Stop features associated with equipment. Recommended values based on TPEG are given in SIRI documentation and enumerated in the siri_facilities package. |
| Situation       |                 | SituationRef           |                   |            | 0:\* | SituationCode                        | Reference to a Situation associated with the ***FacilityChange***.                                                                                                  |

|                 |     |                     |                          |     |                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                 |
| --------------- | --- | ------------------- | ------------------------ | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mobility Effect |     | Mobility­Disruption |                          | 0:1 | +Structure                                                                                                                                                                                                                                                              | Effect of change on impaired access users.                                                                                                                                                                                                                                                      |
|                 |     |                     | Mobility­Impaired­Access | 0:1 | xsd:boolean                                                                                                                                                                                                                                                             | Whether stop or service is accessible to mobility impaired users. This may be further qualified by one ore more MobilityFacility instances to specify which types of mobility access are available (true) or not available (*false*). For example 'suitableForWheelChair', or 'stepFreeAccess'. |
|                 |     |                     | Mobility­Facility        |     | suitableForWheelChairs \| lowFloor \| stepFree­Access \| boarding­Assistance \| onboard­Assistance \| unaccompanied­Minor­Assistance \| audioInformation \| visual­Information \| displays­ForVisually­Impaired \| audio­For­Hearing­Impaired \| tactile­Edge­Platforms | Classification of Mobility Facility type - Based on Tpeg pti23.                                                                                                                                                                                                                                 |

#### JourneyProgressInfoGroup

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 13%" />
<col style="width: 7%" />
<col style="width: 20%" />
<col style="width: 42%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="2">JourneyProgressInfoGroup</td>
<td></td>
<td></td>
<td>Groupe d'attributs précisant l’avancement sur la mission</td>
</tr>
<tr class="even">
<td>Status</td>
<td>Monitored</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indique si le véhicule est toujours localisé (la valeur <em>false</em> indique une délocalisation du bus).</p>
<p>Valeur par défaut : « true »</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Monitoring­Error</td>
<td>0:1</td>
<td>GPS | GPRS | Radio</td>
<td>Si le bus est délocalisé, ce champ précise la cause de cette délocalisation.</td>
</tr>
<tr class="even">
<td>Progress Data Quality</td>
<td>In­Congestion</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Ce champ vaut « true » si le vehicule est pris dans un embouteillage (ou plus généralement un incident d’exploitation).</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="odd">
<td></td>
<td>InPanic</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indique que l'alarme du véhicule est activée.</p>
<p>Valeur par défaut : « false »</p></td>
</tr>
<tr class="even">
<td></td>
<td>Prediction­Inaccurate</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the prediction should be judged as inaccurate.</td>
</tr>
<tr class="odd">
<td></td>
<td>DataSource</td>
<td>0:1</td>
<td>xsd:string</td>
<td>System originating real-time data, if other than producer. Can be used to make judgements of relative quality and accuracy of a proxied source compared to other feeds.</td>
</tr>
<tr class="even">
<td></td>
<td>Confidence­Level</td>
<td>0:1</td>
<td>certain | veryReliable | reliable | probablyReliable | unconfirmed</td>
<td>A confidence level associated with data.</td>
</tr>
<tr class="odd">
<td>Progress Data</td>
<td>Vehicle­Location</td>
<td>0:1</td>
<td>Location­Structure</td>
<td><p>Indique la position du véhicule (voir <em>Location­Structure</em>).</p>
<p>Ce champ est obligatoire quand cette structure fait partie d’une réponse à une requête de type « vehicle monitoring » (il reste facultatif dans les autres cas).</p></td>
</tr>
<tr class="even">
<td></td>
<td>Bearing</td>
<td>0:1</td>
<td>Absolute­Bearing­Type</td>
<td>Indique l’orientation (cap) du véhicule.</td>
</tr>
<tr class="odd">
<td></td>
<td>Progress­Rate</td>
<td>0:1</td>
<td>noProgress | slowProgress | normalProgress | fastProgress | unknown</td>
<td>Classification of the rate of progress of vehicle</td>
</tr>
<tr class="even">
<td></td>
<td>Occupancy</td>
<td>0:1</td>
<td>full | seatsAvailable | standingAvailable</td>
<td><p>Indique le niveau de remplissage du véhicule.</p>
<p>Dans l’état actuel des choses peu (pour ne pas dire aucun) de systèmes disposent de cette information, mais le besoin d’en disposer a été remonté lors des interviews.</p>
<p>Valeur par défaut : « <em>seatsAvailable</em>»</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Delay</td>
<td>0:1</td>
<td>DurationType</td>
<td>Indique le niveau de retard du véhicule (une valeur négative indique une avance).</td>
</tr>
<tr class="even">
<td></td>
<td>Progress­Status</td>
<td>0:1</td>
<td>NLString</td>
<td>A non-displayable status describing the running of this vehicle.</td>
</tr>
<tr class="odd">
<td></td>
<td>Vehicle­Status</td>
<td>0:1</td>
<td>VehicleStatusEnum</td>
<td><p>A classification of the progress state of the VEHICLE JOURNEY. +SIRI 2.0</p>
<p>expected | notExpected | cancelled | assigned | signedOn | atOrigin | inProgress | aborted | offRoute | completed | assumed­Completed | notRun</p></td>
</tr>
</tbody>
</table>

## 

## 

## Connection Monitoring

### Requête d’information sur les correspondances

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 3%" />
<col style="width: 12%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">Connection­Monitoring­Request</td>
<td>+Structure</td>
<td>Requête d’information sur les correspondances</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td colspan="2">version</td>
<td>1:1</td>
<td>VersionString</td>
<td>Version du service “ Connection Monitoring”, intégrant le numéro de version de profil (voir Error: Reference source not found) par exemple. ‘2.0:FR-FR-1.0’.</td>
</tr>
<tr class="odd">
<td rowspan="2">End­point Properties</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td rowspan="2">Date d'émission de la requête.</td>
</tr>
<tr class="even">
<td colspan="2">Message­Identifier</td>
<td>0:1</td>
<td>Message­Qualifier</td>
</tr>
<tr class="odd">
<td rowspan="5">Topic</td>
<td colspan="2">PreviewInterval</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Si ce paramètre est présent, il indique que l'on souhaite recevoir des informations sur toute arrivée et tout départ intervenant dans la durée indiquée.</td>
</tr>
<tr class="even">
<td colspan="2">ConnectionLink­Ref</td>
<td>1:1</td>
<td>Connec­tion­Link­Code</td>
<td><p>Identifiant de la correspondance interrogée (à déterminer entre les participants, ou à terme au niveau du référentiel francilien pour les correspondances structurantes et/ou garanties).</p>
<p>Pour mémoire, le « ConnectionLink » référence le cheminement physique, alors que l’objet « Interchange » référence une correspondance entre deux courses identifiées (généralement, un «Interchange » se réalise donc en empruntant un « ConnectionLink »). </p></td>
</tr>
<tr class="odd">
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td>Seul l’un des filtres peut être utilisé.</td>
</tr>
<tr class="even">
<td>a</td>
<td>Connecting­Time­Filter</td>
<td>–1:1</td>
<td>+Structure</td>
<td>Filtre temporel, indépendant des courses.</td>
</tr>
<tr class="odd">
<td>b</td>
<td>Connecting­Journey­Filter</td>
<td>–1:*</td>
<td>+Structure</td>
<td>Filtre base sur les courses.</td>
</tr>
<tr class="even">
<td rowspan="3">Request Policy</td>
<td colspan="2">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td>Au niveau des échanges inter-systèmes, les textes restent en français. Les éventuelles traductions seront prises en charge par les systèmes de présentation.</td>
</tr>
<tr class="odd">
<td colspan="2">Include­Translations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the producer should include any available translations of NLString text elements into multiple languages. If false elements only one value per text element will be provided.</p>
<p>Default is false.</p></td>
</tr>
<tr class="even">
<td colspan="2">ConnectionMonitoringDetailLevel</td>
<td>0:1</td>
<td>Connection­Monitoring­DetailLevel­Enum</td>
<td><p>Default DetailLevel if none specified on request. Default is ‘normal’.</p>
<p>minimum | basic | normal | calls | full</p></td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

#### Structure ConnectingTimeFilter

|        |                       |                      |     |                 |                                                                              |
| ------ | --------------------- | -------------------- | --- | --------------- | ---------------------------------------------------------------------------- |
| Filter | Connecting­TimeFilter |                      |     | +Structure      | Filtre temporel pour les requêtes                                            |
|        |                       | LineRef              | 1:1 | LineCode       | Identifiant de la ligne amenante.                                            |
|        |                       | DirectionRef         | 1:1 | Direction­Code | Indication de direction (aller/retour).                                      |
|        |                       | Earliest­ArrivalTime | 1:1 | xsd:dateTime    | Début de la fenêtre temporelle d’interrogation (basé sur l’heure d’arrivée). |
|        |                       | Latest­ArrivalTime   | 1:1 | xsd:dateTime    | Fin de la fenêtre temporelle d’interrogation (basé sur l’heure d’arrivée).   |

#### Structure ConnectingJourneyFilter

|        |                          |                          |     |                             |                                                                                                             |
| ------ | ------------------------ | ------------------------ | --- | --------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Filter | Connecting­JourneyFilter |                          |     | +Structure                  | Filtre sur les courses                                                                                      |
|        |                          | Dated­Vehicle­JourneyRef | 1:1 | Dated­Vehicle­Journey­Code | Identifiant de la course.                                                                                   |
|        |                          | Visit­Number             | 0:1 | VisitNumber­Type            | Sequence of visit to stop within vehicle journey. Increases monotonically but not necessarily sequentially. |
|        |                          | Aimed­Arrival­Time       | 0:1 | xsd:dateTime                | Date et heure d’arrivée prévue au point d’arrêt (départ de correspondance).                                 |

### Abonnement aux informations sur les correspondances

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">Connection­Monitoring­Subscription­Request</td>
<td>+Structure</td>
<td>Abonnement aux informations sur les correspondances</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td>Subscriber­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du système demandeur ( voir SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.)</td>
</tr>
<tr class="odd">
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant de l'abonnement pour le système demandeur.</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td>Date et heure de fin de l'abonnement : un abonnement a forcément une date et heure de fin (les partenaires pourront décider de limiter la durée maximale d’un abonnement).</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>Connection­Monitoring­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>Voir ConnectionMonitoringRequest.</td>
</tr>
<tr class="even">
<td>Policy</td>
<td>Change­Before­Updates</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td><p>Permet d'indiquer un écart de temps en dessous duquel on ne souhaite pas être notifié (si l'on demande un seuil de 5mn et qu'un horaire de départ change de 2mn, on ne sera pas notifié, évitant ainsi des flux d'information inutiles).</p>
<p>Si ce champ n'est pas présent, une valeur de <strong>5mn</strong> est prise par défaut.</p>
<p>C’est une valeur « par défaut », qui est volontairement haute pour ne pas surcharger les échanges : dans le cas nominal, elle devra être précisée avec une valeur plus faible (mais tous les systèmes ne fonctionnent pas à la minute, surtout côté client).</p></td>
</tr>
<tr class="odd">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

### Réponse aux requêts d’information sur les correspondances

|                 |                                          |      |                     |                                                            |
| --------------- | ---------------------------------------- | ---- | ------------------- | ---------------------------------------------------------- |
| ServiceDelivery |                                          |      | +Structure          | Réponse aux requêtes d’information sur les correspondances |
| HEADER          | :::                                      | 1:1  | See ServiceDelivery |                                                            |
| Pay­load        | ConnectionMonitoring­FeederDelivery      | 1:\* | +Structure          | voir ConnectionMonitoring­Feeder­Delivery.                 |
|                 | ConnectionMonitoring­DistributorDelivery |      | +Structure          | voir ConnectionMonitoringDistributor­Delivery.             |

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">Connection­MonitoringFeeder­Delivery</td>
<td>+Structure</td>
<td>Réponse aux requêtes d’information sur les correspondances : description des alimentants</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td>version</td>
<td>1:1</td>
<td>VersionString</td>
<td>Numéro de version du service <em>Connection Monitoring</em>, intégrant le numéro de version de profil (voir Error: Reference source not found) (valeur fixe).</td>
</tr>
<tr class="odd">
<td>LEADER</td>
<td>:::</td>
<td>1:1</td>
<td>xxx­Delivery</td>
<td>voir xxx<strong>Delivery</strong>.</td>
</tr>
<tr class="even">
<td rowspan="2">Payload</td>
<td>Monitored­Feeder­Arrival</td>
<td>0:*</td>
<td>+Structure</td>
<td><p>Changement d’heure d’arrivée à la correspondance.</p>
<p>Voir MonitoredFeederArrival.</p></td>
</tr>
<tr class="odd">
<td>Monitored­Feeder­Arrival­Cancellation</td>
<td>0:*</td>
<td>+Structure</td>
<td><p>Annulation de passage à la correspondance.</p>
<p>Voir MonitoredFeederArrival.</p></td>
</tr>
<tr class="even">
<td>Any</td>
<td>Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

#### Structure MonitoredFeederArrival

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 16%" />
<col style="width: 6%" />
<col style="width: 15%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">MonitoredFeederArrival</td>
<td>+Structure</td>
<td>Information sur l’amenant</td>
</tr>
<tr class="even">
<td>Log</td>
<td>Recorded­AtTime</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure à laquelles ces données ont été produites.</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>Item­Identifier</td>
<td>0:1</td>
<td>ItemIdentifier</td>
<td>Référence le message d’information.</td>
</tr>
<tr class="even">
<td>Currency</td>
<td>ValidUntilTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Time until which data is valid. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td rowspan="2">Feeder Inter­change Identity</td>
<td>Interchange­Ref</td>
<td>0:1</td>
<td>Interchange­Code</td>
<td><p>Identifiant de la correspondance entre course</p>
<p>Dans le cadre du profil France, si ce paramètre est présent, il sera constitué des la concaténation de l’identifiant de la course arrivant et de celui de la course au départ (séparés par le caractère ‘<strong>:</strong>’).</p></td>
</tr>
<tr class="even">
<td>Connection­Link­Ref</td>
<td>1:1</td>
<td>Connection­Link­Code</td>
<td>Identifiant de la correspondance physique.</td>
</tr>
<tr class="odd">
<td rowspan="5"></td>
<td>Stop­Point­Ref</td>
<td>0:1</td>
<td>StopPoint­Code</td>
<td><p>Identifiant du point d’arrêt de l’amenant (généralement porté par le ConnectionLink).</p>
<p>Il convient d'utiliser ici un identifiant d'objet de référence : zone d'embarquement ou zone de lieu : granularité la plus fine possible dans tous les cas.</p></td>
</tr>
<tr class="even">
<td>Visit­Number</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the <strong>VisitNumber</strong> is used to distinguish each separate visit.</td>
</tr>
<tr class="odd">
<td>Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission.</td>
</tr>
<tr class="even">
<td>Stop­Point­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom du point d'arrêt.</td>
</tr>
<tr class="odd">
<td>Clear­Down­Ref</td>
<td>0:1</td>
<td>Cleardown­Code</td>
<td><em>Cleardown</em> : indicateur « véhicule à l’arrêt » ou « à l’approche ».</td>
</tr>
<tr class="even">
<td>Journey Info</td>
<td>Feeder­Journey</td>
<td>1:1</td>
<td>Connecting­Journey­Structure</td>
<td>Description de la course de l’amenant.</td>
</tr>
<tr class="odd">
<td rowspan="2">Real-time call</td>
<td>VehicleAt­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indicateur “Véhicule à l’arrêt”.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="even">
<td>NumberOf­Transfer­Passengers</td>
<td>0:1</td>
<td>xsd:non­Negative­Integer</td>
<td>Number of passengers who wish to transfer at the connection. If absent, not known.</td>
</tr>
<tr class="odd">
<td></td>
<td>AimedArrivalTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure d'arrivée planifiée.</td>
</tr>
<tr class="even">
<td>Call time</td>
<td>Expected­Arrival­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Heure d’arrivée prévue à l’arrêt.</td>
</tr>
<tr class="odd">
<td></td>
<td>ArrivalPlatformName</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom du quai d'arrivée.</td>
</tr>
<tr class="even">
<td></td>
<td>SuggestedWait­DecisionTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Latest time by which the feeder needs information about the connection from the distributor as to whether it will wait and for how long. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

#### Structure FeederJourney

|                          |                           |     |                            |                                                                      |
| ------------------------ | ------------------------- | --- | -------------------------- | -------------------------------------------------------------------- |
| FeederJourney            |                           |     | +Structure                 | Description de la course de l’amenant                                |
| Vehicle­Journey­Identity | LineRef                   | 1:1 | LineCode                  | Identifiant de la ligne.                                             |
|                          | DirectionRef              | 1:1 | Direction­Code            | Yes.                                                                 |
|                          | Framed­Vehicle­JourneyRef | 0:1 | +Structure                 | Identification de la course.                                         |
| Journey­Pattern­Info     | :::                       | 0:1 | Journey­Pattern­Info­Group | Voir Journey­Pattern­Info­Group.                                     |
| Vehicle­Journey­Info     | :::                       | 0:1 | Vehicle­JourneyInfo­Group  | Voir Vehicle­JourneyInfo­Group.                                      |
| Operational Info         | :::                       | 0:1 | Operational\_­Info­Group   | See SIRI Part 2 Operational­Info­Group.                              |
| Disruption­Group         | :::                       | 0:1 | Disruption­Group           | Voir DisruptiomInfo­Group                                            |
| Progress                 | Monitored                 | 0:1 | xsd:boolean                | Signale si l’information temps réel est disponible (oui par défaut). |
| Call Times               | Aimed­Arrival­Time        | 0:1 | xsd:dateTime               | Heure d’arrivée prévue à l’arrêt.                                    |
| any                      | Extensions                | 0:1 | any                        | Placeholder for user extensions.                                     |

#### Structure MonitoredFeederArrivalCancellation

<table style="width:100%;">
<colgroup>
<col style="width: 6%" />
<col style="width: 18%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">MonitoredFeederArrival­Cancellation</td>
<td>+Structure</td>
<td>Information d’annulation de course</td>
</tr>
<tr class="even">
<td>Log</td>
<td>Recorded­AtTime</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure auxquelles ces données ont été produites/enregistrées.</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>ItemRef</td>
<td>0:1</td>
<td>ItemIdentifier</td>
<td>Identifie l’objet qui est annulé (voir le <em><strong>ItemRef</strong></em> correspondant dans les précédentes notifications d’information de correspondance).</td>
</tr>
<tr class="even">
<td rowspan="6">Feeder Inter­change­Identity</td>
<td>Interchange­Ref</td>
<td>0:1</td>
<td>Interchange<strong>­</strong>Code</td>
<td><p>Identifiant de la correspondance entre courses.</p>
<p>Dans le cadre du profil France, si ce paramètre est présent, il sera constitué de la concaténation de l’identifiant de la course arrivant et de celui de la course au départ (séparés par le caractère ‘<strong>:</strong>’).</p></td>
</tr>
<tr class="odd">
<td>ConnectionLink­Ref</td>
<td>1:1</td>
<td>Connection­Link­Code</td>
<td>Identifiant de la correspondance physique.</td>
</tr>
<tr class="even">
<td>StopPoint­Ref</td>
<td>0:1</td>
<td>StopPoint­Code</td>
<td><p>Identifiant du point d’arrêt de l’amenant (généralement porté par le <em>ConnectionLink</em>).</p>
<p>Il convient d'utiliser ici un identifiant d'objet de référence :zone d'embarquement ou zone de lieu : granularité la plus fine possible dans tous les cas.</p></td>
</tr>
<tr class="odd">
<td>VisitNumber</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the <strong>VisitNumber</strong> is used to distinguish each separate visit.</td>
</tr>
<tr class="even">
<td>Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission.</td>
</tr>
<tr class="odd">
<td>Stop­Point~Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom du point d'arrêt.</td>
</tr>
<tr class="even">
<td rowspan="3">Jour­ney Info</td>
<td>LineRef</td>
<td>1:1</td>
<td>LineCode</td>
<td>Identifiant de la ligne.</td>
</tr>
<tr class="odd">
<td>DirectionRef</td>
<td>1:1</td>
<td>Destination­Code</td>
<td>Identifiant de la direction (aller/retour).</td>
</tr>
<tr class="even">
<td>Vehicle­JourneyRef</td>
<td>1:1</td>
<td>+Framed­Vehicle­JourneyRef­Structure</td>
<td>Identification de la course.</td>
</tr>
<tr class="odd">
<td></td>
<td>JourneyPatternRef</td>
<td>0:1</td>
<td>Journey­PatternCode</td>
<td>Identifiant de la mission.</td>
</tr>
<tr class="even">
<td></td>
<td>JourneyPatternName</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Nom ou numero de course présenté au public.</p>
<p>Dans le cas de la SNCF et du RER, cet identifiant est le code à 4 lettres qui désigne la mission (RER et Transilien).</p>
<p>(+SIRI 2.0).</p></td>
</tr>
<tr class="odd">
<td></td>
<td>VehicleMode</td>
<td>0:1</td>
<td>air | bus | coach | ferry | metro | rail | tram | under­ground</td>
<td><p>Mode de transport pour cette mission (il s’agit ici d’un mode « générique », tous les avions par exemple seront air, et c’est le <em>ProductCategory</em>, dans <em>ServiceInfoGroup</em>, qui donnera plus de précisions, comme : <em>internationalFlight, intercontinentalFlight, domesticScheduledFlight, shuttleFlight …</em></p>
<p>Valeur par défaut : « bus »</p></td>
</tr>
<tr class="even">
<td></td>
<td>RouteRef</td>
<td>0:1</td>
<td>RouteCode</td>
<td>Identifiant de l'itinéraire suivi.</td>
</tr>
<tr class="odd">
<td></td>
<td>Published­LineName</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom commercial de la ligne.</td>
</tr>
<tr class="even">
<td></td>
<td>GroupOfLinesRef</td>
<td>0:1</td>
<td>GroupOfLinesCode</td>
<td><p>Identifiant du Goupe de Lignes (réseau ou tout autre groupe de ligne auquel la course est rattachée<del>: Noctilien, etc</del>.) <del>auquel la course est rattachée.</del></p>
<p>+SIRI V2.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td>DirectionName</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Nom de la destination.</p>
<p>Ce nom peut par exemple contenir des informations comme "A" ou "R" (Aller ou Retour) pour les lignes qui utilisent ces informations.</p></td>
</tr>
<tr class="even">
<td></td>
<td>ExternalLineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Alternative identifier of LINE that an external system may associate with journey.</td>
</tr>
<tr class="odd">
<td>Info</td>
<td>Reason</td>
<td>0:1</td>
<td>NLString</td>
<td>Cause de l’annulation.</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

#### Structure ConnectionMonitoringDistributorDelivery

|                                          |                                     |      |               |                                                                                                                                     |
| ---------------------------------------- | ----------------------------------- | ---- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| ConnectionMonitoringDistributor­Delivery |                                     |      | +Structure    | Information concernant le “partant”.                                                                                                |
| Attributes                               | version                             | 1:1  | VersionString | Version du service intégrant le numéro de version de profil (voir Error: Reference source not found) par exemple. ‘2.0:FR-IDF-2.4’. |
| LEADER                                   | :::                                 | 1:1  | xxx­Delivery  | See SIRI Part 2-7.2.1.1 xxx***Delivery**.*                                                                                          |
| Payload                                  | WaitProlonged­Departure             | 0:\* | +Structure    | Description d’une prolongation d’attente*.*                                                                                         |
|                                          | Stopping­Position­Changed­Departure | 0:\* | +Structure    | Déplacement du point de départ (et donc du trajet de correspondance).                                                               |
|                                          | Distributor­Departure­Cancellation  | 0:\* | +Structure    | Annulation de départ.                                                                                                               |
| any                                      | Extensions                          | 0:1  | +Structure    | Voir paragraphe 5.4.2.2                                                                                                             |

#### Structure DistributorInfoGroup

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 17%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 49%" />
</colgroup>
<tbody>
<tr class="odd">
<td rowspan="4">Distributor Inter­change_ Identity</td>
<td>Interchange­Ref</td>
<td>0:1</td>
<td>àInterchangeCode</td>
<td><p>Identifiant de la correspondance entre courses</p>
<p>Dans le cadre du profil France, si ce paramètre est présent, il sera constitué de la concaténation de l’identifiant de la course arrivant et de celui de la course au départ (séparés par le caractère ‘<strong>:</strong>’).</p></td>
</tr>
<tr class="even">
<td>Connection­Link­Ref</td>
<td>1:1</td>
<td>àConnection­Link­Code</td>
<td>Identifiant de la correspondance physique.</td>
</tr>
<tr class="odd">
<td>StopPoint­Ref</td>
<td>0:1</td>
<td>àStopPoint­Code</td>
<td><p>Identifiant du point d’arrêt du partant (généralement porté par le <em>ConnectionLink</em>).</p>
<p>Il convient d'utiliser ici un identifiant d'objet de référence zone d'embarquement ou lieu d’arrêt : granularité la plus fine possible dans tous les cas.</p></td>
</tr>
<tr class="even">
<td>Distributor­VisitNumber</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>Order of visit to a stop within journey pattern of distributor vehicle journey.</td>
</tr>
<tr class="odd">
<td></td>
<td>Distributor­Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission.</td>
</tr>
<tr class="even">
<td>Journey Info</td>
<td>Distributor­Journey</td>
<td>1:1</td>
<td>Connecting­Journey­Structure</td>
<td>Description de la course du véhicule au départ.</td>
</tr>
<tr class="odd">
<td>Feeder Info</td>
<td>Feeder­Vehicle­JourneyRef</td>
<td>0:*</td>
<td>Framed­Vehicle­Journey­Ref­Structure</td>
<td>Information sur la course de l’amenant (identifiant de la ou des courses).</td>
</tr>
</tbody>
</table>

#### Structure ConnectingJourney

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 14%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">ConnectingJourney</td>
<td>Connecting­Journey­Structure</td>
<td>Correspondance planifiée : description des courses impliquées : alimentant (“feeder”) ou partant (« distributor”) suivant les cas.</td>
</tr>
<tr class="even">
<td rowspan="3">Vehicle­Journey­Identity</td>
<td>LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Identifiant de la ligne.</td>
</tr>
<tr class="odd">
<td>DirectionRef</td>
<td>0:1</td>
<td>Direction­Code</td>
<td>Identifier of the relative direction the vehicle is running along the line, for example, "in" or "out", “clockwise”. Distinct from a destination.</td>
</tr>
<tr class="even">
<td>Framed­Vehicle­JourneyRef</td>
<td>0:1</td>
<td>+Structure</td>
<td>Identifiant de la course.</td>
</tr>
<tr class="odd">
<td>Journey­PatternInfo</td>
<td>:::</td>
<td>0:1</td>
<td>Journey­Pattern­Info­Group</td>
<td>Voir Journey­Pattern­Info­Group.</td>
</tr>
<tr class="even">
<td>Vehicle­Journey­Info</td>
<td>:::</td>
<td>0:1</td>
<td>Vehicle­Journey­Info­Group</td>
<td>Voir Vehicle­JourneyInfo­Group.</td>
</tr>
<tr class="odd">
<td>Disruption­Group</td>
<td>:::</td>
<td>0:1</td>
<td>Disruption­Group</td>
<td>Voir Disruption­Group.</td>
</tr>
<tr class="even">
<td>Operational Info</td>
<td>:::</td>
<td>0:1</td>
<td>Operational­Info­Group</td>
<td>See SIRI Part 2 Operational­Info­Group.</td>
</tr>
<tr class="odd">
<td>Progress</td>
<td>Monitored</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Signale si les données temps réel sont disponibles pour cette course (« false » permet de signaler une délocalisation).</p>
<p>Valeur par défaut : « true»</p></td>
</tr>
</tbody>
</table>

|     |                    |     |              |                                             |
| --- | ------------------ | --- | ------------ | ------------------------------------------- |
|     | Aimed­Arrival­Time | 0:1 | xsd:dateTime | Heure d’arrivée prévue à la correspondance. |
| any | Extensions         | 0:1 | any          | Placeholder for user extensions.            |

#### Structure WaitProlongedDeparture

|                        |                         |     |                        |                                                                 |
| ---------------------- | ----------------------- | --- | ---------------------- | --------------------------------------------------------------- |
| WaitProlongedDeparture |                         |     | +Structure             | Description d’une prologation d’arrêt pour attente de l’amenant |
| Log                    | Recorded­AtTime         | 1:1 | xsd:dateTime           | Date et heure auxquelles ces données ont été produites.         |
| Distri­butor­Info      | :::                     | 1:1 | Distributor­Info­Group | Voir Distributor­Info­Group.                                    |
| Change                 | Expected­Departure­Time | 1:1 | xsd:dateTime           | Nouvelle heure de départ prévue.                                |
| any                    | Extensions              | 0:1 | any                    | Placeholder for user extensions.                                |

#### Structure StoppingPositionChangedDeparture

|                                   |                 |     |                        |                                                            |
| --------------------------------- | --------------- | --- | ---------------------- | ---------------------------------------------------------- |
| StoppingPosition­ChangedDeparture |                 |     | +Structure             | Description d’un déplacement (temporaire) de point d’arrêt |
| Log                               | Recorded­AtTime | 1:1 | xsd:dateTime           | Date et heure auxquelles ces données ont été produites.    |
| Distri­butor­Info                 | :::             | 1:1 | Distributor­Info­Group | Voir Distrib­utor­Info­Group**.**                          |
| Change                            | ChangeNote      | 1:1 | NLString               | Description de la nouvelle position (textuelle).           |
|                                   | NewLocation     | 0:1 | Location              | Nouvelle position de l’arrêt.                              |
| any                               | Extensions      | 0:1 | any                    | Placeholder for user extensions.                           |

#### Structure Location

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 3%" />
<col style="width: 11%" />
<col style="width: 6%" />
<col style="width: 14%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">LocationStructure</td>
<td>0:1</td>
<td>+Structure</td>
<td>Geospatial Location</td>
</tr>
<tr class="even">
<td rowspan="2">Attributes</td>
<td colspan="2">id</td>
<td>0:1</td>
<td>xsd:NMTOKEN</td>
<td>Identifiant du point (pour un éventuel lien avec une base Géospatiale ou un SIG)</td>
</tr>
<tr class="odd">
<td colspan="2">srsName</td>
<td>0:1</td>
<td>xsd:string</td>
<td>Idenfitiant du référentiel de projection (conforme EPSG, définit par l’OGC, et tel qu’utilisé par GML).</td>
</tr>
<tr class="even">
<td rowspan="4">Coordinates</td>
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td><p>La localisation peut être fournie soit en WGS 84 soit dans un référentiel projeté (Lambert 2 étendu, par exemple).</p>
<p>Ces deux possibilités sont conservées dans le profil SIRI France.</p></td>
</tr>
<tr class="odd">
<td rowspan="2">a</td>
<td>Longitude</td>
<td>–1:1</td>
<td>Longitude­Type</td>
<td>Longitude à partir du meridien de Greenwich :.180° (East) à +180° (West). Degrés décimaux.</td>
</tr>
<tr class="even">
<td>Latitude</td>
<td>–1:1</td>
<td>Latitude­Type</td>
<td>Latitude à partir de l’équateur. -90° (South) à +90° (North). Degrés décimaux</td>
</tr>
<tr class="odd">
<td>b</td>
<td>Coordi­nates</td>
<td>–1:1</td>
<td>xsd:string</td>
<td>Coordonnées au format GML en cohérence avec l’attribut <em><strong>srsName</strong></em>.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Precision</td>
<td>0:1</td>
<td>Distance</td>
<td>Précision du positionnement (en mètres).</td>
</tr>
</tbody>
</table>

#### Structure DistributorDepartureCancellation

|                                    |                 |     |                        |                                                         |
| ---------------------------------- | --------------- | --- | ---------------------- | ------------------------------------------------------- |
| DistributorDeparture­­Cancellation |                 |     | +Structure             | Indication d’annulation de départ                       |
| Log                                | Recorded­AtTime | 1:1 | xsd:dateTime           | Date et heure auxquelles ces données ont été produites. |
| Distributor­Info                   | :::             | 1:1 | Distributor­Info­Group | Voir Distributor­Info­Group.                            |
| Call time                          | Reason          | 1:1 | NLString               | Raison de l’annulation.                                 |
| any                                | Extensions      | 0:1 | any                    | Placeholder for user extensions.                        |

## Vehicle Monitoring

*<u>Note</u>*: l'utilisation des MonitoredCall, OnwardCall et
PreviousCall est précisée en -Error: Reference source not found.

### Requête d’information sur les véhicules

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 11%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">VehicleMonitoringRequest</td>
<td>+Structure</td>
<td>Requête d’information sur les véhicules</td>
</tr>
<tr class="even">
<td>Attrib­utes</td>
<td colspan="2">version</td>
<td>1:1</td>
<td>VersionString</td>
<td>Version du service “Vehicle Monitoring”, intégrant le numéro de version de profil par exemple. ‘1.0:FR-1.0’.</td>
</tr>
<tr class="odd">
<td rowspan="2">End­point Properties</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date d'émission de la requête.</td>
</tr>
<tr class="even">
<td colspan="2">Message­Identifier</td>
<td>0:1</td>
<td>Message­Qualifier</td>
<td>Numéro d'identification du message.</td>
</tr>
<tr class="odd">
<td rowspan="5">Topic</td>
<td colspan="2">Vehicle­Monitoring­Ref</td>
<td>0:1</td>
<td>Vehicle­Monitoring­FIlterCode</td>
<td>The pre-arranged identifier about which data is requested.</td>
</tr>
<tr class="even">
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td>Choix ::</td>
</tr>
<tr class="odd">
<td>a</td>
<td>Vehicle­Ref</td>
<td rowspan="2">0:1</td>
<td>VehicleCode</td>
<td>Identifiant du véhicule.</td>
</tr>
<tr class="even">
<td>b</td>
<td>LineRef</td>
<td>LineCode</td>
<td>Identifiant de la ligne (tous les véhicules de la ligne seront remontés).</td>
</tr>
<tr class="odd">
<td colspan="2">DirectionRef</td>
<td>0:1</td>
<td>DirectionCode</td>
<td><p>Filter the results to include only vehicles going to the specified direction.</p>
<p>Optional SIRI capability: FilterByDirectionRef.</p></td>
</tr>
<tr class="even">
<td>Request Policy</td>
<td colspan="2">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td>Au niveau des échanges inter-systèmes, les textes restent en français. Les éventuelles traductions seront prises en charge par les systèmes de présentation.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Include­Translations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the producer should include any available translations of NLString text elements into multiple languages. If false elements only one value per text element will be provided. +SIRI.2.0</p>
<p>Default is false.</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Maximum­Vehicles</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td><p>The maximum number of vehicle journeys in a given delivery. The most recent n VehicleActivity instances within the look-ahead window are included. If absent, no limit.</p>
<p>Dans le profil France, soit on interroge par véhicule, soit par ligne, auquel cas on ne limite pas le nombre de réponses.</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">MaximumNumberOfCalls</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>The maximum number of CALLs to include per MONITORED VEHICLE JOURNEY in a given delivery. Only applies if Detail is calls.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Vehicle­Monitoring­Detail­Level</td>
<td>0:1</td>
<td>minimum | basic | normal | calls | full</td>
<td><p>Level of detail to include in response. Default is normal.</p>
<p>Optional SIRI capability: DetailLevel (if absent, must support Normal).</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Include­Situations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether any related Situations should be included in the ServiceDelivery. Default is 'false'. +SIRI v2.0</td>
</tr>
<tr class="even">
<td rowspan="3"></td>
<td colspan="2">Maximum­Number­Of­Calls</td>
<td>0:1</td>
<td>+Structure</td>
<td><p>If calls are to be returned, maximum number of calls to include in response. If absent, include all calls.</p>
<p>Optional SIRI capability: DetailLevel: Calls.</p>
<p>Dans le profil France, ce service est centré sur les positions des véhicules, et non sur leur desserte (utiliser les autres services dans ce cas).</p></td>
</tr>
<tr class="odd">
<td rowspan="2"></td>
<td>Previous</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Maximum number of previous calls to include. If set to 1, only the previous call, if any is returned.</td>
</tr>
<tr class="even">
<td>Onwards</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Maximum number of onwards calls to include.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

### Abonnement aux informations sur les véhicules

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 2%" />
<col style="width: 17%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">VehicleMonitoring­SubscriptionRequest</td>
<td>+Structure</td>
<td>Abonnement aux informations sur les véhicules</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td colspan="2">SubscriberRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identification du système demandeur ( voir SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.)</td>
</tr>
<tr class="odd">
<td colspan="2">Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant de l'abonnement pour le système demandeur.</td>
</tr>
<tr class="even">
<td>Lease</td>
<td colspan="2">Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td>Date et heure de fin de l'abonnement : un abonnement a forcément une date et heure de fin (les partenaires pourront décider de limiter la durée maximale d’un abonnement).</td>
</tr>
<tr class="odd">
<td>Request</td>
<td colspan="2">Vehicle­Monitoring­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>Voir VehicleMonitoringRequest.</td>
</tr>
<tr class="even">
<td>Policy</td>
<td colspan="2">Incremental­Updates</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indique s’il faut notifier uniquement les changements d'information, ou s’il faut systématiquement renvoyer toutes les informations si l'une d'elles change.</p>
<p>Voir la documentation SIRI: <em>IncrementalUpdates.</em></p></td>
</tr>
<tr class="odd">
<td rowspan="3"></td>
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td>Choix</td>
</tr>
<tr class="even">
<td>a</td>
<td>Change­Before­Updates</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td>Permet d'indiquer un écart de temps en dessous duquel on ne souhaite pas être notifié (si l'on demande un seuil de 5mn et qu'un horaire de départ change de 2mn, on ne sera pas notifié, évitant ainsi des flux d'information inutiles).</td>
</tr>
<tr class="odd">
<td>b</td>
<td>Update­Interval</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td>Permet d’obtenir les positions (ou mise à jour des positions) à intervalle régulier et prédéterminé<em>.</em></td>
</tr>
</tbody>
</table>

### Réponse aux requêtes d’information sur les véhicules

|                           |                               |      |               |                                                                                                                       |
| ------------------------- | ----------------------------- | ---- | ------------- | --------------------------------------------------------------------------------------------------------------------- |
| VehicleMonitoringDelivery |                               |      | +Structure    | Réponse aux requêtes d’information sur les véhicules                                                                  |
| Attributes                | version                       | 1:1  | VersionString | Numéro de version du service *Vehicle Monitoring*, intégrant le numéro de version de profil (voir 5.7) (valeur fixe). |
| LEADER                    | :::                           | 1:1  | xxx­Delivery  | Voir xxx***Delivery**.*                                                                                               |
| Pay­load                  | Vehicle­Activity              | 0:\* | +Structure    | Fournit les informations concernant le véhicule.                                                                      |
|                           | Vehicle­Activity­Cancellation | 0:\* | +Structure    | Signale l’annulation du service du véhicule.                                                                          |
|                           | VehicleActivity Note          | 0:\* | NLString      | General Text Note associated with delivery. DetailLevel: basic.                                                       |
| any                       | Extensions                    | 0:1  | +Structure    | Voir paragraphe 5.4.2.2                                                                                               |

#### Structure VehicleActivity

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 2%" />
<col style="width: 14%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">VehicleActivity</td>
<td>+Structure</td>
<td>Informations sur le véhicule</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Recorded­At­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Heure à laquelle la position du véhicule a été mise à jour.</td>
</tr>
<tr class="odd">
<td>Currency</td>
<td colspan="2">Valid­Until­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td><p>Heure jusqu'à laquelle l'information est réputée valide.</p>
<p>Cette information obligatoire dans l'XSD SIRI n'est pas considerée indispensable par le profil. Par convention on la remplira avec la même valeur que <em><strong>Recorded­At</strong>­<strong>Time</strong></em> pour signifier que la l'information n'est pas à prendre en compte (on ne peut en efffet pas laisser le champ vide).</p></td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td colspan="2">Item­Identifier</td>
<td>0:1</td>
<td>ItemIdentifier</td>
<td>Identifiant, qui permettra par la suite une annulation (par exemple, particulièrement utile si l’on ne dispose pas d’identifant de véhicule).</td>
</tr>
<tr class="odd">
<td colspan="2">Vehicle­Monitoring­Ref</td>
<td>0:1</td>
<td>Vehicle­Monitoring­Identifier</td>
<td>Identifiant du véhicule.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Monitoring­Name</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Name to use to describe monitor. May be included to improve usability of SIRI LITE services.</p>
<p>One per language.</p></td>
</tr>
<tr class="odd">
<td rowspan="3">Stop­Progr­ess­Info</td>
<td colspan="2">Progress­Between­Stops</td>
<td>0:1</td>
<td>Location­Structure</td>
<td>Position du véhicule entre l’arrêt précédent et l’arrêt suivant.</td>
</tr>
<tr class="even">
<td rowspan="2"></td>
<td>Link­Distance</td>
<td>0:1</td>
<td>xsd:decimal</td>
<td>Distance totale entre les deux arrêts (distance réelle sur le réseau routier).</td>
</tr>
<tr class="odd">
<td>Percentage</td>
<td>0.1</td>
<td>xsd:decimal</td>
<td>Pourcentage de cette distance déjà couverte par le véhicule.</td>
</tr>
<tr class="even">
<td>Journey­Info</td>
<td colspan="2">Monitored­Vehicle­Journey</td>
<td>1:1</td>
<td>Monitored­Vehicle­Journey Structure</td>
<td><p>Décrit la course effectuée par le véhicule.</p>
<p>C’est au sein de cette structure que l’on trouvera la position du véhicule (vehicleLocation).</p></td>
</tr>
<tr class="odd">
<td>Message</td>
<td colspan="2">Vehicle­Activity­Note</td>
<td>0:*</td>
<td>NLString</td>
<td>Information textuelle concernant le véhicule et son état courant (positionnement, etc.).</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

#### Structure VehicleActivityCancellation

|                             |                            |      |                            |                                                               |
| --------------------------- | -------------------------- | ---- | -------------------------- | ------------------------------------------------------------- |
| VehicleActivityCancellation |                            |      | +Structure                 | Annulation de l’affectation d’un véhicule à une course        |
| End­point                   | Recorded­AtTime            | 1:1  | xsd:dateTime               | Heure à laquelle l'annulation a été signalée/publiée.         |
| Event­Identity              | ItemRef                    | 0:1  | ItemIdentifier             | Identifiant de l’objet annulé (voir ***ItemRef*** plus haut). |
|                             | Vehicle­Monitoring­Ref     | 0:1  | Vehicle­Monitoring­Code   | Identifiant du véhicule.                                      |
|                             | Framed­Vehicle­Journey­Ref | 0:1  | +Structure                 | Description de la course annulée.                             |
|                             | LineRef                    | 0:1  | LineCode                  | Identifiant de la ligne.                                      |
|                             | Direction­Ref              | 0:1  | Direction­Code            | Identifier of Direction of journey that is being deleted.     |
| Journey­Pattern­Info        | :::                        | 0:1  | Journey­Pattern­Info­Group | See SIRI Part 2 Journey­Pattern­Info­Group.                   |
| Message                     | Reason                     | 0:\* | NLString                   | Description textuelle de la cause de l’annulation.            |
| any                         | Extensions                 | 0:1  | Any                        | Placeholder for user extensions.                              |

## General Message

Les lignes qui suivent présentent l’implémentation du service SIRI
*General Message* dans le cadre du profil France.

Ce service est particulier, car la norme SIRI ne détaille pas la
structure du message lui-même : ce qui est précisé par la norme SIRI
sont les modalités de requête et de réponse pour accéder aux messages,
ainsi que quelques informations de base comme les canaux de message
(Info Channel).

Le message lui-même, présenté ci-dessous sous forme de schéma XSD, est
donc complètement spécifique au profil France : il est en effet
indispensable de le définir précisément pour assurer la compatibilité
des différents systèmes.

Les messages peuvent être rattachés à n’importe quel objet du réseau
(ligne, mission, itinéraire, section de ligne et bien sur arrêt). SIRI
ne prévoit toutefois pas la possibilité de rattacher un tel message au
service *Stop Monitoring* (pour avoir les deux informations en une seule
requête), ce qui se justifie facilement par le fait que, comme cela
vient d’être indiqué, le message n’est pas forcément rattaché à un
arrêt.

Enfin, il faut rappeler que ce service n’est pas le service de gestion
de perturbation : il est conçu pour pouvoir diffuser les informations
non structurées de perturbation, dans un premier temps, en attendant la
définition finale du service SIRI *Situation Exchange* et surtout en
attendant que les alimentants soient en mesure de diffuser des
informations structurées et non simplement textuelles.

Dans un second temps, l’usage du service *General Message* se
restreindra donc aux messages généraux de type communication (i.e.:
Pensez à acheter votre coupon mensuel, modification de politique
tarifaire ; etc.) ou information ne concernant pas les réseaux (i.e.:
match, concert, etc.).

### Capability Matrix

Cette matrice n'est pas échangée dans le cadre du profil France: elle
est juste présentée ici pour présenter les principales fonctions
retenues pour le service (les explications ne sont pas traduites dans ce
tableau, mais on retrouve les traductions dans les tableaux qui
suivent).

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 18%" />
<col style="width: 67%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Topic</td>
<td colspan="2">TopicFiltering</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>DefaultPreview­Interval</td>
<td>Non</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>FilterByInfo­Channel</td>
<td>Oui</td>
</tr>
<tr class="even">
<td>Request Policy</td>
<td colspan="2">RequestPolicy</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Language</td>
<td><p>Non</p>
<p>(si le message est disponible en plusieurs langues, toutes les langues sont systèmatiquement diffusées)</p></td>
</tr>
<tr class="even">
<td>Access Control</td>
<td colspan="2">AccessControl</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Request­Checking</td>
<td>Non</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>CheckInfo­Channel</td>
<td>Oui</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>Non</td>
</tr>
</tbody>
</table>

### Requête au service « General Message »

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 49%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">GeneralMessageRequest</td>
<td>+Structure</td>
<td>Requête d'accès aux messages</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td>version</td>
<td>1:1</td>
<td>VersionString</td>
<td>Version du service « General Message », intégrant le numéro de version de profil (voir 5) (valeur fixe).</td>
</tr>
<tr class="odd">
<td>Endpoint Proper­ties</td>
<td>Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date d'émission de la requête (voir SIRI Part 2 Common properties of SIRI Functional Service Requests).</td>
</tr>
<tr class="even">
<td></td>
<td>Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Numéro d'identification du message</td>
</tr>
<tr class="odd">
<td>Topic</td>
<td>Info­Channel­Ref</td>
<td>0:*</td>
<td>InfoChannel­Code</td>
<td><p>Identifie le canal pour lequel on souhaite obtenir les messages. Si ce champ n'est pas présent, la requête concerne tous les canaux.</p>
<p>Dans le cadre du profil FR, seules les valeurs suivantes seront utilisées pour identifier les canaux:</p>
<ul>
<li><p>«Perturbation»</p></li>
<li><p>«Information»</p></li>
<li><p>«Commercial»</p></li>
</ul>
<p><u>Note</u>: ce sont bien ces libellés texte précis, qui sont utilisés pour instancier l'attribut <strong>InfoChannelRef</strong> (et non une codification équivalente).</p>
<p>Les travaux prévus et non prévus sont transmis en messages de type « Perturbation ».</p></td>
</tr>
<tr class="even">
<td>Request Policy</td>
<td>Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td><p>Langue dans laquelle le message est demandé.</p>
<p>Dans le cadre du profil FR, seul le français est obligatoire, mais un système pourra optionnellement proposer d'autres langues.</p></td>
</tr>
<tr class="odd">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

### Requête d'abonnement au service « General Message »

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 18%" />
<col style="width: 7%" />
<col style="width: 20%" />
<col style="width: 40%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">GeneralMessage­SubscriptionRequest</td>
<td>+Structure</td>
<td>Requête d’abonnement au service SIRI <em>GeneralMessage</em>.</td>
</tr>
<tr class="even">
<td>Identity</td>
<td>SubscriberRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identifiant du système demandeur (voir SIRI Part 2 Common <em>SubscriptionRequest</em> parameter.</td>
</tr>
<tr class="odd">
<td></td>
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant (externe) du canal d'abonnement.</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td>Date et heure prévues pour la fin de l'abonnement.</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>General­Message­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>Voir GeneralMessageRequest.</td>
</tr>
</tbody>
</table>

### Réponse du service « General Message » (structure générale)

|                 |                          |      |                     |                                             |
| --------------- | ------------------------ | ---- | ------------------- | ------------------------------------------- |
| ServiceDelivery |                          |      | +Structure          | See SIRI Part 2-7.2.1 ***ServiceDelivery*** |
| HEADER          | ::                       | 1:1  | See ServiceDelivery | En-tête générique des réponses.             |
| Payload         | General­Message­Delivery | 1:\* | +Structure          | Voir GeneralMessageDelivery.                |

### Réponse du service « General Message » (structure détaillée)

|                        |                           |      |                |                                                                                       |
| ---------------------- | ------------------------- | ---- | -------------- | ------------------------------------------------------------------------------------- |
| GeneralMessageDelivery |                           |      | +Structure     | Contenu et modification des messages.                                                 |
| Attributes             | version                   | 1:1  | Version­String | Version du service, intégrant le numéro de version de profil (voir 5.7) (valeur fixe) |
| LEADER                 | :::                       | 1:1  | xxx­Delivery   | En-tête (voir paragraphe 2.2*.)*                                                      |
| Payload                | Info­Message              | 0:\* | +Structure     | Le message lui-même (voir ***InfoMessage** ci dessous)*.                              |
|                        | Info­Message­Cancellation | 0:\* | +Structure     | Structure d'annulation d'un message précédent (voir ci dessous).                      |

Note: GeneralMessageDelivery doit contenir au moins un InfoMessage ou un
InfoMessage­Cancellation (il peut bien sur en contenir plusieurs de
chaque)

### Description du « General Message »

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 17%" />
<col style="width: 6%" />
<col style="width: 15%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">InfoMessage</td>
<td>+Structure</td>
<td>Message d'information.</td>
</tr>
<tr class="even">
<td>attribute</td>
<td>format­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>FormatCode</td>
<td><p>Identifie le format du contenu (ouvert pour ce service).</p>
<p>Dans le cadre du profil FR, ce champ sera toujours présent et aura une valeur fixe « <strong>France </strong>» et correspond au transport de la structure spécifique de message décrite plus bas.</p></td>
</tr>
<tr class="odd">
<td>log</td>
<td>Recorded­At­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Heure d'enregistrement du message.</td>
</tr>
<tr class="even">
<td>Identity</td>
<td>Item­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>ItemIdentifier</td>
<td><p>Identifiant unique du message SIRI, fourni par son émetteur (deux réceptions différentes ne peuvent avoir le même identifiant).</p>
<p>Il doit être unique et pérenne et bien identifier le message.</p></td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>Info­Message­Identifier</td>
<td>1:1</td>
<td>Identifier</td>
<td>Identifiant <em><strong>InfoMessage</strong></em> (sera utilisé pour les mises à jour et les abandons de message: toutes les mises à jour du message porteront le même <em><strong>InfoMessage­Identifier</strong></em>).</td>
</tr>
<tr class="even">
<td></td>
<td>Info­Message­Version</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Version du <em><strong>InfoMessage</strong></em>.(considéré comme valant 1 si le champ n'est pas présent)</td>
</tr>
<tr class="odd">
<td></td>
<td>Info­Channel­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>InfoChannel</td>
<td><p>Canal auquel appartient le message.</p>
<p>Dans le cadre du profil FR, seules les valeurs suivantes seront utilisées pour identifier les canaux :</p>
<ul>
<li><p>« Perturbation »</p></li>
<li><p>« Information »</p></li>
<li><p>« Commercial »</p></li>
</ul>
<p><u>Note</u>: ce sont bien ces libellés texte précis, qui sont utilisés pour instancier l'attribut <strong>InfoChannelRef</strong> (et non une codification équivalente).</p>
<p>Les travaux prévus et non prévus sont transmis en messages de type « Perturbation ».</p></td>
</tr>
<tr class="even">
<td>Curr­ency</td>
<td>Valid­Until­Time</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>xsd:dateTime</td>
<td><p>Date et heure jusqu'à laquelle le message est valide.</p>
<p>Si toutefois l'heure de fin d'incident n'est pas connue, cette heure sera fixée en fin de journée d'exploitation (ou une heure fixe de fin de journée).</p>
<p>Cette heure pourra naturellement être modifiée par une mise à jour ultérieure (pour le même <em><strong>Info­Message­Identifier</strong></em>).</p>
<p>L'annulation du message est implicite lorsque que l'on atteint cette heure, mais peut aussi être anticipée en utilisant une <em><strong>InfoMessageCancellation</strong></em> (recommandé en mode abonnement)<em><strong>.</strong></em></p></td>
</tr>
<tr class="odd">
<td>Situation</td>
<td>Situation­Ref</td>
<td>0:*</td>
<td>SituationCode</td>
<td>Référence à un événement externe auquel est rattaché le message.</td>
</tr>
<tr class="even">
<td>Mess­age</td>
<td>Content</td>
<td>1:1</td>
<td>anyType</td>
<td><p>Le message lui-même (voir ci-dessous)</p>
<p><em><u>Note</u></em>: il convient de bien noter que le type utilisé ici par SIRI est "<em>anyType</em>" (et non "<em>any</em>"). Ceci à pour conséquence l'obligation d'encoder (en attribut) le type de la structure utilisé dans pour décrire le message, en l'occurrence sous la forme :</p>
<p>&lt;Content xsi:type="siri: FRGeneralMessageStructure"&gt;</p>
<p>dans le cadre du profil France.</p></td>
</tr>
<tr class="odd">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>Any</td>
<td>Champ réservé pour un usage libre.</td>
</tr>
</tbody>
</table>

### Annulation d'un « General Message »

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 20%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 47%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">InfoMessageCancellation</td>
<td>+Structure</td>
<td>Annulation d'un message émis précédemment.</td>
</tr>
<tr class="even">
<td>log</td>
<td>Recorded­At­Time</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Heure à laquelle le message a été annulé.</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>ItemRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>ItemIdentifier</td>
<td>Identifiant unique du message SIRI (deux réceptions différentes ne peuvent avoir le même identifiant). Sa valeur doit naturellement être unique et pérenne pour un message.</td>
</tr>
<tr class="even">
<td>Identity</td>
<td>Info­Message­Identifier</td>
<td>1:1</td>
<td>Identifier</td>
<td>Référence <em><strong>InfoMessage</strong></em> du message à annuler.</td>
</tr>
<tr class="odd">
<td></td>
<td>Info­Channel­Ref</td>
<td>0:1</td>
<td>Info­ChannelCode</td>
<td><p>Canal auquel appartient le message.</p>
<p>Dans le cadre du profil IDF, seules les valeurs suivantes seront utilisées pour identifier les canaux:</p>
<ul>
<li><p>« Perturbation »</p></li>
<li><p>« Information »</p></li>
<li><p>« Commercial »</p></li>
</ul>
<p><u>Note</u>: ce sont bien ces libellés texte précis qui sont utilisés pour instancier l'attribut <strong>InfoChannelRef</strong> (et non une codification équivalente).</p>
<p>Les travaux prévus et non prévus sont transmis en messages de type « Perturbation ».</p></td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>Any</td>
<td>Champ réservé pour un usage libre.</td>
</tr>
</tbody>
</table>

### Structure spécifique des requêtes « General Message » pour le profil FR

Cette structure spécifique constitue le mécanisme de filtrage du service
« General Message » et s'insère au sein de l'élément **extension** de la
requête.

![image](media/image3.png)

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 88%" />
</colgroup>
<tbody>
<tr class="odd">
<td>GM-1</td>
<td><p>Les champs de la structure sont les suivants:</p>
<ul>
<li><p>Le champ «LineRef» permet de n'obtenir que les messages relatifs à la ligne indiquée ;</p></li>
<li><p>Le champ «StopPointRef» permet de n'obtenir que les messages relatifs à l'arrêt indiqué (Il convient d'utiliser ici un identifiant d'objet de référence de REFLEX - zone d'embarquement ou zone de lieu : granularité la plus fine possible dans tous les cas) ;</p></li>
<li><p>Le champ «JourneyPatternRef» permet de n'obtenir que les messages relatifs à la mission commerciale indiquée ;</p></li>
<li><p>Le champ «DestinationRef» permet de n'obtenir que les messages relatifs à la destination indiquée ;</p></li>
<li><p>Le champ «RouteRef» permet de n'obtenir que les messages relatifs à l'itinéraire indiqué ;</p></li>
<li><p>Le champ «GroupOfLinesRef» permet de n'obtenir que les messages relatifs au groupe de lignes indiqué (réseau ou tout groupe de lignes dont le code a été préalablement échangé comme donnée de référence : Noctilien, lignes attachées à un dépôt, etc.)</p></li>
</ul></td>
</tr>
<tr class="even">
<td>GM-2</td>
<td>Les champs de filtres sont insérés au sein d'une structure "choice" et ne peuvent donc être utilisés simultanément.</td>
</tr>
</tbody>
</table>

### Structure spécifique des messages pour le profil FR

![image](media/image4.png)

Cette structure correspond au champ *Content* de la structure
*Infomessage*.

Cette structure est définie de façon spécifique pour le profil FR car la
norme SIRI n'impose pas de structure de message (et n'en propose pas non
plus) : il revient donc à chaque profil de décrire ces messages.

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 92%" />
</colgroup>
<tbody>
<tr class="odd">
<td>GM-3</td>
<td><p>Les champs de la structure sont les suivants :</p>
<ul>
<li><p>Le champ «LineRef» identifie la ou les lignes concernées par le message.</p></li>
</ul>
<p>Si une ligne est indiquée, le message porte sur toute la ligne sans restriction.</p>
<p>Les choix de comportement pour générer la liste des messages concernant la ligne (messages spécifiques à la ligne, messages concernant tous les arrêts desservis par la ligne, etc.) restent à l'appréciation du producteur et seront précisés par les spécifications.</p>
<ul>
<li><p>Le champ «StopPointRef» identifie le ou les points d'arrêt concernés par le message.</p></li>
</ul>
<p>Il convient d'utiliser ici un identifiant d'objet de référence . Zone dembarquement, Lieu d’arrêt monomodal, Lieu d’arrêt multimodal.</p>
<p>Les choix de comportement pour générer la liste des messages concernant l’arrêt (messages spécifiques à l’arrêt, messages concernant toutes les lignes de l’opérateur desservant l’arrêt, etc.) restent à l'appréciation du producteur et seront précisés par les spécifications.</p>
<ul>
<li><p>Le champ «JourneyPatternRef» identifie la ou les missions concernées par le message.</p></li>
</ul>
<p>Si une mission est indiquée, le message porte sur toute la mission sans restriction.</p>
<ul>
<li><p>Le champ «DestinationRef» identifie la ou les destinations concernées par le message</p></li>
</ul>
<p>Si une destination est indiquée, le message porte sur toutes les courses ayant cette destination sans restriction.</p>
<ul>
<li><p>Le champ «RouteRef» identifie le ou les itinéraires concernés par le message.</p></li>
</ul>
<p>Si un itinéraire est indiqué, le message porte sur tout l'itinéraire sans restriction.</p>
<ul>
<li><p>Le champ «GroupOfLinesRef» permet d'indiquer que le message est relatifs au groupe de lignes indiqué (réseau ou tout groupe de lignes dont le code a été préalablement échangé comme donnée de référence : Noctilien, lignes attachées à un dépôt, etc.). Toutes les lignes du groupe de lignes sont alors concernées par le message.</p></li>
<li><p>Le champ «LineSection» identifie la ou les sections de lignes (premier et dernier arrêt ainsi que leur ligne d'appartenance) concernée(s) par le message.</p></li>
</ul>
<p>Si une section de ligne est indiquée, le message porte sur tous les arrêts de cette section, sans restriction.</p>
<p><u>Note</u>: pour être exact il vaudrait mieux parler de section d’itinéraires, mais beaucoup de systèmes ne disposant pas de la notion d’itinéraires, le choix a été de faire porter la section sur la ligne.</p>
<ul>
<li><p>Le champ « <strong>Message</strong> » contient le message lui-même :</p></li>
<li><p>« NumberOfLines » est une information facultative de formatage précisant le nombre de lignes du message ;</p></li>
<li><p>« NumberOfCharPerLine » est une information facultative de formatage précisant le nombre maximum de caractères par ligne d’affichage dans le message ;</p></li>
<li><p>« <strong>MessageType</strong> » permet de donner un type au contenu du message. Les valeurs possibles pour ce type sont :</p>
<ul>
<li><p><em><strong>shortMessage</strong></em> : Message texte court, par opposition au <em><strong>longMessage</strong></em> ; l'utilisation de ce code suppose que l'on disposera aussi d'une version longue du même message.</p></li>
<li><p><em><strong>longMessage</strong></em> : Message texte long, par opposition au <em><strong>shortMessage</strong></em> ; l'utilisation de ce code suppose que l'on disposera aussi d'une version courte du même message.</p></li>
<li><p><em><strong>textOnly</strong></em> : texte libre sans restriction ni formatage particulier, mais n'utilisant que des caractères textes imprimables sans saut de ligne. Le profil établit depuis sa vesion 2.3 que la fourniture du message sous cette version est <strong>obligatoire</strong>. Un <em><strong>messageText</strong></em> est évidemment obligatoire dans quand on positionne <strong>MessageType</strong> à <em><strong>textOnly</strong></em>.</p></li>
<li><p><em><strong>formattedText</strong></em> : texte formaté en nombre de lignes et de caractères (voir les champs précédents). Dans ce cas le retour chariot est &lt;LF&gt; seul (code ascii 10 en décimal) ;</p></li>
<li><p><em><strong>HTML</strong></em> : format compatible HTML 4 ;</p></li>
<li><p><em><strong>RTF</strong></em> : Rich Text Format ;</p></li>
<li><p><em><strong>codedMessage</strong></em> : Ce type permettra par exemple de définir une bibliothèque de messages de n’en communiquer que le type (en laissant alors vide le champ texte).</p></li>
</ul></li>
</ul>
<p>Si une telle bibliothèque est utilisée, elle devra être définie dans le protocole d’accord établi entre les différents intervenants dans l’échange. On pourra aussi éventuellement en envisager une définition globale au niveau du SDIV.</p>
<ul>
<li><p>« MessageText » est une chaîne de caractères contenant un libellé de message (la langue du message peut être précisée et plusieurs « Message » peuvent être diffusés en une seule fois ce qui permet de diffuser un message en plusieurs langues ou sous plusieurs formes).</p></li>
</ul>
<p>Chaque producteur fournit une information sans mise en page (sans retour chariot) : la charge de la mise en page revient aux diffuseurs en fonction de ses capacités d’affichage.</p></td>
</tr>
</tbody>
</table>

*<u>Note</u>*: Un GeneralMessage peut contenir plusieurs messages (voir
la cardinalité sur la figure ci-dessus) formatés différemment ; charge
au diffuseur de prendre le format le plus adapté à son usage et ses
contraintes.

La fin de validitié d'un message, en particulier d'une perturbation, est
gérée de la façon suivante :

|      |                                                                                                                                                                                                                                                                                                                                                                                    |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| GM-4 | En mode requête, le diffuseur doit considérer une information reçue précédemment comme obsolète quand la réponse qu'il reçoit est vide (ou tout du moins quand elle ne retourne plus l'information précédemment reçue) ou quand l’heure de fin d’évènement est expirée (champ Valid­Until­Time) ; le producteur n’envoie en effet que les messages actifs au moment de la requête. |
| GM-5 | En mode abonnement, le diffuseur doit considérer une information reçue précédemment comme obsolète quand il reçoit une information de type "InfoMessageCancellation" ou quand l’heure de fin d’évènement est expirée (champ Valid­Until­Time).                                                                                                                                     |

### Précision sur l'ecodage de la structure spécifique France et exemple de message

Contrairement aux champs d'extension de SIRI, le type utilisé pour
décrire le contenu du message de General Message est "*anyType*" (et non
"*any*"). Ce choix correspond à une volonté de contraindre à partager,
entre les acteurs impliqués dans l’échange, une structure pour ce
contenu qui correspond au coeur du message, plutôt que de laisser les
acteurs le remplir à leur guise (ce qui est en final une contrainte de
base d'interopérabilité, à laquelle le profil France répond d'ailleurs
bien avec les structures ***FrGeneralMessageStructure***).

En conséquence, il convient donc d'encoder (en attribut) le type de la
structure utilisée pour décrire le message, en l'occurrence sous la
forme :

\<Content xsi:type="siri:~~IDF~~FrGeneralMessageStructure">

Les lignes ci-dessous proposent un exemple de *Delivery* d'un *General
Message* dans le cadre du profil France.

\<siri:GeneralMessageDelivery version="1.3">

\<siri:ResponseTimestamp>2013-12-19T11:26:59.677+01:00\</siri:ResponseTimestamp>

\<siri:RequestMessageRef>SOAP-REQ-12345\</siri:RequestMessageRef>

\<siri:Status>true\</siri:Status>

\<siri:ValidUntil>2013-12-19T11:28:59.677+01:00\</siri:ValidUntil>

\<siri:DefaultLanguage>FR\</siri:DefaultLanguage>

\<siri:GeneralMessage formatRef="France">

\<siri:RecordedAtTime>2013-12-19T11:26:59.767+01:00\</siri:RecordedAtTime>

\<siri:ItemIdentifier>ITEM-ID-1234567\</siri:ItemIdentifier>

\<siri:InfoMessageIdentifier>INFMSG-ID-12345678\</siri:InfoMessageIdentifier>

\<siri:InfoChannelRef>Information\</siri:InfoChannelRef>

\<siri:ValidUntilTime>2013-13-19T11:32:59.767+01:00\</siri:ValidUntilTime>

\<siri:Content xsi:type="siri:FrGeneralMessageStructure">

\<siri:Message>

\<siri:MessageType>textOnly\</siri:MessageType>

\<siri:MessageText xml:lang="FR">Trafic normal sur l'ensemble du
réseau.\</siri:MessageText>

\</siri:Message>

\</siri:Content>

\</siri:GeneralMessage>

\</siri:GeneralMessageDelivery>

# Eléments techniques des messages

## En-têtes des requêtes

Structure générale des requêtes

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 2%" />
<col style="width: 21%" />
<col style="width: 6%" />
<col style="width: 11%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">ServiceRequest</td>
<td>+Structure</td>
<td>Structure générale des requêtes</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">ServiceRequest­Context</td>
<td>0:1</td>
<td>+Structure</td>
<td><p>General request properties – typically configured rather than repeated on request.</p>
<p>Fixé une fois pour toute par le profil France et dans le protocole d’accord.</p></td>
</tr>
<tr class="odd">
<td>log</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date d’émission de la requête.</td>
</tr>
<tr class="even">
<td rowspan="2">Auth</td>
<td colspan="2">AccountId</td>
<td>0:1</td>
<td>+Structure</td>
<td>Account Identifier. May be used to attribute requests to a specific user account for authentication or reporting purposes</td>
</tr>
<tr class="odd">
<td colspan="2">AccountKey</td>
<td>0:1</td>
<td>+Structure</td>
<td>Authentication key for request. May be used to authenticate the request to ensure the user is a registered client.</td>
</tr>
<tr class="even">
<td>Endpoint Proper­ties</td>
<td colspan="2">Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse réseau de destination de la réponse (ici une URL étant donné le choix d’implémentation SOAP).</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Requestor­Ref</td>
<td>1:1</td>
<td>Participant­Code</td>
<td>Identifiant du demandeur (reprendre la structure [<em>fournisseur</em>] des identifiants).</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identifiant unique de ce message.</td>
</tr>
<tr class="odd">
<td rowspan="2">Deleg­ator End­point</td>
<td colspan="2">DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="even">
<td colspan="2">DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Concrete service subscription</td>
<td></td>
<td></td>
<td>Si la suite contient plusieurs réponses, elles doivent toutes être du même type.</td>
</tr>
<tr class="even">
<td>Payload</td>
<td>a</td>
<td>Production­Timetable­Request</td>
<td rowspan="11">-1:*</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Production Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td>b</td>
<td>Estimated­Timetable­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Estimated Timetable.</td>
</tr>
<tr class="even">
<td></td>
<td>c</td>
<td>Stop­Timetable­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Stop Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td>d</td>
<td>StopMonitoring­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Stop Monitoring.</td>
</tr>
<tr class="even">
<td></td>
<td>e</td>
<td>StopMonitoringMultipleRequest</td>
<td>+Structure</td>
<td><p>See SIRI Part 3 – Stop Monitoring.</p>
<p><u>Note</u>: peut être maintenu pour compatibilité ascendante de certaines implémentations du profil 2.2 et 2.3, mais n'est plus retenu à partir de la version 2.4</p></td>
</tr>
<tr class="odd">
<td></td>
<td>f</td>
<td>Vehicle­Monitoring­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Vehicle Monitoring.</td>
</tr>
<tr class="even">
<td></td>
<td>g</td>
<td>Connection­Timetable­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Connection Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td>h</td>
<td>Connection­Monitoring­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – Connection Monitoring.</td>
</tr>
<tr class="even">
<td></td>
<td>i</td>
<td>General­Message­Request</td>
<td>+Structure</td>
<td>See SIRI Part 3 – General Message.</td>
</tr>
<tr class="odd">
<td></td>
<td>j</td>
<td>FacilityMonitoring­Request</td>
<td>+Structure</td>
<td>See SIRI Part 4 – Facility Monitoring. SIRI v1.3.</td>
</tr>
<tr class="even">
<td></td>
<td>k</td>
<td>SituationExchange­Request</td>
<td>+Structure</td>
<td>See SIRI Part 5 – Situation Exchange. SIRI v1.3.</td>
</tr>
</tbody>
</table>

Contexte générique des requêtes

La structure ci-dessous n’est pas échangée, mais son contenu doit être
connu des différents protagonistes (définition par le profil et dans le
cadre du protocole d’accord). Cette structure propose une séparation
très fine des différentes notions, mais sera généralement utilisée de
façon très simplifiée.

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 2%" />
<col style="width: 22%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 40%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">ServiceRequestContext</td>
<td>+Structure</td>
<td>Propriétés générales des requêtes.</td>
</tr>
<tr class="even">
<td>Server Endpoint Address</td>
<td colspan="2">Check­Status­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination du <em><strong>CheckStatus.</strong></em></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Subscribe­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des demandes d’abonnement.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Manage­Subscription­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination pour la gestion des abonnements déjà établis (interruption, …).</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Get­Data­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des réponses aux requêtes.</td>
</tr>
<tr class="even">
<td>Client End­point Address</td>
<td colspan="2">Status­Response­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des réponses aux <em><strong>CheckStatus.</strong></em></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Subscriber­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des réponses aux demandes de notification.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Notify­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des notifications.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Consumer­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des données.</td>
</tr>
<tr class="even">
<td>Name­space</td>
<td colspan="2">Data­Name­Spaces</td>
<td>0:1</td>
<td>+Structure</td>
<td>Eventuel espace de nommage (pour éviter les confusions quand plusieurs systèmes sont en jeu : ce point est traité par le principe d’identification proposé dans le profil).</td>
</tr>
<tr class="odd">
<td>Name­Space</td>
<td></td>
<td>Stop­Point­Name­Space</td>
<td>0:1</td>
<td>xsd:anyUrl</td>
<td>Namespace for stop references.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Line­Name­Space</td>
<td>0:1</td>
<td>xsd:anyUrl</td>
<td>Namespace for line names and directions.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Product­Category­Name­Space</td>
<td>0:1</td>
<td>xsd:anyUrl</td>
<td>Namespace for product categories</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Service­Feature­Name­Space</td>
<td>0:1</td>
<td>xsd:anyUrl</td>
<td>Namespace for Service Features</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Vehicle­Feature­Name­Space</td>
<td>0:1</td>
<td>xsd:anyUrl</td>
<td>Namespace for vehicle features</td>
</tr>
<tr class="even">
<td>Language</td>
<td colspan="2">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td><p>Default language.</p>
<p>La langue par défaut est le français.</p></td>
</tr>
<tr class="odd">
<td>Location</td>
<td>a</td>
<td>Wgs­Decimal­Degrees</td>
<td>0:1</td>
<td>EmptyType</td>
<td>Geospatial coordinates are given as WGS84 latitude and longitude, decimal degrees of arc.</td>
</tr>
<tr class="even">
<td></td>
<td>b</td>
<td>Gml­Coordinate­Format</td>
<td></td>
<td>srsName­Type</td>
<td><p>Name of GML Coordinate format used for Geospatial points in responses.</p>
<p>Les deux formats sont autorisés en France (<em><u>note</u></em> : il existe de nombreux outils libres permettant de convertir les coordonnées d’un référentiel à l’autre).</p></td>
</tr>
<tr class="odd">
<td rowspan="2">Units</td>
<td colspan="2">DistanceUnits</td>
<td>0:1</td>
<td>xsd:normalized­String</td>
<td>Units for <em>DistanceType</em>. Default is metres. <del>+SIRI v2.0</del></td>
</tr>
<tr class="even">
<td colspan="2">VelocityUnits</td>
<td>0:1</td>
<td>xsd:normalized­String</td>
<td><p>Units for <em>VelocityType</em>. Default is metres per second.</p>
<p>On utilise les valeurs par défaut de ces champs en France.</p></td>
</tr>
<tr class="odd">
<td rowspan="2">Temporal Span</td>
<td colspan="2">Data­Horizon</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Durée maximale de l’horizon de données des requêtes.</td>
</tr>
<tr class="even">
<td colspan="2">Request­Timeout</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Délai à partir duquel on peut considérer qu’une requête ne sera plus traitée (par défaut 1 minute).</td>
</tr>
<tr class="odd">
<td rowspan="3">Delivery Method</td>
<td colspan="2">Delivery­Method</td>
<td>0:1</td>
<td>fetch | direct</td>
<td><p>Delivery pattern</p>
<p>Abonnement à une phase (voir en début de document) uniquement : donc <em>direct.</em></p></td>
</tr>
<tr class="even">
<td colspan="2">Multipart­Despatch</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Autorisation de segmentation des messages : <strong>Non</strong> dans le profil francilien.</td>
</tr>
<tr class="odd">
<td colspan="2">Confirm­Receipt</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Confirmation des réceptions: <strong>Non</strong> dans le profil francilien.</td>
</tr>
<tr class="even">
<td>Resource Use</td>
<td colspan="2">Maximum­Number­Of­Subscriptions</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Nombre maximal d’abonnements pour un unique abonné (par défaut non limité).</td>
</tr>
<tr class="odd">
<td rowspan="2">Prediction</td>
<td colspan="2">Allowed­Predictors</td>
<td>0:1</td>
<td>avmsOnly | anyone</td>
<td>Who may make a prediction. Documentation only. Default anyone.</td>
</tr>
<tr class="even">
<td colspan="2">Prediction­Function</td>
<td>0:1</td>
<td>xsd:string</td>
<td>Allows a named to be given to the prediction function. Documentation only.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

## En-têtes des réponses

Structure générique des réponses

<u>Note : Cette structure n'est pas utilisée dans le cadre des échanges
SOAP (point de départ avec ***xxxDelivery***).</u>

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 3%" />
<col style="width: 2%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 0%" />
<col style="width: 14%" />
<col style="width: 45%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">ServiceDelivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>Structure générique de réponse aux requêtes.</td>
</tr>
<tr class="even">
<td>Attrib­utes</td>
<td colspan="3">srsName</td>
<td>0:1</td>
<td colspan="2">xsd:string</td>
<td>Identifiant du système de projection (pour la localisation spatiale) : probablement Lambert 2 étendu (soit EPSG:27582 -NTF(Paris)/Lambert II étendu).</td>
</tr>
<tr class="odd">
<td>Log</td>
<td colspan="3">Response­Timestamp</td>
<td>1:1</td>
<td colspan="2">xsd:dateTime</td>
<td>Heure de production de la réponse.</td>
</tr>
<tr class="even">
<td rowspan="4">End­­poi­nt proper­ties</td>
<td colspan="3">ProducerRef</td>
<td>0:1</td>
<td colspan="2">Participant­Code</td>
<td>Identifiant du producteur de la réponse (reprendre le code [<em>fournisseur</em>] des identifiants du profil FR)..</td>
</tr>
<tr class="odd">
<td colspan="3">Address</td>
<td>0:1</td>
<td colspan="2">Endpoint­Address</td>
<td>Address to which any acknowledgment should be sent. Only needed if <em><strong>ConfirmDelivery</strong></em> specified.</td>
</tr>
<tr class="even">
<td colspan="3">Response­Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td colspan="2">Message­Qualifier</td>
<td>Identifiant unique du message de réponse.</td>
</tr>
<tr class="odd">
<td colspan="3">Request­Message­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td colspan="2">Message­Qualifier</td>
<td>Identifiant de la requête à laquelle on répond.</td>
</tr>
<tr class="even">
<td rowspan="2">Delegator endpoint</td>
<td colspan="3">DelegatorAddress</td>
<td>0:1</td>
<td colspan="2">Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation itself to be stateless.</p></td>
</tr>
<tr class="odd">
<td colspan="3">DelegatorRef</td>
<td>0:1</td>
<td colspan="2">Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="even">
<td>Status</td>
<td colspan="3">Status</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td colspan="2">xsd:boolean</td>
<td>Indique si la requête a pu être traitée avec succès ou non.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">Error­Condition</td>
<td>0:1</td>
<td colspan="2">See below</td>
<td>Signalement d’erreur (voir le paragraphe sur la gestion des erreurs).</td>
</tr>
<tr class="even">
<td></td>
<td>a</td>
<td colspan="2">Capability­Not­Supported­Error</td>
<td>1:1</td>
<td colspan="2">+Error</td>
<td>Requête non supportée.</td>
</tr>
<tr class="odd">
<td></td>
<td>b</td>
<td colspan="2">OtherError</td>
<td colspan="2"></td>
<td>+Error</td>
<td>Autre erreur.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td colspan="2">Description</td>
<td>0:1</td>
<td colspan="2">ErrorDescr­iption­­</td>
<td>Description de l’erreur .</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="3">More­Data</td>
<td>0:1</td>
<td colspan="2">xsd:boolean</td>
<td><p>Whether there are more delivery messages making up this data supply group. Default is false.</p>
<p>Optional SIRI Capability: MultipartDespatch.</p></td>
</tr>
<tr class="even">
<td>Payload</td>
<td colspan="3">Concrete SIRI Service:</td>
<td></td>
<td colspan="2"></td>
<td>Plusieurs des structures suivantes peuvent se succéder, mais elles doivent être toutes du même type.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">a</td>
<td>Production­Timetable­Delivery</td>
<td>0:*</td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Production Timetable.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">b</td>
<td>Estimated­Timetable­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Estimated Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">c</td>
<td>Stop­Timetable­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Stop Timetable.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">d</td>
<td>Stop­Monitoring­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Stop Monitoring.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">e</td>
<td>Vehicle­Monitoring­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Vehicle Monitoring.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">f</td>
<td>Connection­Timetable ­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Connection Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">g</td>
<td>Connection­Monitoring­Feeder­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Connection Monitoring.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">h</td>
<td>Connection­Monitoring­Distributor­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – Connection Monitoring.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">i</td>
<td>General­Message­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 3 – General Message.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">j</td>
<td>FacilityMonitoring­Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 4 – Facility Monitoring. SIRI v1.3</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">k</td>
<td>SituationExchange­ Delivery</td>
<td></td>
<td colspan="2">+Structure</td>
<td>See SIRI Part 5 – Situation Exchange. SIRI v1.3</td>
</tr>
</tbody>
</table>

Structure des réponses aux services

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 2%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 13%" />
<col style="width: 47%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">xxxDelivery</td>
<td></td>
<td>+Structure</td>
<td>Structure générique des réponses aux services</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Response­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure de production de la réponse.</td>
</tr>
<tr class="odd">
<td>Endpoint properties</td>
<td colspan="2">Request­Message­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Référence de la requête.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">SubscriberRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td><p>Identification du souscripteur.</p>
<p>Obligatoire en cas d’abonnement.</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Subscription­Ref</td>
<td>0:1</td>
<td>Subscription­Qualifier</td>
<td><p>Identification de la souscription.</p>
<p>Obligatoire en cas d’abonnement.</p></td>
</tr>
<tr class="even">
<td>Deleg­ation</td>
<td colspan="2">DelegatorAddress</td>
<td>0:1</td>
<td>Xsd:anyURI</td>
<td>Address of original Consumer, i.e. requesting system to which delegating response is to be returned.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="even">
<td>Status</td>
<td colspan="2">Status</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>xsd:boolean</td>
<td>Indique si la requête a pu être traitée avec succès ou non.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">ErrorCondition</td>
<td>0:1</td>
<td>+Structure</td>
<td>Signalement d’erreur (voir le paragraphe sur la gestion des erreurs).</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td>Choix parmi les codes d’erreur</td>
</tr>
<tr class="odd">
<td></td>
<td>a</td>
<td>ServiceNotAvailableError</td>
<td>-1:1</td>
<td></td>
<td>Error : Functional service is not available to use (but it is still capable of giving this response).</td>
</tr>
<tr class="even">
<td rowspan="9"></td>
<td>b</td>
<td>Capability­Not­Supported­Error</td>
<td rowspan="9"></td>
<td>+ Error</td>
<td>Fonction non supportée.</td>
</tr>
<tr class="odd">
<td>c</td>
<td>Access­Not­Allowed­Error</td>
<td>+Error</td>
<td>Accès refusé.</td>
</tr>
<tr class="even">
<td>d</td>
<td>InvalidDataReferencesError</td>
<td>+Error</td>
<td>Error: Request contains references to identifiers that are not known.</td>
</tr>
<tr class="odd">
<td>e</td>
<td>BeyondDataHorizon</td>
<td>+Error</td>
<td>Error: Data period or subscription period is outside of period covered by service.</td>
</tr>
<tr class="even">
<td>f</td>
<td>No­Info­For­Topic­Error</td>
<td>+Error</td>
<td>Pas d’information pour cette requête.</td>
</tr>
<tr class="odd">
<td>g</td>
<td>ParametersIgnoredError</td>
<td>+Error</td>
<td>Error: Request contained parameters that were not supported by the producer. A response has been provided but some parameters have been ignored.</td>
</tr>
<tr class="even">
<td>h</td>
<td>UnknownExtensionsError</td>
<td>+Error</td>
<td>Error: Request contained extensions that were not supported by the producer. A response has been provided but some or all extensions have been ignored.</td>
</tr>
<tr class="odd">
<td>i</td>
<td>Allowed­Resource­Usage­Exceeded­Error</td>
<td>+Error</td>
<td>Réponse trop volumineuse.</td>
</tr>
<tr class="even">
<td>j</td>
<td>OtherError</td>
<td>+Error</td>
<td>Autre erreur.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Description</td>
<td>0:1</td>
<td>Error­Description</td>
<td>Description de l’erreur.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">ValidUntil</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Date de validité maximale de la réponse.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Shortest­Possible­Cycle</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Intervalle minimal de mise à jour de la donnée.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">DefaultLanguage</td>
<td></td>
<td>Xsd:language</td>
<td>Default language for text elements.</td>
</tr>
<tr class="odd">
<td>Pay­load</td>
<td colspan="5">{Content Specific to SIRI Functional Service type. See Part 3.}</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

## Abonnement

Structure générale des abonnements

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 2%" />
<col style="width: 18%" />
<col style="width: 6%" />
<col style="width: 17%" />
<col style="width: 39%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">SubscriptionRequest</td>
<td>+Structure</td>
<td>Structure générale de requêtes d’abonnement</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date de la requête d’abonnement.</td>
</tr>
<tr class="odd">
<td rowspan="2">Auth</td>
<td colspan="2">AccountId</td>
<td>0:1</td>
<td>+Structure</td>
<td>Account Identifier. May be used to attribute requests to a specific user account for authentication or reporting purposes</td>
</tr>
<tr class="even">
<td colspan="2">AccountKey</td>
<td>0:1</td>
<td>+Structure</td>
<td>Authentication key for request. May be used to authenticate the request to ensure the user is a registered client. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td rowspan="7">End­point properties</td>
<td colspan="2">Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse de destination de la réponse à la demande d’abonnement (accepté ou non).</td>
</tr>
<tr class="even">
<td colspan="2">RequestorRef</td>
<td>1:1</td>
<td>Participant­Code</td>
<td>Identifiant du demandeur de la réponse (reprendre le code [<em>fournisseur</em>] des identifiants du profil FR).</td>
</tr>
<tr class="odd">
<td colspan="2">Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identifiant unique de la requête de souscription (utilisé dans la réponse).</td>
</tr>
<tr class="even">
<td colspan="2">DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="odd">
<td colspan="2">DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="even">
<td colspan="2">Consumer­Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination des notifications.</td>
</tr>
<tr class="odd">
<td colspan="2">Subscription­Filter­Identifier</td>
<td>0:1</td>
<td>xsd:NMTOKEN</td>
<td>Identification d’un canal d’abonnement qui permettra de grouper plusieurs requêtes d’abonnement (canal par défaut, non nommé si le champ n’est pas présent).</td>
</tr>
<tr class="even">
<td>Policy</td>
<td colspan="2">Subscription­Context</td>
<td>0:1</td>
<td>+Structure</td>
<td><p>General subscription parameters.</p>
<p>Contexte général d’abonnement défini par le profil et le protocole d’accord (définition par configuration en final).</p></td>
</tr>
<tr class="odd">
<td>Pay­load</td>
<td colspan="2">Concrete service subscription:</td>
<td></td>
<td>choice</td>
<td>Plusieurs des structures suivantes peuvent se succéder, mais elles doivent être toutes du même type.</td>
</tr>
<tr class="even">
<td></td>
<td>a</td>
<td>Production­Timetable­Subscription­Request</td>
<td>–1:*</td>
<td>+Structure</td>
<td>See SIRI Part 3 - Production Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td>b</td>
<td>Estimated­Timetable­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3- Estimated Timetable.</td>
</tr>
<tr class="even">
<td></td>
<td>c</td>
<td>Stop­Timetable­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3 - Stop Timetable.</td>
</tr>
<tr class="odd">
<td></td>
<td>d</td>
<td>Stop­Monitoring­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3 - Stop Monitoring.</td>
</tr>
<tr class="even">
<td></td>
<td>e</td>
<td>Vehicle­Monitoring­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3 - Vehicle Monitoring.</td>
</tr>
<tr class="odd">
<td></td>
<td>f</td>
<td>Connection­Timetable­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3 - Connection Timetable.</td>
</tr>
<tr class="even">
<td></td>
<td>g</td>
<td>Connection­Monitoring­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3 - Connection Monitoring.</td>
</tr>
<tr class="odd">
<td></td>
<td>h</td>
<td>General­Message­Subscription­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 3 – General Message.</td>
</tr>
<tr class="even">
<td></td>
<td>i</td>
<td>FacilityMonitoring­ Subscription­­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 4 - Facility Monitoring. SIRI v1.3</td>
</tr>
<tr class="odd">
<td></td>
<td>j</td>
<td>SituationExchange­ Subscription­­Request</td>
<td></td>
<td>+Structure</td>
<td>See SIRI Part 5 – Situation Exchange. SIRI v1.3</td>
</tr>
</tbody>
</table>

Réponse aux requêtes d’abonnement

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">SubscriptionResponse</td>
<td>+Structure</td>
<td>Réponse à une demande d’abonnement.</td>
</tr>
<tr class="even">
<td>Log</td>
<td>Response­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure de production de la réponse.</td>
</tr>
<tr class="odd">
<td rowspan="3">End­point prop­erties</td>
<td>Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse pour la gestion ultérieure de l’abonnement.</td>
</tr>
<tr class="even">
<td>Responder­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identifiant du système répondant (reprendre le code [<em>fournisseur</em>] des identifiants du profil FR).</td>
</tr>
<tr class="odd">
<td>Request­Message­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identifiant unique du message (de cette réponse).</td>
</tr>
<tr class="even">
<td rowspan="2">Delegation</td>
<td>DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="odd">
<td>DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="even">
<td>Pay­load</td>
<td>Response­Status</td>
<td>1:*</td>
<td>+Structure</td>
<td>Statut de la réponse (en erreur et donc refusée, ou Ok).</td>
</tr>
<tr class="odd">
<td></td>
<td>SubscriptionManagerAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Endpoint address of subscription manager if different from that of the Producer or known default.</td>
</tr>
<tr class="even">
<td></td>
<td>Service­Started­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td><p>Time at which service providing the subscription was last started. Can be used to detect restarts. If absent, unknown.</p>
<p>Dans le cas du profil France, le responsable des abonnements devra les mémoriser et les réactiver automatiquement au redémarrage, ce champ n’est donc pas utile dans le cas classique.</p>
<p>Ce champ sera utilisé dans le cas des échanges avec les concentrateurs pour superviser les connexions d'abonnement.</p></td>
</tr>
<tr class="odd">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

Qualificateur (état) de réponse

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 19%" />
<col style="width: 8%" />
<col style="width: 15%" />
<col style="width: 42%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">Response­Status</td>
<td>+Structure</td>
<td>Qualificateur des réponses.</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Response­Timestamp</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Date de création de ce statut de réponse.</td>
</tr>
<tr class="odd">
<td>End­point</td>
<td colspan="2">Request­Message­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Référence de la requête.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Subscriber­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du souscripteur.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Subscription FilterRef</td>
<td>0:1</td>
<td>SubscriptionFilterRef</td>
<td><p>Référence au filtre utilisé dans l'abonnement et auquel la réponse correspond.</p>
<p>Peut être omis si un seul filtre est associé à l'abonnement.</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Subscription­Ref</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identification de la souscription.</td>
</tr>
<tr class="odd">
<td>Pay­load</td>
<td colspan="2">Status</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>xsd:boolean</td>
<td>Indique si la requête a été traitée normalement ou pas.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Error­Condition</td>
<td>0:1</td>
<td>+Structure</td>
<td>Signalement d’erreur (voir le paragraphe sur la gestion des erreurs).</td>
</tr>
<tr class="odd">
<td></td>
<td>a</td>
<td>Capability­Not­Supported­Error</td>
<td>–1:1</td>
<td>+Error</td>
<td>Fonction non supportée.</td>
</tr>
<tr class="even">
<td></td>
<td>b</td>
<td>AccessNot­AllowedError</td>
<td></td>
<td>+Error</td>
<td>Accès refusé.</td>
</tr>
<tr class="odd">
<td></td>
<td>c</td>
<td>No­Info­For­TopicError</td>
<td></td>
<td>+Error</td>
<td>Pas d’information pour cette requête.</td>
</tr>
<tr class="even">
<td></td>
<td>d</td>
<td>Allowed­Resource­Usage­Exceeded­Error</td>
<td></td>
<td>+Error</td>
<td>Réponse trop volumineuse.</td>
</tr>
<tr class="odd">
<td></td>
<td>e</td>
<td>OtherError</td>
<td></td>
<td>+Error</td>
<td>Autre erreur.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Description</td>
<td>0:1</td>
<td>Error­Description</td>
<td>Description de l’erreur.</td>
</tr>
<tr class="odd">
<td>Info</td>
<td colspan="2">ValidUntil</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Date de validité maximale de la réponse.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Shortest­Possible­Cycle</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Intervalle minimal de mise à jour de la donnée.</td>
</tr>
</tbody>
</table>

Requête de cloture d’abonnement

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 2%" />
<col style="width: 17%" />
<col style="width: 7%" />
<col style="width: 18%" />
<col style="width: 41%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">TerminateSubscriptionRequest</td>
<td>+Structure</td>
<td>Demande de fin d’abonnement</td>
</tr>
<tr class="even">
<td>Endpoint properties</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date de la demande.</td>
</tr>
<tr class="odd">
<td rowspan="2">Auth</td>
<td colspan="2">AccountId</td>
<td>0:1</td>
<td>+Structure</td>
<td>Account Identifier. May be used to attribute requests to a specific user account for authentication or reporting purposes</td>
</tr>
<tr class="even">
<td colspan="2">AccountKey</td>
<td>0:1</td>
<td>+Structure</td>
<td>Authentication key for request. May be used to authenticate the request to ensure the user is a registered client.</td>
</tr>
<tr class="odd">
<td rowspan="3">End­point prop­erties</td>
<td colspan="2">Address</td>
<td>0:1</td>
<td>EndpointAddress</td>
<td>Adresse du souscripteur.</td>
</tr>
<tr class="even">
<td colspan="2">Requestor­Ref</td>
<td>1:1</td>
<td>Participant­Code</td>
<td>Identifiant du souscripteur de la réponse (reprendre le code [fournisseur] des identifiants du profil FR).</td>
</tr>
<tr class="odd">
<td colspan="2">MessageIdentifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identifiant unique du message.</td>
</tr>
<tr class="even">
<td rowspan="2">Delegation</td>
<td colspan="2">DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="odd">
<td colspan="2">DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="even">
<td>Topic</td>
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td>Au choix:</td>
</tr>
<tr class="odd">
<td></td>
<td>a</td>
<td>All</td>
<td>–1:1</td>
<td>EmptyType</td>
<td>Demande de clôture de tous les abonnements.</td>
</tr>
<tr class="even">
<td></td>
<td>b</td>
<td>Subscription­Ref</td>
<td></td>
<td>Subscription­Qualifier</td>
<td>Identifiant de l’abonnement à clôturer.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

Réponse aux demandes de clôture de souscription

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 2%" />
<col style="width: 2%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 12%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="5">TerminateSubscriptionResponse</td>
<td>+Structure</td>
<td>Réponse aux demandes de fin de souscription</td>
</tr>
<tr class="even">
<td rowspan="3">Endpoint properties</td>
<td colspan="3">Response­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Datation de la réponse.</td>
</tr>
<tr class="odd">
<td colspan="3">Responder­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du système répondant.</td>
</tr>
<tr class="even">
<td colspan="3">Request­Message­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identification de la requête.</td>
</tr>
<tr class="odd">
<td>Delegation</td>
<td colspan="3">DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="odd">
<td>Payload</td>
<td colspan="3">Termination­Response­Status</td>
<td>1:*</td>
<td>+Structure</td>
<td>Statut de la demande de clôture d’abonnement.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td colspan="2">Response­Timestamp</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Heure de réponse (pour l’abonnement ci-dessous).</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td colspan="2">Subscriber­Ref</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifiant du souscripteur.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td colspan="2">Subscription­Ref</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant de la souscription.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td colspan="2">Status</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>xsd:boolean</td>
<td>Indique si la souscription a bien pu être clôturée.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td colspan="2">Error­Condition</td>
<td>0:1</td>
<td>+Structure</td>
<td>Signale une éventuelle erreur.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td colspan="2"></td>
<td></td>
<td>choice</td>
<td>Au choix :</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>a</td>
<td>Capability­Not­Supported­Error</td>
<td>–1:1</td>
<td>+Error</td>
<td>Fonction non supportée.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>b</td>
<td>Unknown­Subscriber­Error</td>
<td></td>
<td>+Error</td>
<td>Souscripteur inconnu.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>c</td>
<td>Unknown­Subscription­Error</td>
<td></td>
<td>+Error</td>
<td>Souscription inconnue.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>d</td>
<td>OtherError</td>
<td></td>
<td>+Error</td>
<td>Autre erreur.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td>Description</td>
<td>0:1</td>
<td>Error­Description</td>
<td>Description de l’erreur.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="3">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

Notification de clôture de souscription

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 7%" />
<col style="width: 15%" />
<col style="width: 1%" />
<col style="width: 4%" />
<col style="width: 7%" />
<col style="width: 0%" />
<col style="width: 0%" />
<col style="width: 55%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">SubscriptionTerminatedNotification</td>
<td colspan="2">+Structure</td>
<td colspan="3">Notification permettant au producteur de données de signaller l'interruption d'un ou plusieurs abonnement en cours</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Response­Timestamp</td>
<td colspan="2">1:1</td>
<td colspan="2">xsd:dateTime</td>
<td colspan="2">Heure de production de la réponse.</td>
</tr>
<tr class="odd">
<td rowspan="4">End­point</td>
<td colspan="2">ProducerRef</td>
<td colspan="2">0:1</td>
<td colspan="2">Participant­Code</td>
<td colspan="2">Identifiant du producteur de la réponse (reprendre le code [<em>fournisseur</em>] des identifiants du profil IDF).</td>
</tr>
<tr class="even">
<td colspan="2">Address</td>
<td colspan="2">0:1</td>
<td colspan="3">Endpoint­Address</td>
<td>Address to which any acknowledgment should be sent. Only needed if <em><strong>ConfirmDelivery</strong></em> specified.</td>
</tr>
<tr class="odd">
<td colspan="2">Response­Message­Identifier</td>
<td colspan="2"><p>0:1</p>
<p>1:1</p></td>
<td colspan="3">Message­Qualifier</td>
<td>Identifiant unique du message de réponse.</td>
</tr>
<tr class="even">
<td colspan="2">Request­Message­Ref</td>
<td colspan="2"><p>0:1</p>
<p>1:1</p></td>
<td colspan="3">Message­Qualifier</td>
<td>Identifiant de la requête à laquelle on répond.</td>
</tr>
<tr class="odd">
<td rowspan="2">Delegator</td>
<td colspan="2">DelegatorAddress</td>
<td colspan="2">0:1</td>
<td colspan="2">Endpoint­Address</td>
<td colspan="2"><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation itself to be stateless.</p></td>
</tr>
<tr class="even">
<td colspan="2">DelegatorRef</td>
<td colspan="2">0:1</td>
<td colspan="3">Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="odd">
<td rowspan="3">Sub­scription</td>
<td colspan="2">Subscriber­Ref</td>
<td colspan="2">0:1</td>
<td colspan="2">Participant­Code</td>
<td colspan="2">Identification du souscripteur.</td>
</tr>
<tr class="even">
<td colspan="2">SubscriptionFilterRef</td>
<td colspan="2">0:1</td>
<td colspan="3">SubscriptionFilterRef</td>
<td><p>Référence au filtre utilisé dans l'abonnement et auquel la réponse correspond.</p>
<p>Peut être omis si un seul filtre est associé à l'abonnement.</p></td>
</tr>
<tr class="odd">
<td colspan="2">Subscription­Ref</td>
<td colspan="2">1:1</td>
<td colspan="3">Subscription­Qualifier</td>
<td>Identification de la souscription.</td>
</tr>
<tr class="even">
<td rowspan="3"></td>
<td colspan="2">Error­Condition</td>
<td colspan="2">0:1</td>
<td colspan="2">See below</td>
<td colspan="2">Signalement d’erreur (voir le paragraphe sur la gestion des erreurs).</td>
</tr>
<tr class="odd">
<td rowspan="2">Choice</td>
<td>OtherError</td>
<td colspan="2"></td>
<td colspan="3">+Error</td>
<td>Autre erreur.</td>
</tr>
<tr class="even">
<td>Description</td>
<td colspan="2">0:1</td>
<td colspan="3">Error­Description</td>
<td>Description de l’erreur.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td colspan="2">0:1</td>
<td colspan="2">xsd:any</td>
<td colspan="2">Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

## Vérification de l’état des partenaires (service Check Status)

Requête de vérification d'état

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 17%" />
<col style="width: 7%" />
<col style="width: 17%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">CheckStatusRequest</td>
<td>+Structure</td>
<td>Requête de vérification d’état</td>
</tr>
<tr class="even">
<td>Log</td>
<td>Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Datation de la requête.</td>
</tr>
<tr class="odd">
<td rowspan="2">Auth.</td>
<td>AccountId</td>
<td>0:1</td>
<td>+Structure</td>
<td><p>Account Identifier. May be used to attribute requests to a specific user ACCOUNT for authentication or reporting purposes</p>
<p>Note that an ACCOUNT may be shared between more than one consumer device, for example if used to authenticate an application.</p></td>
</tr>
<tr class="even">
<td>AccountKey</td>
<td>0:1</td>
<td>+Structure</td>
<td>Authentication key for request. May be used to authenticate the request to ensure the user is a registered and approved client.</td>
</tr>
<tr class="odd">
<td>Endpoint</td>
<td>Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Adresse (URL) de destination de la requête.</td>
</tr>
<tr class="even">
<td></td>
<td>RequestorRef</td>
<td>1:1</td>
<td>Participant­Code.</td>
<td>Identifiant du demandeur.</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>MessageIdentifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identifiant de la requête.</td>
</tr>
<tr class="even">
<td rowspan="2">Delegator endpoint</td>
<td>DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="odd">
<td>DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

Réponse aux requêtes de vérification d'état

<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 18%" />
<col style="width: 7%" />
<col style="width: 11%" />
<col style="width: 47%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">CheckStatusResponse</td>
<td>+Structure</td>
<td>Réponses aux requêtes de vérification d’état.</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">Response­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime:</td>
<td>Datation de la réponse.</td>
</tr>
<tr class="odd">
<td rowspan="3">End­point</td>
<td colspan="2">ProducerRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du répondant.</td>
</tr>
<tr class="even">
<td colspan="2">Address</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td>Endpoint Address to which acknowledgements to confirm delivery are to be sent.</td>
</tr>
<tr class="odd">
<td colspan="2">Response­Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Identifiant unique du message de réponse.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">Request­Message­Ref</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>MessageQualifier</td>
<td>Identifiant de la requête à laquelle on répond.</td>
</tr>
<tr class="odd">
<td rowspan="2">Delegator</td>
<td colspan="2">DelegatorAddress</td>
<td>0:1</td>
<td>Endpoint­Address</td>
<td><p>Address of originated system to which delegated response is to be returned.</p>
<p>If request has been proxied by an intermediate aggregating system this provides tracking information relating to the original requestor. This allows the aggregation to be stateless.</p></td>
</tr>
<tr class="even">
<td colspan="2">DelegatorRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td>Identifier of delegating system that originated message.</td>
</tr>
<tr class="odd">
<td>Payload</td>
<td colspan="2">Status</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>xsd boolean</td>
<td>Signale si le système est bien disponible.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">DataReady</td>
<td>0:1</td>
<td>xsd boolean</td>
<td>Whether data delivery is ready to be fetched</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Error­Condition</td>
<td>0:1</td>
<td>+Structure</td>
<td>Signalement d’erreur.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2"></td>
<td></td>
<td>Choice</td>
<td>Au choix :</td>
</tr>
<tr class="odd">
<td></td>
<td>a</td>
<td>Service­Not­Available­Error</td>
<td>–1:1</td>
<td>+Error</td>
<td>Service indisponible.</td>
</tr>
<tr class="even">
<td></td>
<td>c</td>
<td>OtherError</td>
<td></td>
<td>+Error</td>
<td>Autre erreur.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>Description</td>
<td>0:1</td>
<td>Error­Description</td>
<td>Description de l’erreur.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">ValidUntil</td>
<td>0:1</td>
<td>xsd:date­Time:</td>
<td>End of data horizon of the data producer.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Shortest­Possible­Cycle</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Minimum separation between two updates.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">ServiceStarted­Time</td>
<td>0:1</td>
<td>xsd:date­Time:</td>
<td>Dernière date et heure de mise en marche du système.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

1.  Number range aaaNumber range TableNumber range Figure  
      
    <span id="__RefHeading___Toc26889615" class="anchor"></span>Termes
    et définitions

.

<table>
<colgroup>
<col style="width: 23%" />
<col style="width: 76%" />
</colgroup>
<tbody>
<tr class="odd">
<td>APPLICATIF APPLICATION METIER</td>
<td>Ensemble de fonctions métiers associées à l’IHM (Interface Homme Machine).</td>
</tr>
<tr class="even">
<td>AVMS</td>
<td>Automated Vehicle Management System</td>
</tr>
<tr class="odd">
<td>CORBA</td>
<td><em><strong>C</strong>ommon <strong>O</strong>bject <strong>R</strong>equest <strong>B</strong>roker <strong>A</strong>rchitecture</em>- Architecture qui désigne une norme de gestion d'objets distribués. Conçue par l'OMG pour concurrencer le COM de Microsoft, cette architecture rend possible la communication entre plusieurs applications développées dans des langages différents et installées sur des machines différentes.</td>
</tr>
<tr class="even">
<td>DMZ</td>
<td><em><strong>D</strong>e<strong>M</strong>ilitarised <strong>Z</strong>one</em> - Zone tampon d'un réseau d'entreprise, située entre le réseau local et Internet, derrière le coupe-feu, qui correspond à un réseau intermédiaire regroupant des serveurs publics (HTTP, SMTP, FTP, DNS, etc.), et dont le but est d'éviter toute connexion directe avec le réseau interne et de prévenir celui-ci de toute attaque extérieure depuis le Web.</td>
</tr>
<tr class="odd">
<td>EXTRANET</td>
<td>Utilisation de l'Internet dans laquelle une organisation profite du réseau des Réseaux pour interconnecter ses différents constituants.</td>
</tr>
<tr class="even">
<td>FIREWALL</td>
<td>Porte coupe-feu. Système de sécurité anti-intrusion permettant une protection des réseaux informatiques internes de l’entreprise contre les intrusions du monde extérieur, en particulier les piratages informatiques.</td>
</tr>
<tr class="odd">
<td>HEART BEAT</td>
<td>« heartbeat » - battement de cœur – fonction qui permet de s’assurer de l’existence opérationnelle d’un système informatique distant.</td>
</tr>
<tr class="even">
<td>HTML</td>
<td><em><strong>H</strong>yper <strong>T</strong>ext <strong>M</strong>arkup <strong>L</strong>anguage</em> - langage de programmation utilisé pour créer des documents hypertexte.</td>
</tr>
<tr class="odd">
<td>HTTP</td>
<td><em><strong>H</strong>yperText <strong>T</strong>ransfer <strong>P</strong>rotocol</em> - Le protocole technique utilisé sur le *Web pour transférer des fichiers au cours d'une séance entre le serveur et l'utilisateur.</td>
</tr>
<tr class="even">
<td>HTTPS</td>
<td>HyperText Transfer Protocol Secured – Protocole Web sécurisé</td>
</tr>
<tr class="odd">
<td>IPsec</td>
<td>Extensions de sécurité au protocole internet IPv4, requises pour l'IPv6. Un protocole pour le chiffrement et l'authentification au niveau IP (hôte à hôte). SSL sécurise uniquement une socket d'application ; SSH sécurise seulement une session ; PGP sécurise uniquement un fichier spécifique ou un message. IPSec chiffre tout entre deux hôtes.</td>
</tr>
<tr class="even">
<td>INTRANET</td>
<td>Utilisation des techniques et des principes de l’Internet dans un réseau fermé, d’entreprise ou de ville. Un Intranet peut comprendre des contenus réservés à ses membres et d’autres accessibles depuis l’extérieur (voir "Extranet").</td>
</tr>
<tr class="odd">
<td>Mbps</td>
<td>Megabits par seconde - Taux de transfert des <a href="http://www.dicofr.com/cgi-bin/n.pl/dicofr/definition/20010101001410">données</a> qui atteint un million de <a href="http://www.dicofr.com/cgi-bin/n.pl/dicofr/definition/20010101000510">bits</a> par seconde.</td>
</tr>
<tr class="even">
<td>PBS</td>
<td>Personne à Besoin Spécifique</td>
</tr>
<tr class="odd">
<td>PMR</td>
<td>Personne à Mobilité Réduite</td>
</tr>
<tr class="even">
<td>QUAY</td>
<td>Voie d’embarquement</td>
</tr>
<tr class="odd">
<td>RER</td>
<td>Réseau Express Régional. Le RER est un réseau de transport en commun urbain propre à la région parisienne.</td>
</tr>
<tr class="even">
<td>RTC</td>
<td><em><strong>R</strong>éseau <strong>T</strong>éléphonique <strong>C</strong>ommuté</em>. Désigne le réseau téléphonique actuellement en place, utilisant des autocommutateurs pendant l’établissement des communications.</td>
</tr>
<tr class="odd">
<td>RTIG</td>
<td>Normalisation Anglaise, reposant déjà sur TRIDENT pour l'échange de l'information en temps réel.</td>
</tr>
<tr class="even">
<td>SERVEUR</td>
<td>Processus ayant un ou plusieurs threads et qui reçoit des demandes de processus. Il implémente un ensemble de services et les met à la disposition de clients tournant sur le même ordinateur, ou sur divers ordinateurs dans un réseau distribué.</td>
</tr>
<tr class="odd">
<td>SAE</td>
<td>Système d’Aide à l’Exploitation</td>
</tr>
<tr class="even">
<td>SAEIV</td>
<td>Système d'Aide à l'Exploitation et d’Information Voyageurs<br />
pour véhicules de transport en commun</td>
</tr>
<tr class="odd">
<td>SIRI</td>
<td><em><strong>S</strong>ervice <strong>I</strong>nterface for <strong>R</strong>ealtime <strong>I</strong>nformation</em> – norme de diffusion des données temps reel dans le domaine du transport.</td>
</tr>
<tr class="even">
<td>SIV</td>
<td>Système d’Information Voyageurs</td>
</tr>
<tr class="odd">
<td>SMS</td>
<td><em><strong>S</strong>hort <strong>M</strong>essage <strong>S</strong>ystem</em>- Message de 130 caractères au maximum qui transite entre les <a href="http://www.bonweb.com/glo_P.php#650">pagers</a> ou les téléphones portables.</td>
</tr>
<tr class="even">
<td>SOAP</td>
<td><p><em><strong>S</strong>imple <strong>O</strong>bject <strong>A</strong>ccess <strong>P</strong>rotocol -</em> Protocole fondé sur XML pour l'échange d'informations en environnement décentralisé.</p>
<p>Ce protocole qui fait l'objet d'une recommandation de la part du W3C, est couramment utilisé pour établir un canal de communication entre services web (invocation à distance via Internet de traitements informatiques). Il détaille 3 parties :<br />
- l'enveloppe qui dessine les contours du message et en décrit le contenu,<br />
- les règles d'encodage des données et types de données,<br />
- les conventions du protocole d’échange qui permettent de définir les procédures d'invocation et de réponse à distance.<br />
<br />
SOAP peut être utilisé au-dessus de nombreux protocoles de transport dont HTTP.</p></td>
</tr>
<tr class="odd">
<td>SSL</td>
<td><em><strong>S</strong>ecure <strong>S</strong>ocket <strong>L</strong>ayer</em> - Protocole qui permet de chiffrer les données envoyées par un navigateur, développé par Netscape.</td>
</tr>
<tr class="even">
<td>TRANSMODEL</td>
<td>Norme européenne - modélisation conceptuelle de l’ensemble des notions utiles au transport en commun (définition des concepts, des objets et de leurs relations)</td>
</tr>
<tr class="odd">
<td>Travel Angel</td>
<td>Concept de mise à disposition d’une information vers le voyageur à tout moment de la préparation de son voyage, en mobilité et en fin de voyage à travers des suppors tels que le Web, le téléphone mobile, des bornes ou affiches interactives, etc..</td>
</tr>
<tr class="even">
<td>TRIDENT</td>
<td><p><em><strong>TR</strong>ansport <strong>I</strong>ntermodality <strong>D</strong>ata sharing and <strong>E</strong>xchange. <strong>N</strong>e<strong>T</strong>work</em> – Norme européenne d’échanges de données au format XML dans le domaine du transport</p>
<p>Dans le cadre du profil, elle est utilisée essentiellement pour la partie qui concerne l’échange de la description des réseaux, des correspondances et des horaires théoriques.</p></td>
</tr>
<tr class="odd">
<td>UML</td>
<td><em><strong>U</strong>nify <strong>M</strong>odel <strong>L</strong>anguage</em> - Langage d'analyse et de conception orienté objet défini par l'OMG (Object Management Group). UML homogénéise les représentations graphiques des objets issues des travaux de Grady Booch chez Rational Software, de Rumbaugh et d'Ivar Jacobson.</td>
</tr>
<tr class="even">
<td>URL</td>
<td><em><strong>U</strong>niform <strong>R</strong>esource <strong>L</strong>ocation</em> - adresse Internet reconnue par les navigateurs, qui leur permet d’appeler n’importe quelle page ou document.</td>
</tr>
<tr class="odd">
<td>VPN</td>
<td><em><strong>V</strong>irtual <strong>P</strong>rivate <strong>N</strong>etwork</em>. Réseau privé virtuel composé d'ordinateurs qui ne constituent pas un seul et même réseau à la base, mais qui peuvent être distants géographiquement.</td>
</tr>
<tr class="even">
<td>WAP</td>
<td><em><strong>W</strong>ireless <strong>A</strong>pplication <strong>P</strong>rotocol</em>. Norme d'accès à des services Internet sur des téléphones mobiles. Le WAP définit les normes de transmission des données, mais aussi la manière dont les documents doivent être structurés, grâce à un langage dérivé de l'HTML (WML, pour <em>Wireless Markup Language</em>).</td>
</tr>
<tr class="odd">
<td>WEB</td>
<td>"toile d'araignée" composée des pages HTML reliées entre elles par un réseau complexe de liens *hypertexte.</td>
</tr>
<tr class="even">
<td>WIDGET</td>
<td><em><strong>Wi</strong>ndow ga<strong>dget</strong></em>. Elements visuels statiques ou dynamiques qui peuvent être mis sur une fenêtre : onglets, menus, zones textes, etc ..</td>
</tr>
<tr class="odd">
<td>WLAN</td>
<td><em><strong>W</strong>ireless Local <strong>A</strong>rea <strong>N</strong>etwork</em> - Réseau local radioélectrique, version sans fil des réseaux informatiques locaux. Terme plus général utilisé par les acteurs de l'Internet pour tous réseaux sans fil.</td>
</tr>
<tr class="even">
<td>WSDL</td>
<td><p><em><strong>W</strong>eb <strong>S</strong>ervices <strong>D</strong>efinition <strong>L</strong>anguage -</em> WSDL est une tentative de normalisation du W3C suite à une proposition d'IBM, Microsoft et Ariba.</p>
<p>WSDL met en oeuvre XML pour décrire, de manière indépendante de la plate-forme et du langage, la façon dont les applications peuvent accéder à un service web.</p></td>
</tr>
<tr class="odd">
<td>XML</td>
<td><em>e<strong>X</strong>tended <strong>M</strong>arkup <strong>L</strong>anguage</em> - Langage de description des documents qui utilise des balises, permet l'utilisation de balises personnalisées et permet l'échange des données.</td>
</tr>
</tbody>
</table>

2.  <span id="__RefHeading___Toc26889616"
    class="anchor"></span>(informative)Number range aaaNumber range
    TableNumber range Figure  
      
    Service SIRI Situation Exchange

    1.  ## Requête pour l’obtention d’information sur les événements et leurs conséquences (perturbations)

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 2%" />
<col style="width: 9%" />
<col style="width: 5%" />
<col style="width: 11%" />
<col style="width: 63%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">SituationExchangeRequest</td>
<td>+Structure</td>
<td>Request for information about facilities status</td>
</tr>
<tr class="even">
<td>Attrib­utes</td>
<td colspan="2">Version</td>
<td>1:1</td>
<td>Version­String</td>
<td>Version Identifier of Situation Exchange Service, e.g. ‘1.0c’.</td>
</tr>
<tr class="odd">
<td rowspan="2">Message Id</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td rowspan="2">See SIRI Part 2 Common properties of SIRI Functional Service Requests.</td>
</tr>
<tr class="even">
<td colspan="2">Message­Identifier</td>
<td>0:1</td>
<td>Message­Qualifier</td>
</tr>
<tr class="odd">
<td rowspan="16">Topic</td>
<td colspan="2">Preview­Interval</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Forward duration for which Situations should be included, that is, only Situations that start before the end of this window time will be included</td>
</tr>
<tr class="even">
<td colspan="2">StartTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Initial start time for <em><strong>PreviewInterval</strong></em>. If absent, then current time is assumed. Must be within data Horizon.</td>
</tr>
<tr class="odd">
<td colspan="2">VehicleMode</td>
<td>0:1</td>
<td>ModeCode</td>
<td>The Mode for which Situations will be returned. Default is all</td>
</tr>
<tr class="even">
<td colspan="2">SubMode</td>
<td>0:1</td>
<td>ModeCode</td>
<td>The Submode for which Situations will be returned. Default is all</td>
</tr>
<tr class="odd">
<td colspan="2">AccessMode</td>
<td>0:1</td>
<td>enums</td>
<td>The allowed categroies of access to stop place for which Situations will be returned. Default is all</td>
</tr>
<tr class="even">
<td colspan="2">Severity</td>
<td>0:1</td>
<td>enums</td>
<td>Severity filter value to apply: only Situations with a severity greater than or equal to the specified value will be returned. See TPEG severities. Default is all.</td>
</tr>
<tr class="odd">
<td colspan="2">Scope</td>
<td>0:*</td>
<td>enums</td>
<td>Types of SITUATION to include.</td>
</tr>
<tr class="even">
<td colspan="2">Predictability</td>
<td>0:1</td>
<td>planned | unplanned | both</td>
<td>Whether just planned, unplanned or both Situations will be returned.</td>
</tr>
<tr class="odd">
<td colspan="2">Keywords</td>
<td>0:*</td>
<td>string</td>
<td>Any arbitrary filter keywords to use.</td>
</tr>
<tr class="even">
<td colspan="2">Situation­StatusFilter</td>
<td>0:1</td>
<td>+structure</td>
<td></td>
</tr>
<tr class="odd">
<td colspan="2">Situation­NetworkFilter</td>
<td>0:1</td>
<td>+structure</td>
<td>Filter the results to include only Situations relating to the network filter elements</td>
</tr>
<tr class="even">
<td colspan="2">Situation­StopPlace­Filter</td>
<td>0:1</td>
<td>structure</td>
<td>Filter the results to include only Situations for the given stop place filter elements..</td>
</tr>
<tr class="odd">
<td colspan="2">Situation­JourneyFilter</td>
<td>0:1</td>
<td>+structure</td>
<td>Filter the results to include only Situations relating to the given Vehicle Journey filter elements.</td>
</tr>
<tr class="even">
<td colspan="2">Situation­PlaceFilter</td>
<td>0:1</td>
<td>+structure</td>
<td>Filter the results to include only Situations relating to the given Place filter elements.</td>
</tr>
<tr class="odd">
<td colspan="2">Situation­RoadFilter</td>
<td>0:1</td>
<td>+structure</td>
<td>Filter the results to include only Situations relating to the given Road filter elements.</td>
</tr>
<tr class="even">
<td colspan="2">AccessibilityNeed­Filter</td>
<td>0:*</td>
<td>User</td>
<td>Filter the results to include only Situations marked as affecting these needs</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>UserNeed</td>
<td>0:1</td>
<td>UserNeed</td>
<td>Filter the results to include only Situations marked as affecting this User need. User Need can include exclude/include flag.</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>AccompaniedByCarer</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the passenger is accompanied by a carer or assistant.</td>
</tr>
<tr class="odd">
<td rowspan="3">Request Policy</td>
<td colspan="2">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td><p>Preferred language in which to return text values.</p>
<p>Optional SIRI capability: <em>National­Language.</em></p></td>
</tr>
<tr class="even">
<td colspan="2">IncludeTranslations</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether additional transaltions of text names are to be included in elements. If false, then only one element should be returned. Defaukt is false.</p>
<p>Where multiple values are returned The first element returned ill be used as the defaukt value</p></td>
</tr>
<tr class="odd">
<td colspan="2">Maximum­NumberOf­Situations</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>The maximum number of <em><strong>SituationElements</strong></em> to includes in a given delivery. The n most recent Events within the look ahead window are included.</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 11%" />
<col style="width: 5%" />
<col style="width: 11%" />
<col style="width: 63%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">SituationStatusFilter</td>
<td>+Structure</td>
<td>Filter values for Network elements</td>
</tr>
<tr class="even">
<td rowspan="3">Filter</td>
<td>Verification</td>
<td>0:1</td>
<td>verified | unverified | unknown</td>
<td>Whether incident has been verified or not. If not specified return all.</td>
</tr>
<tr class="odd">
<td>Progress</td>
<td>0:*</td>
<td>Closed | closing | open | published</td>
<td>ProgressStatus. One of a specified set of overall processing states assigned to situation. For example, 'Draft' for not yet published; 'Published' for live situations; 'Closed' indicates a completed situation. If not specified return open, published closing and closed. l</td>
</tr>
<tr class="even">
<td>Reality</td>
<td>0:1</td>
<td>Real | test | security<br />
Exercise | technicalExercise</td>
<td>Whether situation is real or a test. If not specified return all</td>
</tr>
</tbody>
</table>

|                        |                     |      |                       |                                                                                                  |
| ---------------------- | ------------------- | ---- | --------------------- | ------------------------------------------------------------------------------------------------ |
| SituationNetworkFilter |                     |      | +Structure            | Filter values for Network elements                                                               |
| Filter                 | OperatorRef         | 0:1  | Operator­Code        | Filter the results to include only Situations relating to the Operator.                          |
|                        | Operational­UnitRef | 0:\* | OperationalUnit­Code | Filter the results to include only Situations relating to the Opera Operational torational Unit. |
|                        | NetworkRef          | 0:1  | Network­Code         | Filter the results to include only Situations relating to the Operational Unit.                  |
|                        | LineRef             | 0:\* | LineCode             | Filter the results to include only Situations for the given line.                                |
|                        | StopPointRef        | 0:1  | StopPoint­Code       | Filter the results to include only Situations relating to the Stop Point or Stop Area.           |
|                        | Connection­LinkRef  | 0:\* | Connection-LinkCode  | Filter the results to include only Situations relating to the given Connection Link              |
|                        | FacilityRef         | 0:\* | FacilityCode         | Filter the results to include only Situations relating to the given referenced Facility.         |

|                          |              |     |                |                                                                          |
| ------------------------ | ------------ | --- | -------------- | ------------------------------------------------------------------------ |
| SituationStopPlaceFilter |              |     | +Structure     | Filter values for Network elements                                       |
| Filter                   | StopPlaceRef | 0:1 | StopPlaceCode | Filter the results to include only Situations relating to the StopPlace. |

|                        |                    |     |                      |                                                                                      |
| ---------------------- | ------------------ | --- | -------------------- | ------------------------------------------------------------------------------------ |
| SituationJourneyFilter |                    |     | +Structure           | Filter values for Journey elements                                                   |
| Filter                 | Vehicle­JourneyRef | 0:1 | Vehicle-JourneyCode | Filter the results to include only Situations relating to the given Vehicle Journey. |
|                        | Interchange­Ref    | 0:1 | Interchange­­Code   | Filter the results to include only Situations relating to the given Interchange.     |
|                        | Vehicle­Ref        | 0:1 | Vehicle­Code        | Filter the results to include only Situations relating to the given Vehicle          |

## Abonnement pour l’obtention d’information sur les événements et leurs conséquences (perturbations)

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 13%" />
<col style="width: 57%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">Situation ExchangeMonitoring­SubscriptionRequest</td>
<td>+Structure</td>
<td>Request for a subscription to the Vehicle Monitoring Service.</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td>SubscriberRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td rowspan="3">See SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.</td>
</tr>
<tr class="odd">
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>SituationExchange­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>See SituationExchangeRequest.</td>
</tr>
<tr class="even">
<td>Policy</td>
<td>Incremental­Updates</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the producer should only provide updates to the last data returned, i.e. additions, modifications and deletions, or always return the complete set of current data, Default is true, i.e. once the initial transmission has been made, return only incremental updates.</p>
<p>If <em>false</em> each subscription response will contain the full information as specified in this request.</p>
<p>Optional SIRI capability: <em>IncrementalUpdates.</em></p></td>
</tr>
</tbody>
</table>

## Réponse aux demandes d’information sur les événements et leurs conséquences (perturbations)

|                           |                     |      |               |                                                                       |
| ------------------------- | ------------------- | ---- | ------------- | --------------------------------------------------------------------- |
| SituationExchangeDelivery |                     |      | +Structure    | Describes the status of facilities.                                   |
| Attributes                | version             | 1:1  | VersionString | Version Identifier of Situation Exchange Service. Fixed, e.g. ‘1.1a’. |
| LEADER                    | :::                 | 1:1  | xxx­Delivery  | See SIRI Part 2-7.2.1.1 xxx***Delivery**.*                            |
| Payload                   | PtSituation­Context | 0:1  | +Structure    | Describes values that are common to all situations in the delivery    |
|                           | Situations          | 0:\* | +Structure    | Describes a Situation                                                 |
| any                       | Extensions          | 0:1  | any           | Placeholder for user extensions.                                      |

## Description de l’événement (cause de la perturbation)

<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 2%" />
<col style="width: 0%" />
<col style="width: 14%" />
<col style="width: 5%" />
<col style="width: 13%" />
<col style="width: 52%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="5">PtSituationElement</td>
<td>+Structure</td>
<td>Disruption affecting services.</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="3">CreationTime</td>
<td>1:1</td>
<td>dateTime</td>
<td>Time of creation of Situation</td>
</tr>
<tr class="odd">
<td rowspan="6">Identity</td>
<td colspan="3">CountryRef</td>
<td>0:1</td>
<td>CountryCode</td>
<td>Country code of Participant</td>
</tr>
<tr class="even">
<td colspan="3">ParticipantRef</td>
<td>1:1</td>
<td>Participan­t­Code</td>
<td>Identifier of participant system that creates Situation. See Part 2. Unique within Country</td>
</tr>
<tr class="odd">
<td colspan="3">SituationNumber</td>
<td>1:1</td>
<td>Situation­Number</td>
<td>Unique Identifier of Situation within Participant</td>
</tr>
<tr class="even">
<td colspan="3">UpdateCountry­Ref</td>
<td>0:1</td>
<td>CountryCode</td>
<td>Country code of Participant that creates Update if different from <em><strong>CountryRef</strong></em>.</td>
</tr>
<tr class="odd">
<td colspan="3">Update­Participant­Ref</td>
<td>0:1</td>
<td>Participan­t­Code</td>
<td>Identifier of participant system that creates Update if different from <em><strong>ParticipantRef</strong></em>. See Part 2.</td>
</tr>
<tr class="even">
<td colspan="3">Version</td>
<td>0:1</td>
<td>Version</td>
<td>Version of Update Situation element</td>
</tr>
<tr class="odd">
<td rowspan="2">Xref</td>
<td colspan="3">References</td>
<td>0:1</td>
<td>many</td>
<td>Associations with other Situations.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="2">RelatedToRef</td>
<td>0:*</td>
<td>+Related­Situation</td>
<td>A reference to another Situation with an indication of the nature of the association, e.g. a cause, a result.</td>
</tr>
<tr class="odd">
<td>Source</td>
<td colspan="3">Source</td>
<td>1:1</td>
<td>+Structure</td>
<td>Information about source of information, that is, where the agent using the capture client obtained an item of information, or in the case of an automated feed, an identifier of the specific feed. Can be used to obtain updates, verify details or otherwise assess relevance. See below.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">VersionedAtTime</td>
<td>0:1</td>
<td>Xsd:dateTime</td>
<td>Time at which SITUATION element was versioned. Once versioned, no further changes can be made (on this version…).</td>
</tr>
<tr class="odd">
<td rowspan="5">Status</td>
<td colspan="3">Verification</td>
<td>0:1</td>
<td>enum</td>
<td>Whether the situation has been verified.</td>
</tr>
<tr class="even">
<td colspan="3">Progress</td>
<td>0:1</td>
<td>enum</td>
<td>Status of Situation. See below.</td>
</tr>
<tr class="odd">
<td colspan="3">QualityIndex</td>
<td>0:1</td>
<td>enum</td>
<td>Assessment of likely correctness of data.</td>
</tr>
<tr class="even">
<td colspan="3">Reality</td>
<td>0:1</td>
<td>enum</td>
<td>Whether situation is real or a test.</td>
</tr>
<tr class="odd">
<td colspan="3">Likelihood</td>
<td>0:1</td>
<td>enum</td>
<td>Likelihood to ascribe to a future situation.</td>
</tr>
<tr class="even">
<td></td>
<td colspan="3">Publication</td>
<td>0:1</td>
<td>enum</td>
<td>Publishing status is one of a specified set of substates to which a SITUATION can be assigned.</td>
</tr>
<tr class="odd">
<td rowspan="8">Temporal Group</td>
<td colspan="3">ValidityPeriod</td>
<td>0:*</td>
<td>range</td>
<td>On or more Overall inclusive Period of applicability of situation</td>
</tr>
<tr class="even">
<td colspan="2"></td>
<td>StartTime</td>
<td>0:1</td>
<td>dateTime</td>
<td>The (inclusive) start time stamp.</td>
</tr>
<tr class="odd">
<td colspan="2"></td>
<td>EndTime</td>
<td>0:1</td>
<td>dateTime</td>
<td>The (inclusive) end time stamp. If omitted, the range end is open-ended, that is, it should be interpreted as "forever".</td>
</tr>
<tr class="even">
<td colspan="3">Repetitions</td>
<td>0:*</td>
<td>DayType</td>
<td>Situation applies only on the repeated day types within the overall validity period(s). For example Sunday.</td>
</tr>
<tr class="odd">
<td colspan="2"></td>
<td>DayType</td>
<td>1:1</td>
<td>enum</td>
<td>Tpeg DayType pti 34</td>
</tr>
<tr class="even">
<td colspan="3">Publication­Window</td>
<td>0:1</td>
<td>range</td>
<td>Publication Window for situation if different from validity period. Period during which audience is informed of situation may start before or after situation</td>
</tr>
<tr class="odd">
<td colspan="2"></td>
<td>StartTime</td>
<td>0:1</td>
<td>dateTime</td>
<td>The (inclusive) start time stamp.</td>
</tr>
<tr class="even">
<td colspan="2"></td>
<td>EndTime</td>
<td>0:1</td>
<td>dateTime</td>
<td>The (inclusive) end time stamp. If omitted, the range end is open-ended, that is, it should be interpreted as "forever".</td>
</tr>
<tr class="odd">
<td rowspan="12">Class­ifier Group</td>
<td colspan="3">Reason</td>
<td></td>
<td>enum</td>
<td>Nature of Situation – TPEG Reason Code See below.</td>
</tr>
<tr class="even">
<td colspan="3">PublicEventReason</td>
<td>0:1</td>
<td>enum</td>
<td>Subclassification of Classifier of Public Event. Situation. See below.</td>
</tr>
<tr class="odd">
<td colspan="3">ReasonName</td>
<td>0:1</td>
<td>string</td>
<td>Text explanation of situation reason. Not normally needed.</td>
</tr>
<tr class="even">
<td colspan="3">Severity</td>
<td>0:1</td>
<td>enum</td>
<td>Severity of Situation. Corresponds to TPEG Pti26 severities. Default is normal.</td>
</tr>
<tr class="odd">
<td colspan="3">Priority</td>
<td>0:1</td>
<td>enum</td>
<td><p>Arbitrary rating of priority of message if different from severity 1-High.</p>
<p>Note this can be used for Datex2 <em><strong>Urgency</strong></em> levels</p>
<p>1=extremelyUrgent</p>
<p>2= urgent</p>
<p>3= normal</p></td>
</tr>
<tr class="even">
<td colspan="3">Sensitivity</td>
<td>0:1</td>
<td>enum</td>
<td>Confidentiality of situation.</td>
</tr>
<tr class="odd">
<td colspan="3">Audience</td>
<td>0:1</td>
<td>enum</td>
<td>Intended audience of situation.</td>
</tr>
<tr class="even">
<td colspan="3">ReportType</td>
<td>0:1</td>
<td>enum</td>
<td>Report type of situation Corresponds to TPEG Pti27.</td>
</tr>
<tr class="odd">
<td colspan="3">ScopeType</td>
<td>0:1</td>
<td>enum</td>
<td>Scope type of situation. See below.</td>
</tr>
<tr class="even">
<td colspan="3">Planned</td>
<td>0:1</td>
<td>boolean</td>
<td>Whether the situation was planned (e.g. engineering works) or unplanned (e.g. service alteration). Default is false, i.e. unplanned.</td>
</tr>
<tr class="odd">
<td colspan="3">Keywords</td>
<td>0:*</td>
<td>string</td>
<td>Arbitrary application specific classifiers.</td>
</tr>
<tr class="even">
<td colspan="3">SecondaryReasons</td>
<td>0:1</td>
<td>reasons</td>
<td>Set of additional reasons.</td>
</tr>
<tr class="odd">
<td rowspan="8">Description Group</td>
<td colspan="3">Language</td>
<td>0:1</td>
<td>lang</td>
<td>Default Language of descriptions</td>
</tr>
<tr class="even">
<td colspan="3">Summary</td>
<td>0:*</td>
<td>DefaultedText</td>
<td>Summary of situation. If absent should be generated from structure elements / and or by condensing Description. For use of defaulted text see below.</td>
</tr>
<tr class="odd">
<td colspan="3">Description</td>
<td>0:*</td>
<td>DefaultedText</td>
<td>Description of situation. Should not repeat any strap line included in Summary See below.</td>
</tr>
<tr class="even">
<td colspan="3">Detail</td>
<td>0:*</td>
<td>DefaultedText</td>
<td>Additional descriptive details about the situation. For use of defaulted text see below.</td>
</tr>
<tr class="odd">
<td colspan="3">Advice</td>
<td>0:*</td>
<td>DefaultedText</td>
<td>Further advice to passengers. For use of defaulted text see below.</td>
</tr>
<tr class="even">
<td colspan="3">Internal</td>
<td>0:1</td>
<td>DefaultedText</td>
<td>Further advice to passengers. For use of defaulted text see below.</td>
</tr>
<tr class="odd">
<td colspan="3">Image</td>
<td>0:*</td>
<td>Image</td>
<td>Image for description. See below.</td>
</tr>
<tr class="even">
<td colspan="3">InfoLink</td>
<td>0:*</td>
<td>InfoLink</td>
<td>Further web links. See below.</td>
</tr>
<tr class="odd">
<td>Scope</td>
<td colspan="3">AffectsScope</td>
<td>0:1</td>
<td>+Structure</td>
<td>Scope model identifying parts of transport network affected by situation. See below.</td>
</tr>
<tr class="even">
<td rowspan="2">Consequence</td>
<td colspan="3">Consequences</td>
<td>0:1</td>
<td>many</td>
<td>One or more consequences.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Consequence</td>
<td>0:*</td>
<td>+Structure</td>
<td>Consequence of the situation. See below.</td>
</tr>
<tr class="even">
<td rowspan="2">Actions</td>
<td colspan="3">PublishingActions</td>
<td>0:1</td>
<td>many</td>
<td>One or more publishing actions.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">PublishingAction</td>
<td>0:*</td>
<td>+Structure</td>
<td>Distribution actions to disseminate situation. See below.</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="3">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

## Description de la source d’information ayant fourni la description de la perturbation

|                 |                     |     |                  |                                                                                                                               |
| --------------- | ------------------- | --- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| SituationSource |                     |     | +Structure       | Where the information about the Situation came from.                                                                          |
|                 | Country             | 0:1 | enum             | Country of origin of source element. IANA code                                                                                |
|                 | SourceType          | 1:1 | enum             | Nature of Source communication type. See below.                                                                               |
|                 | SourceMethodType    | 0:1 | enum             | How the source obtained the information. See below.                                                                           |
|                 | Phone               | 0:1 | email            | Email of Supplier of information.                                                                                             |
|                 | Fax                 | 0:1 | phoneNumber      | Fax number of Supplier of information.                                                                                        |
|                 | Web                 | 0:1 | anyURL           | Fax number of Supplier of information.                                                                                        |
|                 | Email               | 0:1 | EmailAddressType | Email of Supplier of information.                                                                                             |
|                 | Other               | 0:1 | string           | Other information about source                                                                                                |
|                 | AgentReference      | 0:1 | string           | Reference to an Agent, i.e. Capture client user who input an SITUATION. Available for use in intranet exchange of SITUATIONs. |
|                 | Name                | 0:1 | string           | Name of source.                                                                                                               |
|                 | TimeOfCommunication | 0:1 | dateTime         | Time of communication of message, if different from creation time.                                                            |
|                 | ExternalCode        | 0:1 | string           | External system reference to situation.                                                                                       |
|                 | SourceFile          | 0:1 | anyURL           | External system reference to situation.                                                                                       |
|                 | Extension           | 0:1 | any              | Placeholder for user extensions.                                                                                              |

## SourceType

|              |                               |
| ------------ | ----------------------------- |
| SIRI-SX      | Description                   |
| directReport | Report came in person         |
| email        | Report came by email person   |
| phone        | Report came by phone          |
| fax          | Report came by fax            |
| post         | Report came by post           |
| feed         | Report came by automated feed |
| radio        | Report came from radio        |
| tv           | Report came from tv           |
| web          | Report came from web site     |
| pager        | Report came by pager          |
| text         | Report came by text message   |
| other        | Report came by other means    |

## SourceMethodType

|                                   |                                                           |                                   |
| --------------------------------- | --------------------------------------------------------- | --------------------------------- |
| SIRI-SX                           | Description                                               | Datex2 Source Type                |
| automobileClubPatrol              | Source was an Automobile Club Patrol Source was           | automobileClubPatrol              |
| cameraObservation                 | Source was a Camera Observation                           | cameraObservation                 |
| freightVehicleOperator            | Source was a Freight Vehicle Operator                     | freightVehicleOperator            |
| inductionLoopMonitoringStation    | Source was an Induction Loop Monitoring Station           | inductionLoopMonitoringStation    |
| microwavedMonitoringStation       | Source was a Microwaved Monitoring Station                | microwavedMonitoringStation       |
| mobileTelephoneCaller             | Source was a Mobile Telephone Caller                      | mobileTelephoneCaller             |
| nonPoliceEmergencyServices­Patrol | Source was a Non Police Emergency Services Patrol         | nonPoliceEmergencyServices­Patrol |
| otherInformation                  | Source was Other                                          | otherInformation                  |
| otherOfficialVehicle              | Source was an Official Vehicle other than a police patrol | otherOfficialVehicle              |
| policePatrol                      | Source was a Police Patrol                                | policePatrol                      |
| privateBreakdownService           | Source was a Private Breakdown Service                    | privateBreakdownService           |
| publicAndPrivateUtilities         | Source was a Public And Private Utility                   | publicAndPrivateUtilities         |
| registeredMobileObserver          | Source was a Registered Mobile Observer                   | registeredMobileObserver          |
| roadAuthorities                   | Source was a Road Authority                               | roadAuthorities                   |
| roadOperatorPatrol                | Source was a Road Operator Patrol                         | roadOperatorPatrol                |
| roadsideTelephoneCaller           | Roadside Telephone Caller                                 | roadsideTelephoneCaller           |
| spotterAircraft                   | Source was a Spotter Aircraft                             | spotterAircraft                   |
| trafficMonitoringStation          | Source was a Traffic Monitoring Station                   | trafficMonitoringStation          |
| transitOperator                   | Source was a Transit Operator                             | transitOperator                   |
| vehicleProbeMeasurement           | Source was a Vehicle Probe Measurement                    | vehicleProbeMeasurement           |
| videoProcessingMonitoring­Station | Source was a Video Processing Monitoring Station          | videoProcessingMonitoring­Station |

## Verification

|                     |                                            |            |
| ------------------- | ------------------------------------------ | ---------- |
| SIRI-SX             | Description                                | TPEG Pti32 |
| unknown             | Status is unknown                          | pti32_0    |
| unverified          | Situation is not verified                  | pti32_1    |
| verified            | Situation has been verified                | pti32_255  |
| verifiedAsDuplicate | Situation has been verified as a duplicate | v          |

## Progress

|                 |                                        |     |
| --------------- | -------------------------------------- | --- |
| SIRI-SX         | Description                            |     |
| draft           | Content is being drafted               |     |
| pendingApproval | Content is pending approval            |     |
| approvedDraft   | Content is approved                    |     |
| open            | Situation is open                      |     |
| published       | Situation is open and published        |     |
| closing         | Situation is in the process of closing |     |
| closed          | Situation is closed                    |     |

## QualityIndex

|                  |                                |                         |
| ---------------- | ------------------------------ | ----------------------- |
| SIRI-SX          | Description                    | ProbabilityOfOccurrence |
| certain          | Information is certain         |                         |
| veryReliable     | Certainty is                   | veryReliable            |
| reliable         | Certainty is Reliable          | reliable                |
| probablyReliable | Certainty is Probably Reliable | probable                |
| improbable       | Not confirmed                  | unconfirmed             |

## Reality

|                   |                                              |                          |
| ----------------- | -------------------------------------------- | ------------------------ |
| SIRI-SX           | Description                                  | Datex2 InformationStatus |
| real              | Situation is real                            | real                     |
| securityExercise  | Situation is a real-world security exercise  | securityExercise         |
| technicalExercise | Situation is a real-world technical exercise | technicalExercise        |
| test              | Situation is not real                        | test                     |
| unconfirmed       | Uncertain                                    | unconfirmed              |

## Likelihood

|            |                                 |                                |
| ---------- | ------------------------------- | ------------------------------ |
| SIRI-SX    | Description                     | Datex2 ProbabilityOfOccurrence |
| certain    | Event is will definitely happen | certain                        |
| probable   | Event is likely is very likely  | probable                       |
| riskOf     | Risk of event happening         | riskOf                         |
| improbable | Uncertain                       | improbable                     |

## DayType 

|                          |        |                           |
| ------------------------ | ------ | ------------------------- |
| SIRI-SX                  | Pti34  | TPEG                      |
| unknown                  | 34_0   | Unknown                   |
| monday                   | 34_1   | Monday                    |
| tuesday                  | 34_2   | Tuesday                   |
| wednesday                | 34_3   | Wednesday                 |
| thursday                 | 34_4   | Thursday                  |
| friday                   | 34_5   | Friday                    |
| saturday                 | 34_6   | Saturday                  |
| sunday                   | 34_7   | Sunday                    |
| weekdays                 | 34_8   | Weekdays                  |
| weekends                 | 34_9   | Weekends                  |
| holiday                  | 34_10  | Holiday                   |
| publicHoliday            | 34_11  | Public Holiday            |
| religiousHoliday         | 34_12  | Religious Holiday         |
| federalHoliday           | 34_13  | Federal Holiday           |
| regionalHoliday          | 34_14  | Regional Holiday          |
| nationalHoliday          | 34_15  | National Holiday          |
| mondayToFriday           | 34_16  | Monday To Friday          |
| mondayToSaturday         | 34_17  | Monday To Saturday        |
| sundaysAndPublicHolidays | 34_18  | Sundays & Public Holidays |
| schoolDays               | 34_19  | School Days               |
| everyDay                 | 34_20  | Every Day                 |
| undefinedDayType         | 34_255 | Undefined DayType         |

## Severity 

|            |             |            |                      |
| ---------- | ----------- | ---------- | -------------------- |
| SIRI-SX    | Description | TPEG Pti26 | Datex2.OverallImpact |
| unknown    | unknown     | 0          |                      |
| verySlight | very slight | 1          | lowest               |
| slight     | slight      | 2          | low                  |
| normal     | normal      | 3          | normal               |
| severe     | severe      | 4          | high                 |
| verySevere | very severe | 5          | highest              |
| noImpact   | no impact   | 6          |                      |
| undefined  | undefined   | 255        |                      |

## Audience 

| SIRI-SX            | Description                                                       | Datex2 Confidentiality                                |
| ------------------ | ----------------------------------------------------------------- | ----------------------------------------------------- |
| public             | Of interest to public.                                            | noRestriction                                         |
| emergencyServices  | Primarily of interest for emergency services.                     |                                                       |
| staff              | Primarily of interest for operator staff.                         | internalUse                                           |
| stationStaff       | Primarily of interest for station staff.                          |                                                       |
| management         | Primarily of interest for operator management.                    |                                                       |
| authorities        | Transport Authorities                                             | restrictedToAuthorities                               |
| infoServices       | Transport and Traffic operators and information service providers | restrictedToAuthoritiesTrafficOperators andPublishers |
| transportOperators | Transport and Traffic operators                                   | restrictedToAuthoritiesAndTrafficOperators            |

## Sensitivity 

|          |                                        |
| -------- | -------------------------------------- |
| SIRI-SX  | Description                            |
| veryHigh | Situation is very sensitive            |
| high     | Situation is sensitive                 |
| medium   | Situation is of average sensitiveness  |
| low      | Situation is not very sensitive        |
| veryLow  | Situation is not of a sensitive nature |

## ReportType 

|                   |                                          |        |
| ----------------- | ---------------------------------------- | ------ |
| SIRI-SX           | Description                              | Pti27  |
| unknown           | predictable                              | 27_1   |
| route             | Situation concerns a route               | 27_2   |
| network           | Situation concerns a route               | 27_3   |
| point             | Situation concerns a point               | 27_4   |
| individualService | Situation concerns an individual service | 27_255 |
| undefined         |                                          | 27_1   |

## ScopeType 

|                     |                                                            |
| ------------------- | ---------------------------------------------------------- |
| SIRI-SX             | Description                                                |
| general             | Situation has a general scope                              |
| operator            | Situation scope is a specific OPERATOR                     |
| network             | Situation scope is whole network                           |
| route               | Situation scope is a specific route                        |
| line                | Situation scope is a specific LINE                         |
| place               | Situation scope is a specific PLACE                        |
| StopPlace           | Situation scope is a specific STOP PLACE                   |
| stopPlaceComponent  | Situation scope is a specific STOP PLACE COMPONENT         |
| stopPoint           | Situation scope is a specific STOP POINT                   |
| vehicleJourney      | Situation scope is a specific VEHICLE JOURNEY              |
| datedVehicleJourney | Situation scope is a specific DATED VEHICLE JOURNEY        |
| connectionLink      | Situation scope is a specific CONNECTION LINK              |
| interchange         | Situation scope is a specific Interchange between journeys |

## Reason 

| SIRI-SX             | TPEG                       | Pti18 | Further Details | Datex2 CauseType                                                                                        |
| ------------------- | -------------------------- | ----- | --------------- | ------------------------------------------------------------------------------------------------------- |
| UnknownReason       | unknown                    | 0     |                 |                                                                                                         |
| MiscellaneousReason | miscellaneous event reason | 1     | Pti 19          | accident, congestion, vandalism, obstruction, roadsideEvent, problemsAtBorderPost, problemsAtCustomPost |
| PersonnelReason     | personnel event reason     | 2     | Pti 20          |                                                                                                         |
| EquipmentReason     | equipment event reason     | 3     | Pti 21          | equipmentFailure                                                                                        |
| EnvironmentReason   | environment event reason   | 4     | Pti 22          | poorWeather, InfrastructureFailure                                                                      |
| UndefinedReason     | undefined event reason     | 255   |                 |                                                                                                         |

## MiscellaneousReason 

| Group          | SIRI-SX                 | Pti19 | TPEG                      | Datex2 CauseType       | Datex2 Disturbance Activity |
| -------------- | ----------------------- | ----- | ------------------------- | ---------------------- | --------------------------- |
| Miscell­aneous | unknown                 | 0     | unknown                   |                        |                             |
|                | incident                | 1     | incident                  |                        |                             |
|                | bombExplosion           | 2     | bomb explosion            | terrorism              | explosion                   |
|                | securityAlert           | 3     | security alert            | securityIncident       | securityAlert               |
|                | fire                    | 4     | fire                      |                        |                             |
|                | vandalism               | 5     | vandalism                 | vandalism              | asset­Destruction           |
|                | accident                | 6     | accident                  | accident               |                             |
|                | overcrowded             | 7     | overcrowded               |                        | crowd                       |
|                | insufficientDemand      | 8     | insufficient demand       |                        |                             |
|                | lightingFailure         | 9     | lighting failure          |                        |                             |
|                | leaderBoardFailure      | 10    | leader board failure      |                        |                             |
|                | serviceIndicatorFailure | 11    | service indicator failure |                        |                             |
|                | serviceFailure          | 12    | service failure           |                        |                             |
|                | operatorCeasedTrading   | 13    | operator ceased trading   |                        |                             |
|                | operatorSuspended       | 14    | operator suspended        |                        |                             |
|                | congestion              | 15    | congestion                | congestion             |                             |
|                | routeBlockage           | 16    | route blockage            | obstruction            |                             |
|                | personOnTheLine         | 17    | person on the line        |                        |                             |
|                | vehicleOnTheLine        | 18    | vehicle on the line       |                        |                             |
|                | objectOnTheLine         | 19    | object on the line        |                        |                             |
|                | animalOnTheLine         | 20    | animal on the line        |                        |                             |
|                | routeDiversion          | 21    | route diversion           |                        |                             |
|                | roadClosed              | 22    | road closed               |                        |                             |
|                | roadworks               | 23    | roadworks                 |                        |                             |
|                | specialEvent            | 24    | special event             | roadsideEvent          |                             |
|                | bridgeStrike            | 25    | bridge strike             |                        |                             |
|                | overheadObstruction     | 26    | overhead obstruction      |                        |                             |
|                | undefinedProblem        | 255   | undefined problem         | infrastructure­Problem | other                       |

## Miscellaneous subreasons 

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 22%" />
<col style="width: 7%" />
<col style="width: 13%" />
<col style="width: 21%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>SIRI-SX</th>
<th>---</th>
<th>Subclass of TPEG</th>
<th>Datex2 CauseType</th>
<th>Datex2 Disturbance Activity</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Miscell­aneous</td>
<td>previous disturbances</td>
<td>0_1</td>
<td>unknown</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td rowspan="6">TrainSafety Subreason</td>
<td>safetyViolation</td>
<td>1_1</td>
<td>incident</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>nearMiss</td>
<td>1_2</td>
<td>incident</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>signalPassedAtDanger</td>
<td>1_3</td>
<td>incident</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>stationOverrun</td>
<td>1_4</td>
<td>incident</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>trainDoor</td>
<td>1_5</td>
<td>incident</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>emergencyServicesCall</td>
<td>1_6</td>
<td>incident</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td rowspan="17">SecuritySub­Reason</td>
<td>policeRequest</td>
<td>3_1</td>
<td>security alert</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>fireBrigadeSafetyChecks</td>
<td>3_2</td>
<td>security alert</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>unattendedBag</td>
<td>3_3</td>
<td>security alert</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>telephonedThreat</td>
<td>3_4</td>
<td>security alert</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>suspectVehicle</td>
<td>3_5</td>
<td>security alert</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>civilEmergency</td>
<td>3_6</td>
<td>security alert</td>
<td></td>
<td>civil­Emergency</td>
</tr>
<tr class="even">
<td>airRaid</td>
<td>3_7</td>
<td>security alert</td>
<td></td>
<td>airRaid</td>
</tr>
<tr class="odd">
<td>sabotage</td>
<td>3_8</td>
<td>security alert</td>
<td></td>
<td>sabotage</td>
</tr>
<tr class="even">
<td>bombAlert</td>
<td>3_9</td>
<td>security alert</td>
<td></td>
<td>bombAlert</td>
</tr>
<tr class="odd">
<td>attack</td>
<td>3_10</td>
<td>security alert</td>
<td></td>
<td>attack</td>
</tr>
<tr class="even">
<td>evacuation</td>
<td>3_11</td>
<td>security alert</td>
<td></td>
<td>evacuation</td>
</tr>
<tr class="odd">
<td>terroristIncident</td>
<td>3_12</td>
<td>security alert</td>
<td></td>
<td>terroristIncident</td>
</tr>
<tr class="even">
<td>gunfireOnRoadway</td>
<td>3_13</td>
<td>security alert</td>
<td></td>
<td>gunFireOnRoadway</td>
</tr>
<tr class="odd">
<td>explosion</td>
<td>3_14</td>
<td>security alert</td>
<td></td>
<td>explosion</td>
</tr>
<tr class="even">
<td>explosionHazard</td>
<td>3_15</td>
<td>security alert</td>
<td></td>
<td>explosionHazard</td>
</tr>
<tr class="odd">
<td>securityIncident</td>
<td>3_16</td>
<td>security alert</td>
<td></td>
<td>securityIncident</td>
</tr>
<tr class="even">
<td>fireBrigadeOrder</td>
<td>3_17</td>
<td>security alert</td>
<td>r</td>
<td></td>
</tr>
<tr class="odd">
<td rowspan="7">Accident Subreason</td>
<td>fatality</td>
<td>6_1</td>
<td>security alert</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>personUnderTrain</td>
<td>6_2</td>
<td>accident</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>personHitByTrain</td>
<td>6_3</td>
<td>accident</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>personIllOnVehicle</td>
<td>6_4</td>
<td>accident</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>emergencyServices</td>
<td>6_5</td>
<td>accident</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>collision</td>
<td>6_6</td>
<td>accident</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>linesideFire</td>
<td>4_1</td>
<td>fire</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td rowspan="5">Train­Obstruction­Subreason</td>
<td>fallenTreeOnTheLine</td>
<td>19_1</td>
<td>object on the line</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>vegetation</td>
<td>19_2</td>
<td>object on the line</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>trainStruckAnimal</td>
<td>19_3</td>
<td>object on the line</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>trainStruckObject</td>
<td>19_4</td>
<td>object on the line</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>levelCrossingIncident</td>
<td>18_1</td>
<td>vehicle on the line</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td rowspan="4">Roadworks subreason</td>
<td>sewerageMaintenance</td>
<td>23__1</td>
<td>roadworks</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>roadMaintenance</td>
<td>23__2</td>
<td>roadworks</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>asphalting</td>
<td>23__3</td>
<td>roadworks</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>paving</td>
<td>23__4</td>
<td>roadworks</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td rowspan="6">Special Event Subreason</td>
<td>march</td>
<td>24_1</td>
<td>special event</td>
<td></td>
<td>march</td>
</tr>
<tr class="even">
<td>procession</td>
<td>24_2</td>
<td>special event</td>
<td></td>
<td>procession</td>
</tr>
<tr class="odd">
<td>demonstration</td>
<td>24_3</td>
<td>special event</td>
<td></td>
<td>demonstration</td>
</tr>
<tr class="even">
<td>publicDisturbance</td>
<td>24_4</td>
<td>special event</td>
<td></td>
<td>publicDisturbance</td>
</tr>
<tr class="odd">
<td>filterBlockade</td>
<td>24_5</td>
<td>special event</td>
<td></td>
<td>filterBlockade</td>
</tr>
<tr class="even">
<td>sightseersObstructing­Access</td>
<td>24_6</td>
<td>special event</td>
<td></td>
<td>sightseers­Obstructing­Access</td>
</tr>
<tr class="odd">
<td>Bridge</td>
<td>viaductFailure</td>
<td>25_1</td>
<td>bridgeStrike</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td rowspan="7">Passenger Subreason</td>
<td>passengerAction</td>
<td>5_1</td>
<td>vandalism</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>staffAssault</td>
<td>5_2</td>
<td>vandalism</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>railwayCrime</td>
<td>5_3</td>
<td>vandalism</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>assault</td>
<td>5_4</td>
<td>vandalism</td>
<td></td>
<td>assault</td>
</tr>
<tr class="even">
<td>theft</td>
<td>5_5</td>
<td>vandalism</td>
<td></td>
<td>theft</td>
</tr>
<tr class="odd">
<td>altercation</td>
<td>1_7</td>
<td>incident</td>
<td></td>
<td>altercationOfVehicle­Occupants</td>
</tr>
<tr class="even">
<td>illVehicleOccupants</td>
<td>1_8</td>
<td>incident</td>
<td></td>
<td>illVehicleOccupants</td>
</tr>
<tr class="odd">
<td rowspan="3">Border Process Subreason</td>
<td>problemsAtBorderPost</td>
<td>255_1</td>
<td>incident</td>
<td>problemsAtBorderPost</td>
<td></td>
</tr>
<tr class="even">
<td>problemsAt­CustomsPost</td>
<td>255_2</td>
<td>incident</td>
<td>problemsAt­CustomsPost</td>
<td></td>
</tr>
<tr class="odd">
<td>problemsOnLocalRoad</td>
<td>255_3</td>
<td>incident</td>
<td>problemsOn­LocalRoad</td>
<td></td>
</tr>
<tr class="even">
<td rowspan="2"><p>Indirect</p>
<p>Subreasons</p></td>
<td>speedRestrictions</td>
<td>255_1</td>
<td>incident</td>
<td>speedRestrictions</td>
<td></td>
</tr>
<tr class="odd">
<td>logisticProblems</td>
<td>255_2</td>
<td>incident</td>
<td>logisticProblems</td>
<td></td>
</tr>
</tbody>
</table>

## PersonnelReason 

| Group            | SIRI-SX                   | Pti20 | TPEG                        | Datex2 Disturbance Activity |
| ---------------- | ------------------------- | ----- | --------------------------- | --------------------------- |
| Personnel Reason | unknown                   | 0     | unknown                     |                             |
|                  | staffSickness             | 1     | staff sickness              |                             |
|                  | staffAbsence              | 2     | staff absence               |                             |
|                  | staffInWrongPlace         | 3     | staff in wrong place        |                             |
|                  | staffShortage             | 4     | staff shortage              |                             |
|                  | industrialAction          | 5     | industrial action           | strike                      |
|                  | workToRule                | 6     | work to rule                | goSlowOperation             |
|                  | undefinedPersonnelProblem | 255   | undefined personnel problem |                             |

|                      |                            |     |                   |
| -------------------- | -------------------------- | --- | ----------------- |
| Personne sub lReason | staffInjury                | 1_1 | staff sickness    |
|                      | contractorStaffInjury      | 1_1 | staff sickness    |
|                      | unofficialIndustrialAction | 5_1 | industrial action |

## EquipmentReason 

|                  |                           |       |                             |                  |
| ---------------- | ------------------------- | ----- | --------------------------- | ---------------- |
|                  | SIRI-SX                   | Pti21 | TPEG                        | Datex2           |
| Equipment Reason | unknown                   | 0     | unknown                     |                  |
|                  | pointsProblem             | 1     | points problem              |                  |
|                  | pointsFailure             | 2     | points failure              |                  |
|                  | signalProblem             | 3     | signal problem              |                  |
|                  | signalFailure             | 4     | signal failure              |                  |
|                  | derailment                | 5     | derailment                  |                  |
|                  | engineFailure             | 6     | engine failure              |                  |
|                  | breakDown                 | 7     | break down                  |                  |
|                  | technicalProblem          | 8     | technical problem           |                  |
|                  | repairWork                | 9     | repair work                 |                  |
|                  | constructionWork          | 10    | construction work           |                  |
|                  | maintenanceWork           | 11    | maintenance work            |                  |
|                  | powerProblem              | 12    | power problem               |                  |
|                  | fuelProblem               | 13    | fuel problem                |                  |
|                  | swingBridgeFailure        | 14    | swing bridge failure        |                  |
|                  | escalatorFailure          | 15    | escalator failure           |                  |
|                  | liftFailure               | 16    | lift failure                |                  |
|                  | gangwayProblem            | 17    | gangway problem             |                  |
|                  | closedForMaintenance      | 18    | closed for maintenance      |                  |
|                  | fuelShortage              | 19    | fuel shortage               |                  |
|                  | deicingWork               | 20    | de-icing work               |                  |
|                  | wheelProblem              | 21    | wheel problem               |                  |
|                  | luggageCarouselProblem    | 22    | luggage carousel problem    |                  |
|                  | undefinedEquipmentProblem | 255   | undefined equipment problem | equipmentFailure |

|                     | SIRI-SX                           | Pti21 | TPEG                 |
| ------------------- | --------------------------------- | ----- | -------------------- |
| Equipment Subreason | tractionFailure                   | 6_1   | engine failure       |
|                     | defectiveTrain                    | 6_2   | engine failure       |
|                     | slipperyTrack                     | 21_1  | wheelProblem failure |
|                     | trainWarningSystemProblem         | 3_1   | signal problem       |
|                     | trackCircuitProblem               | 3_2   | signal problem       |
|                     | Signal and Switch Failure         | 4_1   | signal failure       |
|                     | brokenRail                        | 8_1   | technical problem    |
|                     | poorRailConditions                | 8_2   | technical problem    |
|                     | wheelImpactLoad                   | 8_3   | technical problem    |
|                     | lackOfOperationalStock            | 8_4   | technical problem    |
|                     | defectiveFireAlarmEquipment       | 8_5   | technical problem    |
|                     | defectivePlatformEdgeDoors        | 8_6   | technical problem    |
|                     | defectiveCctv                     | 8_7   | technical problem    |
|                     | defectivePublicAnnouncementSystem | 8_8   | technical problem    |
|                     | ticketingSystemNotAvailable       | 8_9   | technical problem    |
|                     | levelCrossingFailure              | 8_10  | technical problem    |
|                     | trafficManagementSystemFailure    | 8_11  | technical problem    |
|                     | emergencyEngineeringWork          | 11_1  | maintenance work     |
|                     | lateFinishToEngineeringWork       | 11_2  | maintenance work     |
|                     | overheadWireFailure               | 12_1  | powerProblem         |

## EnvironmentReason 

|                    |                               |       |                    |                                       |
| ------------------ | ----------------------------- | ----- | ------------------ | ------------------------------------- |
| Group              | SIRI-SX                       | Pti22 | TPEG               | Datex2 Environmental Obstruction Type |
| Environment Reason | unknown                       | 0     | unknown            |                                       |
|                    | fog                           | 1     | fog                |                                       |
|                    | roughSea                      | 2     | rough sea          |                                       |
|                    | heavySnowFall                 | 3     | heavy snow fall    |                                       |
|                    | heavyRain                     | 4     | heavy rain         |                                       |
|                    | strongWinds                   | 5     | strong winds       |                                       |
|                    | tidalRestrictions             | 6     | tidal restrictions |                                       |
|                    | highTide                      | 7     | high tide          |                                       |
|                    | lowTide                       | 8     | low tide           |                                       |
|                    | ice                           | 9     | ice                |                                       |
|                    | frozen                        | 10    | frozen             |                                       |
|                    | hail                          | 11    | hail               |                                       |
|                    | highTemperatures              | 12    | high temperatures  |                                       |
|                    | flooding                      | 13    | flooding           | flooding                              |
|                    | waterlogged                   | 14    | waterlogged        |                                       |
|                    | lowWaterLevel                 | 15    | low water level    |                                       |
|                    | highWaterLevel                | 16    | high water level   |                                       |
|                    | fallenLeaves                  | 17    | fallen leaves      |                                       |
|                    | fallenTree                    | 18    | fallen tree        | fallenTrees                           |
|                    | landslide                     | 19    | landslide          | landslips                             |
|                    | undefinedEnvironmentalProblem | 255   | poorWeather        | other                                 |

| Group                         | SIRI-SX            | Pti22 | TPEG                            | Datex2 Environmental Obstruction Type |
| ----------------------------- | ------------------ | ----- | ------------------------------- | ------------------------------------- |
| Environment Weather Subreason | driftingSnow       | 3_1   | heavy snow fall                 |                                       |
|                               | blizzardConditions | 3_2   | heavy snow fall                 |                                       |
|                               | stormDamage        | 5_1   | strong winds                    | stormDamage                           |
|                               | stormConditions    | 5_1   | strong winds                    |                                       |
|                               | slipperiness       | 9_1   | ice                             |                                       |
|                               | iceDrift           | 9_2   | ice                             |                                       |
|                               | glazedFrost        | 9_3   | ice                             |                                       |
|                               | lightningStrike    | 255_1 | undefined environmental problem |                                       |
|                               | avalanches         | 3_1   | heavy snow fall                 | avalanches                            |
|                               | flashFloods        | 13_1  | flooding                        | flashFloods                           |
| Environment ground Subreason  | mudslide           | 19_1  | landslide                       | mudslide                              |
|                               | rockfalls          | 19_2  | landslide                       | rockfalls                             |
|                               | subsidence         | 19_3  | landslide                       | subsidence                            |
|                               | earthquake­Damage  | 19_4  | landslide                       | earthquake­Damage                     |
|                               | sewerOverflow      | 255_2 | undefined environmental problem | sewerOverflow                         |
|                               | grassFire          | 255_3 | undefined environmental problem | grassFire                             |

## ***PublicEventType*** 

| SIRI-SX                    | Description                  | Datex2 CauseType           |
| -------------------------- | ---------------------------- | -------------------------- |
| athleticsMeeting           | Athletics Meeting            | athleticsMeeting           |
| ballGame                   | Ball Game                    | ballGame                   |
| baseballGame               | Baseball Game                | baseballGame               |
| basketballGame             | Basketball Game              | basketballGame             |
| bicycleRace                | Bicycle Race                 | bicycleRace                |
| boatRace                   | Boat Race                    | boatRace                   |
| boxingTournament           | Boxing Tournament            | boxingTournament           |
| bullFight                  | Bull Fight                   | bullFight                  |
| ceremonialEvent            | Ceremonial Event             | ceremonialEvent            |
| concert                    | Concert                      | concert                    |
| cricketMatch               | Cricket Match                | cricketMatch               |
| exhibition                 | Exhibition                   | exhibition                 |
| fair                       | fair                         | fair                       |
| festival                   | festival                     | festival                   |
| filmTVMaking               | Film or TV on location       | filmTVMaking               |
| footballMatch              | Football Match               | footballMatch              |
| funfair                    | funfair                      | funfair                    |
| golfTournament             | Golf Tournament              | golfTournament             |
| hockeyGame                 | Hockey Game                  | hockeyGame                 |
| horseRaceMeeting           | Horserace Meeting            | horseRaceMeeting           |
| internationalSportsMeeting | International Sports Meeting | internationalSportsMeeting |
| majorEvent                 | Major Event                  | majorEvent                 |
| marathon                   | marathon                     | marathon                   |
| market                     | market                       | market                     |
| match                      | match                        | match                      |
| motorSportRaceMeeting      | Motor Sport Race Meeting     | motorSportRaceMeeting      |
| parade                     | Parade                       | parade                     |
| raceMeeting                | Race Meeting                 | raceMeeting                |
| rugbyMatch                 | Rugby Match                  | rugbyMatch                 |
| severalMajorEvents         | Several Major Events         | severalMajorEvents         |
| show                       | show                         | show                       |
| showJumping                | Show Jumping                 | showJumping                |
| sportsMeeting              | Sports Meeting               | sportsMeeting              |
| stateOccasion              | State Occasion               | stateOccasion              |
| tennisTournament           | Tennis Tournament            | tennisTournament           |
| tournament                 | tournament                   | tournament                 |
| tradeFair                  | Trade Fair                   | tradeFair                  |
| waterSportsMeeting         | Water Sports Meeting         | waterSportsMeeting         |
| winterSportsMeeting        | Winter Sports Meeting        | winterSportsMeeting        |
| other                      | other                        | other                      |
| flowerParade               | Flower Parade                | (parade)                   |
| rummageSale                | Rummage Sale                 | (market)                   |
| carnival                   | Carnival                     | (parade)                   |
| fete                       | Fete                         | (fair)                     |
| Royal birthday             |                              | majorEvent                 |
| massWalk                   | Mass Walk                    | (sportsMeeting)            |
| Cycle Tour                 |                              | (bicycleRace)              |
| Organised walk             |                              | (sportsMeeting)            |

## Information textuelle associée aux perturbations

|               |            |     |            |                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------- | ---------- | --- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DefaultedText |            |     | +Structure | Overridable Text element                                                                                                                                                                                                                                                                                                                                                                                                      |
| Identity      | lang       | 0:1 | lang       | Language for text content.                                                                                                                                                                                                                                                                                                                                                                                                    |
|               | overridden | 0:1 | boolean    | Whether the default text phrase has been overridden The ***overridden*** attribute indicate whether the text has been changed from the computer generated default - And therefore cannot be regenerated or translated automatically. This is useful to know because a text that has not been modified may be regenerated in different languages, and also may be processed in IVR speech systems using pre-recorded elements. |
|               | string     | 0:1 | string     | Text content                                                                                                                                                                                                                                                                                                                                                                                                                  |

## Images

|       |              |     |              |                                                        |
| ----- | ------------ | --- | ------------ | ------------------------------------------------------ |
| Image |              |     | +Structure   | Graphic Resource                                       |
|       | ImageRef     | 0:1 | anyUrl       | Reference to an image                                  |
|       | ImageBinary  | 0:1 | Base64Binary | Embedded image in binary form                          |
|       | ImageContent | 0:1 | enum         | Classification du type d'image (voir table ci-dessous) |

|         |                        |
| ------- | ---------------------- |
| SIRI-SX | Description            |
| map     | Image is a map         |
| logo    | Image is a logo        |
| graphic | Image is other graphic |

## InfoLinks

|          |             |     |            |                                                           |
| -------- | ----------- | --- | ---------- | --------------------------------------------------------- |
| InfoLink |             |     | +Structure | Web Link                                                  |
|          | Uri         | 1:1 | anyUrl     | Link url                                                  |
|          | Label       | 0:1 | nlString   | label for link                                            |
|          | Image       | 0:1 | Image      | Image associated with link                                |
|          | LinkContent | 0:1 | enum       | Classification du type de contenu (voir table ci-dessous) |

|             |                                      |
| ----------- | ------------------------------------ |
| Value       | Description                          |
| other       | Other                                |
| timetable   | Link is to a timetable               |
| relatedSite | Link is to a related Site            |
| details     | Link is to a page of further details |

## Description globale des conséquences

|                   |               |                            |           |        |              |                                                                                                                                                                             |
| ----------------- | ------------- | -------------------------- | --------- | ------ | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Consequence       |               |                            |           |        | +Structure   | Effect of a Situation on services.                                                                                                                                          |
| Time              | Period        |                            |           | 0:\*   | range        | On or more overall inclusive Period of applicability of consequence                                                                                                         |
|                   |               | Start                      |           | 0:1    | dateTime     | The (inclusive) start time stamp.                                                                                                                                           |
|                   |               | End                        |           | 0:1    | dateTime     | The (inclusive) end time stamp. If omitted, the range end is open-ended, that is, it should be interpreted as "forever".                                                    |
| Class­ifiers      | Condition     |                            |           | 1:1    | enum         | Classification of effect on service. TPEG Pti13 Service Condition values.                                                                                                   |
|                   | Severity      |                            |           | 0:1    | enum         | Severity of Situation. Corresponds to TPEG Pti26 severities. Default is normal.                                                                                             |
| Scope             | Affects       |                            |           | 0:1    | AffectsScope | Structured model identifying parts of transport t affected by consequence. See Below                                                                                        |
|                   | Suitabilities |                            |           | 0:\*   | many         | Effect on different passenger needs.                                                                                                                                        |
|                   |               | Suitability                |           | 0:1    | Suitability  | Effect on a passenger need. See Below.                                                                                                                                      |
| Advice            | Advice        |                            |           | 0:1    | +Structure   | Advice to passengers.                                                                                                                                                       |
|                   |               | AdviceRef                  |           | 0:1    | id           | Identifier of standard Further advice message to passengers.                                                                                                                |
|                   |               | Details                    |           | 0:1    | nlString     | Further Textual advice to passengers.                                                                                                                                       |
| Blocking          | Blocking      |                            |           | 0:1    | +Structure   | How Disruption should be handled in Info systems                                                                                                                            |
|                   |               | JourneyPlanner             |           | 0:1    | boolean      | Whether information about parts of the network identified by ***AffectsScope*** should be blocked from the Journey Planner. Default is false; do not suppress.              |
|                   |               | RealTime                   |           | 0:1    | boolean      | Whether information about parts of the network identified by ***AffectsScope*** should be blocked from real-time departure info systems. Default is false; do not suppress. |
| Act­ivity         | Boarding      |                            |           | 0:1    | +Structure   | Intended audience of situation.                                                                                                                                             |
|                   |               | ArrivalBoarding­Activity   |           | 0:1    | enum         | Type of boarding and alighting allowed at stop. Default is Alighting                                                                                                        |
|                   |               | DepartureBoarding­Activity |           | 0:1    | enum         | Type of boarding and alighting allowed at stop. Default is Alighting                                                                                                        |
| Delay             | Delays        |                            |           | 0:1    | +Structure   | Predicted delays                                                                                                                                                            |
|                   |               |                            | DelayBand | 0:1    | enum         | Timeband of likely delay length                                                                                                                                             |
|                   |               | DelayType                  |           | 0:1    | enum         | Nature of delay                                                                                                                                                             |
|                   |               | Delay                      |           | 0:1    | duration     | Additional Journey time needed to overcome disruption.                                                                                                                      |
| Description Group | Casualties    |                            |           | 0:1    |              | Information on casualties.                                                                                                                                                  |
|                   |               | NumberOf­Deaths            |           | 0:1    | integer      | Number of fatalities                                                                                                                                                        |
|                   |               | NumberOf­Injured           |           | 0:1    | integer      | Number of injured persons.                                                                                                                                                  |
| Ease­ments        | Easements     |                            |           | \*0:\* | +Structure   | Description of fare exceptions allowed because of disruption.                                                                                                               |
|                   |               | TicketRestriction          |           | 0:1    | enum         | Ticket restriction conditions in effect. TPEG pti table pti25.                                                                                                              |
|                   |               | Easement                   |           | 0:1    | nlString     | Description of fare exceptions allowed because of disruption.                                                                                                               |
|                   |               | EasementRef                |           | 0:1    | nlString     | Identifier of a fare exceptions code allowed because of the disruption.                                                                                                     |
| any               | Extensions    |                            |           | 0:1    | any          | Placeholder for user extensions.                                                                                                                                            |

## Service Condition

|                       |                                  |       |
| --------------------- | -------------------------------- | ----- |
| SIRI-SX               | Description                      | Pti13 |
| unknown               | unknown                          | 0     |
| altered               | altered                          | 1     |
| cancelled             | cancelled                        | 2     |
| delayed               | delayed                          | 3     |
| diverted              | diverted                         | 4     |
| noService             | no service                       | 5     |
| disrupted             | disrupted                        | 6     |
| additionalService     | additional service               | 7     |
| specialService        | special service                  | 8     |
| onTime                | on time                          | 9     |
| normalService         | normal service                   | 10    |
| intermittentService   | intermittent service             | 11    |
| shortFormedService    | short formed service             | 12    |
| fullLengthService     | full length service              | 13    |
| extendedService       | extended service                 | 14    |
| splittingTrain        | splitting train                  | 15    |
| replacement Transport | replacement transport            | 16    |
| arrivesEarly          | arrives early                    | 17    |
| shuttleService        | shuttle service                  | 18    |
| replacementService    | replacement service              | 19    |
| alternateTrack        | redirected to an alternate track | 20    |
| undefined             | undefined service information    | 255   |

## Conséquences en terme d’accessibilité

|             |          |                   |     |            |                              |
| ----------- | -------- | ----------------- | --- | ---------- | ---------------------------- |
| Suitability |          |                   |     | +Structure | Overridable Text element     |
| Identity    | Suitable |                   | 1:1 | enum       | Language for text content.   |
|             | UserNeed |                   | 1:1 | choice     |                              |
|             | a        | MobilityNeed      | 1:1 | enum       | Specific User need see below |
|             | b        | MedicalNeed       | 1:1 | enum       | Specific User need see below |
|             | c        | PsychoSensoryNeed | 1:1 | enum       | Specific User need see below |
|             | d        | EncumbranceNeed   | 1:1 | enum       | Specific User need see below |

## Suitability

|             |                                      |
| ----------- | ------------------------------------ |
| SIRI-SX     | Description                          |
| suitable    | Suitable for specified user need     |
| notSuitable | Not suitable for specified user need |
| unknown     | Suitability is unknown               |

|                   |                        |                                 |
| ----------------- | ---------------------- | ------------------------------- |
| Need Group        | SIRI-SX                | Description                     |
| MobilityNeed      | wheelchair             | User needs wheelchair           |
|                   | motorizedWheelchair    | User needs motorized wheelchair |
|                   | walkingFrame           | User needs walking frame        |
|                   | restrictedMobility     | User has limited mobility       |
|                   | otherSpecificNeed      | User has other need             |
| MedicalNeed       | allergic               | User has severe allergies       |
|                   | heartCondition         | User has heart condition        |
| PsychosensoryNeed | visualImpairment       | User has visual impairment      |
|                   | auditoryImpairment     | User has Auditory impairment    |
|                   | cognitiveImpairment    | User has cognitive impairment   |
|                   | averseToLifts          | Use is averse to lifts          |
|                   | averseToEscalators     | User is averse to Escalators    |
|                   | averseToConfinedSpaces | User dislikes confined spaces   |
|                   | averseToCrowds         | User dislikes Crowds            |
|                   | otherSensoryNeed       | User has other need             |
| EncumbranceNeed   | luggageEncumbered      | User has luggage encumbered     |
|                   | pushchair              | User has pushchair              |
|                   | baggageTrolley         | User has Baggage trolley        |
|                   | oversizeBaggage        | User has Oversize baggage       |
|                   | guideDog               | User has Guide dog              |
|                   | otherAnimal            | User has Other animal           |
|                   | otherEncumbrance       | User has Other encumbrance      |

## Boarding / Alighting

|             |                                     |     |
| ----------- | ----------------------------------- | --- |
| SIRI-SX     | Description                         |     |
| alighting   | Passengers may alight at stop       |     |
| noAlighting | Passengers may not alight at stop   |     |
| passThrough | Passengers may pass through at stop |     |

|             |                                     |     |
| ----------- | ----------------------------------- | --- |
| SIRI-SX     | Description                         |     |
| boarding    | Passengers may board at stop        |     |
| noBoard     | Passengers may not board at stop    |     |
| passThrough | Passengers may pass through at stop |     |

## DelayBand 

|                                     |               |                                     |
| ----------------------------------- | ------------- | ----------------------------------- |
| SIRI-SX                             | Description   | Datex2 DelayCode                    |
| delayLongerThanSixHours             | \> 6 Hours    | delayLongerThanSixHours             |
| delayBetweenThreeHousrAndSixHours   | 3-6 Hours     | delayBetweenThreeHousrAndSixHours   |
| delayBetweenOneHourAndThreeHours    | 1-3 Hours     | delayBetweenOneHourAndThreeHours    |
| delayBetweenThirtyMinutesandOneHour | 30min-1 Hour  | delayBetweenThirtyMinutesandOneHour |
| delayLessThanThirtyMinutes          | \< 30 minutes | delayLessThanThirtyMinutes          |
| negligble                           | negligble     | negligble                           |

## DelayType

|                           |                              |                           |
| ------------------------- | ---------------------------- | ------------------------- |
| SIRI-SX                   | Description                  | Datex2 DelaysType         |
| delays                    | Material delays              | delays                    |
| delaysOfUncertainDuration | Delays Of Uncertain Duration | delaysOfUncertainDuration |
| longDelays                | Long Delays                  | longDelays                |
| veryLongDelays            | Very Long Delays             | veryLongDelays            |

## TicketRestrictions

|                                |                                    |            |
| ------------------------------ | ---------------------------------- | ---------- |
| SIRI-SX                        | Description                        | TPG Pti 25 |
| unknown                        | unknown                            | pti25_0    |
| allTicketClassesValid          | All Ticket Classes Valid           | pti25_1    |
| fullFareOnly                   | Full Fare Only                     | pti25_2    |
| certainTicketsOnly             | Certain Tickets Only               | pti25_3    |
| ticketWithReservation          | Ticket with Reservation            | pti25_4    |
| specialFare                    | Special Fare                       | pti25_5    |
| onlyTicketsOfSpecifiedOperator | Only Tickets of Specified Operator | pti25_6    |
| noRestrictions                 | No Restrictions                    | pti25_7    |
| noOffPeakTickets               | No Off-peak Tickets                | pti25_8    |
| noWeekendReturnTickets         | No Weekend Return Tickets          | pti25_9    |
| noReducedFareTickets           | No Reduced Fare Tickets            | pti25_10   |
| unknownTicketRestriction       | Unknown Ticket Restriction         | pti25_255  |

## AffectsScope

|                |                   |                   |      |                         |                                                                                                 |
| -------------- | ----------------- | ----------------- | ---- | ----------------------- | ----------------------------------------------------------------------------------------------- |
| AffectsScope   |                   |                   |      | +Structure              | The scope of the situation or consequence                                                       |
| AreaOfInterest |                   |                   |      | enum                    | Affected overall Geographic scope (i.e. regional, nationale, etc.).                             |
| Operat­ors     | Operators         |                   | 0:1  | choice                  | Networks scope.                                                                                 |
|                | a                 | AllOperators      | 0:1  | empty                   | All operators are effected                                                                      |
|                | b                 | AffectedOperator  | 0:\* | +Structure              | Annotated reference to Operator of services affected by situation. See Below.                   |
| Stops          | StopPoints        |                   | 0:\* | +Structure              | Scheduled Stop Point scope                                                                      |
|                |                   | AffectedStopPoint | 0:1  | +Structure              | Scheduled Stop Point scope. See below.                                                          |
| StopPlaces     | StopPlaces        |                   | 0:\* | +Structure              | Stop Place scope                                                                                |
|                | AffectedStopPlace |                   | 0:1  | +Structure              | Stop Place scope. See below.                                                                    |
| network        | Networks          |                   | 0:\* | +Structure              | Networks scope.                                                                                 |
|                |                   | AffectedNetwork   | 0:1  | +Structure              | Network scope. See below.                                                                       |
| Journey        | VehicleJourneys   |                   | 0:\* | +Structure              | Vehicle Journeys scope. See below.                                                              |
|                |                   | VehicleJourney    | 0:1  | +Structure              | Vehicle Journey scope                                                                           |
| Places         | StopPlaces        |                   | 0:\* | +Structure              | Stop Places scope                                                                               |
|                |                   | AffectedStopPlace | 0:1  | +Structure              | Annotated reference to Stop Place. See below.                                                   |
| Roads          | AffectedRoads     |                   | 0:1  | Datex2:GroupOfLocations | Scope of Road/transport network as described by datex3 location model. See Datex2 documentation |
| any            | Extensions        |                   | 0:1  | any                     | Placeholder for user extensions.                                                                |

## AreaOfInterest 

|                       |                                          |                       |
| --------------------- | ---------------------------------------- | --------------------- |
| SIRI-SX               | Description                              | Datex2                |
| continentWide         | Applies to whole continent               | continentWide         |
| national              | Affects a whole country                  | national              |
| neighbouringCountries | Affects a country and its neighbours     | neighbouringCountries |
| regional              | Affects a region within a country        | regional              |
| notSpecified          | Situation concerns an individual service | notSpecified          |

## Conséquences sur un réseau

|                 |                |                   |      |              |                                                                                                                              |
| --------------- | -------------- | ----------------- | ---- | ------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| AffectedNetwork |                |                   |      | +Structure   | The scope of the situation or consequence                                                                                    |
| Operators       | Operators      |                   | 0:\* | choice       | Networks scope.                                                                                                              |
|                 | b              | AffectedOperator  | 0:1  | +Structure   | Annotated reference to Operator of services affected by situation. See Below.                                                |
| network         | NetworkRef     |                   | 0:1  | Network­Code | Network of affected line. If absent, may be taken from context.                                                              |
|                 | NetworkName    |                   | 0:1  | nlString     | Name of Network.                                                                                                             |
|                 | RoutesAffected |                   | 0:1  | nlString     | Textual description of overall routes affected. Should correspond to any structured description.                             |
|                 | VehicleMode    |                   |      | enum         | Modes Affected Vehicle mode- Tpeg ModeType pti1.                                                                             |
| Mode            | Submode        |                   |      | Choice       |                                                                                                                              |
|                 | a              | AirSubmode        | 0:1  | enum         | TPEG pti08 Air submodes.                                                                                                     |
|                 | b              | BusSubmode        | 0:1  | enum         | TPEG pti05 Bus submodes.                                                                                                     |
|                 | c              | Coach             | 0:1  | enum         | TPEG pti03 Coach submodes.                                                                                                   |
|                 | d              | MetroSubmode      | 0:1  | enum         | TPEG pti04 Metro submodes.                                                                                                   |
|                 | e              | RailSubmode       | 0:1  | enum         | TPEG pti02 Rail submodes loc13.                                                                                              |
|                 | f              | TramSubmode       | 0:1  | enum         | PEG pti06 Tram submodes.                                                                                                     |
|                 | g              | WaterSubmode      | 0:1  | enum         | TPEG pti07 Water submodes.                                                                                                   |
|                 | h              | TelecabineSubmode | 0:1  | enum         | TPEG pti09 Telecabin submodes.                                                                                               |
|                 | AccessMode     |                   | 0:1  | enum         | The allowed categroies of access to stop place for which Situations will be returned. Default is all                         |
| network         | Lines          |                   | 0:1  | choice       | Line scope.                                                                                                                  |
|                 | a              | AllLines          | 0:1  | emptyType    | All lines in the network are affected.                                                                                       |
|                 | b              | SelectedRoutes    | 0:1  | emptyType    | Only some routes are affected, line level information not available. See the AffectedRoutes element for textual description. |
|                 | c              | AffectedLine      | 0:\* | +Structure   | Line affected by situation. See Below.                                                                                       |
| any             | Extensions     |                   | 0:1  | any          | Placeholder for user extensions.                                                                                             |

## Conséquences sur un exploitant

|                  |                    |      |                  |                                                                  |
| ---------------- | ------------------ | ---- | ---------------- | ---------------------------------------------------------------- |
| AffectedOperator |                    |      | +Structure       | Annotated Reference to Operator & Unit                           |
| Operat­or        | OperatorRef        | 0:1  | **Operator­Code | Identifier of Operator.                                          |
|                  | OperatorName       | 0:1  | nlString         | Name of Operator.                                                |
|                  | OperatorShortName  | 0:1  | nlString         | ShortName for Operator. E.g. TfL, LUL                            |
| Unit             | OperationalUnitRef | 0:\* | UnitCode        | Identifier of Operational unit responsible for managing services |
| any              | Extensions         | 0:1  | any              | Placeholder for user extensions.                                 |

## Conséquences sur une ligne ou une section de ligne

|              |              |                  |                    |      |                         |            |                                                                               |                             |
| ------------ | ------------ | ---------------- | ------------------ | ---- | ----------------------- | ---------- | ----------------------------------------------------------------------------- | --------------------------- |
| AffectedLine |              |                  |                    |      |                         | +Structure |                                                                               | Annotated Reference to Line |
| Operators    | Operators    |                  |                    | 0:\* | choice                  |            | Networks scope.                                                               |                             |
|              |              | AffectedOperator |                    | 0:1  | +Structure              |            | Annotated reference to Operator of services affected by situation. See Below. |                             |
| Operat­or    | LineRef      |                  |                    | 0:1  | Line­Code              |            | Identifier of Line.                                                           |                             |
|              | Destinations |                  |                    | 0:\* | choice                  |            | Routes scope.                                                                 |                             |
|              |              |                  | AffectedStop­Point | 0:1  | +Structure              |            | Annotated reference to destination Stop Point affected by Situation           |                             |
|              | Directions   |                  |                    | 0:\* | +Structure              |            | Directions affected.                                                          |                             |
|              |              |                  | DirectionRef       | 0:1  | Direction­­Code        |            | Identifier of Direction.                                                      |                             |
| Routes       | Routes       |                  |                    | 0:\* | choice                  |            | Routes scope.                                                                 |                             |
|              |              |                  | AffectedRoute      | 0:1  | AffectedRouteStructure |            | Route affected by Situation.                                                  |                             |
| Sect­ions    | Sections     |                  |                    | 0:\* | choice                  |            | Section of Line scope.                                                        |                             |
|              |              |                  | Section            | 0:1  | +Structure              |            | Identifier of Section affected by Situation.                                  |                             |
| any          | Extensions   |                  |                    | 0:1  | any                     |            | Placeholder for user extensions.                                              |                             |

## Conséquences sur un itinéraire

|               |            |               |      |                  |                                                  |
| ------------- | ---------- | ------------- | ---- | ---------------- | ------------------------------------------------ |
| AffectedRoute |            |               |      | +Structure       | Annotated Reference to Route                     |
| Route         | RouteRef   |               | 0:1  | Route­Code      | Identifier of Line.                              |
|               | Directions |               | 0:\* | +Structure       | Directions affected.                             |
|               |            | DirectionRef  | 0:1  | Direction­­Code | Identifier of Direction.                         |
|               |            | DirectionName | 0:1  | nlString         | Name of direction                                |
| Sect­ions     | Sections   |               | 0:\* | choice           | Section of route scope.                          |
|               |            | SectionRef    | 0:1  | +Structure       | Identifier of Section affected by Situation.     |
| Routes        | RouteLinks |               | 0:\* | choice           | Route scope.                                     |
|               |            | RouteLinkRef  | 0:1  | Route­Code      | Identifier of Route Limnk affected by Situation. |
| any           | Extensions |               | 0:1  | any              | Placeholder for user extensions.                 |

## Conséquences sur un point d’arrêt

|                   |                         |          |                         |      |                 |                                                                               |
| ----------------- | ----------------------- | -------- | ----------------------- | ---- | --------------- | ----------------------------------------------------------------------------- |
| AffectedStopPoint |                         |          |                         |      | +Structure      | Annotated Reference to Stop Point                                             |
| Stop              | StopPointRef            |          |                         | 0:1  | StopPoint­Code | Identifier of Stop Point.                                                     |
|                   | PrivateRef              |          |                         | 0:1  | string          | Additional external code of                                                   |
|                   | StopPointName           |          |                         | 0:1  | nlString        | Name of Stop.                                                                 |
|                   | StopPointType           |          |                         | 0:1  | enum            | Type Of Stop. See below                                                       |
|                   | Location                |          |                         | 0:1  | Location        | Point Projection to use for stop point                                        |
| Modes             | AffectedModes           |          |                         | 0:1  | choice          | Mode scope.                                                                   |
|                   | a                       | AllModes |                         | 0:1  | emptyType       | All modes for the StopPoint are affected.                                     |
|                   | b                       | mode     |                         | 0:\* | +Structure      | Annotated reference to Operator of services affected by situation. See Below. |
| Zone              | PlaceRef                |          |                         | 0:1  | PlaceIdPlaceId | Identifier of Place in which Stop lies                                        |
|                   | PlaceName               |          |                         | 0:1  | nlString        | Name of Stop.                                                                 |
|                   | AccessibilityAssessment |          |                         | 0:1  | +Structure      | Accessibility Disruption                                                      |
|                   | ConnectionLinks         |          |                         | 0:\* | choice          | Connection Link scope.                                                        |
|                   |                         |          | Affected­ConnectionLink | 0:1  | +Structure      | Annotated reference to ConnectionLink affected by Situation                   |
| any               | Extensions              |          |                         | 0:1  | any             | Placeholder for user extensions.                                              |

## StopPointType

|                    |                  |             |
| ------------------ | ---------------- | ----------- |
| SIRI-SX            | TPEG             | TPEG Pti 17 |
| --                 | unknown          | pti17_0     |
| railPlatform       | Platform Number  | pti17_1     |
| metroPlatform      | (platformNumber) |             |
| airlineGate        | Terminal Gate    | pti17_2     |
| boatQuay           | Ferry Berth      | pti17_3     |
| (boatQuay)         | Harbour Pier     | pti17_4     |
| ferryLanding       | Landing Stage    | pti17_5     |
| busStop            | Bus Stop         | pti17_6     |
| coachStop          | (bus Stop)       |             |
| tramStop           | (bus Stop)       |             |
| taxiStand          | undefined        |             |
| setDownPlace       | undefined        |             |
| telecabinePlatform | undefined        |             |
| unknown            | undefined        | pti17_255   |

## Conséquences sur une correspondance

|                              |                          |          |                         |      |                     |                                                             |
| ---------------------------- | ------------------------ | -------- | ----------------------- | ---- | ------------------- | ----------------------------------------------------------- |
| ***AffectedConnectionLink*** |                          |          |                         |      | +Structure          | Annotated Reference to ConenctionLink                       |
| Stop                         | ***ConnectionLink***Ref  |          |                         | 0:1  | ConnectionLinkCode | Identifier of Stop Point.                                   |
|                              | ***Connection***Name     |          |                         | 0:1  | nlString            | Name of Stop.                                               |
| Lines                        | Lines                    |          |                         | 0:1  | choice              | Mode scope.                                                 |
|                              | a                        | AllLines |                         | 0:1  | Line­Code          | Identifier of Line.                                         |
|                              | b                        | LineRef  |                         | 0:\* | nlString            | Public Number or Name of Line.                              |
| To Stop                      | ConnectingStop­PointRef  |          |                         | 0:1  | StopPoint­Code      | Identifier of Connecting Stop Point.                        |
|                              | ConnectingStop­PointName |          |                         | 0:1  | nlString            | Name of Connecting Stop.                                    |
|                              | Connecting­ZoneRef       |          |                         | 0:1  | ZoneCode           | Identifier of Zone in which Connecting Stop lies            |
| Operat­or                    | ConenctionDirection      |          |                         | 0:1  | from \| to \| both  | Direction of Connection. Default is both                    |
| Links                        | AffectedLinks            |          |                         | 0:\* | choice              | Connection Link scope.                                      |
|                              |                          |          | Affected­ConnectionLink | 0:1  | +Structure          | Annotated reference to ConnectionLink affected by Situation |
| any                          | Extensions               |          |                         | 0:1  | any                 | Placeholder for user extensions.                            |

## Conséquences sur une zone d’arrêt (gare, pôle d’échange, etc.)

|                   |                         |                    |      |                |                                                                      |
| ----------------- | ----------------------- | ------------------ | ---- | -------------- | -------------------------------------------------------------------- |
| AffectedStopPlace |                         |                    |      | +Structure     | Annotated Reference to StopPlace                                     |
|                   | AccessibilityAssessment |                    | 0:1  | +Structure     | Accessibility Disruption to Journey                                  |
| Stop Place        | StopPlaceRef            |                    | 0:1  | Operator­Code | Identifier of Stop Place.                                            |
|                   | StopPlaceName           |                    | 0:1  | nlString       | Public Number or Name of Stop Place.                                 |
|                   | StopPlaceType           |                    | 0:1  | enum           | Type of Stop Place. See below.                                       |
| Routes            | Components              |                    | 0:\* | choice         | Stop Place Components scope.                                         |
|                   |                         | Affected­Component | 0:1  | Route­Code    | Identifier of Stop Place Component affected by Situation. See below. |
| Sect­ions         | NavigationPaths         |                    | 0:\* | choice         | Navigation path scope.                                               |
|                   |                         | NavigationPath­Ref | 0:1  | PathId        | Identifier of a path affected by Situation.                          |
| any               | Extensions              |                    | 0:1  | any            | Placeholder for user extensions.                                     |

## StopPlaceType 

|              |                |
| ------------ | -------------- |
| SIRI-SX      | Description    |
| airport      | Airport        |
| railStation  | Rail Station   |
| metroStation | Metro Station  |
| coachStation | Coach Station  |
| busStation   | Bus Station    |
| shipPort     | Ship Port      |
| ferryPort    | Ferry Port     |
| ferryStop    | Ferry Stop     |
| onStreetBus  | On Street Bus  |
| onStreetTram | On Street Tram |
| skiLift      | Ski Lift       |
| other        | other          |

## Conséquences sur les composants d’une zone d’arrêt

|                                  |                         |                   |     |                 |                                                                                                        |
| -------------------------------- | ----------------------- | ----------------- | --- | --------------- | ------------------------------------------------------------------------------------------------------ |
| ***AffectedStopPlaceComponent*** |                         |                   |     | +Structure      | Annotated Reference to a Stop Place Component                                                          |
|                                  | AccessibilityAssessment |                   | 0:1 | +Structure      | Accessibility Disruption to Component                                                                  |
| Identity                         | ComponentRef            |                   | 0:1 | **ComponentId  | Identifier of Component.                                                                               |
|                                  | ComponentName           |                   | 0:1 | nlString        | Public Number or Name of Component.                                                                    |
|                                  | ComponentType           |                   | 0:1 | enum            | Type of Stop Place Component. See below                                                                |
| Place Projection                 | PointProjection         |                   | 0:1 | +Structure      | Points may be defined in tagged format or using GM coordinates element.                                |
|                                  | LinkProjection          |                   | 0:1 | +Structure      | Projection as a geospatial polyline.                                                                   |
|                                  | ZoneProjection          |                   | 0:1 | +Structure      | PROJECTION onto a geospatial zone.                                                                     |
|                                  | Offset                  |                   | 0:1 |                 | Further qualifcation of affected part of Link projection,                                              |
|                                  |                         | DistanceFromStart | 0:1 | xsd:unsignedInt | Distance in metres from start of link at which SITUATION is to be shown. I f absent use start of link. |
|                                  |                         | DistanceFromEnd   | 0:1 | xsd:unsignedInt | Distance in metres from end of link at which SITUATION is to be shown. I f absent use end of link.     |
| any                              | Extensions              |                   | 0:1 | any             | Placeholder for user extensions.                                                                       |

## StopPlaceComponentType

|                  |                   |
| ---------------- | ----------------- |
| SIRI-SX          | Description       |
| quay             | Quay              |
| accessSpace      | Access Space      |
| boardingPosition | Boarding Position |
| stoppingPlace    | Stopping Place    |
| stoppingPosition | Stopping Position |
| entrance         | Entrance          |
| stopPathLink     | Stop Path Link    |
| accessPathLink   | Access Path Link  |
| other            | other             |

## StopAccessFeatureType

|                 |                  |
| --------------- | ---------------- |
| SIRI-SX         | Description      |
| lift            | Lift             |
| escalator       | Escalator        |
| travelatorr     | Travelator       |
| ramp            | Ramp             |
| stairs          | Stairs           |
| shuttle         | Shuttle          |
| barrier         | Barrier          |
| narrowEntrance  | Narrow Entrance  |
| confinedSpace   | Confined Space   |
| queueManagement | Queue Management |
| unknown         | Unknown          |

## Conséquences sur une course

|                              |                               |                    |      |                           |                                                                                                  |
| ---------------------------- | ----------------------------- | ------------------ | ---- | ------------------------- | ------------------------------------------------------------------------------------------------ |
| ***AffectedVehicleJourney*** |                               |                    |      | +Structure                | Annotated Reference to Vehicle Journey                                                           |
| Vehicle Journey              | ***VehicleJourneyRef***       |                    | 1:1  | :Vehicle­JourneyCode     | Identifier of a service vehicle journey.                                                         |
|                              | ***DatedVehicle­JourneyRef*** |                    | 0:1  | DatedVehicleJourney­Code | Identifier of a specific vehicle journey.                                                        |
|                              | ***JourneyName***             |                    | 0:1  | nlString                  | Name of Journey                                                                                  |
|                              | Operator                      |                    | 0:1  | AffectedOperator          | Annotated reference to Operator of services affected by situation. See AffectedOperator Element. |
| Operat­or                    | LineRef                       |                    | 0:1  | Operator­Code            | Identifier of Line.                                                                              |
|                              | PublishedLineName             |                    | 0:1  | nlString                  | Public Number or Name of Line.                                                                   |
|                              | DirectionRef                  |                    | 0:\* | Direction­Code           | Directions affected.                                                                             |
|                              | Origins                       |                    | 0:\* |                           | Scope within Journey                                                                             |
|                              |                               | AffectedStop­Point | 0:1  | +Structure                | Annotated reference to origin Stop Point affected by Situation                                   |
|                              | Destinations                  |                    | 0:\* |                           | Scope within Journey                                                                             |
|                              |                               | AffectedStop­Point | 0:1  | +Structure                | Annotated reference to destination Stop Point affected by Situation                              |
| Routes                       | RouteRef                      |                    | 0:1  | +Structure                | Identifier of Route affected by Situation.                                                       |
| Times                        | OriginAimed­DepartureTime     |                    | 0:1  | dateTime                  | Timetabled DepartureTime from Origin.                                                            |
|                              | DestinationAimed­ArrivalTime  |                    | 0:1  | dateTime                  | Timetabled Arrival time at Destination.                                                          |
|                              | AccessibilityAssessment       |                    | 0:1  | +Structure                | Accessibility Disruption to Journey                                                              |
| Sect­ions                    | Calls                         |                    | 0:\* | choice                    | Scope within Journey                                                                             |
|                              |                               | AffectedCall       | 0:1  | +Structure                | Annotated reference to Call affected by Situation.                                               |
| any                          | Extensions                    |                    | 0:1  | any                       | Placeholder for user extensions.                                                                 |

## Conséquences sur un arrêt marqué dans le cadre d’une course (call)

|              |                         |          |                         |      |                     |                                                                               |
| ------------ | ----------------------- | -------- | ----------------------- | ---- | ------------------- | ----------------------------------------------------------------------------- |
| AffectedCall |                         |          |                         |      | +Structure          | Annotated Reference to Stop Point                                             |
| Stop         | StopPointRef            |          |                         | 0:1  | StopPoint­Code     | Identifier of Stop Point.                                                     |
|              | PrivateRef              |          |                         | 0:1  | string              | Additional external code of                                                   |
|              | StopPointName           |          |                         | 0:1  | nlString            | Name of Stop.                                                                 |
|              | StopPointType           |          |                         | 0:1  | enum                | Type Of Stop                                                                  |
|              | Location                |          |                         | 0:1  | Location            | Point Projection to use for stop point                                        |
| Modes        | AffectedModes           |          |                         | 0:1  | choice              | Mode scope.                                                                   |
|              | a                       | AllModes |                         | 0:1  | emptyType           | All modes for the StopPoint are affected.                                     |
|              | b                       | mode     |                         | 0:\* | +Structure          | Annotated reference to Operator of services affected by situation. See Below. |
| Zone         | PlaceRef                |          |                         | 0:1  | ZoneCode           | Identifier of Topographic Place in which Stop lies                            |
|              | PlaceName               |          |                         | 0:1  | nlString            | Name of Stop.                                                                 |
|              | AccessibilityAssessment |          |                         | 0:1  | +Structure          | Accessibility Disruption                                                      |
|              | ConnectionLinks         |          |                         | 0:\* | choice              | Connection Link scope.                                                        |
|              |                         |          | Affected­ConnectionLink | 0:1  | +Structure          | Annotated reference to ConnectionLink affected by Situation                   |
|              | Order                   |          |                         | 0:1  | xsd:positiveInteger | Order of visit to stop within JORUNYE PATTERN of journey.                     |
| Status       | CallCondition           |          |                         | 0:1  | enum                | Status of call – TPEG value                                                   |
|              | VehicleAtStop           |          |                         | 0:1  | boolean             | Whether vehicle is located at stop                                            |
|              | VehicleLocationAtStop   |          |                         | 0:1  | +Structure          | Exact location that VEHICLE will take up / or has taken at STOP POINT.        |
| Times        | ArrivalTimes            |          |                         | 0:1  | +Structure          | Arrival times of call See SIRI-Part3                                          |
|              | ArrivalInfo             |          |                         | 0:1  | +Structure          | Arrival info of call See SIRI- Part3                                          |
|              | DepartureTimes          |          |                         | 0:1  | +Structure          | Departure times of call See SIRI-Part3                                        |
|              | DepartureInfo           |          |                         | 0:1  | +Structure          | Departure info of call See SIRI- Part3                                        |
|              | Headwaylnfo             |          |                         | 0:1  | +Structure          | Headway info of call See SIRI- Part3                                          |
|              | Affected­Interchanges   |          |                         | 0:\* | +Structure          | Journey Interchanges affected by Situation                                    |
| any          | Extensions              |          |                         | 0:1  | any                 | Placeholder for user extensions.                                              |

## Conséquence sur une correspondance planifiée

|                           |                              |     |                           |                                                        |
| ------------------------- | ---------------------------- | --- | ------------------------- | ------------------------------------------------------ |
| ***Affected***Interchange |                              |     | +Structure                | Annotated Reference to a Place                         |
| Identity                  | InterchangeRef               | 0:1 | **Interchange­Id         | Identifier of Journey Interchange                      |
|                           | InterchangeStop­PointRef     | 0:1 | StopPointCode            | Identifier of stop point to which interchange connects |
|                           | InterchanegStop­PointName    | 0:1 | nlString                  | Name of interchjange stop point.                       |
|                           | ConnectingVehicle­JourneyRef | 0:1 | DatedVehicle­JoruneyCode | Reference to Connnecting journey affected by Situation |
|                           | Interchange­StatusType       | 0:1 | enum                      | TpegInterchangeStatusCOde                              |
|                           | Connection­Link              | 0:1 | +Structure                | Reference to ConnectingLink affected by Situation      |
| any                       | Extensions                   | 0:1 | any                       | Placeholder for user extensions.                       |

## Conséquence sur un Lieu

|                     |                         |      |                  |                                                     |
| ------------------- | ----------------------- | ---- | ---------------- | --------------------------------------------------- |
| ***AffectedPlace*** |                         |      | +Structure       | Annotated Reference to a Place                      |
| Identity            | PlaceRef                | 0:1  | **PlaceIde      | Identifier of Place                                 |
|                     | PlaceName               | 0:1  | nlString         | Name of place.                                      |
|                     | PrivateCode             | 0:1  | **PlaceIde      | Alternative identifier of SITE or TOPOGRAPHIC PLACE |
|                     | Location                | 0:1  | Location         | Point refercne for place                            |
|                     | PlaceCategory           | 0:1  | nmtoken          | Type of Place . See below                           |
|                     | EquipmentRef            | 0:\* | **EquipmentCode | Reference to an EQUIPMENT found at location.        |
|                     | AccessibilityAssessment | 0:1  | +Structure       | Accessibility Disruption to Component               |
| any                 | Extensions              | 0:1  | any              | Placeholder for user extensions.                    |

## Conséquences en termes d’accessibilité (en complément des conséquences précédentes)

|                         |                               |                              |      |                          |                                                                                                                                                                                                   |
| ----------------------- | ----------------------------- | ---------------------------- | ---- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AccessibilityAssessment |                               |                              |      | +Structure               | Annotated Reference to Vehicle Journey                                                                                                                                                            |
| Operators               | ***MobilityImpaired­Access*** |                              | 0:1  | boolean                  | Whether stop or service is accessible to mobility impaired users. This may be further qualified by one ore more Limitation & Suitability instances to specify which types of access are available |
| Limitat­ion             | ***Limitations***             |                              | 0:1  | +Structure               | Limitation of entity                                                                                                                                                                              |
|                         | *0:\**                        | ***LimitationId***           |      | **LimitaionId           | Identifier of LIMITATION.                                                                                                                                                                         |
|                         |                               | ***ValidityCondition***      |      | +Structure               | Validty condition governing applicability of LIMITATION.                                                                                                                                          |
|                         |                               | ***Wheelchair­Access***      |      | true \| false \| unknown | Whether a Place is wheelchair accessible.                                                                                                                                                         |
|                         |                               | ***StepFreeAccess***         |      | true \| false \| unknown | Whether a Place has step free access.                                                                                                                                                             |
|                         |                               | ***EscalatorAccess***        |      | true \| false \| unknown | Whether a Place has escalator free access.                                                                                                                                                        |
|                         |                               | ***LiftFreeAccess***         |      | true \| false \| unknown | Whether a Place has lift free access.                                                                                                                                                             |
|                         |                               | ***AudibleSigns­Available*** |      | true \| false \| unknown | Whether a Place has Audible signals for the visually impaired.                                                                                                                                    |
|                         |                               | ***VisualSigns­Available***  |      | true \| false \| unknown | Whether a Place has visual signals for the hearing impaired.                                                                                                                                      |
| Suitab­ility            | ***Suitabilities***           |                              | 0:1  | many                     | Suitabilities of facility for specific passenger needs                                                                                                                                            |
|                         |                               | ***Suitability***            | 0:\* | +Structure               | Suitability of facility for a specific passenger need. See earlier                                                                                                                                |
| any                     | Extensions                    |                              | 0:1  | any                      | Placeholder for user extensions.                                                                                                                                                                  |

## Publication

|                     |                       |      |            |                                                                                                                                                                                                      |
| ------------------- | --------------------- | ---- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ActionsStructure    |                       |      | +Structure | Structured model describing distribution actions to handle SITUATION. Any actions stated completely replace those from Context. If no actions are stated, any actions from general Context are used. |
| Publication actions | PublishToWebAction    | 0:\* | +Structure | Action: Publish SITUATION To Web.                                                                                                                                                                    |
|                     | PublishToMobileAction | 0:\* | +Structure | Action: Publish SITUATION To Smartphone, WAP and PDA.                                                                                                                                                |
|                     | PublishToTvAction     | 0:\* | +Structure | Action: Publish SITUATION To TvService.                                                                                                                                                              |
|                     | PublishToAlertsAction | 0:\* | +Structure | Action: Publish SITUATION To Alert Service.                                                                                                                                                          |
|                     | ManualAction          | 0:\* | +Structure | Action: Publish SITUATION Manually. i.e. a procedure must be carried out                                                                                                                             |
|                     | NotifyByEmailAction   | 0:\* | +Structure | Action: Publish SITUATION to a named workgroup or individual by email.                                                                                                                               |
|                     | NotifyBySmsAction     | 0:\* | +Structure | Action: Publish SITUATION to an individual by SMS.                                                                                                                                                   |
|                     | NotifyByPagerAction   | 0:\* | +Structure | Action: Publish SITUATION To pager.                                                                                                                                                                  |
|                     | NotifyUserAction      | 0:\* | +Structure | Action: Publish SITUATION To User.                                                                                                                                                                   |
| any                 | Extensions            | 0:1  | any        | Placeholder for user extensions.                                                                                                                                                                     |

## Publication Web

|                             |              |        |      |                       |                                                                          |
| --------------------------- | ------------ | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| PublishToWebActionStructure |              |        |      | +Structure            |                                                                          |
|                             | ActionStatus |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                             | Description  |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                             | ActionData   |        | 0:\* |                       | Data associated with action.                                             |
|                             |              | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                             |              | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                             |              | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                             |              | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                             | Incidents    |        | 0:1  | xsd:boolean           | Include in SITUATION lists on web site. Default is 'true'                |
|                             | HomePage     |        | 0:1  | xsd:boolean           | Include on home page on web site. Default is 'false'                     |
|                             | Ticker       |        | 0:1  | xsd:boolean           | Include in moving ticker band. Default is 'false'.                       |

## Publication Mobile

|                                |              |        |      |                       |                                                                          |
| ------------------------------ | ------------ | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| PublishToMobileActionStructure |              |        |      | +Structure            |                                                                          |
|                                | ActionStatus |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                                | Description  |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                                | ActionData   |        | 0:\* |                       | Data associated with action.                                             |
|                                |              | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                                |              | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                                |              | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                                |              | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                                | Incidents    |        | 0:1  | xsd:boolean           | Include in SITUATION lists on web site. Default is 'true'                |
|                                | HomePage     |        | 0:1  | xsd:boolean           | Include on home page on web site. Default is 'false'                     |

## Publication Télévisuelle

|                            |              |        |      |                       |                                                                          |
| -------------------------- | ------------ | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| PublishToTvActionStructure |              |        |      | +Structure            |                                                                          |
|                            | ActionStatus |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                            | Description  |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                            | ActionData   |        | 0:\* |                       | Data associated with action.                                             |
|                            |              | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                            |              | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                            |              | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                            |              | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                            | Ceefax       |        | 0:1  | xsd:boolean           | Publish to Teltext. Default is 'true'.                                   |
|                            | Teletext     |        | 0:1  | xsd:boolean           | Publish to Ceefax. Default is 'true'.                                    |

## Publication vers service d'alerte

|                                |               |        |      |                       |                                                                          |
| ------------------------------ | ------------- | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| PublishToAlertsActionStructure |               |        |      | +Structure            |                                                                          |
|                                | ActionStatus  |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                                | Description   |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                                | ActionData    |        | 0:\* |                       | Data associated with action.                                             |
|                                |               | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                                |               | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                                |               | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                                |               | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                                | BeforeNotices |        | 0:1  | No type               | Whether reminders should be sent.                                        |
|                                | ClearNotice   |        | 0:1  | xsd:boolean           | Whether a clearing notice should be displayed.                           |
|                                | ByEmail       |        | 0:1  | xsd:boolean           | Send as email alert.                                                     |
|                                | ByMobile      |        | 0:1  | xsd:boolean           | Send as mobile alert by SMS or WAP push.                                 |

## Publication "manuelle" (mise en place d'une procédure)

|                       |              |        |      |                       |                                                                          |
| --------------------- | ------------ | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| ManualActionStructure |              |        |      | +Structure            |                                                                          |
|                       | ActionStatus |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                       | Description  |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                       | ActionData   |        | 0:\* |                       | Data associated with action.                                             |
|                       |              | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                       |              | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                       |              | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                       |              | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |

## Publication par email

|                              |               |        |      |                       |                                                                          |
| ---------------------------- | ------------- | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| NotifyByEmailActionStructure |               |        |      | +Structure            |                                                                          |
|                              | ActionStatus  |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                              | Description   |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                              | ActionData    |        | 0:\* |                       | Data associated with action.                                             |
|                              |               | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                              |               | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                              |               | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                              |               | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                              | BeforeNotices |        | 0:1  | No type               | Whether reminders should be sent.                                        |
|                              | ClearNotice   |        | 0:1  | xsd:boolean           | Whether a clearing notice should be displayed.                           |
|                              | email         |        | 0:1  | EmailAddressType      | Email address to which notice should be sent.                            |

## Publication par SMS

|                            |               |        |      |                       |                                                                          |
| -------------------------- | ------------- | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| NotifyBySmsActionStructure |               |        |      | +Structure            |                                                                          |
|                            | ActionStatus  |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                            | Description   |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                            | ActionData    |        | 0:\* |                       | Data associated with action.                                             |
|                            |               | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                            |               | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                            |               | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                            |               | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                            | BeforeNotices |        | 0:1  | No type               | Whether reminders should be sent.                                        |
|                            | ClearNotice   |        | 0:1  | xsd:boolean           | Whether a clearing notice should be displayed.                           |
|                            | Phone         |        | 0:1  | PhoneType             | MSISDN of user to which to send messages.                                |
|                            | Premium       |        | 0:1  | xsd:boolean           | Whether content is flagged as subject to premium charge.                 |

## Publication par pager

|                              |               |        |      |                       |                                                                          |
| ---------------------------- | ------------- | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| NotifyByPagerActionStructure |               |        |      | +Structure            |                                                                          |
|                              | ActionStatus  |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                              | Description   |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                              | ActionData    |        | 0:\* |                       | Data associated with action.                                             |
|                              |               | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                              |               | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                              |               | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                              |               | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                              | BeforeNotices |        | 0:1  | No type               | Whether reminders should be sent.                                        |
|                              | ClearNotice   |        | 0:1  | xsd:boolean           | Whether a clearing notice should be displayed.                           |
|                              | PagerGroupRef |        | 0:1  | xsd:string            | Reference to a pager group to be notfied.                                |
|                              | Pager         |        | 0:1  | xsd:NMTOKEN           | Pager number of pager to be notfied.                                     |

## Publication pour un utilisateur spécifique

|                              |               |        |      |                       |                                                                          |
| ---------------------------- | ------------- | ------ | ---- | --------------------- | ------------------------------------------------------------------------ |
| NotifyByPagerActionStructure |               |        |      | +Structure            |                                                                          |
|                              | ActionStatus  |        | 0:1  | enum                  | Processing Status of action at time of SITUATION publication.            |
|                              | Description   |        | 0:1  | NaturalLanguageString | Description of action                                                    |
|                              | ActionData    |        | 0:\* |                       | Data associated with action.                                             |
|                              |               | Name   | 1:1  | xsd:NMTOKEN           | Name of action data Element.                                             |
|                              |               | Type   | 1:1  | xsd:NMTOKEN           | Data type of action data.                                                |
|                              |               | Value  | 1:\* | xsd:anyType           | Value for action.                                                        |
|                              |               | Prompt | 0:\* | NaturalLanguageString | Display prompt for presenting action to user. (Unbounded since SIRI 2.0) |
|                              | BeforeNotices |        | 0:1  | No type               | Whether reminders should be sent.                                        |
|                              | ClearNotice   |        | 0:1  | xsd:boolean           | Whether a clearing notice should be displayed.                           |
|                              | WorkgroupRef  |        | 0:1  | xsd:string            | Workgroup of user to be notified.                                        |
|                              | UserName      |        | 0:1  | xsd:string            | Name of user to be notified.                                             |
|                              | UserRef       |        | 0:1  | xsd:string            | Reference to a user to be notified.                                      |

## Utilisation de Situation Exchange en lieu et place de General Message.

Note: Les lignes qui suivent sont spécifiques au profil FR.

Le service Situation Exchange peut être utilisé en lieu et place du
service General Message tel qu'il a été particularisé dans le cadre du
profil France. Cela permettra d'éviter une utilisation combinée des deux
services, tout en permettant aux acteurs qui le souhaitent d'utiliser le
service en restant sur le périmètre fonctionnel retenu pour General
Message.

Seule la compatibilité concernant les filtres de requête n'est pas
totale. Ainsi, les filtres ***DestinationRef***, ***RouteRef*** et
***JourneyPatternRef*** ne sont pas disponibles au niveau de Situation
Exchange. Mais l'information est disponible dans les réponses.

On notera aussi certaines différences de mode de fonctionnement. Ainsi
le service Situation Exchange ne dispose pas d'InfoMessageCancellation,
mais effectue cette notification en positionnant l'attribut Progress à
Closed (PtSituationElement).

Notons aussi que, par nature, le champ SituationRef de General Message
n'a pas de correspondance car il a pour vocation de permettre de faire
le lien avec une Situation de Situation Exchange, ce qui n'a guère
d'intérêt ici….

|       |                                                                                                                                                    |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| SX-01 | ~~On notera enfin que l~~ Le champ ValidUntil utilisé dans Situation exchange est celui de l'entête du message (AbstractServiceDeliveryStructure). |

Les messages textuels eux même seront traités de la façon suivante :

<table>
<colgroup>
<col style="width: 7%" />
<col style="width: 92%" />
</colgroup>
<tbody>
<tr class="odd">
<td>SX-02</td>
<td><ul>
<li><p><strong>shortMessage</strong> : Message dans Summary (dans <em><strong>PtSituationElement</strong></em>)</p></li>
<li><p><strong>longMessage</strong> : Message dans Description (dans <em><strong>PtSituationElement</strong></em>)</p></li>
<li><p><strong>textOnly</strong> : Type MIME <em><strong>text/plain</strong></em> (dans Summary ou Description suivant que le message est court ou long) avec un champ additionnel " Content-Description: SIRI-FR-IDF no line break message".</p></li>
</ul>
<p>Note: il n'y a pas de type MIME générique excluant les sauts de ligne, d’où cet usage du champ MIME Content-Description.</p>
<ul>
<li><p><strong>formattedText</strong> : Type MIME <strong>text/plain</strong> (dans Summary ou Description suivant que le message est court ou long).</p></li>
</ul>
<p>Note: les champs <em><strong>NumberOfLines</strong></em> et <em><strong>NumberOfCharPerLine</strong></em> n'ont pas d'équivalent dans Situation Exchange, mais peuvent aisément être recalculés à partir du message lui-même.</p>
<ul>
<li><p><strong>HTML</strong> : Type MIME <em><strong>text/html</strong></em> (dans Summary ou Description suivant que le message est court ou long)</p></li>
<li><p><strong>RTF</strong> : Type MIME <em><strong>text/rtf</strong></em> (dans Summary ou Description suivant que le message est court ou long)</p></li>
<li><p>codedMessage : Message dans <em>ReasonName</em> (dans <em>PtSituationElement</em>)</p></li>
</ul></td>
</tr>
</tbody>
</table>

Exemple de message :

MIME-Version: 1.0

Content-Type: text/plain

Content-Description: SIRI-FR-IDF no line break message

Ceci est un Message

Les tableaux ci-dessous reprennent ceux du service Situation Exchange en
se limitant aux éléments nécessaires pour assurer cette compatibilité.

Requête pour l’obtention d’information sur les événements et leurs
conséquences (perturbations)

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 14%" />
<col style="width: 4%" />
<col style="width: 14%" />
<col style="width: 59%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">SituationExchangeRequest</td>
<td>+Structure</td>
<td>Request for information about facilities status</td>
</tr>
<tr class="even">
<td>Attrib­utes</td>
<td>Version</td>
<td>1:1</td>
<td>Version­String</td>
<td>Version Identifier of Stop Monitoring Service, e.g. ‘1.0c’.</td>
</tr>
<tr class="odd">
<td rowspan="2">Message Id</td>
<td>Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td rowspan="2">See SIRI Part 2 Common properties of SIRI Functional Service Requests.</td>
</tr>
<tr class="even">
<td>Message­Identifier</td>
<td>0:1</td>
<td>Message­Qualifier</td>
</tr>
<tr class="odd">
<td rowspan="2">Topic</td>
<td>Keywords</td>
<td>0:*</td>
<td>string</td>
<td><p>Any arbitrary filter keywords to use.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, seules les valeurs suivantes seront utilisées et permettent de gérer la mise en cohérence avec les canaux General Message :</p>
<ul>
<li><p>«Perturbation»</p></li>
<li><p>«Information»</p></li>
<li><p>«Commercial»</p></li>
</ul></td>
</tr>
<tr class="even">
<td>Situation­NetworkFilter</td>
<td>0:1</td>
<td>structure</td>
<td>Filter the results to include only Situations relating to the network filter elements</td>
</tr>
<tr class="odd">
<td>Request Policy</td>
<td>Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td><p>Preferred language in which to return text values.</p>
<p>Optional SIRI capability: <em>National­Language.</em></p></td>
</tr>
</tbody>
</table>

|                        |              |      |                 |                                                                                        |
| ---------------------- | ------------ | ---- | --------------- | -------------------------------------------------------------------------------------- |
| SituationNetworkFilter |              |      | +Structure      | Filter values for Network elements                                                     |
| Filter                 | NetworkRef   | 0:1  | Network­Code   | Filter the results to include only Situations relating to the Operational Unit.        |
|                        | LineRef      | 0:\* | LineCode       | Filter the results to include only Situations for the given line.                      |
|                        | StopPointRef | 0:1  | StopPoint­Code | Filter the results to include only Situations relating to the Stop Point or Stop Area. |

## Abonnement pour l’obtention d’information sur les événements et leurs conséquences (perturbations)

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 19%" />
<col style="width: 6%" />
<col style="width: 16%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">Situation ExchangeMonitoring­SubscriptionRequest</td>
<td>+Structure</td>
<td>Request for a subscription to the Vehicle Monitoring Service.</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td>SubscriberRef</td>
<td>0:1</td>
<td>Participant­Code</td>
<td rowspan="3">See SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.</td>
</tr>
<tr class="odd">
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>SituationExchange­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>See SituationExchangeRequest.</td>
</tr>
<tr class="even">
<td>Policy</td>
<td>Incremental­Updates</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Whether the producer should only provide updates to the last data returned, i.e. additions, modifications and deletions, or always return the complete set of current data, Default is true, i.e. once the initial transmission has been made, return only incremental updates.</p>
<p>If <em>false</em> each subscription response will contain the full information as specified in this request.</p>
<p>Optional SIRI capability: <em>IncrementalUpdates.</em></p></td>
</tr>
</tbody>
</table>

## Réponse aux demandes d’information sur les événements et leurs conséquences (perturbations)

|                           |                    |      |               |                                                                       |
| ------------------------- | ------------------ | ---- | ------------- | --------------------------------------------------------------------- |
| SituationExchangeDelivery |                    |      | +Structure    | Describes the status of facilities.                                   |
| Attrib­utes               | version            | 1:1  | VersionString | Version Identifier of Situation Exchange Service. Fixed, e.g. ‘1.1a’. |
| LEADER                    | :::                | 1:1  | xxx­Delivery  | See SIRI Part 2-7.2.1.1 xxx***Delivery**.*                            |
| Pay­load                  | PtSituationElement | 0:\* | +Structure    | Describes a Situation                                                 |

## Description de l’événement (cause de la perturbation)

<table style="width:100%;">
<colgroup>
<col style="width: 12%" />
<col style="width: 2%" />
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 14%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">PtSituationElement</td>
<td>+Structure</td>
<td>Disruption affecting services.</td>
</tr>
<tr class="even">
<td>Log</td>
<td colspan="2">CreationTime</td>
<td>1:1</td>
<td>dateTime</td>
<td>Time of creation of Situation</td>
</tr>
<tr class="odd">
<td rowspan="3">Identity</td>
<td colspan="2">ParticipantRef</td>
<td>1:1</td>
<td>Participan­t­Code</td>
<td>Identifier of participant system that creates Situation. See Part 2. Unique within Country</td>
</tr>
<tr class="even">
<td colspan="2">SituationNumber</td>
<td>1:1</td>
<td>Situation­Numberr</td>
<td><p>Unique Identifier of Situation within Participant</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, correspond au <em><strong>InfoMessageIdentifier.</strong></em></p></td>
</tr>
<tr class="odd">
<td colspan="2">Version</td>
<td>0:1</td>
<td>Version</td>
<td><p>Version of Update Situation element</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, correspond au <em><strong>InfoMessageVersion.</strong></em></p></td>
</tr>
<tr class="even">
<td>Source</td>
<td colspan="2">Source</td>
<td>1:1</td>
<td>+Structure</td>
<td><p>Information about source of information, that is, where the agent using the capture client obtained an item of information, or in the case of an automated feed, an identifier of the specific feed. Can be used to obtain updates, verify details or otherwise assess relevance. See below.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, seul le champ <strong>SourceType</strong> de la structure sera utilisé, et positionné à <em><strong>directReport.</strong></em></p></td>
</tr>
<tr class="odd">
<td>Status</td>
<td colspan="2">Progress</td>
<td>0:1</td>
<td>enum</td>
<td><p>Status of Situation. See below.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, seuls les codes <em><strong>Open</strong></em> et <em><strong>Closed</strong></em> sont utilisés. Le <em><strong>Closed</strong></em> équivaut alors à un <strong>InfoMessageCancellation</strong></p></td>
</tr>
<tr class="even">
<td rowspan="2">Classifier Group</td>
<td colspan="2">ReasonName</td>
<td>0:1</td>
<td>string</td>
<td><p>Text explanation of situation reason. Not normally needed.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, ce champ sera utlisé pour les messages de type <em><strong>codedMessage</strong></em> (le champ porte alors valeur du <strong>MessageText</strong> pour les messages de type <em><strong>codedMessage).</strong></em></p></td>
</tr>
<tr class="odd">
<td colspan="2">Keywords</td>
<td>0:*</td>
<td>string</td>
<td><p>Arbitrary application specific classifiers.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, seules les valeurs suivantes seront utilisées et permettent de gérer la mise en cohérence avec les canaux General Message :</p>
<ul>
<li><p>«Perturbation»</p></li>
<li><p>«Information»</p></li>
<li><p>«Commercial»</p></li>
</ul></td>
</tr>
<tr class="even">
<td rowspan="2">Classifier Group</td>
<td colspan="2">Summary</td>
<td>0:*</td>
<td>DefaultedText</td>
<td>Summary of situation. If absent should be generated from structure elements / and or by condensing Description. For use of defaulted text see below.</td>
</tr>
<tr class="odd">
<td colspan="2">Description</td>
<td>0:*</td>
<td>DefaultedText</td>
<td>Description of situation. Should not repeat any strap line included in Summary See below.</td>
</tr>
<tr class="even">
<td rowspan="2">Consequence</td>
<td colspan="2">Consequences</td>
<td>0:1</td>
<td>many</td>
<td>One or more consequences.</td>
</tr>
<tr class="odd">
<td></td>
<td>Consequence</td>
<td>0:*</td>
<td>+Structure</td>
<td>Consequence of the situation. See below.</td>
</tr>
</tbody>
</table>

## Description de la source d’information ayant fourni la description de la perturbation

<table>
<colgroup>
<col style="width: 8%" />
<col style="width: 21%" />
<col style="width: 6%" />
<col style="width: 17%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">SituationSource</td>
<td>+Structure</td>
<td>Where the information about the Situation came from.</td>
</tr>
<tr class="even">
<td></td>
<td>SourceType</td>
<td>1:1</td>
<td>enum</td>
<td><p>Nature of Source communication type. See below.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, seul le champ <strong>SourceType</strong> de la structure sera utilisé, et positionné à <em><strong>directReport.</strong></em></p></td>
</tr>
</tbody>
</table>

## Information textuelle associée aux pertubation

|               |        |     |            |                            |
| ------------- | ------ | --- | ---------- | -------------------------- |
| DefaultedText |        |     | +Structure | Overridable Text element   |
| Identity      | lang   | 0:1 | lang       | Language for text content. |
|               | string | 0:1 | string     | Text content               |

## Description globale des conséquences

|             |         |     |              |                                                                                      |
| ----------- | ------- | --- | ------------ | ------------------------------------------------------------------------------------ |
| Consequence |         |     | +Structure   | Effect of a Situation on services.                                                   |
| Scope       | Affects | 0:1 | AffectsScope | Structured model identifying parts of transport t affected by consequence. See Below |

## AffectsScope

|              |            |                   |      |            |                                           |
| ------------ | ---------- | ----------------- | ---- | ---------- | ----------------------------------------- |
| AffectsScope |            |                   |      | +Structure | The scope of the situation or consequence |
| Stops        | StopPoints |                   | 0:\* | +Structure | Scheduled Stop Point scope                |
|              |            | AffectedStopPoint | 0:1  | +Structure | Scheduled Stop Point scope. See below.    |
| network      | Networks   |                   | 0:\* | +Structure | Networks scope.                           |
|              |            | AffectedNetwork   | 0:1  | +Structure | Network scope. See below.                 |

## Conséquences sur un réseau

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 3%" />
<col style="width: 22%" />
<col style="width: 6%" />
<col style="width: 12%" />
<col style="width: 45%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">AffectedNetwork</td>
<td>+Structure</td>
<td>The scope of the situation or consequence</td>
</tr>
<tr class="even">
<td>network</td>
<td colspan="2">NetworkRef</td>
<td>0:1</td>
<td>Network­Code</td>
<td>Network of affected line. If absent, may be taken from context.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">RoutesAffected</td>
<td>0:1</td>
<td>nlString</td>
<td><p>Textual description of overall routes affected. Should correspond to any structured description.</p>
<p>Dans le cas de l'utilisation en lieu et place de General Message, ce champ est détourné pour porter le nom des missions (Journey Pattern) concernées<em><strong>.</strong></em> <del>Il portera donc principalement le nom des missions de RER et Transilien.</del></p></td>
</tr>
<tr class="even">
<td rowspan="2">network</td>
<td colspan="2">Lines</td>
<td>0:1</td>
<td>choice</td>
<td>Line scope.</td>
</tr>
<tr class="odd">
<td>c</td>
<td>AffectedLine</td>
<td>0:*</td>
<td>+Structure</td>
<td>Line affected by situation. See Below.</td>
</tr>
</tbody>
</table>

## Conséquences sur une ligne ou une section de ligne

|              |              |                    |      |                           |                                                                     |
| ------------ | ------------ | ------------------ | ---- | ------------------------- | ------------------------------------------------------------------- |
| AffectedLine |              |                    |      | +Structure                | Annotated Reference to Line                                         |
| Operat­or    | LineRef      |                    | 0:1  | Line­Code                | Identifier of Line.                                                 |
|              | Destinations |                    | 0:\* | choice                    | Routes scope.                                                       |
|              |              | AffectedStop­Point | 0:1  | +Structure                | Annotated reference to destination Stop Point affected by Situation |
| Routes       | Routes       |                    | 0:\* | choice                    | Routes scope.                                                       |
|              |              | AffectedRoute      | 0:1  | Affect+Structure edRoute | Route affected by Situation..                                       |
| Sect­ions    | Sections     |                    | 0:\* | choice                    | Section of Line scope.                                              |
|              |              | Section            | 0:1  | +Structure                | Identifier of Section affected by Situation.                        |

## Conséquences sur un itinéraire

|               |          |     |             |                              |
| ------------- | -------- | --- | ----------- | ---------------------------- |
| AffectedRoute |          |     | +Structure  | Annotated Reference to Route |
| Route         | RouteRef | 0:1 | Route­Code | Identifier of Line.          |

## Conséquences sur un point d’arrêt

|                   |              |     |                 |                                   |
| ----------------- | ------------ | --- | --------------- | --------------------------------- |
| AffectedStopPoint |              |     | +Structure      | Annotated Reference to Stop Point |
| Stop              | StopPointRef | 0:1 | StopPoint­Code | Identifier of Stop Point.         |

3.  <span id="__RefHeading___Toc26889694"
    class="anchor"></span>(informative)Number range aaaNumber range
    TableNumber range Figure  
      
    SIRI Facility Monitoring

    1.  ## Matrice de capacité du service sur état des équipements

Le rapport des messages ***FacilityMonitoringCapabilitiesRequest*** */*
***FacilityMonitoringCapabilities-Response*** peut être utilisé pour
déterminer les capacités de mise en oeuvre définies pour le FM.

|                                |                    |                             |      |                         |      |                                                                                                                                                           |     |     |     |
| ------------------------------ | ------------------ | --------------------------- | ---- | ----------------------- | ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | --- | --- | --- |
| FacilityMonitoringCapabilities |                    |                             |      | +Structure              |      | Capabilities describing implementation of Facility Monitoring service.                                                                                    |     |     |     |
| inherit                        | :::                |                             | 0:1  | See Capability-response | xxx- | See SIRI Part 2-12.4 for Common Capability attributes.                                                                                                    |     |     |     |
| Topic                          | TopicFiltering     |                             | 0:1  | +Structure              |      | Which optional filtering features are supported                                                                                                           |     |     |     |
|                                |                    | FilterByFacilityRef         | 1:1  | xsd:boolean             |      | Whether results can be filtered by location. Fixed as true.                                                                                               |     |     |     |
|                                |                    | DefaultPreviewInterval      | 1:1  | xsd:boolean             |      | Default preview interval. Default is 60 minutes                                                                                                           |     |     |     |
|                                |                    | FilterByLocationRef         | 1:1  | xsd:boolean             |      | Whether results can be filtered by Monitoring point. Required Facility: Fixed as true.                                                                    |     |     |     |
|                                |                    | FilterByVehicleRef          | 0:1  | xsd:boolean             |      | Whether results can be filtered by Vehicle. Default is false.                                                                                             |     |     |     |
|                                |                    | FilterByLineRef             | 0:1  | xsd:boolean             |      | Whether results can be filtered by Line. Default is true                                                                                                  |     |     |     |
|                                |                    | FilterByStopPointRef        | 0:1  | xsd:boolean             |      | Whether results can be filtered by Stop Point. Default is true.                                                                                           |     |     |     |
|                                |                    | FilterByVehicle- JourneyRef | 0:1  | xsd:boolean             |      | Whether results can be filtered by VehicleJourney. Default is false.                                                                                      |     |     |     |
|                                |                    | FilterByConnection- LinkRef | 0:1  | xsd:boolean             |      | Whether results can be filtered by Connection link. Default is true.                                                                                      |     |     |     |
|                                |                    | FilterByInterchangeRef      | 0:1  | xsd:boolean             |      | Whether results can be filtered by Interchange. Default is false.                                                                                         |     |     |     |
|                                |                    | FilterBySpecificNeed        | 0:1  | xsd:boolean             |      | Whether results can be filtered by Specific Needs. Default is true                                                                                        |     |     |     |
| Request Policy                 | RequestPolicy      |                             | 0:1  | +Structure              |      | Which features of ***RequestPolicy*** are supported by service?                                                                                           |     |     |     |
|                                |                    | Language                    | 1:\* | xsd:language            |      | National languages used by service.                                                                                                                       |     |     |     |
|                                |                    | GmlCoordinateFormat         | 1:1  | SrsNameType             |      | Default coordinate format is given by a GML value.                                                                                                        |     |     |     |
|                                |                    | WgsDecimalDegrees           |      | EmptyType               |      | Default coordinate data system is WGS 84 latitude and longitude.                                                                                          |     |     |     |
|                                |                    | HasMaximumFacility-Status   | 0:1  | xsd:boolean             |      | Whether *DetailLevel* filtering is supported. Default *false*. Whether a maximum number of Facility Status to include can be specified. Default is false. |     |     |     |
| Subscription-Policy            | SubscriptionPolicy |                             | 0:1  | +Structure              |      | Which features of ***SubscriptionPolicy*** are supported by service?                                                                                      |     |     |     |
|                                |                    | HasIncremental-updates      | 0:1  | xsd:boolean             |      | Whether incremental updates can be specified for updates Default is *true*.                                                                               |     |     |     |
|                                |                    | HasChangeSensitivity        | 0:1  | xsd:boolean             |      | Whether change threshold can be specified for updates. Default is *true*.                                                                                 |     |     |     |
| Access                         | AccessControl      |                             | 0:1  | +Structure              |      | Which optional Access Control features are supported by service?                                                                                          |     |     |     |
|                                |                    | RequestChecking             | 1:1  | xsd:boolean             |      | Whether access control of requests is supported. Default is *false*.                                                                                      |     |     |     |
|                                |                    | CheckOperatorRef            | 0:1  | xsd:boolean             |      | If access control is supported, whether access control by Operator is supported Default is *true*.                                                        |     |     |     |
|                                |                    | CheckLineRef                | 0:1  | xsd:boolean             |      | If access control is supported, whether access control by Line is supported. Default is true.                                                             |     |     |     |
| Response                       | ResponseFeatures   |                             | 0:1  | +Structure              |      | Which features of Response data are supported by service?                                                                                                 |     |     |     |
|                                |                    | HasFacilityLocation         | 0:1  | xsd:boolean             |      | Whether result supports facility location information Default is true.                                                                                    |     |     |     |
| any                            | Extensions         |                             | 0:1  | \+                      |      | Placeholder for user extensions                                                                                                                           |     |     |     |

## Requête d’information sur l’état des équipements *(the FacilityMonitoringRequest)*

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 22%" />
<col style="width: 5%" />
<col style="width: 16%" />
<col style="width: 39%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">FacilityMonitoringRequest</td>
<td>+Structure</td>
<td>Request for information about facilities status</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td>Version</td>
<td>1:1</td>
<td>Version­String</td>
<td>Version Identifier of Facility Monitoring Service, intégrant le numéro de version de profil (voir 5) par exemple. ‘2.0:FR -1.0’avec valeur fixe</td>
</tr>
<tr class="odd">
<td rowspan="2">Endpoint Properties</td>
<td>Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>See SIRI Part 2 Common properties of SIRI Functional Service Requests.</td>
</tr>
<tr class="even">
<td>Message­Identifier</td>
<td>1:1</td>
<td>Message­Qualifier</td>
<td></td>
</tr>
<tr class="odd">
<td rowspan="4">Topic</td>
<td>Preview­Interval</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Forward duration for which Visits should be included, that is, interval before predicted arrival at the stop for which to include visits: only journeys which will arrive or depart within this time span will be returned.</td>
</tr>
<tr class="even">
<td>StartTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Initial start time for <em><strong>PreviewInterval</strong></em>. If absent, then current time is assumed. Must be within data Horizon.</td>
</tr>
<tr class="odd">
<td>FacilityRef</td>
<td><p>0:1</p>
<p>0:*</p></td>
<td>FacilityCode</td>
<td>The Facility for which status will be returned.</td>
</tr>
<tr class="even">
<td>StopPointRef</td>
<td>0:1</td>
<td>StopPoint­Code</td>
<td>All the status of facilities located on this Stop Point or Stop Area will be returned.</td>
</tr>
<tr class="odd">
<td rowspan="3"></td>
<td>LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Filter the results to include only facilities for the given line.</td>
</tr>
<tr class="even">
<td>Vehicle­Journey­Ref</td>
<td>0:1</td>
<td>Vehicle-Journey­Code</td>
<td>Filter the results to include only facilities for the given Vehicle Journey.</td>
</tr>
<tr class="odd">
<td>Connection­Link­Ref</td>
<td>0:1</td>
<td>Connection-LinkCode</td>
<td>Filter the results to include only facilities located on the given Connection Link</td>
</tr>
<tr class="even">
<td rowspan="3"></td>
<td>VehicleRef</td>
<td>0:1</td>
<td>Vehicle­Code</td>
<td>Filter the results to include only facilities located in the given Vehicle</td>
</tr>
<tr class="odd">
<td>Interchange­Ref</td>
<td>0:1</td>
<td>Interrchange­Code</td>
<td>Filter the results to include only facilities for the given Interchange.</td>
</tr>
<tr class="even">
<td>Specifical­Need­Service­Filter</td>
<td>0:1</td>
<td>Auditory | wheelChair | motorized<em>­</em>WheelChair | mobility | visual | cognitive | psychiatric | incapaciting<em>­</em>disease | young<em>­</em>Passenger | luggage<em>­</em>Encumbered | stroller | elderly | other<em>­</em>SpecificNeed</td>
<td>All the status of facilities located concerning this specific need will be returned (both available or not available informations).</td>
</tr>
<tr class="odd">
<td rowspan="2">Request Policy</td>
<td>Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td><p>Preferred language in which to return text values.</p>
<p>Optional SIRI capability: <em>National­Language.</em></p></td>
</tr>
<tr class="even">
<td>MaximumFacility­Status</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>The maximum number of facility status in a given delivery. The most recent n Events within the look ahead window are included.</td>
</tr>
<tr class="odd">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

Exemple de rêquete FM :

\<ServiceRequest">

\<!--======ENDPOINT REFERENCES================================-->
\<RequestorRef>NADER\</RequestorRef>
\<RequestTimestamp>2004-12-17T09:30:47-05:00\</RequestTimestamp>
\<FacilityMonitoringRequest version="1.1">

\<RequestTimestamp>2004-12-17T09:30:47-05:00\</RequestTimestamp>
\<!--=======TOPIC ===================================== -->
\<StopPointRef>SPR55\</StopPointRef>

\<AccessibilityNeedsFilter>

\<UserNeed>wheelChair\</UserNeed>

\</AccessibilityNeedsFilter>

\</FacilityMonitoringRequest>

\</ServiceRequest>

## Requête d’abonnement sur l’état des équipements *(the FacilityMonitoring Subscription Request)*

<table>
<colgroup>
<col style="width: 9%" />
<col style="width: 18%" />
<col style="width: 5%" />
<col style="width: 15%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="2">VehicleMonitoring-</td>
<td></td>
<td>+Structure</td>
<td>Request for a subscription to the Vehicle Monitoring Service.</td>
</tr>
<tr class="even">
<td colspan="2">SubscriptionRequest</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>SubscriberRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant- Code</td>
<td>See SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.</td>
</tr>
<tr class="even">
<td></td>
<td>Subscription- Identifier</td>
<td>1:1</td>
<td>Subscription- Qualifier</td>
<td></td>
</tr>
<tr class="odd">
<td>Lease</td>
<td>InitialTermination- Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td></td>
</tr>
<tr class="even">
<td>Request</td>
<td>FacilityMonitoring- Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>See FacilityMonitoringRequest.</td>
</tr>
<tr class="odd">
<td>Policy</td>
<td>Incremental- Updates</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>xsd:boolean</td>
<td><p>Whether the producer should only provide updates to the last data returned, i.e. additions, modifications and deletions, or always return the complete set of current data, Default is true, i.e. once the initial transmission has been made, return only incremental updates. If <em>false</em> each subscription response will contain the full information as specified in this request.</p>
<p>Optional SIRI capability: <em>IncrementalUpdates.</em></p></td>
</tr>
</tbody>
</table>

**Exemple de requête** FacilityMonitoringSubscriptionRequest :

\<SubscriptionRequest>

\<!--======ENDPOINT REFERENCES================================-->
\<RequestorRef>NADER\</RequestorRef>
\<RequestTimestamp>2004-12-17T09:30:47-05:00\</RequestTimestamp> \<!--
Subscription 1 for SPR55 --> \<FacilityMonitoringSubscriptionRequest>

\<SubscriptionIdentifier>00000456\</SubscriptionIdentifier>
\<InitialTerminationTime>2004-12-17T09:30:47-05:00\</InitialTerminationTime>
\<!-- ====== ENDPOINT REFERENCE =====================-->

\< FacilityMonitoringRequest version="1.1">
\<RequestTimestamp>2004-12-17T09:30:47-05:00\</RequestTimestamp>
\<!--=======TOPIC ===================================== -->
\<StopPointRef>SPR55\</StopPointRef>

\<AccessibilityNeedsFilter>

\<UserNeed>wheelChair\</UserNeed>

\</AccessibilityNeedsFilter>

\</FacilityMonitoringRequest>

\</FacilityMonitoringSubscriptionRequest>

\<!-- Subscription 2 for SPR56 -->

\<FacilityMonitoringSubscriptionRequest>

\<SubscriptionIdentifier>00000456\</SubscriptionIdentifier>
\<InitialTerminationTime>2004-12-17T09:30:47-05:00\</InitialTerminationTime>
\<!-- ====== ENDPOINT REFERENCE =====================-->

\< FacilityMonitoringRequest version="1.1">
\<RequestTimestamp>2004-12-17T09:30:47-05:00\</RequestTimestamp>
\<!--=======TOPIC ===================================== -->
\<StopPointRef>SPR56\</StopPointRef> \<AccessibilityNeedsFilter>

\<UserNeed>wheelChair\</UserNeed>

\</AccessibilityNeedsFilter>

\</FacilityMonitoringRequest>

\</FacilityMonitoringSubscriptionRequest>

\</SubscriptionRequest>

## Structure FacilityMonitoringDelivery

La structure ***FacilityMonitoringDelivery*** (incluse dans la structure
***ServiceDelivery***) permet de livrer au Hub plusieurs états
d’équipement (***FacilityCondition***).

|                            |                   |      |                    |     |                                                                                     |
| -------------------------- | ----------------- | ---- | ------------------ | --- | ----------------------------------------------------------------------------------- |
| FacilityMonitoringDelivery |                   |      | +Structure         |     | Describes the status of facilities.                                                 |
| Attributes                 | version           | 1:1  | VersionString      |     | Version Identifier of Vehicle Monitoring Service. Fixed, e.g. 1.1a . "**2.0FR1.0**" |
| LEADER                     | :::               | 1:1  | xxxServiceDelivery |     | Voir paragraphe 2.2*.*                                                              |
| Payload                    | FacilityCondition | 0:\* | +Structure         |     | Describes the status of a facility.                                                 |
| any                        | Extensions        | 0:1  | +Structure         |     | Voir paragraphe 5.4.2.2                                                             |

## Description générale d’un équipement et de son état *(the FacilityCondition element)*

|                    |                 |     |                                     |                                                                                                                         |
| ------------------ | --------------- | --- | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| FacilityCondition  |                 |     | +Structure                          | Describes the status of a facility                                                                                      |
| Timing information | Validity­Period | 0:1 | Half­Open­Timestamp­Range Structure | Validity period (start & duration) of the status for the facility. The Start Time may be predate from the request date. |
| Facility           | Facility        | 1:1 | +Structure                          | Generic description of a facility (see **Facility**)                                                                    |
| Status             | Facility­Status | 1:1 | +Structure                          | Describes the status of the facility (see **FacilityStatus**)                                                           |
| Situation          | Situation­Ref   | 0:1 | Situation­Code                      | Reference to a Situation associated with the facility status                                                            |
| Remedy             | Remediation     | 0:1 | +Structure                          | Describes the remedy associated with the facility status (see **Remedy**)                                               |
| Monitoring         | Monitoring­Info | 0:1 | +Structure                          | Describes monitoring condition of the facility status (see **MonitoringInformation**)                                   |
| any                | Extensions      | 0:1 | +Structure                          | Voir paragraphe 5.4.2.2                                                                                                 |

## Description de l’état d’un équipement *(The Facility element)*

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 3%" />
<col style="width: 16%" />
<col style="width: 6%" />
<col style="width: 18%" />
<col style="width: 8%" />
<col style="width: 2%" />
<col style="width: 3%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 2%" />
<col style="width: 6%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Facility</td>
<td></td>
<td></td>
<td></td>
<td>+Structure</td>
<td colspan="4">Describes the status of a facility</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="4"></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Identify</td>
<td colspan="2">FacilityCode</td>
<td>0:1</td>
<td>FacilityCode</td>
<td colspan="4">The Facility for which status is returned.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Description</td>
<td colspan="2">Description</td>
<td>0:1</td>
<td>nLString</td>
<td colspan="4">Description of the facility.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Class</td>
<td colspan="2">FacilityClass</td>
<td>0:1</td>
<td>unknown |</td>
<td colspan="5">Category (type) of the facility. See Table 10.</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td>fixedEquipment |</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td>service |</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td>personalDevice |</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td>reservedArea|</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td>onBoard</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">FeatureRef</td>
<td>0-*</td>
<td>enumeration</td>
<td colspan="5">Classification of facility. See earlier Table 1.</td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Owner</td>
<td colspan="2">FacilityOwnerRef</td>
<td>0-1</td>
<td>OrganisationCode</td>
<td colspan="7">Identifier of Owner of facility. May be an Operator. Authority or</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">OwnerName</td>
<td>0-1</td>
<td>nLString</td>
<td colspan="4">Name Owner of facility.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Location</td>
<td colspan="2">FacilityLocation</td>
<td>0:1</td>
<td>+Structure</td>
<td colspan="7">Features of the facility (several features may be associated ti a</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="2">single facility).</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="7">See <strong>Siri Part 1 - Facility features</strong> for a detailed proposed list of facilities.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td rowspan="3">StopPointRef</td>
<td rowspan="3">0:1</td>
<td rowspan="3">StopPointCode</td>
<td colspan="7" rowspan="3"><p>Reference to the Stop Point (or Stop Area) where the facility is located (TRANSMODEL)</p>
<p>located ( TRANSMODEL)</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td colspan="5">Reference to the Line where the facility is located (TRANSMODEL)</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>ConnectionLinkRef</td>
<td>0:1</td>
<td>Connection-LinkCode</td>
<td colspan="7">Reference to the Connection Link where the facility is located (TRANSMODEL)</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>InterchangeRef</td>
<td>0:1</td>
<td>InterchangeCode</td>
<td colspan="7">Reference to the Interchange where the facility is located (TRANSMODEL)</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>VehicleJourneyRef</td>
<td>0:1</td>
<td>Vehicle-JourneyCode</td>
<td colspan="7"></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>VehicleRef</td>
<td>0:1</td>
<td>VehicleCode</td>
<td colspan="7">Reference to the Vehicle where the facility is located (TRANSMODEL)</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td>StopPlaceRef</td>
<td>0:1</td>
<td>StopPlaceCode</td>
<td colspan="7">Reference to the Interchange where the facility is located (TRANSMODEL)</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>ComponentRef</td>
<td>0:1</td>
<td>ComponentId</td>
<td colspan="7">Reference to the Stop Place Component where the facility is located (TRANSMODEL)</td>
</tr>
<tr class="odd">
<td>Specific- Need</td>
<td colspan="2">Accessibility- Assessment</td>
<td>0:n</td>
<td>+Structure</td>
<td colspan="7">Describes the status for accessibility fro different types of Special Needs special needs</td>
</tr>
<tr class="even">
<td>Temporal</td>
<td colspan="2">ValidityCondition</td>
<td>0:*1</td>
<td>+Structure</td>
<td colspan="5">Validity period (start &amp; duration) of the facility.</td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td colspan="7">Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

## Description de l’état lui-même (*FacilityStatus element*)

|                |                           |     |                       |                                                                             |
| -------------- | ------------------------- | --- | --------------------- | --------------------------------------------------------------------------- |
| FacilityStatus |                           |     | +Structure            | Describes the status of a Facility                                          |
| Status         | Status                    | 1:1 | unknown \|            | Specific status of the facility. See Table 16.                              |
|                |                           |     | available \|          |                                                                             |
|                |                           |     | notAvailable \|       |                                                                             |
|                |                           |     | partiallyAvailable \| |                                                                             |
|                |                           |     | added \|              |                                                                             |
|                |                           |     | removed               |                                                                             |
| Description    | Description               | 0:1 | nlString              | Literal description of the status.                                          |
| Special Needs  | Accessibility- Assessment | 0:n | +Structure            | Describes the status for accessibility for different types of special need. |
| any            | Extensions                | 0:1 | +Structure            | Voir paragraphe 5.4.2.2                                                     |

## Description des actions paliatives (*Remedy element*)

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 18%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 0%" />
<col style="width: 43%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Remedy</td>
<td></td>
<td></td>
<td>+Structure</td>
<td></td>
<td>Describes a remedy to a facility unavailability</td>
</tr>
<tr class="even">
<td>Remedy</td>
<td>RemedyType</td>
<td>0:1</td>
<td colspan="2">Unknown |</td>
<td>Describes the type of remedy. See Table 18.</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td colspan="2">replace|</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td colspan="2">repair |</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td colspan="2">remove</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td colspan="2">otherLocation</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td colspan="2">otherRoute</td>
<td></td>
</tr>
<tr class="even">
<td>Description</td>
<td>Description</td>
<td>0:1</td>
<td>nLString</td>
<td></td>
<td>Literal description of the remedy</td>
</tr>
<tr class="odd">
<td>Advice</td>
<td>RemedyPeriod</td>
<td>0:1</td>
<td colspan="2"><p>halfOpenTime-</p>
<p>stampRange</p></td>
<td>Period within which remedy applies.</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td colspan="2">+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

## Description du mode de supervision de l’équipement (*The MonitoringInformation element*)

|                       |                    |       |                                |                                                         |
| --------------------- | ------------------ | ----- | ------------------------------ | ------------------------------------------------------- |
| MonitoringInformation |                    |       | +Structure                     | Describes the monitoring conditions                     |
| Description           | MonitoringInterval | 0:1   | xsd:duration                   | Mean time interval between two measurements             |
|                       |                    |       |                                |                                                         |
| Remedy                | MonitoringType     | 0:1   | unknown \| manual \| automatic | What kind of monitoring is it: automatic, manual, etc.. |
| Temporal              | MonitoringPeriod   | 0:\*1 | +ValidityCondition             | Validity period (start & duration) of the facility.     |
| any                   | Extensions         | 0:1   | +Structure                     | Voir paragraphe 5.4.2.2                                 |

4.  (informative) Production TimeTable

    1.  ##  Requête d’information sur les horaires commandés/théoriques

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 3%" />
<col style="width: 11%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 48%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">ProductionTimetable­Request</td>
<td></td>
<td>+Structure</td>
<td>Requête d’information sur les horaires commandés/théoriques</td>
</tr>
<tr class="even">
<td>Attributes</td>
<td colspan="2">Version</td>
<td>1:1</td>
<td>VersionString</td>
<td>Version du service “ <em><strong>ProductionTimetable</strong></em> ”, intégrant le numéro de version de profil (voir 5.7)</td>
</tr>
<tr class="odd">
<td rowspan="2">Endpoint Properties</td>
<td colspan="2">Request­Timestamp</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date d'émission de la requête.</td>
</tr>
<tr class="even">
<td colspan="2">Message­Identifier</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Message­Qualifier</td>
<td>Numéro d'identification du message.</td>
</tr>
<tr class="odd">
<td rowspan="7">Line Topic</td>
<td colspan="2">Validity­Period</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>ClosedDate­Range­Structure</td>
<td>Période pour laquelle on souhaite avoir des informations horaires.</td>
</tr>
<tr class="even">
<td></td>
<td>Start</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure de début de période.</td>
</tr>
<tr class="odd">
<td></td>
<td>End</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure de fin de période.</td>
</tr>
<tr class="even">
<td colspan="2">Timetable­Version­Ref</td>
<td>0:1</td>
<td>xsd:string</td>
<td>Version du référentiel théorique connue : seuls les écarts par rapport à ce référentiel seront transmis (ce champ ne sera utilisable qu’à partir de la mise en œuvre du référentiel régional)</td>
</tr>
<tr class="odd">
<td colspan="2">Operator­Ref</td>
<td>0:*</td>
<td>Operator­Code</td>
<td>Identifie le ou les exploitants pour lesquel on souhaite obtenir des informations<em>.</em></td>
</tr>
<tr class="even">
<td></td>
<td>LineRef</td>
<td>0:1</td>
<td>LineCode</td>
<td>Identifie la ligne pour laquelle on souhaite obtenir des informations.</td>
</tr>
<tr class="odd">
<td></td>
<td>Direction­Ref</td>
<td>0:1</td>
<td>Direction­Code</td>
<td><p>Filter the results to include only journeys for vehicles running in a specific relative direction.</p>
<p>Optional SIRI capability: TopicFiltering / ByDirection.</p></td>
</tr>
<tr class="even">
<td>Policy</td>
<td colspan="2">Language</td>
<td>0:1</td>
<td>xml:lang</td>
<td>Au niveau des échanges inter-systèmes, les textes restent en français. Les éventuelles traductions seront prises en charge par les systèmes de présentation.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Incremental­Updates</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Indique si l’on souhaite ne disposer que des écarts par rapport aux données théoriques, ou de l’ensemble des informations sur la période.</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

<u>Note</u> : En fournissant des dates de début et de fin de période, on
pourra obtenir en réponse des modifications horaires sur toute la
période ; en retour SIRI fournira des « DatedVehicleJourney »,
c'est-à-dire des descriptions de courses valables pour un jour
d’application donné (on n’a pas, dans ce cas, de description d’une part
des courses et d’autre part des jours d’application). En d’autres
termes, si la période demandée couvre deux jours, et qu’une course est
active sur ces deux jours, la réponse comportera ces deux courses. La
différence s’établit au niveau des heures de départ et d’arrivée
indiquées par les éléments « Call » : ces heures sont en effet de type
« DateTime » et comportent donc à la fois le jour et l’heure.

## Abonnement aux informations sur les horaires commandés/théoriques

<table>
<colgroup>
<col style="width: 10%" />
<col style="width: 23%" />
<col style="width: 6%" />
<col style="width: 18%" />
<col style="width: 40%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">ProductionTimetable­SubscriptionRequest</td>
<td>+Structure</td>
<td>Requête pour un abonnement au service SIRI <em>Production Timetable Service</em>.</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td>SubscriberRef</td>
<td><p>0:1</p>
<p>1:1</p></td>
<td>Participant­Code</td>
<td>Identification du système demandeur (voir SIRI Part 2 Common <em><strong>SubscriptionRequest</strong></em> parameters.)</td>
</tr>
<tr class="odd">
<td>Subscription­Identifier</td>
<td>1:1</td>
<td>Subscription­Qualifier</td>
<td>Identifiant de l'abonnement pour le système demandeur.</td>
</tr>
<tr class="even">
<td>Lease</td>
<td>Initial­Termination­Time</td>
<td>1:1</td>
<td>xsd:dateTIme</td>
<td>Date et heure de fin de l'abonnement : un abonnement a forcément une date et heure de fin (les partenaires pourront décider de limiter la durée maximale d’un abonnement).</td>
</tr>
<tr class="odd">
<td>Request</td>
<td>Production­Timetable­Request</td>
<td>1:1</td>
<td>+Structure</td>
<td>Voir ProductionTimetable­Request.</td>
</tr>
</tbody>
</table>

## Réponse aux requêtes d’informations sur les horaires commandés/théoriques

|                               |                               |      |               |                                                                                                                                                       |
| ----------------------------- | ----------------------------- | ---- | ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Production­Timetable­Delivery |                               |      | +Structure    | Description des horaires sur la période                                                                                                               |
| Attributes                    | version                       | 1:1  | VersionString | Numéro de version du service *Production Timetable*, intégrant le numéro de version de profil (voir Error: Reference source not found) (valeur fixe). |
| LEADER                        | ::                            | 1:1  | xxx­Delivery  | voir paragraphe 2.2                                                                                                                                   |
| Payload                       | Dated­Timetable­Version­Frame | 0:\* | +Structure    | Voir DatedTimetableVersionFrame element.                                                                                                              |
| any                           | Extensions                    | 0:1  | +Structure    | Voir paragraphe 5.4.2.2                                                                                                                               |

## Structure DatedTimetableVersionFrame

<table>
<colgroup>
<col style="width: 13%" />
<col style="width: 20%" />
<col style="width: 5%" />
<col style="width: 18%" />
<col style="width: 42%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="3">DatedTimetableVersionFrame</td>
<td>+Structure</td>
<td>Fournit les courses applicables pour un itinéraire</td>
</tr>
<tr class="even">
<td>Log</td>
<td>Recorded­AtTime</td>
<td>1:1</td>
<td>xsd:dateTime</td>
<td>Date et heure auxquelles ces données ont été produites.</td>
</tr>
<tr class="odd">
<td>Identity</td>
<td>VersionRef</td>
<td>0:1</td>
<td>Version­Code</td>
<td>Identifier of Timetable version frame.</td>
</tr>
<tr class="even">
<td rowspan="2">Line</td>
<td>LineRef</td>
<td>1:1</td>
<td>LineCode</td>
<td>Identifiant de la ligne.</td>
</tr>
<tr class="odd">
<td>DirectionRef</td>
<td>1:1</td>
<td>Direction­Code</td>
<td><p>Identifie la direction (typiquement Aller/Retour).</p>
<p>La sélection de ce champ n’est pas dans la logique du reste du profil (plutôt porté sur Destination, voir plus bas) mais est maintenue du fait de la cardinalité imposée par SIRI.</p></td>
</tr>
<tr class="even">
<td>Journey Pattern Info</td>
<td>:::</td>
<td>0:1</td>
<td>JourneyPattern­Info­Group</td>
<td><p>Voir Journey­Pattern­Info­Group.</p>
<p>Renseigné dans la description de la course.</p></td>
</tr>
<tr class="odd">
<td>Service Info</td>
<td>:::</td>
<td>0:1</td>
<td>Service­Info­Group</td>
<td><p>Voir Service­Info­Group.</p>
<p>Renseigné dans la description de la course.</p></td>
</tr>
<tr class="even">
<td>Notes</td>
<td>Destination­Display</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Destination telle qu'elle est affichée sur la girouette du véhicule à cet arrêt (ou sur l’afficheur local).</p>
<p>Renseigné dans la description de la course.</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Monitored</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Signale si les données temps réel seront disponibles pour cette course.</p>
<p>Renseigné dans la description de la course.</p></td>
</tr>
<tr class="even">
<td>Journ­eys</td>
<td>Dated­Vehicle­Journey</td>
<td>0:*</td>
<td>+Structure</td>
<td>Description des horaires de la course.</td>
</tr>
<tr class="odd">
<td>Inter­changes</td>
<td>ServiceJourney­Interchange</td>
<td>0:*</td>
<td>+Structure</td>
<td>Provides schedule information about the planned SERVICE JOURNEY INTERCHANGEs that connect services.</td>
</tr>
<tr class="even">
<td>any</td>
<td>Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

## Structure DatedVehicleJourney

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 2%" />
<col style="width: 3%" />
<col style="width: 2%" />
<col style="width: 8%" />
<col style="width: 5%" />
<col style="width: 14%" />
<col style="width: 47%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="6">DatedVehicleJourney</td>
<td>+Structure</td>
<td>Description de la course</td>
</tr>
<tr class="even">
<td rowspan="3">Vehicle Journey Identity</td>
<td rowspan="2">choice</td>
<td colspan="3">Dated­Vehicle­Journey­Code</td>
<td>1:1</td>
<td>Vehicle­Journey­Code</td>
<td>Identifie la course datée.</td>
</tr>
<tr class="odd">
<td colspan="3">Framed-Vehicle-JourneyRef</td>
<td>1:1</td>
<td>+Structure</td>
<td><p>Identifie la course datée.</p>
<p>Cette version permet de préciser la version de jeu de données associé et est recommandée à partir de SIRI 2 (et doc du profil 2.4). Le mécanisme de choix placé ici permet d'assurer la compatibilité ascendante.</p></td>
</tr>
<tr class="even">
<td colspan="4">Vehicle­Journey­Ref</td>
<td>0:1</td>
<td>Vehicle­Journey­Code</td>
<td>Vehicle Journey from which this journey is different.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="4">ExtraJourney</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Signale qu’il s’agit d’une nouvelle course, ajoutée par rapport aux horaires théoriques.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="even">
<td></td>
<td colspan="4">Cancellation</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Signale la suppression de la course identifiée.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="odd">
<td>Journey Pattern Info</td>
<td colspan="4">:::</td>
<td>0:1</td>
<td>Journey­Pattern­Info­Group</td>
<td>Voir Journey­Pattern­Info­Group.</td>
</tr>
<tr class="even">
<td>Service Info</td>
<td colspan="4">:::</td>
<td>0:1</td>
<td>Service­Info­Group</td>
<td>Voir ServiceInfo­Group.</td>
</tr>
<tr class="odd">
<td rowspan="2">Journey Info</td>
<td colspan="4">Vehicle­Journey­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Nom commercial de la course.</td>
</tr>
<tr class="even">
<td colspan="4">Journey­Note</td>
<td>0:*</td>
<td>NLString</td>
<td>Additional descriptive text associated with journey. Inherited property.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="4">PublicContact</td>
<td>0:1</td>
<td>+Structure</td>
<td>Contact details for use by members of public. +SIRI v2.0</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td colspan="3">PhoneNumber</td>
<td>0:1</td>
<td>PhoneType</td>
<td>Phone number for Public to contact OPERATOR of journey. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td colspan="3">Url</td>
<td>0:1</td>
<td>xsd:anyUri</td>
<td>Public URL to contact OPERATOR of journey. +SIRI v2.0</td>
</tr>
<tr class="even">
<td></td>
<td colspan="4">OperationsContact</td>
<td>0:1</td>
<td>+Structure</td>
<td>Contact details for use by operational staff. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td colspan="3">PhoneNumber</td>
<td>0:1</td>
<td>PhoneType</td>
<td>Phone number for operational contact. Not for Public use. +SIRI v2.0</td>
</tr>
<tr class="even">
<td></td>
<td colspan="3"></td>
<td>Url</td>
<td>0:1</td>
<td>xsd:anyUri</td>
<td>URL number for operational contact. Not for Public use. +SIRI v2.0</td>
</tr>
<tr class="odd">
<td rowspan="2">Notes</td>
<td colspan="4">Destination­Display</td>
<td>0:1</td>
<td>NLString</td>
<td>Destination telle qu'elle est affichée sur la girouette du véhicule à cet arrêt (ou sur l’afficheur local).</td>
</tr>
<tr class="even">
<td colspan="4">Line­Note</td>
<td>0:1</td>
<td>NLString</td>
<td>Additional Text associated with line. Inherited property.</td>
</tr>
<tr class="odd">
<td>Timetable­info</td>
<td colspan="4">Headway­Service</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Indique si la course est gérée dans un contexte d’exploitation (ou d’information seulement) en fréquence.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="even">
<td>Real-time Info</td>
<td colspan="4">Monitored</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>Signale si les données temps réel sont disponibles pour cette course (« false » permet de signaler une délocalisation).</p>
<p>Valeur par défaut : « true»</p></td>
</tr>
<tr class="odd">
<td>Operational Block</td>
<td colspan="4">:::</td>
<td>0:1</td>
<td>OperationalBlock­Group</td>
<td>See SIRI Part 2 Operational­Block­Group.</td>
</tr>
<tr class="even">
<td rowspan="3">Children</td>
<td rowspan="2">a</td>
<td colspan="3">Dated­Calls</td>
<td>1:1</td>
<td>+Structure</td>
<td>Description ordonnée des arrêts et heures de passage.</td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">Dated­Call</td>
<td>2:*</td>
<td>+Structure</td>
<td>Voir DatedCall..</td>
</tr>
<tr class="even">
<td>b</td>
<td colspan="3"></td>
<td>2:*</td>
<td>DatedCalls­AsFlatGroup</td>
<td>Unnested children for compatibility.</td>
</tr>
<tr class="odd">
<td>any</td>
<td colspan="4">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

## Structure DatedCall

<table>
<colgroup>
<col style="width: 14%" />
<col style="width: 2%" />
<col style="width: 13%" />
<col style="width: 5%" />
<col style="width: 17%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">DatedCall</td>
<td>+Structure</td>
<td>Information et heures de passage à l’arrêt</td>
</tr>
<tr class="even">
<td rowspan="4">Stop Identity</td>
<td colspan="2">StopPoint­Ref</td>
<td>1:1</td>
<td>StopPoint­Code</td>
<td><p>Identifiant du Point d'arrêt (cet identifiant est à rapprocher de l’attribut <em>MonitoringRef</em> de la structure <em>MonitoredStopVisit</em>, mais restreint à ce cas de point d’arrêt là, ou le <em>MonitoringRef</em> peut aussi, dans le contexte général de SIRI, mais pas celui du profil francilien, référencer un afficheur, par exemple).</p>
<p>Il convient d'utiliser ici un identifiant d'objet issu du profil NeTex Fr (Lieu d’arrêt mono ou multimodaux, zone d'embarquement): granularité la plus fine possible dans tous les cas.</p></td>
</tr>
<tr class="odd">
<td colspan="2">Visit­Number</td>
<td>0:1</td>
<td>VisitNumber­Type</td>
<td>For journey patterns that involve repeated visits by a vehicle to a stop, the <strong>VisitNumber</strong> count is used to distinguish each separate visit. Default is ‘1’</td>
</tr>
<tr class="even">
<td colspan="2">Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>Numéro d'ordre de l'arrêt dans la mission.</td>
</tr>
<tr class="odd">
<td colspan="2">StopPoint­Name</td>
<td>0:1</td>
<td>NLString</td>
<td><p>Nom du point d'arrêt.</p>
<p>Si plusieurs noms sont disponibles chez le producteur, le nom le plus détaillé sera utilisé en priorité.</p></td>
</tr>
<tr class="even">
<td rowspan="3">Info</td>
<td colspan="2">Timing­Point</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the stop is a timing point. Times for stops that are not timing points are sometimes interpolated crudely from the timing points, and may represent a lower level of accuracy. Default is true.</td>
</tr>
<tr class="odd">
<td colspan="2">Boarding­Stretch</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether this is a Hail and Ride Stop. A hail and ride stop may represent a linear stretch in the stop model. Default is false.</td>
</tr>
<tr class="even">
<td colspan="2">Request­Stop</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether Vehicle stops only if requested explicitly by passenger. Default is false.</td>
</tr>
<tr class="odd">
<td>Service Info</td>
<td colspan="2">Destination­Display</td>
<td>0:1</td>
<td>NLString</td>
<td>Destination telle qu'elle est affichée sur la girouette du véhicule à cet arrêt (ou sur l’afficheur local).</td>
</tr>
<tr class="even">
<td>Call</td>
<td colspan="2">CallNote</td>
<td>0:1</td>
<td>NLString</td>
<td>Text annotation that applies to this call.</td>
</tr>
<tr class="odd">
<td rowspan="6">Arrival</td>
<td colspan="2">Aimed­Arrival­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Date et Heure d'arrivée théorique (ou commandée)</td>
</tr>
<tr class="even">
<td colspan="2">Arrival­Platform­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Identification ou nom du quai d'arrivée.</td>
</tr>
<tr class="odd">
<td colspan="2">Arrival­Boarding­Activity</td>
<td>0:1</td>
<td>alighting | noAlighting | passthru</td>
<td><p>Type of boarding and alighting allowed at stop. Default is Alighting.</p>
<p>On utilisera le <em><strong>Departure­Boarding­Activity</strong></em> dans le profil Fr</p></td>
</tr>
<tr class="even">
<td colspan="2">ArrivalStop­Assignment</td>
<td>0:1</td>
<td>+Structure</td>
<td>Affectation du point d'arrêt planifié à un quay +SIRI v2.0.</td>
</tr>
<tr class="odd">
<td></td>
<td>Aimed­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY to use according to the planned timetable. +SIRI v2.0</td>
</tr>
<tr class="even">
<td></td>
<td>Aimed­­QuayName</td>
<td>0:1</td>
<td>NLString</td>
<td>Indication de la voie d'arrivée (en complément de Platform)<em>.</em></td>
</tr>
<tr class="odd">
<td rowspan="6">Departure</td>
<td colspan="2">Aimed­Departure­Time</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Date et Heure de départ théorique (ou commandée).</td>
</tr>
<tr class="even">
<td colspan="2">Departure­Platform­Name</td>
<td>0:1</td>
<td>NLString</td>
<td>Identification ou nom du quai de départ.</td>
</tr>
<tr class="odd">
<td colspan="2">Departure­Boarding­Activity</td>
<td>0:1</td>
<td>boarding | noBoarding| passthru</td>
<td>Caractérisation de l'horaire de départ attendu (ou mesuré si le véhicule est à quai).</td>
</tr>
<tr class="even">
<td colspan="2">DepartureStop­Assignment</td>
<td>0:1</td>
<td>+Structure</td>
<td><p>Assignments of departure platform for SCHEDULED STOP POINT to a physical QUAY. +SIRI v2.0.</p>
<p>+SIRI v2.0. DetailLevel: normal.</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Aimed­­QuayRef</td>
<td>0:1</td>
<td>QuayCode­Type</td>
<td>Physical QUAY (Platform) to use according to the planned timetable. +SIRI v2.0</td>
</tr>
<tr class="even">
<td></td>
<td>Aimed­­QuayName</td>
<td>0:*</td>
<td>NLString</td>
<td><p>Scheduled QUAY (Platform) name. Can be used to indicate a platform change. +SIRI v2.0</p>
<p>One per language</p></td>
</tr>
<tr class="odd">
<td></td>
<td colspan="2">AimedLatestPassengerAccessTime</td>
<td>0:1</td>
<td>xsd:dateTime</td>
<td>Latest target time at which a PASSENGER should aim to arrive at the STOP PLACE containing the stop. This time may be earlier than the VEHICLE departure times and may include time for processes such as checkin, security, etc.(As specified by CHECK CONSTRAINT DELAYs in the underlying data) If absent assume to be the same as Earliest expected departure time, +SIRI 2.0</td>
</tr>
<tr class="even">
<td>Headway</td>
<td colspan="2">Aimed­Headway­Interval</td>
<td>0:1</td>
<td>Positive­DurationType</td>
<td>Fréquence de passage théorique (ou commandée).</td>
</tr>
<tr class="odd">
<td rowspan="3">Interchange</td>
<td colspan="2">Targeted­Interchange</td>
<td>0:*</td>
<td>+Structure</td>
<td><p>Permet de signaler une correspondance programmée à cet arrêt (possibilité d’attendre une course arrivant).</p>
<p>voir. Targeted­Interchange.</p></td>
</tr>
<tr class="even">
<td colspan="2">FromServiceJourneyInterchange</td>
<td>0:*</td>
<td>+Structure</td>
<td><p>Information on any feeder of a planned connections.</p>
<p>+SIRI v2.0</p></td>
</tr>
<tr class="odd">
<td colspan="2">ToServiceJourneyInterchange</td>
<td>0:*</td>
<td>+Structure</td>
<td><p>Information on any distributor of a planned connections.</p>
<p>+SIRI v2.0</p></td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>+Structure</td>
<td>Voir paragraphe 5.4.2.2</td>
</tr>
</tbody>
</table>

## Structure TargetedInterchange

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 2%" />
<col style="width: 16%" />
<col style="width: 5%" />
<col style="width: 14%" />
<col style="width: 44%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="4">Targeted­Interchange</td>
<td>+Structure</td>
<td>Description d’une correspondance programmée (description de l’arrivant)</td>
</tr>
<tr class="even">
<td rowspan="2">Identity</td>
<td colspan="2">Interchange­Code</td>
<td>0:1</td>
<td>Inter­change­Code</td>
<td><p>Identification de la correspondance.</p>
<p>Dans le cadre du profil France, si ce paramètre est présent, il sera constitué de la concaténation de l’identifiant de la course de l’arrivant et de celui de la course au départ (séparés par le caractère ‘<strong>:</strong>’)</p></td>
</tr>
<tr class="odd">
<td colspan="2">Distributor­Vehicle­Journey­Ref</td>
<td>1:1</td>
<td>Dated­Vehicle­Journey­Code</td>
<td>Identifie la course de l’arrivant</td>
</tr>
<tr class="even">
<td rowspan="7">Connection</td>
<td colspan="2">Distributor­Connection­Link</td>
<td>1:1</td>
<td>+Structure</td>
<td>Description du cheminement physique de correspondance.</td>
</tr>
<tr class="odd">
<td rowspan="2"></td>
<td>Connection­Code</td>
<td>1:1</td>
<td>Connection­Code</td>
<td><p>Identifiant du cheminement physique de correspondance.</p>
<p>Ce champ est obligatoire dans le XSD SIRI, et l’est donc aussi dans le profil France : toutefois s’il n’était pas disponible au niveau du système alimentant, le champ sera fourni, mais laissé vide.</p></td>
</tr>
<tr class="even">
<td>Stop­Point­Ref</td>
<td>0:1</td>
<td>StopPoint­Code</td>
<td><p>Identifant du point d’arrêt de départ de la correspondance.</p>
<p>Il convient d'utiliser ici un identifiant d'objet de référence partagé entre les systèmes communiquants (cf 5.4.2)</p></td>
</tr>
<tr class="odd">
<td rowspan="4"></td>
<td>Interchange­Duration</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Durée de la correspondance (temps « normal » de marche à pied).</td>
</tr>
<tr class="even">
<td>Frequent­Traveller­Duration</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Durée de la correspondance pour un voyageur habitué.</td>
</tr>
<tr class="odd">
<td>Occasional­Traveller­Duration</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Durée de la correspondance pour un voyageur lent ou ne connaissant pas la correspondance.</td>
</tr>
<tr class="even">
<td>Impaired­Access­Duration</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Durée de la correspondance pour une personne à mobilité réduite.</td>
</tr>
<tr class="odd">
<td rowspan="2">Identity</td>
<td colspan="2">Distributor­VisitNumber</td>
<td>0:1</td>
<td>Visit­Number­Type</td>
<td>Sequence of visit to stop within distributor vehicle journey. Increases monotonically, but not necessarily sequentially.</td>
</tr>
<tr class="even">
<td colspan="2">Distributor­Order</td>
<td>0:1</td>
<td>xsd:positive­Integer</td>
<td>For implementations for which the overall Order within journey pattern is not used for <strong>VisitNumber</strong>, (i.e. if <strong>VisitNumberIsOrder</strong> is false) then can be used to associate the overall Order as well if useful.</td>
</tr>
<tr class="odd">
<td rowspan="3">Interchange Properties</td>
<td colspan="2">StaySeated</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>« true » signale que la correspondance s’effectue en restant dans le même véhicule.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="even">
<td colspan="2">Guaranteed</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td><p>« true » signale que la correspondance est garantie ou non.</p>
<p>Valeur par défaut : « false»</p></td>
</tr>
<tr class="odd">
<td colspan="2">Advertised</td>
<td>0:1</td>
<td>xsd:boolean</td>
<td>Whether the interchange is advertised as a connection. Default is false.</td>
</tr>
<tr class="even">
<td rowspan="6">Interchange Times</td>
<td colspan="2">Maximum­Wait­Time</td>
<td>0:1</td>
<td>Positive­Duration­Type</td>
<td>Temps maximum qu’attendra le véhicule au depart si l’amenant est en retard.</td>
</tr>
<tr class="odd">
<td colspan="2">StandardWaitTime</td>
<td>0:1</td>
<td>xsd:duration</td>
<td>Standard wait time for INTERCHANGE. SIRI v2.0</td>
</tr>
<tr class="even">
<td colspan="2">MaximumAutomatic­WaitTime</td>
<td>0:1</td>
<td>xsd:duration</td>
<td>Maximum automatic wait time that Distributor will wait for Feeder for INTERCHANGE. SIRI v2.0.</td>
</tr>
<tr class="odd">
<td colspan="2">StandardTransfer­Time</td>
<td>0:1</td>
<td>xsd:duration</td>
<td>Standard transfer duration for INTERCHANGE. SIRI</td>
</tr>
<tr class="even">
<td colspan="2">MinimumTransfer­Time</td>
<td>0:1</td>
<td>xsd:duration</td>
<td>Minimum transfer duration for INTERCHANGE. SIRI</td>
</tr>
<tr class="odd">
<td colspan="2">MaximumTransfer­Time</td>
<td>0:1</td>
<td>xsd:duration</td>
<td>Maximum transfer duration for INTERCHANGE. SIRI</td>
</tr>
<tr class="even">
<td>any</td>
<td colspan="2">Extensions</td>
<td>0:1</td>
<td>any</td>
<td>Placeholder for user extensions.</td>
</tr>
</tbody>
</table>

<span id="__RefHeading___Toc26889712"
class="anchor"></span>Bibliographie

1.  ISO 8601, Data elements and interchange formats – Information
    interchange – Representation of dates and times

2.  ISO 639/IETF 1766, Tags for the Identification of Languages

3.  ISO/IEC 19501-1:2002, Unified Modelling Language (UML) – Part 1:
    Specification

4.  National standards, in particular profile NEPTUNE, TransXChange,
    BISON and VDV 452, and other standards like NOPTIS

5.  ERA TAP-TSI: Commission Regulation (EU) No 454/2011 of 5 May 2011 on
    the technical specification for interoperability relating to the
    subsystem ‘telematics applications for passenger services’ of the
    trans-European rail system.

6.  UIC recommendations and leaflets

7.  XML, Extensible Mark-up Language (XML) 1.0 W3C Recommendation 04
    February 2004, available at
    http://www.w3.org/TR/2004/REC-xml-20040204.

8.  Europe on the Move: Commission takes action for clean, competitive
    and connected mobility

<https://ec.europa.eu/transport/modes/road/news/2017-05-31-europe-on-the-move_en>

9.  Commission Delegated Regulation on the provision of EU-wide
    multimodal travel information service

<http://ec.europa.eu/info/law/better-regulation/initiatives/c-2017-3574_en>

10. Github SIRI disponible sur le lien

Accès aux xsd et wsdl SIRI

## Documents d’accompagnement

\[A1\] Description des Cas d’usage du profil SIRI France

\[A2\] Règles de gestion dynamique

\[A3\] Bonnes Pratiques Implémentation SIRI
