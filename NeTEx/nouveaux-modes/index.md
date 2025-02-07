## Avant-propos
L’harmonisation des pratiques dans l’échange des données relatives aux offres de transport est essentielle :

* pour l’usager, aux fins d’une présentation homogène et compréhensible de l’offre de transport et de l’engagement sous-jacent des organisateurs (autorités organisatrices et opérateurs de transports) ;

* pour les AOT, de manière à fédérer des informations homogènes venant de chacun des opérateurs de transports qui travaillent pour elle. 

*   L’harmonisation des échanges, et en particulier le présent profil, pourra le cas échéant être imposée par voie contractuelle. Cette homogénéité des formats d’information permet d’envisager la mise en place de systèmes d’information multimodaux, produisant une information globale de l’offre de transports sur un secteur donné, et garantir le fonctionnement des services d’information, en particulier des calculateurs d’itinéraires, et la cohérence des résultats, que ces services soient directement intégrés dans ces systèmes d’information multimodaux ou qu’ils puisent leurs informations sur des bases de données réparties ;

* pour les opérateurs, qui pourront utiliser ce format d’échange pour leurs systèmes de planification, les systèmes d’aide à l’exploitation, leurs systèmes billettiques et leurs systèmes d’information voyageur (information planifiée et information temps réel)

* pour les industriels et développeurs pour pérenniser et fiabiliser leurs investissements sur les formats d’échanges implémentés par les systèmes qu’ils réalisent, tout en limitant fortement l’effort de spécification lié aux formats d’échange

Ce document est le fruit de la collaboration entre les différents partenaires des autorités organisatrices de transports, opérateurs, industriels, développeurs de solutions et de systèmes informatiques, et associations d'usagers ayant pour objet l’aide à l’exploitation du transport public et l’information des voyageurs. Il a pour objet de présenter le profil d’échange Profil NeTEx Nouveaux modes: "format de référence pour l'échange de données de description des nouveaux modes" (issu des travaux NeTEx et Transmodel) qui aujourd’hui fait consensus dans les groupes de normalisation (CN03/GT7 – Transport public / information voyageur).

# Introduction

Le présent format déchange est un profil France de NeTEx

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
<span style='color:green'>***A rédiger ***</span>

# Références Normatives
Les documents de référence suivants sont indispensables pour l'application du présent document. Pour les références datées, seule l'édition citée s'applique. Pour les références non datées, la dernière édition du document de référence s'applique (y compris les éventuels amendements).

CEN/TS 16614-1, Network and Timetable Exchange (NeTEx) — Part 5: Alternative modes exchange format
CEN/prEN 12896-10: 2021, Public transport - Reference data model -Part 10 : Alternative modes

<span style='color:green'>***A rédiger ***</span>

# Termes et Définitions

Pour les besoins du présent document, les termes et définitions suivants s'appliquent. Ils sont directement issus de Transmodel et NeTEx. Pour une information complète, il conviendra toutefois de se référer au document nor-matif.
> NOTE	Les définitions ci-dessus sont des traductions littérales du document normatif. Seules les définitions spécifiques du profil France 'Nouveaux Modes' sont proposées ici, celles relatives aux autres profils sont disponibles dans les profils correspondants. 
## MODE OF OPERATION (MODE OPERATOIRE)
## CONVENTIONAL MODE OF OPERATION (MODE OPERATOIRE CONVENTIONNEL)
## ALTERNATIVE MODE OF OPERATION (MODE OPERATOIRE ALTERNATIF)
## VEHICLE SHARING (VEHICULE PARTAGE)
Location de véhicules à court terme où le véhicule peut être pris et garé à différents endroits de la zone urbaine, souvent sans la contrainte de ramener le véhicule à un endroit spécifique dédié.

