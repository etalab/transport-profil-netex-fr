## Avant-propos
L’harmonisation des pratiques dans l’échange des données relatives aux offres de transport est essentielle :

* pour l’usager, aux fins d’une présentation homogène et compréhensible de l’offre de transport et de l’engagement sous-jacent des organisateurs (autorités organisatrices et opérateurs de transports) ;

* pour les AOT, de manière à fédérer des informations homogènes venant de chacun des opérateurs de transports qui travaillent pour elle. 

*   L’harmonisation des échanges, et en particulier le présent profil, pourra le cas échéant être imposée par voie contractuelle. Cette homogénéité des formats d’information permet d’envisager la mise en place de systèmes d’information multimodaux, produisant une information globale de l’offre de transports sur un secteur donné, et garantir le fonctionnement des services d’information, en particulier des calculateurs d’itinéraires, et la cohérence des résultats, que ces services soient directement intégrés dans ces systèmes d’information multimodaux ou qu’ils puisent leurs informations sur des bases de données réparties ;

* pour les opérateurs, qui pourront utiliser ce format d’échange pour leurs systèmes de planification, les systèmes d’aide à l’exploitation, leurs systèmes billettiques et leurs systèmes d’information voyageur (information planifiée et information temps réel)

* pour les industriels et développeurs pour pérenniser et fiabiliser leurs investissements sur les formats d’échanges implémentés par les systèmes qu’ils réalisent, tout en limitant fortement l’effort de spécification lié aux formats d’échange

Ce document est le fruit de la collaboration entre les différents partenaires des autorités organisatrices de transports, opérateurs, industriels, développeurs de solutions et de systèmes informatiques, et associations d'usagers ayant pour objet l’aide à l’exploitation du transport public et l’information des voyageurs. Il a pour objet de présenter le profil d’échange Profil NeTEx Nouveaux modes: "format de référence pour l'échange de données de description des nouveaux modes" (issu des travaux NeTEx et Transmodel) qui aujourd’hui fait consensus dans les groupes de normalisation (CN03/GT7 – Transport public / information voyageur).

# Introduction

Le présent format déchange est un profil France de NeTEX

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

<span style='color:green'>***A rédiger ***</span>

# Termes et Définitions

Pour les besoins du présent document, les termes et définitions suivants s'appliquent. Ils sont directement issus de Transmodel et NeTEx. Pour une information complète, il conviendra toutefois de se référer au document nor-matif.
> NOTE	Les définitions ci-dessus sont des traductions littérales du document normatif. Seules les définitions spécifiques du profil France 'Nouveaux Modes' sont proposées ici, celles relatives aux autres profils sont disponibles dans les profils correspondants. 

## Covoiturage (car pooling)
Mode consistant à partager une voiture privée pour un trajet entre un conducteur défini qui est déjà engagé dans le trajet et au moins un autre voyageur.

## Mode alternatif (alternative mode)
Mode d'exploitation annoncé publiquement, différent du mode d'exploitation conventionnel, en particulier le partage de véhicules, la location de véhicules et la mise en commun de véhicules.

## Mode de marche (walking mode)
la marche est considérée comme un mode d'accès, c'est-à-dire que le voyageur marche jusqu'à un point d'arrêt pour accéder aux autres modes de transports.

## Mode d'accès (access mode)
Caractérisation du déplacement du voyageur (par exemple, marche, vélo, etc.) lui permettant de se rendre à un arrêt de transport public ou d'effectuer une étape de son voyage.

## Partage de véhicules (Vehicle Sharing)
Location de véhicules à court terme où le véhicule peut être pris et garé à différents endroits de la zone urbaine, souvent sans la contrainte de ramener le véhicule à un endroit spécifique dédié.
## Service aux voyageurs (traveler service)
activité (en général, initiée par les utilisateurs) en vue de faciliter/permettre un voyage


## <span style='color:green'>***A compléter ***</span>



# Symboles et abréviations

# Description du profil d'échange

## Elements de contexte

<span style='color:green'>Element de l'annexe 1 PArt 5 NeTEx à synthétiser</span> 

## Cas d'usage

### Vélos en libre Service

#### Free floating

<span style='color:red'>Traduction_?</span>

#### Docking

<span style='color:red'>Traduction_?</span>

### Covoiturage

<span style='color:green'>***A rédiger ***</span>

# Entêtes NeTEx

# Annexes

# Bibliographie
