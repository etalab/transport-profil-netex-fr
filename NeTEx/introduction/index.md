# Cadre réglementaire

La mise à disposition des données, quand elles existent, est obligatoire et se
conforme aux exigences:

- Au niveau européen, du
  [règlement délégué (UE) 2017/1926](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:02017R1926-20240304)
  de la Commission du 31 mai 2017, dit « **règlement MMTIS** » (MultiModal
  Travel Information Services) modifié par le
  [règlement délégué (UE) 2024/490](https://eur-lex.europa.eu/legal-content/FR/TXT/PDF/?uri=OJ:L_202400490)
  de la Commission du 29 novembre 2023
- Au niveau français, des articles
  [L. 1115-1 à L. 1115-7](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000023086525/LEGISCTA000039670430/#LEGISCTA000039670430),
  D. 1115-1, R. 1115-2 à R. 1115-8 et D. 1115-9 à D. 1115-11 du code des
  transports, créés ou modifiés par
  [loi n° 2019-1428](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000039666574/)
  du 24 décembre 2019 d'orientation des mobilités (dite «**loi LOM**»). Ces
  mêmes articles de la LOM précise le calendrier de mise à disposition des
  données.

Pour les données d'accessibilité, la collecte et la mise à disposition sont
obligatoires:

- Les modalités de collecte et de mise à disposition de ces données sont
  détaillées dans
  l'[arrêté du 28 mai 2024](https://www.legifrance.gouv.fr/loda/id/LEGITEXT000049643437/2024-06-05#LEGITEXT000049643437)
  relatif aux dispositions de la collecte des données « accessibilité » dans les
  transports et en voirie pour les déplacements des personnes handicapées ou à
  mobilité réduite pris en application des articles L. 1115-6, L. 1115-7, D.
  1115-9 et D. 1115-10 du code des transports, des articles L. 141-13 et R.
  121-24 du code de la voirie routière.
- Les exigences techniques en matière d’accessibilité de la voirie, des espaces
  publics et des équipements associés (arrêts de bus, information voyageur…) à
  respecter sont listées dans l’arrêté du 15 janvier 2007 (modifié) relatif
  l'accessibilité de la voirie et des espaces publics.
- Pour les établissements recevant du public et les équipements de type
  sanitaires, l’ensemble des exigences techniques à respecter est listée dans
  l’arrêté du 20 avril 2017 relatif à l’accessibilité des établissements
  recevant du public, dits arrêté « ERP ».

# Concepts relatifs à la LOM et à la Règlementation Européenne

## Aide à la lecture du document

Le tableau ci-dessous résulte de l’analyse du code des transports et du
règlement MMTIS et fournit la liste des concepts correspondant aux données
mentionnées dans l’annexe du règlement.

Il sera donc nécessaire de fournir au moins ces données pour être conforme au
cadre réglementaire.

Cependant, certaines données peuvent être exigées par le règlement MMTIS si
celles-ci sont disponibles dans les SI, même si elles sont considérées comme
facultatives dans ce profil. Dans ce cas, il est recommandé de les fournir. En
cas de doute, se référer au règlement et notamment à son annexe pour connaître
les catégories de données à ouvrir.

Notez que beaucoup de concepts dépendent d’autres concepts issus de
Transmodel/NeTEx (soit par héritage soit par relation, au sens UML des termes).
Ces éléments d’héritage et de relations sont présentés dans les différentes
parties du profil France, mais pas dans ce tableau.

De plus, les noms des catégories du règlement MMTIS ont été conservés dans la
langue originale du document (l’anglais) pour éviter tout risque de confusion.
Pour la même raison, les noms des concepts concernés sont ceux de la version
originale de Transmodel.

Pour certaines catégories de données, il peut arriver que les concepts
correspondants soient multiples, mais aussi qu’ils soient différents suivant le
niveau de précision porté par la donnée. La colonne « Concepts à minima »
correspond alors au minimum à fournir pour répondre à la catégorie en question
et les colonnes « Autres concepts » décrit des informations complémentaires qui,
si elles sont utiles, ne sont pas indispensables pour répondre à cette
catégorie.

Le découpage en *Level of Service* (niveau) utilisé par le règlement européen a
été repris ici car il a notamment une incidence sur le calendrier de mise à
disposition de la donnée.

Les différents concepts présentés ne sont bien sûr pas détaillés dans ce
tableau, mais dans le profil lui-même. C’est aussi dans la description du profil
que l’on trouvera les détails concernant les attributs (obligatoire/facultatif,
règles de remplissage, codification, etc.). Pour ce qui est des attributs
facultatifs, la règle reste que, pour les objets ci-dessous, toute information
disponible est supposée être fournie (mais on ne crée pas d’information si elle
n’est pas disponible, à l'exception de données d'accessibilité, pour lesquelles
la LOM impose également la collecte).

## Correspondance avec les concepts relatifs à la Règlementation Européenne

### Level of Service 1

| Catégorie                                                                                                                                                                   | Concepts à minima                                                                                                                               | Autres concepts                                                                                                                                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Address identifiers (building number, street name, postcode)                                                                                                                | Tous les objets héritant d'ADRESSABLE PLACE <br> (Les informations d’adresse sont attendues pour tous les objets susceptibles d’en porter)      | ENTRANCE, QUAY, <br> POI,  <br> ENTRANCE (VEHICLE and PASSENGER), PARKING                                                                                                                                                                                               |
| Location search : Topographic places (city, town, village, suburb, administrative unit)                                                                                     | TOPOGRAPHIC PLACE                                                                                                                               |                                                                                                                                                                                                                                                                         |
| Location search : Points of interest (related to transport information) to which people may wish to travel                                                                  | POI <br>Même si le transport en commun n'est probablement pas la meilleure source pour les POI, NeTEx reste néanmoins en mesure de les décrire. |                                                                                                                                                                                                                                                                         |
| Trip plans: operational calendar, mapping day types to calendar dates                                                                                                       | UicOperatingPeriod, DAY TYPE                                                                                                                    | SERVICE CALENDAR, OPERATING DAY, DAY TYPE ASSIGNMENT, PROPERTY OF DAY, OPERATING PERIOD                                                                                                                                                                                 |
| Location search (access nodes) : Identified access nodes                                                                                                                    | STOP PLACE                                                                                                                                      | QUAY, SCHEDULED STOP POINT, PASSENGER STOP ASSIGNMENT                                                                                                                                                                                                                   |
| Location search (access nodes) : Geometry/map layout structure of access nodes                                                                                              | STOP PLACE                                                                                                                                      | QUAY                                                                                                                                                                                                                                                                    |
| Trip plan computation: Connection where interchanges may be made                                                                                                            | DEFAUT CONNECTION                                                                                                                               | CONNECTION, SITE CONNECTION, <br> INTERCHANGE                                                                                                                                                                                                                           |
| Trip plan computation: Network topology and routes/lines (topology)                                                                                                         | LINE, SERVICE PATERN, SCHEDULED STOP POINT                                                                                                      | ROUTE, ROUTE POINT, ROUTE LINK, SERVICE LINK, POINT IN JOURNEY PATTERN, DESTINATION DISPLAY                                                                                                                                                                             |
| Trip plan computation: Transport operators                                                                                                                                  | OPERATOR                                                                                                                                        | ORGANISATION, GROUP OF OPERATORS, AUTHORITY                                                                                                                                                                                                                             |
| Trip plan computation: Timetables                                                                                                                                           | SERVICE JOURNEY, TIMETABLE PASSING TIME                                                                                                         | JOURNEY FREQUENCY GROUP, HEADWAY JOURNEY GROUP, TEMPLATE SERVICE JOURNEY <br> Ne pas oublier les calendriers d'application ainsi que les éléments constitutifs des SERVICE JOURNEY.                                                                                     |
| Trip plan computation: Hours of operation                                                                                                                                   | AVAILABILITY CONDITIONS, <br>SERVICE JOURNEY, TIMETABLE PASSING TIME                                                                            |                                                                                                                                                                                                                                                                         |
| Trip plan computation: Facilities of access nodes (including platform information, help desk/information points, ticket booths, lifts/stairs, entrances and exit locations) | FACILITIES des STOP PLACE                                                                                                                       | EQUIPMENT                                                                                                                                                                                                                                                               |
| Trip plan computation: Vehicles, including their accessibility                                                                                                              | VEHICLE TYPE et FACILITIES associées                                                                                                            | EQUIPMENT                                                                                                                                                                                                                                                               |
| Trip plan computation: Accessibility of access nodes, and paths within an interchange (such as existence of lifts, escalators)                                              | FACILITIES des STOP PLACE                                                                                                                       | EQUIPMENT, NAVIGATION PATH                                                                                                                                                                                                                                              |
| Trip plan computation: Existence of assistance services (such as existence of on-site assistance)                                                                           | FACILITIES des STOP PLACE                                                                                                                       | LOCAL SERVICE                                                                                                                                                                                                                                                           |
| Trip plan computation: Pedestrian network and accessibility facilities                                                                                                      | SITE PATH LINK                                                                                                                                  | NAVIGATION PATH <br> Le profil peut caractériser l'accessibilité des infrastructures mais pas fournir la topologie nécessaire à un calculateur d'itinéraire. INSPIRE (en partie seulement), OSM et DGF sont les principales sources potentielles pour ces informations. |

### Level of Service 2

| Catégorie                                                                                                                                              | Concepts à minima                              | Autres concepts                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Location search: Location of parking places                                                                                                            | PARKING                                        | PARKING AREA, REFUELLING EQUIPMENT, VEHICLE CHARGING EQUIPMENT et leurs informations d'accessibilité |
| Location search: Park & Ride stops                                                                                                                     | PARKING                                        | PARKING AREA, REFUELLING EQUIPMENT, VEHICLE CHARGING EQUIPMENT et leurs informations d'accessibilité |
| Location search: Bike sharing stations                                                                                                                 | PARKING                                        | PARKING AREA, REFUELLING EQUIPMENT, VEHICLE CHARGING EQUIPMENT et leurs informations d'accessibilité |
| Location search: Car-sharing stations                                                                                                                  | PARKING                                        | PARKING AREA, REFUELLING EQUIPMENT, VEHICLE CHARGING EQUIPMENT et leurs informations d'accessibilité |
| Location search: Secure bike parking (such as locked bike garages)                                                                                     | PARKING                                        | PARKING AREA, REFUELLING EQUIPMENT, VEHICLE CHARGING EQUIPMENT et leurs informations d'accessibilité |
| Where and how to buy tickets for scheduled transport, including retail channels, fulfilment methods, payment methods                                   | *voir la partie Tarifs*                        |                                                                                                      |
| Where and how to pay for parking, including retail channels, fulfilment methods, payment methods                                                       | PARKING (attributs relatifs à la tarification) |                                                                                                      |
| Basic common standard fares (all scheduled modes): Standard fare structures (point to point including daily and weekly fares, zonal fares, flat fares) | *voir la partie Tarifs*                        |                                                                                                      |

### Level of Service 3

| Catégorie                                                                                                                                                                                                                             | Concepts à minima                                                                                                                                                                                                                                 | Autres concepts |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------- |
| Passenger classes (classes of user such as adult, child, student, veteran, impaired access and qualifying conditions and classes of travel such as 1st, 2nd.)                                                                         | ACCESS RIGHT PARAMETER ASSIGNMENT <br> À associer au FARE PRODUCT en priorité, ou aux FARE OFFER PACKAGEs et FARE STRUCTURE ELEMENTs                                                                                                              |                 |
| Special Fare Products: offers with additional special conditions such as promotional fares, group fares, season passes, aggregated products combining different products and add on products such as parking and travel, minimum stay | *voir la partie Tarifs*                                                                                                                                                                                                                           |                 |
| Basic commercial conditions such as refunding/replacing/exchanging/transferring and basic booking conditions such as purchase windows, validity periods, routing restrictions zonal sequence fares, minimum stay.                     | *voir la partie Tarifs*                                                                                                                                                                                                                           |                 |
| How to book car sharing, taxis, cycle hire etc. (incl. retail channels, fulfilment methods, payment methods)                                                                                                                          | *voir la partie Tarifs*                                                                                                                                                                                                                           |                 |
| Where how to pay for car parking, public charging stations for electric vehicles and refuelling points for CNG/LNG, hydrogen, petrol and diesel powered vehicles (incl. retail channels, fulfilment methods, payment methods)         | *voir la partie Tarifs*                                                                                                                                                                                                                           |                 |
| Parameters needed to calculate an environmental factor such as carbon per vehicle type or passenger mile or per distance walked                                                                                                       | VEHICLE TYPE, CONNECTION et SITE CONNECTION. <br> ROUTE LINK (donc ROUTE) ou SERVICE LINK en alternative, ainsi que leurs POINTs (POINT IN JOURNEY PATTERN, ROUTE POINT, POINT ON ROUTE, etc.) pour évaluer la distance parcourue par le véhicule | NAVIGATION PATH |
| Parameters needed to calculate fuel consumption of conventional and alternative fuels                                                                                                                                                 | VEHICLE TYPE <br> (d'autres sources de données devront être utilisées en combinaison pour effectuer le calcul de consommation)                                                                                                                    |                 |

## Remarques additionnelles sectorielles

Concernant les tarifs :

Il est assez complexe de réaliser une sélection de concepts dans ce que propose
NeTEx qui corresponde exactement aux attentes du règlement européen. Si
l’autorité organisatrice des transports décide de sélectionner les titres et les
tarifs sur lesquels elle communique de façon exhaustive (description complète
même s’ils sont complexes), alors, il y a lieu que cette sélection couvre:

- Les abonnements et le ou les titres unitaires les plus utilisés,
  l’ensemble devant représenter au moins 80% des validations.

- Ainsi que les tarifs sociaux et ceux dédiés aux accompagnateurs de
  personnes handicapées.

- Les titres restants pourront être décrits de façon plus succincte,
  comme indiqué en 6.12, et illustré en B.2 et B.3 en utilisant des
  « Notices » en lieu et place d’une description structurée et détaillée
  des droits d’accès et paramètres d’utilisation.

Concernant les parkings :

En complément du tableau ci-dessus, le tableau en Annexe B (Traçabilité avec les
éléments d’entrée) de la partie « Parking » du profil fournit une analyse
attribut par attribut des éléments attendus.

Concernant l'accessibilité :

La partie « Accessibilité » du profil propose 3 niveaux d’information, du plus
basique au plus complet.

Ces 3 niveaux d’information sont :

- les informations de base (voir 6.2), fondées sur l’évaluation a minima du
  respect des exigences d'accessibilité définies par la réglementation en
  vigueur mais pouvant également être déduites par le renseignement du niveau 3
  (6.5, 6.6 et Annexes);
- un niveau intermédiaire décrivant les services disponibles (voir 6.4) ;
- un niveau complet détaillant les cheminements et les équipements (voir 6.5,
  6.6 et Annexe), permettant le déploiement de l’information voyageur afin de
  proposer des trajets accessibles selon le profil et les besoins des usagers,
  respectant ainsi le caractère non discriminatoire des services d’information
  et les exigences de l’article L. 1115-8 du code des transports en matière
  d’information sur l’accessibilité.

L’arrêté du 28 mai 2024 définit les éléments a minima obligatoires pour la
description de l’accessibilité, soit tous les éléments de base.

Afin de fournir une information détaillée aux usagers, il est cependant
recommandé de compléter directement les attributs du niveau 3 de la partie «
Accessibilité » du profil lorsqu’ils sont disponibles.