## VEHICULE SHARING TYPE (TYPE DE VEHICULE PARTAGE)
## PERSONAL MODE OF OPERATION (MODE OPERATOIRE PERSONEL)
## MOBILITY SERVICE (SERVICE DE MOBILITE)
## VEHICLE SHARING SERVICE (SERVICE DE PARTAGE DE VEHICULE)
## VEHICLE SHARING PARKING AREA (STATION DE PARTAGE DE VEHICLES°)
## VEHICLE SHARING PARKING BAY (EMPLACEMENT DE VEHICLE DANS UNE STATION)
## VEHICLE SHARING PLACE ASSIGNEMENT (AFFECTATION DE LIEU DE  PARTAGE DE VEHICULE)
## MOBILITY SERVICE CONSTRAINT ZONE (ZONE D'UTILISATION DU SERVICE)µ
## ZONE USE TYPE (TYPE DE CONTRAINTE GEOGRAPHIQUE)
## VEHICLE TYPE ZONE RESTRICTION (TYPE DE CONTRAINTE SUR ZONE D'UTILISATION°)
## TARIFF DESCRIPTION GROUP
<span style='color:red'>***A confirmer ***</span>

## TARIFF ORGANISATION GROUP 
<span style='color:red'>***A confirmer ***</span>

## MONITORED VEHICLE SHARING PARKING BAY
## PARKING BAY STATUS
## PARKING AREA CAPACITY ASSIGNMENT



## Covoiturage (car pooling)
Mode consistant à partager une voiture privée pour un trajet entre un conducteur défini qui est déjà engagé dans le trajet et au moins un autre voyageur.

## Mode alternatif (alternative mode)
Mode d'exploitation annoncé publiquement, différent du mode d'exploitation conventionnel, en particulier le partage de véhicules, la location de véhicules et la mise en commun de véhicules.

## Mode de marche (walking mode)
la marche est considérée comme un mode d'accès, c'est-à-dire que le voyageur marche jusqu'à un point d'arrêt pour accéder aux autres modes de transports.

## Mode d'accès (access mode)
Caractérisation du déplacement du voyageur (par exemple, marche, vélo, etc.) lui permettant de se rendre à un arrêt de transport public ou d'effectuer une étape de son voyage.

## Service aux voyageurs (traveler service)
activité (en général, initiée par les utilisateurs) en vue de faciliter/permettre un voyage


## <span style='color:green'>***A compléter ***</span>


# Symboles et abréviations


# Description du profil d'échange Nouveaux Modes
## Conventions 
### De nommage
Dans ce profil, l'utilisation de "mode alternatif" ou "nouveau mode" est synonyme.
### De représentation
<span style='color:green'>***A compléter ***</span>

## Elements de contexte
### Catégorisation des modes de transport
Le terme 'mode' désigne tout moyen de transport utilisé ou disponible. Il est divisé en 'mode véhicule' et 'mode d'accès'.
* Le **'mode véhicule'** est une caractérisation de l'exploitation du transport public selon le moyen de transport, par exemple, bus, tramway, métro, train, ferry, bateau ou vélo.
* Le **'mode d'accès'** (par exemple, la marche, le cyclisme, la conduite de voiture privée, etc.) est une caractérisation du mouvement du voyageur (par exemple, marcher, faire du vélo, etc.) lui permettant d'atteindre le 'mode véhicule' ou de réaliser un voyage complet.

### Mode alternatifs
Les modes et sous-modes définis comme des 'moyens de transport' peuvent être caractérisés en termes de types de fonctionnement, c'est-à-dire des façons dont ils sont opérés.
Ce document distingue les types suivants de 'mode de fonctionnement' :
* **Mode de fonctionnement conventionnel** : le mode de fonctionnement traditionnel qui est proposé sous forme d'une offre de transport public annoncée et/ou flexible, selon un horaire fixe et/ou flexible. Ce mode de fonctionnement suit soit un horaire et des itinéraires fixes, soit est lié à un réseau/horaires fixes mais offre de la flexibilité, afin d'optimiser par exemple le service ou de répondre à la demande des passagers ;
* **Mode alternatif de fonctionnement** : tout mode de fonctionnement public annoncé différent du mode de fonctionnement conventionnel, notamment le partage de véhicules, la location de véhicules et le covoiturage ;
* **Mode personnel de fonctionnement** : un mode de transport privé excluant toute utilisation publiquement annoncée.
La distinction entre les modes de fonctionnement alternatif et conventionnel repose sur le fait qu'un mode conventionnel repose sur un ensemble de caractéristiques : les conducteurs sont des employés, la flotte est détenue par un opérateur ou une autorité, et la topologie du réseau est définie à l'avance et repose sur des lignes et des modèles de trajets ; tandis que les modes alternatifs peuvent ne pas remplir une ou plusieurs de ces caractéristiques.
Ce profil concerne le mode alternatif de fonctionnement.


<span style='color:green'>Element de l'annexe 1 PArt 5 NeTEx à synthétiser</span> 

## Les fonctions spécifiques

### Géorepérage et zones d'utilisation autorisées
La plupart des systèmes de partage de véhicules (vélo, trottinette, voiture, etc.) ne fonctionnent que dans une zone géographique spécifique. Cette zone peut être indiquée par des cartes ou des informations aux passagers, ou pour les véhicules avec des systèmes d'immobilisation à distance, peut même être imposée électroniquement par détection GPS. En outre, certaines zones de la zone opérationnelle peuvent être restreintes en raison de raisons opérationnelles, de sécurité ou autres, par exemple pour contrôler la pollution environnementale. Des pénalités financières peuvent être associées à la violation des limites restreintes à tout moment ou à un moment donné.
Les zones autorisées peuvent être décrites à l'aide de zones de contraintes de service de mobilité, chaque zone exprimant une étendue spatiale et les usages autorisés.
### Réservation
Les services de partage de vélos offrent une capacité de réservation à court terme, permettant aux utilisateurs de vérifier la station disponible la plus proche, de réserver un vélo et de s'enregistrer dans un délai court. Cependant, il n'y a généralement pas de réservation à l'avance ; l'utilisateur prend l'un des vélos disponibles à la station la plus proche.
### Tarifs et paiement
Dans le cadre du partage de vélos, dans la plupart des cas, les utilisateurs ne paient le service qu'une seule fois lors de l'abonnement et chaque fois qu'ils ont utilisé le vélo plus longtemps que la durée de location gratuite.


## Les services disponibles

### Véhicules partagés

#### Vélo en libre Service
Le partage de vélos est un mode d'exploitation dédié à la location de vélos à court terme, dans lequel le vélo peut être pris et garé à différents endroits dans une zone urbaine. L'une des principales différences entre le partage de vélos et la location de vélos réside dans le système sous lequel ils fonctionnent. La location de vélos est généralement ponctuelle. Le partage de vélos repose sur un ensemble d'utilisateurs abonnés qui partagent le service, généralement pour de courtes durées ou pour effectuer de petits trajets, moyennant un abonnement mensuel ou annuel fixe. 

Le tarif dépend d'un certain nombre de paramètres : il peut s'agir d'un simple intervalle de temps, d'un tarif pour excès de temps, ou inclure des réductions pour une utilisation fréquente en fonction d'un "profil de voyageur fréquent". Il convient de noter que, comme pour les services de transport conventionnels, les tarifs reposent sur un contrat qui peut être implicite et anonyme (mais dans de nombreux cas, le contrat est personnel), et ce contrat exprime l'"adhésion" à une communauté d'utilisateurs de services spécifiques
##### Avec Station
les vélos sont obtenus à partir d'un emplacement prédéterminé, comme une station de stationnement de vélos, où la station communique la disponibilité du vélo et enregistre quand il a été pris et retourné et par qui. La station de stationnement disposera de systèmes pour libérer un vélo pour le voyageur potentiel. Une station peut en réalité avoir une capacité supérieure au nombre strict de bornes si elle dispose de personnel pour récupérer des véhicules supplémentaires du stockage ou y en ramener afin d'équilibrer la demande – le service « voiturier ». Il peut être tout aussi important pour un utilisateur qu'il y ait une borne libre disponible pour y retourner son vélo à la fin de son trajet, sinon il pourrait faire face à une recherche chronophage et même à une pénalité pour usage prolongé.
##### Sans Station (Flottant)
Pour les vélos dans un système de partage de vélos sans station, qui disposent généralement de verrous d'immobilisation intégrés dans leur cadre, aucune station n'est nécessaire. Le vélo peut être laissé à n'importe quel endroit sûr dans la zone du schéma et être immobilisé ou réactivé à l'aide d'un code.


#### Auto Partage
### Representation (Concept & implémentation)

## CoVoiturage




# Entêtes NeTEx

# Annexes

# Bibliographie
