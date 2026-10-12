# Termes et définitions

Pour les besoins du présent document, les termes et définitions
suivants s'appliquent. Ils sont directement issus de la traduction
française de Transmodel et NeTEx <span class="hl">(on notera que
certaines traductions sont un peu « étonnantes », toutefois il a été
jugé préférable de rester cohérent avec la traduction officielle). Il
conviendra souvent de se référer au corps du document car certaines
traductions officielles peuvent amener à une totale incompréhension des
concepts.</span>

Les termes spécifiquement introduits par le profil d’arrêt sont
signalés par le mot *(profil)*, en italique et entre parenthèses.

Pour une information complète, il conviendra toutefois de se référer au
document normatif.

# Partie Réseaux

## **ACCESS MODE** (MODE D’ACCÉS)

Caractérisation de déplacement d’un passager relatif à son mode de
transport en dehors des transports public (piéton, vélo, etc.).

→ Partie Réseaux

## **AUTHORITY** (AUTORITÉ ORGANISATRICE)

INSTITUTION sous la responsabilité de laquelle l’organisation des
transports est placée pour une zone géographique ou administrative
donnée.

→ Partie Réseaux

## **BOARDING POSITION** (POSITION D’EMBARQUEMENT)

Position d’une ZONE D’EMBARQUEMENT à partir de laquelle un passager
pourra embarquer, ou vers laquelle il débarquera d’un VÉHICULE

Note: cet objet n’a pas été retenu dans le Modèle d’Arrêt Partagé, mais
il s’y raccroche directement et est donc à considérer comme une
extension du Modèle d’Arrêt Partagé)

→ Partie Réseaux

## **BOOKING ARRANGEMENT** (CONDITIONS DE RESERVATION)

CONDITIONS DE RÉSERVATION pour une LIGNE FLEXIBLE.

→ Partie Réseaux

## **COMPOUND TRAIN** (TRAIN COMPOSÉ)

TYPE DE VEHICULE composé d’une séquence d’un ou plusieurs TRAIN.

→ Partie Réseaux

## **CONNECTION** (CORRESPONDANCE)

Possibilité physique (spatiale) d'un passager de passer d'un véhicule de
transport public vers un autre dans le but de continuer son voyage. Des
temps de parcours différents peuvent être nécessaires en fonction du
type de passager.

→ Partie Réseaux

## **CONNECTION END** (EXTRÉMITÉ DE CORRESPONDANCE)

Début ou fin d'une CORRESPONDANCE. Il s’agit forcément d’une relation
avec un POINT D’ARRÊT PLANIFIÉ.

→ Partie Réseaux

## **CONTACT DETAILS** (INFORMATIONS DE CONTACT)

Informations permettant au public de contacter une INSTITUTION.

→ Partie Réseaux

## **CONTROL CENTRE** (CENTRE DE CONTROL)

UNITÉ ORGANISATIONNELLE composée d’une équipe opérationnelle en charge
des commandes et du contrôle des services d’exploitation.

→ Partie Réseaux

## **DEAD RUN** (HAUT LE PIED)

PARCOURS associé à un HAUT LE PIED (sans transport des passagers :
retour dépôt, jonction entre ligne, etc.).

→ Partie Réseaux

## **DEFAULT CONNECTION** (CORRESPONDACE PAR DEFAUT)

Possibilité physique (spatiale) d'un passager de passer d'un véhicule de
transport public vers un autre dans le but de continuer son voyage. Elle
définit le temps par défaut à utiliser pour passer d'un véhicule de
transport à un autre au sein d'une zone (SITE, LIEU TOPOGRAPHIQUE, ZONE
D'ARRÊT). Elle peut être restreinte à des OPERATEURS ou des MODES des
transports particuliers, ou ne s'applique que dans un sens donné (une
correspondance bus vers train peut être différente de train vers bus).

→ Partie Réseaux

## **DESTINATION DISPLAY** (DESTINATION AFFICHÉE)

Une destination d'un PARCOURS (ou ITINÉRAIRE) particulier, affichée au
public en général sur une girouette ou sur tout autre afficheur
embarqué. Cette information peut évoluer au fur et à mesure de
l'évolution de la course et, en particulier, être mise à jour lors du
franchissement des points VIA.

→ Partie Réseaux

## **DESTINATION DISPLAY VARIANT** (VARIANTE DE DESTINATION AFFICHÉE)

alternative à la DESTINATION AFFICHÉE, généralement destiné à des média
spécifiques (SMS, type d’afficheur particulier, etc.)

→ Partie Réseaux

## **DIRECTION** (SENS)

Classification de l'orientation générale des ITINÉRAIREs.

→ Partie Réseaux

## **FLEXIBLE LINE** (LIGNE FLEXIBLE)

Spécialisation de la LIGNE pour décrire les services flexibles. Tous les
services d'une LIGNE peuvent ne pas être flexibles, la flexibilité
elle-même étant alors décrite au niveau du PARCOURS (cela signifie aussi
qu'il faudra définir des parcours spécifiques pour chaque type de
flexibilité de la LIGNE).

→ Partie Réseaux

## **FLEXIBLE LINK PROPERTIES** (PROPRIÉTÉ DE TRONÇON FLEXIBLE)

Ensemble de caractéristiques décrivant les éventuelles flexibilités
associées à un lien

Note: la relation est établie par composition pour limiter le recours à
l'héritage multiple.

→ Partie Réseaux

## **FLEXIBLE POINT PROPERTIES** (PROPRIÉTÉ DE POINT FLEXIBLE)

Ensemble de caractéristiques décrivant les éventuelles flexibilités
associées à un point

Note: la relation est établie par composition pour limiter le recours à
l'héritage multiple.

→ Partie Réseaux

## **FLEXIBLE ROUTE** (ITINERAIRE FLEXIBLE)

Spécialisation de l'ITINÉRAIRE pour décrire les services flexibles. Il
peut inclure des POINTs et des ZONEs, et des sections parcourues dans un
ordre prédéfini ou non.

→ Partie Réseaux

## **FLEXIBLE STOP PLACE** (LIEU D’ARRÊT FLEXIBLE)

Spécialisation du LIEU D’ARRÊT décrivant un arrêt d'un service flexible.
Il peut être composé de zones flexibles ou de zones de type « hail and
ride » identifiant les zones de montée ou descente possible des services
flexibles (quand ils utilisent des zones ou des quais flexibles).
Certains services flexibles utilisent aussi des LIEUx D’ARRÊT classiques
pour leurs arrêts. Quand il est assigné à un POINT D'ARRÊT PLANIFIÉ, ce
POINT D'ARRÊT PLANIFIÉ est alors censé être une zone (le centroïd de la
ZONE étant alors considéré comme le POINT D'ARRÊT PLANIFIÉ).

→ Partie Réseaux

## **GROUP OF LINES** (GROUPE DE LIGNES)

Regroupement de lignes référencées de manière commune relative à un
objectif donné.

→ Partie Réseaux

## **GROUP OF OPERATOR** (GROUPE D’EXPLOITANTS)

Groupe d’EXPLOITANTs ayant en commun, par exemple, un ensemble de règles
tarifaires et d’information voyageur.

→ Partie Réseaux

## **JOURNEY PATTERN** (PARCOURS)

Liste ordonnée de POINTs D'ARRÊT PLANIFIÉs et de POINTs HORAIREs sur un
unique ITINÉRAIRE, décrivant le plan de déplacement pour les véhicules
de transport public. Un PARCOURS peut passer par le même POINT plus
d'une fois. Le premier point d'un PARCOURS est l'origine. Le dernier
point est la destination.

→ Partie Réseaux

## **LINE** (LIGNE)

Groupe d'ITINÉRAIREs (voir plus bas) qui est en général connu du public
par une appellation commune (nom ou numéro, extrémités de ligne, etc.).

→ Partie Réseaux

## **NETWORK** (RÉSEAU)

Un GROUPE DE LIGNES disposant d'un nom sous lequel un réseau de
transport est connu.

→ Partie Réseaux

## **OPERATOR** (EXPLOITANT)

Entreprise offrant des services de transport public.

→ Partie Réseaux

## **PASSENGER STOP ASSIGNMENT** (AFFECTATION D’ARRÊT POUR PASSAGER)

Affection d’un POINT D’ARRÊT PLANIFIÉ à un LIEU D’ARRÊT (ou un de ses
composant de type ZONE D’EMBARQUEMENT ou POSITION D’EMBARQUEMENT) pour
un service passager.

→ Partie Réseaux

## **POINT IN JOURNEY PATTERN** (POINT SUR PARCOURS)

Un POINT D'ARRÊT PLANIFIÉ ou un POINT HORAIRE dans un PARCOURS indiquant
son rang dans ce PARCOURS.

→ Partie Réseaux

## **POINT IN TIMING PATTERN** (POINT SUR PARCOURS HORAIRE)

POINT sur PARCOURS qui est un POINT HORAIRE.

→ Partie Réseaux

## **POINT ON ROUTE** (POINT SUR ITINÉRAIRE)

POINT D'ITINÉRAIRE (accompagné de son rang) qui sert à définir un
ITINÉRAIRE.

→ Partie Réseaux

## **ROUTE LINK** (TRONÇON D'ITINÉRAIRE)

Tronçon orienté entre deux POINTs D'ITINÉRAIRE permettant une définition
univoque d'un chemin à travers le réseau.

→ Partie Réseaux

## **ROUTE POINT** (POINT D'ITINÉRAIRE)

POINT permettant de définir la géométrie d'un ITINÉRAIRE à travers le
réseau.

→ Partie Réseaux

## **ROUTE** (ITINÉRAIRE)

Liste ordonnée de POINTs définissant un seul chemin à travers le réseau
routier (ou ferré). Un ITINÉRAIRE peut passer deux fois par un même
POINT.

→ Partie Réseaux

## **ROUTING CONSTRAINT ZONE** (ZONE DE CONTRAINTE)

ZONE au sein de laquelle une contrainte d'acheminement s'applique. La
ZONE peut être définie soit par un périmètre géographique, soit par la
liste des POINTs D'ARRÊT PLANIFIÉS qu'elle contient.

→ Partie Réseaux

## **SCHEDULED STOP POINT** (POINT D'ARRÊT PLANIFIÉ)

POINT où les passagers peuvent monter à bord ou descendre des véhicules.

→ Partie Réseaux

## **SCHEMATIC MAP** (PLAN SCHÉMATIQUE)

Carte représentant schématiquement la disposition de la structure
topographique des lieux (par exemple, un ensemble de sites) ou le réseau
de transports en commun (un ensemble de lignes). Il peut comprendre une
projection de pixel ou objet de dessin vectoriel vers un ensemble
d'objet transport pour permettre les interactions, services et
hyperliens.

→ Partie Réseaux

## **SCHEMATIC MAP MEMBER** (COMPOSANT DE PLAN SCHÉMATIQUE)

Projection d’un objet transport sur un PLAN SCHÉMATIQUE.

→ Partie Réseaux

## **SERVICE JOURNEY PATTERN** (PARCOURS COMMERCIAL)

PARCOURS associé à une COURSE COMMERCIALE (transportant des passagers).

→ Partie Réseaux

## **SERVICE LINK** (TRONÇON COMMERCIAL)

TRONÇON entre une paire ordonnée de POINTs D'ARRÊT PLANIFIÉS.

→ Partie Réseaux

## **SERVICE PATTERN** (MISSION COMMERCIALE)

Vue d'un PARCOURS définie uniquement par des POINTs D'ARRÊT SUR
PARCOURS. La MISSION COMMERCIALE se distingue du PARCOURS COMMERCIAL par
le fait qu'elle n'est définie que par une séquence d'arrêts, sans point
intermédiaire.

→ Partie Réseaux

## **SITE CONNECTION** (CORRESPONDANCE ENTRE SITES)

La possibilité physique (spatiale) d'un passager de continuer son
déplacement déterminé par deux localisations comme des SITEs ou leurs
ENTRÉEs. Des temps de parcours différents peuvent être nécessaires en
fonction du type de passager.

→ Partie Réseaux

## **STOP ASSIGNMENT** (AFFECTATION D’ARRÊT)

Affection d’un POINT D’ARRÊT PLANIFIÉ à un LIEU D’ARRÊT.

→ Partie Réseaux

## **STOP POINT IN JOURNEY PATTERN** (POINT D'ARRÊT SUR PARCOURS)

POINT d'un PARCOURS qui est un POINT D'ARRÊT

→ Partie Réseaux

## **SUBMODE** (SOUS-MODE)

Précision sur le MODE, comme "international" ou "longue distance" (pour
un MODE Rail par exemple). Le SOUS-MODE caractérise très souvent un type
d'exploitation qui vient donc compléter le MODE.

→ Partie Réseaux

## **TIMING LINK** (TRONÇON HORAIRE)

Paire ordonnée de POINTs HORAIREs qui peut être utilisée pour
l'enregistrement des temps de parcours.

→ Partie Réseaux

## **TIMING PATTERN** (PARCOURS HORAIRE)

Vue d'un PARCOURS définie uniquement par des POINTs HORAIRE SUR
PARCOURS.

→ Partie Réseaux

## **TIMING POINT** (POINT HORAIRE)

POINT servant de référence aux données nécessaires à la conception des
horaires. Un POINT HORAIRE peut aussi être un POINT D’ARRÊT PLANIFIÉ
mais cela n’a rien d’obligatoire ou de systématique.

→ Partie Réseaux

## **TRAIN STOP ASSIGNMENT** (AFFECTATION D’ARRÊT DE TRAIN)

Affection d’un COMPOSANT DE TRAIN à un LIEU D’ARRÊT (ou un de ses
composant de type ZONE D’EMBARQUEMENT ou POSITION D’EMBARQUEMENT) pour
un POINT D’ARRÊT PLANIFIÉ donné.

→ Partie Réseaux

## **TRANSFER RESTRICTION** (RESTRICTION DE CORRESPONDANCE)

Contrainte qui s’applique aux CORRESPONDANCES (ou CORRESPONDANCES ENTRE
COURSES) entre deux POINTs D’ARRÊT PLANIFIÉs, en limitant voir
interdisant l’usage pour les passagers.

→ Partie Réseaux

## **TYPE OF LINES** (TYPE DE LIGNES)

Classification pour les lignes

→ Partie Réseaux

## **VEHICLE MODE** (MODE DE VÉHICULE)

Typologie de l'exploitation suivant le moyen de transport (bus, tramway,
métro, train, ferry, bateau).

→ Partie Réseaux

## **VIA** (VIA)

POINT utilisé comme POINT D'ITINÉRAIRE et permettant de distinguer deux
cheminements (ITINÉRAIREs) entre une origine et une destination. Il est
généralement défini à des fins d'information voyageur pour par exemple
différentier deux itinéraires sur un afficheur du réseau, ou encore sur
un système de vente.

→ Partie Réseaux

# Partie Parking

## **PARKING** (PARKING)

*(Transmodel)*

Emplacements désignés pour stationner des véhicules tels que des
voitures, des motos et des vélos.

→ Partie Parking

## **PARKING PROPERTIES** (PROPRIÉTÉ DU PARKING)

*(Transmodel)*

Propriéte spécifique du PARKING en complément de sa simple capacité
d’accueil.

→ Partie Parking

## **PARKING CAPACITY** (CAPACITÉ DU PARKING)

*(Transmodel)*

Capacités d’accueil du parking.

→ Partie Parking

## **PARKING ENTRANCE FOR VEHICLES** (ENTRÉE DU PARKING POUR LES VÉHICULES)

*(Transmodel)*

Entrée (et/ou sortie) du parking destinée aux véhicules

→ Partie Parking

## **PARKING PASSENGER ENTRANCE** (ENTRÉE DU PARKING POUR LES PIÉTONS)

*(Transmodel)*

Entrée (et/ou sortie) du parking destinée aux piétons et tout conducteur
ou passager des véhicule (y-compruis fauteuils roulants).

→ Partie Parking

## **PARKING COMPONENT** (COMPOSANT DE PARKING)

*(Transmodel)*

Composant générique du parking (par exemple PARKING AREA -zone de
parking- ou PARKING BAY -place de stationnement-)

→ Partie Parking

## **PARKING AREA** (ZONE DE PARKING)

*(Transmodel)*

Zone identifiée à l’intérieur d’un parking, et contenant des places de
stationnement (PARKING BAYs).

→ Partie Parking

## **PARKING BAY** (PLACE DE STATIONNEMENT)

*(Transmodel)*

Emplacement où l’on peut stationner un (unique) véhicule.

→ Partie Parking

# Partie éléments communs

## **NOTICE ASSIGNEMENT** (AFFECTATION DE NOTE)

*(TRANSMODEL)*

Affectation d'une NOTE à un objet pour signaler une exception sur une
COURSE, un PARCOURS. L'AFFECTATION DE NOTE permet de préciser les points
ou les sections d'un parcours concerné par la NOTE

→ Partie éléments communs

## **RESPONSIBILITY ROLE ASSIGNMENT** (AFFECTATION DE RÔLE)

*(NeTEx)*

Affectation d'un ou plusieurs RÔLEs à une INSTITUTION (ou une de ses
sous-organisation) vis-à-vis des responsabilités à assurer concernant
une donnée spécifique (comme la propriété, la planification, etc.) et de
la gestion de cette donnée (diffusion, mise à jour, etc.).

→ Partie éléments communs

## **ALTERNATIVE NAME** (ALIAS)

*(NeTEx)*

Nom alternatif pour un objet.

→ Partie éléments communs

## **ACCESSIBILITY ASSESSMENT** (ACCESSIBILITÉ)

*(IFOPT)*

L'ACCESSIBILITÉ représente les caractéristiques d'accessibilité, pour
les passagers, d'un SITE (comme un LIEU D'ARRÊT, un COMPOSANT DE LIEU
D'ARRÊT, etc.). Elle est décrite par des limitations d'ACCESSIBILITÉ
et/ou un ensemble de prise en compte d'exigences d'accessibilités.

→ Partie éléments communs

## **VALIDITY CONDITION** (CONDITION DE VALIDITÉ)

*(TRANSMODEL)*

Condition concourant à caractériser une VERSION donnée appartenant à un
CADRE DE VERSIONS. Une CONDITION DE VALIDITÉ est constituée d’un
paramètre (ex : une certaine date, un certain événement déclencheur,
etc.) et de son type d’application (Ex : « pour », « depuis »,
« jusqu’à », etc.).

→ Partie éléments communs

## **CONTACT DETAILS** (CONTACT)

*(NeTEx)*

Information des contacts permettant au public de joindre une INSTITUTION
(téléphone, mail, etc.).

→ Partie éléments communs

## **VALIDITY TRIGGER** (DÉCLENCHEMENT DE VALIDITÉ)

*(TRANSMODEL)*

Un événement extérieur définissant une CONDITION DE VALIDITÉ. Par
exemple : crue exceptionnelle, mauvais temps, route barrée pour travaux.

→ Partie éléments communs

## **ENTITY** (ENTITÉ)

*(TRANSMODEL)*

Une occurrence d'entité qui est gérée par un système de gestion de
versions. Quand des données de sources différentes coexistent dans un
système (multimodal ou multi-opérateur), une ENTITÉ doit être associée à
un SYSTÈME DE DONNÉES particulier qui l'a définie.

→ Partie éléments communs

## **ENTITY IN VERSION** (ENTITÉ PAR VERSION)

*(TRANSMODEL)*

Les ENTITÉs associées à une VERSION spécifique.

→ Partie éléments communs

## **PURPOSE OF GROUPING** (FINALITÉ DE GROUPEMENT)

*(TRANSMODEL)*

Un but fonctionnel pour lequel des GROUPEMENTs d'éléments sont définis.
La FINALITÉ DE GROUPEMENT peut être limitée à un ou plusieurs types d'un
objet donné.

→ Partie éléments communs

## **GROUP OF ENTITIES** (GROUPE D'ENTITÉS)

*(TRANSMODEL)*

Un regroupement d'ENTITÉs, connu souvent des usagers par un nom
spécifique ou un numéro.

→ Partie éléments communs

## **ORGANISATION** (INSTITUTION)

*(NeTEx)*

Une instance légale impliquée dans certains aspects du transport public.

→ Partie éléments communs

## **VEHICLE MODE** (MODE DE TRANSPORT)

*(TRANSMODEL)*

Le MODE DE TRANSPORT est une caractérisation du transport public
correspondant au moyen (véhicule) de transport (bus, tram, métro, train,
ferry, bateau, etc.).

→ Partie éléments communs

## **NOTICE** (NOTE)

*(TRANSMODEL)*

Un texte à vocation informationnelle, en général concernant des
exceptions d'utilisation (sans que cela ne soit une limitation), et
rattaché à une LIGNE, un PARCOURS, etc.

→ Partie éléments communs

## **POINT** (POINT)

*(TRANSMODEL)*

Un nœud de dimension 0 servant à la description spatiale du réseau. Les
POINTs peuvent être localisés par la LOCALISATION dans un SYSTÈME DE
LOCALISATION donné.

→ Partie éléments communs

## **DATA SOURCE** (SOURCE DE DONNEES)

*(TRANSMODEL)*

La SOURCE DE DONNEES identifie le système qui a produit la donnée. La
connaissance de la SOURCE DE DONNÉES est particulièrement utile dans le
contexte de l'interopérabilité des systèmes d'information.

→ Partie éléments communs

## **SUB-MODE** (SOUS MODE)

*(NeTEx)*

Le SOUS MODE est un complément d'information au MODE DE TRANSPORT,
permettant généralement de caractériser le type d'exploitation (par
exemple "bus interurbain" dans le cas d'un MODE DE TRANSPORT "bus").

→ Partie éléments communs

## **LINK SEQUENCE** (SUITE DE TRONÇON)

*(TRANSMODEL)*

Une suite ordonnée de POINTs ou TRONÇONs définissant un chemin à travers
le réseau.

→ Partie éléments communs

## **LINK** (TRONÇON)

*(TRANSMODEL)*

Un objet défini dans l'espace, orienté et de dimension 1, utilisé pour
décrire la structure du réseau, définissant la connexion entre deux
POINTs.

→ Partie éléments communs

## **DELIVERY VARIANT** (VARIANTE DE DIFFUSION)

*(TRANSMODEL)*

Variante d'une NOTE pour une utilisation sur un média spécifique (texte
lu, imprimé, etc.).

→ Partie éléments communs

## **VERSION** (VERSION)

*(TRANSMODEL)*

Un ensemble de données opérationnelles qui sont caractérisées par les
mêmes CONDITIONs DE VALIDITÉ. Une version appartient à un seul CADRE DE
VERSIONS et est caractérisée par un unique TYPE DE VERSION, par exemple
VERSION du réseau pour la ligne 12 à partir du 01-01-2000.

→ Partie éléments communs

## **ZONE** (ZONE)

*(TRANSMODEL)*

Espace de dimension 2 (surface) au sein de la zone de couverture d'un
opérateur de transport public (zone administrative, zone tarifaire, zone
d'accès, etc.).

→ Partie éléments communs

# Partie horaires

## **COUPLED JOURNEY** (COURSE COUPLÉE)

Un voyage complet opéré par un train couplé, composé de deux COURSES, ou
plus, restant couplées tout au long d’un PARCOURS. Une COURSE COUPLÉE
peut être considérée comme une simple COURSE.

→ Partie horaires

## **DATED PASSING TIME** (HEURE DE PASSAGE DATÉE)

HEURE DE PASSAGE pour un JOUR D'EXPLOITATION donné. Cet objet restera
abstrait dans le contexte de ce profil et ne sera utiliséutilisé qu’au
travers de sa spécialisation en HEURE DE PASSAGE COMMANDÉE.

→ Partie horaires

## **DATED VEHICLE JOURNEY** (COURSE DATÉE)

Service service particulier d'un véhicule sur un jour de fonctionnement
particulier, y compris toutes les modifications éventuellement décidées
par le personnel de contrôle. Cet objet restera abstrait dans le
contexte de ce profil et ne sera utilisé qu’au travers de sa
spécialisation en COURSE DATÉE NORMALE.

→ Partie horaires

## **DEAD RUN** (HAUT LE PIED)

Un service voiture haut-le-pied (non commercial).

→ Partie horaires

## **DEFAULT INTERCHANGE** (CORRESPONDANCE PAR DEFAUT)

Paramètre définissant la durée acceptable (maximum autorisée et objectif
de durée standard) pour une correspondance entre deux POINTS D'ARRÊT.

→ Partie horaires

## **FLEXIBLE SERVICE PROPERTIES** (PROPRIÉTÉS DE COURSE FLEXIBLE)

Propriété supplémentaire d'un service permettant de caractériser sa
flexibilité. Un service peut n'être que partiellement flexible.

→ Partie horaires

## **HEADWAY INTERVAL** (INTERVAL)

Intervalle temporel caractérisant un GROUPE DE COURSE À INTERVALLE (par
exemple toutes les 10 minutes ou toutes les 4 à 6 minutes).

→ Partie horaires

## **HEADWAY JOURNEY GROUP** (GROUPE DE COURSES EN FRÉQUENCE)

Groupe de COURSEs suivant le même PARCOURS et dont les départs sont
séparés d'un intervalle temporel fixe au sein d'un créneau horaire donné
(par exemple toutes les 10 minutes entre 8h et 10h30). Cette information
est particulièrement utile dans le cadre de l'information voyageur. Le
créneau horaire est exprimé par l'objet TIME BAND.

→ Partie horaires

## **INTERCHANGE** (CORRESPONDANCE DE COURSES)

Une possibilité théorique de correspondance entre courses intervenant à
un seul POINT D'ARRÊT ou entre différents POINTs D'ARRÊT.

→ Partie horaires

## **JOURNEY FREQUENCY GROUP** (GROUPE DE COURSES EN FRÉQUENCE)

Définit un groupe de COURSEs afin de leur attribuer un comportement
particulier comme un service en fréquence ou un service cadencé (passe
toutes les heures ..h10, ..h25 et ..h45 par exemple).

→ Partie horaires

## **JOURNEY PART** (PARTIE DE COURSE)

Une partie d'une COURSE créée dans un but fonctionnel spécifique,
notamment dans les situations lors de couplage ou de séparation de
véhicule.

→ Partie horaires

## **JOURNEY PART COUPLE** (COUPLE DE PARTIES DE COURSE)

Deux PARTIEs DE COURSEs de différentes COURSES effectuées simultanément
par un train constitué par le couplage de plusieurs véhicules ou rames.

→ Partie horaires

## **NORMAL DATED VEHICLE JOURNEY** (COURSE DATÉE NORMALE)

Une COURSE DATÉE correspondant à la planification du parcours des
véhicules.

→ Partie horaires

## **PASSING TIME** (HEURE DE PASSAGE)

Données temporelles concernant le passage des véhicules de transport
public à un POINT particulier (par exemple heure d'arrivée, heure de
départ, temps d'attente).

→ Partie horaires

## **RHYTMHICAL JOURNEY GROUP** (GROUPE DE COURSES CADENCÉES)

Groupe de COURSEs suivant le même PARCOURS et répétant le même rythme de
départ toutes les heures (passe toutes les heures ..h10, ..h25 et ..h45
par exemple) et ce dans un créneau horaire donnée. Le créneau horaire
est exprimé par l'objet TIME BAND sur le schéma.

→ Partie horaires

## **SERVICE JOURNEY** (COURSE COMMERCIALE)

Une COURSE transportant des passagers prévus pour un JOUR TYPE donné. Le
déroulement est en principe défini par le PARCOURS COMMERCIAL.

→ Partie horaires

## **SERVICE JOURNEY INTERCHANGE** (CORRESPONDANCE DE COURSES COMMERCIALES)

Une possibilité théorique de correspondance entre COURSEs COMMERCIALEs
intervenant à un seul POINT D'ARRÊT ou entre différents POINTs D'ARRÊT.

→ Partie horaires

## **TARGET PASSING TIME** (HEURE DE PASSAGE COMMANDÉE)

Données temporelles indiquant l'objectif à atteindre quant au passage du
véhicule à un POINT SUR PARCOURS particulier pour une COURSE DATÉE afin
de respecter l'horaire en vigueur. Concrètement il s'agit de
l'adaptation des HEUREs DE PASSAGE DATÉEs faite en exploitation pour
prendre en compte les changements de condition d'exploitation en amont
du départ du véhicule (travaux, etc.).

→ Partie horaires

## **TEMPLATE SERVICE JOURNEY** (MODÈLE DE COURCE COMMERCIALE)

COURSE DE RÉFÉRENCE transportant des voyageurs.

→ Partie horaires

## **TEMPLATE VEHICLE JOURNEY** (COURSE DE RÉFÉRENCE)

COURSE modèle dont l'occurrence a été spécifiée au sein d'un GROUPE DE
COURSE À INTERVALLE ou d'un GROUPE DE COURSE CADENCÉ; elle peut donc
représenter un grand nombre de COURSEs.

→ Partie horaires

## **TIMETABLE PASSING TIME** (HEURE DE PASSAGE PLANIFIÉE)

Donnée temporelle théorique relative au passage d'un véhicule de
transport public à un POINT SUR PARCOURS donné sur une COURSE et pour un
JOUR TYPE. On notera qu'il ne s'agit pas d'une simple heure de
franchissement, mais que cette heure de passage est constituée de
l’heure de d’arrivée et de départ ainsi que d’informations associées
(quai, marges d’erreur, etc.).

→ Partie horaires

## **TRAIN** (TRAIN)

Un véhicule composé d'ÉLÉMENTs DE TRAIN dans un certain ordre,
c'est-à-dire de voitures reliées et tirées par une locomotive ou une des
voitures.

→ Partie horaires

## **TRAIN COMPONENT** (COMPOSANT DE TRAIN)

La position d'un ÉLÉMENT DE TRAIN dans un TRAIN.

→ Partie horaires

## **TRAIN COMPONENT LABEL ASSIGNMENT** (AFFECTION DE LABEL DE VOITURE)

L'affectation d'une désignation annoncée pour un véhicule ou un élément
de véhicule pour passagers. Concrètement, cela permet de connaître le
libellé de la voiture (tel qu’indiqué sur la réservation du voyageur).
Ce libellé ne dépend pas que du type de TRAIN mais aussi de la COURSE à
laquelle il est affecté.

→ Partie horaires

## **TRAIN ELEMENT** (ÉLÉMENT DE TRAIN)

Une composante élémentaire d'un TRAIN (par exemple voiture, locomotive).

→ Partie horaires

## **TRAIN IN COMPOUND TRAIN** (TRAIN DANS UN TRAIN COMPOSÉ)

La position d'un TRAIN dans un TRAIN COMPOSÉ.

→ Partie horaires

## **TRAIN NUMBER** (NUMÉRO DE TRAIN)

Spécification spécification des codes attribués à certaines COURSES ou
PARTIE DE COURSE, lorsqu'elles sont réalisées par des TRAINs ou des
TRAINs COMPOSÉs, pour répondre à un objectif fonctionnel (d'information
des passagers, suivi des opérations, etc).

→ Partie horaires

## **TYPE OF FLEXIBLE SERVICE** (TYPE DE COURSE FLEXIBLE)

Classification classification des services flexibles.

→ Partie horaires

## **VEHICLE JOURNEY** (COURSE)

Le mouvement planifié d'un véhicule de transport public effectué un JOUR
TYPE donné, depuis un point début à un point fin d'un PARCOURS sur un
ITINÉRAIRE. La COURSE est donc l'instanciation d'un PARCOURS donné,
auquel on va attribuer des heures de passage aux arrêts et des jours
d'application.

→ Partie horaires

## **VEHICLE MODEL** (MODÈLE DE VEHICULE)

Une classification des véhicules de transport public d'un même TYPE DE
VÉHICULE, par exemple suivant les spécifications relatives aux
équipements ou à la génération du modèle.

→ Partie horaires

## **VEHICLE TYPE** (TYPE DE VEHICULE)

Une classification des véhicules de transport public résultant des
spécifications de la planification des horaires en tenant compte du mode
de transport et de la capacité requise (par exemple bus standard, bus à
étage, …).

→ Partie horaires

# Partie Arrêts

## **STOP PLACE ENTRANCE** (ACCÈS DE LIEU D'ARRÊT)

*(Transmodel)*

Un ACCÈS DE LIEU D'ARRÊT est un accès physique à un LIEU D’ARRÊT (entrée
ou sortie). Il peut comporter une porte, une barrière, un portillon ou
tout autre signe distinctif d’un accès.

→ Partie Arrêts

## **ENTRANCE** (ACCÈS DE SITE)

*(Transmodel)*

Un ACCÈS DE SITE est un accès physique à un SITE (entrée ou sortie). Il
peut comporter une porte, une barrière, un portillon ou tout autre signe
distinctif d’un accès.

→ Partie Arrêts

## **ADDRESS** (ADRESSE)

*(Transmodel)*

Adresse d'un lieu (postale et/ou sur voirie)

→ Partie Arrêts

## **POSTAL ADDRESS** (ADRESSE POSTALE)

*(Transmodel)*

Spécification d'une ADRESSE sur la base des attributs
conventionnellement utilisés par les services postaux. Cela comprend
diverses identifications du bâtiment, le nom de la rue, le code postal
et d'autres descripteurs.

→ Partie Arrêts

## **ROAD ADDRESS** (ADRESSE SUR VOIRIE)

*(Transmodel)*

Spécification d'une ADRESSE sur la base des attributs permettant
d’identifier sa position sur la voirie, comme les numéros, types et nom
de voies, et les éléments de positionnement le long de la voie.

→ Partie Arrêts

## **STOP PLACE COMPONENT** (COMPOSANT DE LIEU D'ARRÊT)

*(Transmodel)*

Un COMPOSANT DE LIEU D'ARRÊT est un constituant d'un LIEU D'ARRÊT qui en
décrit une partie de la structure. Les COMPOSANTs DE LIEU D'ARRÊT
partagent avec le LIEU D'ARRÊT lui-même un certain nombre de propriétés
pour la gestion des données, l'accessibilité et diverses autres
caractéristiques.

→ Partie Arrêts

## **SITE COMPONENT** (COMPOSANT DE SITE)

*(Transmodel)*

Un COMPOSANT DE LIEU est un constituant d'un SITE qui en décrit une
partie de la structure. Les COMPOSANTs DE LIEU partagent avec le LIEU
lui-même un certain nombre de propriétés pour la gestion des données,
l'accessibilité et diverses autres caractéristiques.

→ Partie Arrêts

## **SITE ELEMENT** (ÉLÉMENT DE SITE)

*(Transmodel)*

Type de LIEU définissant des propriétés communes pour les SITEs et
COMPOSANTs DE SITES auxquels il correspond, incluant l’ACCESSIBILITÉ.

→ Partie Arrêts

## **STOP PLACE SPACE** (ESPACE DE LIEU D'ARRÊT)

*(Transmodel)*

Espace (physique) au sein d'un LIEU D'ARRÊT, par exemple une ZONE
D'EMBARQUEMENT, un POINT D'EMBARQUEMENT, un LIEU D'ÉQUIPEMENT, etc.

→ Partie Arrêts

## **GROUP OF STOP PLACE** (GROUPE DE LIEUX D’ARRÊT)

*(Transmodel)*

Il correspond à une spécialisation de la notion normalisée TRANSMODEL de
GROUPE D’ENTITÉs (GROUP OF ENTITIES en anglais).

→ Partie Arrêts

## **PLACE** (LIEU)

*(Transmodel)*

Zone géographique d'un quelconque type qui peut être utilisé comme point
de départ ou d'arrivée d'un déplacement. Un lieu peut être de dimension
0 (POINT), 1 (comme une route par exemple) ou 2 (ZONE).

→ Partie Arrêts

## **Monomodal STOP PLACE** (LIEU D’ARRÊT Monomodal)

*(profil)*

Il correspond à une spécialisation de la notion normalisée de LIEU
D'ARRÊT (STOP PLACE en anglais) dédiant le LIEU et ses COMPOSANT à un
unique MODE.

→ Partie Arrêts

## **Multimodal STOP PLACE** (LIEU D’ARRÊT Multimodal)

*(profil)*

Il correspond aussi à une spécialisation de la notion normalisée de LIEU
D'ARRÊT (STOP PLACE en anglais) : un LIEU D’ARRÊT Multimodal n’est
composé que de LIEUx D’ARRÊT Monomodaux et Pôles Monomodaux de modes
différents.

→ Partie Arrêts

## **STOP PLACE** (LIEU D'ARRÊT)

*(Transmodel)*

Lieu comprenant un ou plusieurs emplacements où les véhicules peuvent
s’arrêter et où les voyageurs peuvent monter à bord ou descendre des
véhicules ou préparer leur déplacement.

→ Partie Arrêts

## **TOPOGRAPHICAL PLACE** (LIEU TOPOGRAPHIQUE)

*(Transmodel)*

Espace géographique offrant un contexte topographique lors de la
recherche ou de la présentation d'itinéraire (par exemple pour l'origine
ou la destination du déplacement). Cet espace peut être de toute taille
(pays, ville, village, etc.) et correspondre à des périmètres très
variés (Greater London, London, West End, Westminster, St James s,
etc.).

Un LIEU TOPOGRAPHIQUE doit toujours disposer d'un nom officiel. Il peut
être utile/nécessaire de définir une relation hiérarchique entre les
LIEUx TOPOGRAPHIQUEs de façon à les distinguer de façon non ambigüe, en
particulier en cas d'identité de nom.

→ Partie Arrêts

## **VEHICLE MODE** (MODE DE TRANSPORT)

*(Transmodel)*

Le MODE DE TRANSPORT est une caractérisation du transport public
correspondant au moyen (véhicule) de transport (bus, tram, métro, train,
ferry, bateau, etc.).

→ Partie Arrêts

## **Monomodal Hub** (Pôle Monomodal)

*(profil)*

Le Pôle Monomodal correspond à une spécialisation de la notion
normalisée de LIEU D'ARRÊT (STOP PLACE en anglais) : un Pôle Monomodal
n’est composé que de LIEUx D’ARRÊT Monomodaux de modes identiques mais
de noms différents.

→ Partie Arrêts

## **BOARDING POSITION** (POSITION D'EMBARQUEMENT)

*(Transmodel)*

Emplacement au sein d'une ZONE D'EMBARQUEMENT à partir desquels les
passagers peuvent embarquer, ou vers lequel ils peuvent débarquer du
VÉHICULE.

→ Partie Arrêts

## **SITE** (SITE)

*(Transmodel)*

Type de LIEU (comme un LIEU D'ARRÊT, un POINT D'INTÉRÊT, etc.) vers ou à
partir duquel un voyageur peut souhaiter vouloir voyager. Un SITE peut
avoir des ENTRÉEs qui en constituent les points d'accès (correspondant
éventuellement à des besoins utilisateurs particuliers: PMR, etc.).

→ Partie Arrêts

## **LINK SEQUENCE** (SUITE DE TRONÇON)

*(Transmodel)*

Une suite ordonnée de POINTs ou TRONÇONs définissant un chemin à travers
le réseau.

→ Partie Arrêts

## **QUAY** (ZONE D’EMBARQUEMENT)

*(Transmodel)*

Lieu tel qu’une plateforme, zone, quai ou voie à quai où les voyageurs
peuvent accéder aux véhicules de transport public, taxis, cars ou tout
autre mode de transport.

→ Partie Arrêts

## **TARIFF ZONE** (ZONE TARIFAIRE)

*(Transmodel)*

Une ZONE utilisée dans un système de tarification zonale.

→ Partie Arrêts

# Partie Accessibilité



## **ACCESSIBILITY ASSESSMENT** (ÉVALUATION D'ACCESSIBILITÉ)

Caractéristiques d'accessibilité d'une entité utilisée par les
passagers, telles qu'un LIEU D’ARRET ou un COMPOSANT DE LIEU D’ARRET.
Décrites par LIMITES D'ACCESSIBILITÉ et / ou un ensemble de d’APTITUDEs
(pour l’accessibilité).

→ Partie Accessibilité

## **ACCESSIBILITY LIMITATION** (LIMITE D'ACCESSIBILITÉ)

Catégorisation des caractéristiques d'accessibilité d'un SITE (p. ex. :
LIEU D'ARRÊT ou COMPOSANT DE LIEU D'ARRÊT) pour indiquer son
utilisabilité par les passagers ayant des besoins spécifiques, notamment
ceux nécessitant un accès par fauteuil roulant, un accès sans marche ou
ceux voulant éviter les espaces confinés tels que les ascenseurs.
Quelques catégories bien définies sont utilisées, choisies pour
permettre la saisie efficace des données et le calcul efficace
d'itinéraires pour les différentes classes d'usager.

→ Partie Accessibilité

## **ACCESS** (ACCÈS)

Possibilité matérielle (spatiale) pour un usager d'accéder à un système
de transports publics ou de le quitter. Ce tronçon peut être utilisé
pendant un déplacement pour permettre au voyageur d'effectuer : - le
trajet à pied d'un LIEU (origine du déplacement) vers un POINT D'ARRÊT
PLANIFIÉ (origine du DÉPLACEMENT SUR RÉSEAU), ou - le trajet à pied
depuis un POINT D'ARRÊT PLANIFIÉ (destination du DÉPLACEMENT SUR RÉSEAU)
vers un LIEU (destination du déplacement).

→ Partie Accessibilité

## **ACCESS END** (FIN D'ACCÈS)

Origine ou destination d'un tronçon d'ACCÈS. Peut indiquer un POINT
et/ou un LIEU.

→ Partie Accessibilité

## **ACCESS MODE** (MODE D'ACCÈS)

Caractérisation du trajet d'un passager lorsqu'il emprunte un moyen de
transport autre que les transports publics (p. ex : à pied, à vélo, etc.).

→ Partie Accessibilité

## **ACCOMODATION** (HÉBERGEMENT)

Combinaison de caractéristiques d'hébergement disponibles sur un service
(p. ex : "Couchette première classe douche/2 lits").

→ Partie Accessibilité

## **ACTUAL VEHICLE EQUIPMENT** (ÉQUIPEMENT VÉHICULE RÉEL)

Équipement d'un type particulier sur un VÉHICULE donné.

→ Partie Accessibilité

## **ASSISTANCE SERVICE** (SERVICE D'ASSISTANCE)

SERVICE LOCAL spécialisé dans l'ASSISTANCE, fournissant des informations
telles que la langue, le personnel formé à l'accessibilité, etc.

→ Partie Accessibilité

## **CATERING SERVICE** (SERVICE DE RESTAURATION)

Spécialisation de SERVICE LOCAL dédiée aux services de restauration.

→ Partie Accessibilité

## **COMMUNICATION SERVICE** (SERVICE DE COMMUNICATIONS)

Spécialisation de SERVICE LOCAL dédiée aux services de communications.

→ Partie Accessibilité

## **COMPLAINTS SERVICE** (SERVICE DE RÉCLAMATIONS)

Spécialisation du SERVICE CLIENT pour les RÉCLAMATIONS.

→ Partie Accessibilité

## **CROSSING EQUIPMENT** (ÉQUIPEMENT DE CROISEMENT)

ÉQUIPEMENT D'ACCÈS À LA PLACE spécialisé pour ÉQUIPEMENTS DE
FRANCHISSEMENT (passages piétons, éclairage piétons, dispositif
acoustique, capteurs, bandes de guidage tactiles, etc.).

→ Partie Accessibilité

## **CUSTOMER SERVICE** (SERVICE CLIENT)

SERVICE LOCAL générique spécial pour SERVICE CLIENT (objets perdus,
point de rencontre, réclamations, etc.).

→ Partie Accessibilité

## **CYCLE STORAGE EQUIPMENT** (ÉQUIPEMENT DE STOCKAGE DE CYCLE)

Spécialisation de l'ÉQUIPEMENT DE PLACE décrivant les équipements de
parc pour deux-roues.

→ Partie Accessibilité

## **ENCUMBRANCE NEED** (BESOIN DE TRANSPORT DE BAGAGES)

BESOIN D'USAGER spécifique, à savoir une exigence d'un passager
voyageant avec des bagages, un animal ou tout autre objet, et qui
nécessite donc des dispositions particulières pour accéder aux
transports publics.

→ Partie Accessibilité

## **ENTRANCE EQUIPMENT** (ÉQUIPEMENT D'ENTRÉE)

Spécialisation d'ÉQUIPEMENT D'ACCÈS À LA PLACE pour ENTRÉES (portes,
barrières, portes tournantes, etc.)

→ Partie Accessibilité

## **EQUIPMENT** (ÉQUIPEMENT)

Équipement installé de manière fixe (ÉQUIPEMENT DE LIEU) ou à bord des
véhicules (ÉQUIPEMENT VÉHICULE). Un service (SERVICE LOCAL de type
CONSIGNE, SERVICE DE BILLETTERIE) est considéré comme un équipement
immatériel.

→ Partie Accessibilité

## **EQUIPMENT PLACE** (LIEU DES EQUIPEMENTS)

COMPOSANT DE SITE comprenant un ÉQUIPEMENT

→ Partie Accessibilité

## **EQUIPMENT POSITION** (POSITION DES EQUIPEMENTS)

La place précise au sein d'un LIEU DES ÉQUIPEMENTS d'équipements
particuliers.

→ Partie Accessibilité

## **ESCALATOR EQUIPMENT** (ÉQUIPEMENT D'ESCALIER ROULANT)

Spécialisation de l'ÉQUIPEMENT D'ESCALIER pour des ESCALIERS ROULANTS.

→ Partie Accessibilité

**FACILITY (INSTALLATION)** 

*note : la traduction SERVICE aurait probablement été plus appropriée*

Commodité nommée mise à la disposition du public sur un SITE ou un
SERVICE. Une prestation ne possède pas d'autres propriétés qu'un nom. Un
ÉQUIPEMENT ou SERVICE LOCAL est utilisé pour décrire les autres
propriétés fournies dans le cadre d'une prestation particulière.

→ Partie Accessibilité

## **FACILITY SET** (ENSEMBLE D'INSTALLATIONS)

Ensemble d'INSTALLATIONS disponibles pour une COURSE COMMERCIALE ou un
MORCEAU DE COURSE. L'ensemble peut être disponible uniquement pour un
TYPE DE VÉHICULE spécifique du SERVICE (p. ex : voiture équipée d'un
plancher surbaissé).

→ Partie Accessibilité

## **GENERAL SIGN** (SIGNALISATION GÉNÉRALE)

Spécialisation d'ÉQUIPEMENT DE SIGNALISATION différent des INDICATIONS
DE DIRECTION et de LIEU.

→ Partie Accessibilité

**HEADING SIGN (SIGNALISATION DE TITRE)** 

*note : GIROUETTE aurait été une traduction plus appropriée*

Spécialisation d'ÉQUIPEMENT DE SIGNALISATION indiquant le nom d'une
direction, d'une ligne, etc.

→ Partie Accessibilité

## **HIRE SERVICE** (SERVICE DE LOCATION)

Spécialisation de SERVICE LOCAL dédiée aux services de location (cycles,
voitures).

→ Partie Accessibilité

## **INSTALLED EQUIPMENT** (ÉQUIPEMENT INSTALLÉ)

Équipement installé de manière fixe (ÉQUIPEMENT DE LIEU) ou embarqué
(associé à des véhicules). Cet équipement est matérialisé par opposition
à un service (SERVICE LOCAL), considéré comme un équipement immatériel.

→ Partie Accessibilité

## **LEFT LUGGAGE SERVICE** (SERVICE DE CONSIGNE)

Spécialisation du SERVICE CLIENTÈLE pour les consignes à bagages
(casiers en libre-service, gratuits, etc.).

→ Partie Accessibilité

## **LIFT EQUIPMENT** (ÉQUIPEMENT D'ASCENSEUR)

Spécialisation d'ÉQUIPEMENT D'ACCÈS À LA PLACE pour ASCENSEURS (indique
des caractéristiques telles que la profondeur, la charge maximale,
etc.).

→ Partie Accessibilité

## **LOCAL SERVICE** (SERVICE LOCAL)

Service identifié en fonction de l'utilisation du SITE ou des services
de transport à un lieu particulier (p. ex :porteur, assistance aux
usagers handicapés, bureaux de réservation). Le service peut posséder
une CONDITION DE VALIDITÉ qui lui est associée. Un SERVICE LOCAL est
traité comme une forme d'ÉQUIPEMENT immatériel.

→ Partie Accessibilité

## **LOST PROPERTY SERVICE** (SERVICE DES OBJETS TROUVÉS)

Spécialisation du SERVICE CLIENTÈLE pour les objets trouvés.

→ Partie Accessibilité

## **LUGGAGE SERVICE** (SERVICE BAGAGES)

Spécialisation du SERVICE CLIENTÈLE pour les bagages
(installations/équipements et caractéristiques telles que les chariots à
bagages, l'utilisation gratuite, etc.).

→ Partie Accessibilité

## **LUGGAGE LOCKER EQUIPMENT** (ÉQUIPEMENT DE CONSIGNE À BAGAGES)

Spécialisation de l'ÉQUIPEMENT DE POINT D'ARRÊT pour les consignes à
bagages.

→ Partie Accessibilité

## **MEDICAL NEED** (BESOIN MÉDICAL)

BESOIN D'USAGER spécifique, à savoir une exigence d'un passager en ce
qui concerne une contrainte médicale (p. ex : allergie) pour accéder aux
transports publics.

→ Partie Accessibilité

## **MEETING POINT SERVICE** (SERVICE DE POINT DE RENCONTRE)

Spécialisation du SERVICE CLIENT pour les points de rencontre
(caractéristiques telles que la description, le libellé, etc.).

→ Partie Accessibilité

## **MOBILITY NEED** (BESOIN DE MOBILITÉ)

BESOIN D'USAGER spécifique, à savoir une contrainte d'un passager en ce
qui concerne sa mobilité (p. ex : fauteuil roulant, fauteuil roulant
motorisé).

→ Partie Accessibilité

## **MONEY SERVICE** (SERVICE DE CHANGE)

Spécialisation de SERVICE LOCAL dédiée aux services d'argent.

→ Partie Accessibilité

## **NAVIGATION PATH** (CHEMINEMENT USAGER)

Un tronçon désigné entre deux endroits. Peut inclure une séquence triée
de TRONÇONS DE CHEMINEMENT.

→ Partie Accessibilité

## **NAVIGATION PATH ASSIGNMENT** (AFFECTATION DE CHEMINEMENT DE NAVIGATION)

Affectation d'un CHEMINEMENT USAGER à une AFFECTATION DE POINT D'ARRÊT
spécifique, par exemple, pour indiquer le chemin à prendre pour établir
une CONNEXION.

→ Partie Accessibilité

## **ONBOARD STAY** (SÉJOUR À BORD)

Permission d'embarquer avant la course ou de rester à bord après la
course.

→ Partie Accessibilité

## **PASSENGER EQUIPMENT** (ÉQUIPEMENT USAGER)

Équipement d'un type particulier réellement disponible au niveau d'un
LIEU ou d'un VÉHICULE.

→ Partie Accessibilité

## **PASSENGER INFORMATION EQUIPMENT** (ÉQUIPEMENT D'INFORMATIONS AUX PASSAGERS)

Un équipement destiné à fournir des informations sur les transports en
commun, tels que des terminaux (dans la rue, aux guichets ou reliés à un
central, etc.) ou des supports papier (affichettes aux points d'arrêt,
fascicules, etc.).

→ Partie Accessibilité

## **PASSENGER SAFETY EQUIPMENT** (ÉQUIPEMENT DE SÉCURITÉ DES PASSAGERS)

Spécialisation ÉQUIPEMENT PASSAGER pour la sécurité des passagers.

→ Partie Accessibilité

## **PATH JUNCTION** (NŒUD DE CHEMINEMENT)

Un point précis, à l'intérieur ou à l'extérieur d'un LIEU D'ARRÊT ou
d'un POINT D'INTERÊT, au niveau duquel deux TRONÇONS DE CHEMINEMENTS
peuvent se connecter

→ Partie Accessibilité

## **PATH LINK** (TRONÇON DE CHEMINEMENT)

Un tronçon dans un LIEU ou entre plusieurs LIEUX (par exemple, LIEUX
D'ARRÊT, ESPACES D'ACCÈS ou QUAIS, POINTS D'EMBARQUEMENT, POINTS
D'INTÉRÊT, etc., NŒUDS DE CHEMINEMENT), qui représente une étape d'un
itinéraire possible pour les piétons, les cyclistes ou les autres
passagers non véhiculés au sein d'un LIEU ou entre des LIEUX.

NOTE Il est possible, mais pas obligatoire, qu'un TRONÇON DE CHEMINEMENT
projette sur un ensemble d'infrastructures ou de tronçons de mapping
plus détaillés qui tracent l'itinéraire dans l'espace, ce qui permet de
le représenter sur des plans et des systèmes de suivi.

→ Partie Accessibilité

## **PATH LINK END** (FIN DE TRONÇON DE CHEMINEMENT)

SITE de départ ou d'arrivée d'un TRONÇON DE CHEMINEMENT. Il peut être
lié à un NIVEAU spécifique du SITE.

→ Partie Accessibilité

## **PATH LINK IN SEQUENCE** (TRONÇON DE CHEMINEMENT EN SÉQUENCE)

Étape d'un CHEMINEMENT USAGER indiquant la traversée d'un TRONÇON DE
CHEMINEMENT particulier au sein d'un itinéraire recommandé.

→ Partie Accessibilité

## **PLACE ACCESS EQUIPMENT** (ÉQUIPEMENT D'ACCÈS À LA PLACE)

Spécialisation d'ÉQUIPEMENT DE LIEU dédiée à l'accès (ascenseurs,
entrées, escaliers, rampes, etc.).

→ Partie Accessibilité

## **PLACE EQUIPMENT** (ÉQUIPEMENT DE LIEU)

Équipement d'un type particulier réellement disponible au niveau d'un
LIEU.

→ Partie Accessibilité

## **PLACE IN SEQUENCE** (LIEUX ACCESSIBLES EN SEQUENCE)

Point traversé par un CHEMINEMENT USAGER en séquence, connecté par un
TRONÇON DE CHEMINEMENT jusqu'au point suivant. Il peut s'agir d'un lieu,
d'un NŒUD ou d'un POINT.

→ Partie Accessibilité

## **PLACE LIGHTING** (ÉCLAIRAGE DE LA PLACE)

Spécialisation de l'ÉQUIPEMENT DE LIEU pour ÉQUIPEMENT D'ÉCLAIRAGE (par
ex., réverbère).

→ Partie Accessibilité

## **PLACE SIGN** (SIGNALISATION DE PLACE)

Panneau portant le nom d'un LIEU.

→ Partie Accessibilité

## **POINT OF INTEREST** (POINTS D'INTÉRÊT)

Type de LIEU vers ou à travers lequel les passagers peuvent souhaiter
circuler au cours de leur course et qui est modélisé en détail par les
calculateurs d'itinéraire.

→ Partie Accessibilité

## **PSYCHOSENSORY NEED** (BESOIN PSYCHOSENSORIEL)

BESOIN D'USAGER spécifique, à savoir une contrainte d'un passager
relative à un handicap psychosensoriel (p. ex : troubles visuels ou
auditifs, aversion pour les espaces confinés).

→ Partie Accessibilité

## **QUEUING EQUIPMENT** (ÉQUIPEMENT DE FILE D'ATTENTE)

Spécialisation d'ÉQUIPEMENT D'ACCÈS AU LIEU dédiée aux files d'attente.

→ Partie Accessibilité

## **RAMP EQUIPMENT** (ÉQUIPEMENT DE RAMPE)

Spécialisation d'ÉQUIPEMENT D'ACCÈS AU LIEU pour rampes (indique des
caractéristiques telles que la profondeur, la pente, etc.).

→ Partie Accessibilité

## **RETAIL SERVICE** (SERVICE DE DÉTAIL)

Spécialisation de SERVICE LOCAL dédiée aux services de distribution.

→ Partie Accessibilité

## **ROUGH SURFACE** (SURFACE RUGUEUSE)

Spécialisation de l'ÉQUIPEMENT DE LIEU pour surfaces rugueuses, qui
indique la texture des surfaces, principalement pour informer les
personnes handicapées.

→ Partie Accessibilité

## **RUBBISH DISPOSAL** (ÉLIMINATION DES DÉCHETS)

Spécialisation des ÉQUIPEMENTS pour évacuation des déchets, indiquant
les types de déchets, etc.

→ Partie Accessibilité

## **SANITARY EQUIPMENT** (ÉQUIPEMENT SANITAIRE)

Spécialisation ÉQUIPEMENT PASSAGER pour les installations sanitaires.

→ Partie Accessibilité

## **SEATING EQUIPMENT** (ÉQUIPEMENT DE SIÈGES)

Spécialisation de l'ÉQUIPEMENT DE LIEU décrivant les propriétés des
sièges

→ Partie Accessibilité

## **SERVICE FACILITY SET** (ENSEMBLE D'INSTALLATIONS DE SERVICE)

Ensemble d'INSTALLATIONS disponibles pour un TYPE DE VÉHICULE spécifique
(p. ex : voiture équipée d'un plancher surbaissé), éventuellement pour
un service uniquement (ou pour une COURSE ou une COURSE COMMERCIALE).

→ Partie Accessibilité

## **SHELTER EQUIPMENT** (ÉQUIPEMENT D'ABRIS)

Spécialisation de l'ÉQUIPEMENT D'ATTENTE pour un abri.

→ Partie Accessibilité

## **SIGN EQUIPMENT** (ÉQUIPEMENT DE SIGNALISATION)

Spécialisation de l'ÉQUIPEMENT DE LIEU pour la signalisation
(directions, etc.).

→ Partie Accessibilité

## **SITE EQUIPMENT** (ÉQUIPEMENT DE SITE)

Spécialisation d'ÉQUIPEMENT DE LIEU pour SITES (CASIER À BAGAGES,
ÉQUIPEMENT D'ATTENTE, STAND DE CHARIOTS, etc.)

→ Partie Accessibilité

## **SITE FACILITY SET** (ENSEMBLE D'INSTALLATIONS SUR SITE)

Ensemble d'INSTALLATIONS disponibles pour un ÉLÉMENT DE SITE.

→ Partie Accessibilité

## **STAIR EQUIPMENT** (ÉQUIPEMENT D'ESCALIER)

Specialisation of ACCESS EQUIPMENT for stairs (stair, escalator,
staircase, etc.).

→ Partie Accessibilité

## **STAIRCASE EQUIPMENT** (ÉQUIPEMENT D'ESCALIER)

Spécialisation d'ÉQUIPEMENT D'ACCÈS AU LIEU pour escaliers (escalier,
escalier mécanique, cage d'escalier, etc.).

→ Partie Accessibilité

## **SUITABILITY** (APPROPRIATION)

Déclaration stipulant si un BESOIN D'USAGER particulier peut être
satisfait. Elle peut être utilisée pour indiquer si un SITE est
accessible par un passager ayant un BESOIN particulier.

→ Partie Accessibilité

## **TICKET VALIDATOR EQUIPMENT** (ÉQUIPEMENT DE VALIDATION DE TITRES DE TRANSPORT)

Spécialisation de l'ÉQUIPEMENT PASSAGER (ÉQUIPEMENT DE LIEU) décrivant
les contrôleurs de billets.

→ Partie Accessibilité

## **TICKETING EQUIPMENT** (ÉQUIPEMENT DE DISTRIBUTION DE TITRES DE TRANSPORT)

Spécialisation de l'ÉQUIPEMENT PASSAGER pour la billetterie.

→ Partie Accessibilité

## **TICKETING SERVICE** (SERVICE DE DISTRIBUTION DE TITRES DE TRANSPORT)

Spécialisation de SERVICE LOCAL pour billetterie, fournissant des
informations sur les guichets de billetterie et les achats en ligne,
également associée à la méthode de paiement et au TYPE DE BILLET.

→ Partie Accessibilité

## **TRAVELATOR EQUIPMENT** (ÉQUIPEMENT DE TAPIS ROULANT)

Spécialisation d'ÉQUIPEMENT D'ACCÈS AU LIEU pour tapis roulants
(propriétés telles que la vitesse, etc.).

→ Partie Accessibilité

## **TROLLEY STAND EQUIPMENT** (ÉQUIPEMENT DE STANDS DE CHARIOTS)

Spécialisation de l'ÉQUIPEMENT DE POINT D'ARRÊT pour les stands de
chariots.

→ Partie Accessibilité

## **TYPE OF ACCESSIBILITY TOOLS** (TYPE D'OUTILS D'ACCESSIBILITÉ)

Classification des OUTILS D'ACCESSIBILITÉ utilisés ou mis à disposition
par le SERVICE D'ASSISTANCE (fauteuils roulants, cannes, navigateurs
audio, navigateurs visuels, etc.).

→ Partie Accessibilité

## **TYPE OF ASSISTANCE SERVICE** (SERVICE DE TYPE D'ASSISTANCE)

Classification de SERVICE D'ASSISTANCE (assistance à l'embarquement, à
bord, portage, langues étrangères, traduction en langage des signes,
etc.).

→ Partie Accessibilité

## **TYPE OF EMERGENCY SERVICE** (SERVICE DE TYPE D'URGENCE)

Typologie des services d'urgence (police, premiers secours, borne
d'appel, vidéosurveillance).

→ Partie Accessibilité

**TYPE OF GENDER LIMITATION (SERVICE DE LIMITATION DE SEXE)** 

*Note le
traducteur officiel aurait peut-être pu se relire ici !!* 

Classification des LIMITATIONS SELON LE GENRE (principalement pour
ÉQUIPEMENTS SANITAIRES, par ex., réservé aux hommes/femmes, ou les
deux).

→ Partie Accessibilité

## **TYPE OF HANDRAIL** (TYPE DE MAIN COURANTE)

Classification de MAIN COURANTE (un côté, deux côtés).

→ Partie Accessibilité

## **TYPE OF SANITARY FACILITY** (SERVICE D'INSTALLATION SANITAIRE)

Classification d'ÉQUIPEMENT SANITAIRE (toilettes, toilettes pour
handicapés, douches, table à langer, table à langer pour handicapés)

→ Partie Accessibilité

## **TYPE OF STAFFING** (TYPE DE PERSONNEL)

Classification de disponibilité du PERSONNEL associé à un SERVICE
D'ASSISTANCE (plein temps, temps partiel)

→ Partie Accessibilité

## **TYPE OF USER NEED** (TYPE DE BESOIN D'USAGER)

Classification des BESOINS D'USAGERS.

→ Partie Accessibilité

## **USER NEED** (BESOIN D'USAGER)

Besoin d'un usager exigeant une APPROPRIATION particulière.

→ Partie Accessibilité

## **VEHICLE ACCESS EQUIPMENT** (ÉQUIPEMENT D'ACCÈS AU VÉHICULE)

Spécialisation de l'ÉQUIPEMENT VÉHICULE permettant l'accès aux
véhicules, qui fournit différentes

informations (p. ex : plancher surbaissé, rampe, dimensions de la zone
d'accès).

→ Partie Accessibilité

## **VEHICLE CHARGING EQUIPMENT** (ÉQUIPEMENT DE RECHARGE DE VÉHICULE)

Spécialisation de l'ÉQUIPEMENT DE PLACE pour la recharge de véhicule.

→ Partie Accessibilité

## **WAITING EQUIPMENT** (ÉQUIPEMENT D'ATTENTE)

Spécialisation de l'ÉQUIPEMENT DE LIEU D'ARRÊT pour ÉQUIPEMENTS
D'ATTENTE (abri, salle d'attente, etc.).

→ Partie Accessibilité

## **WAITING ROOM EQUIPMENT** (ÉQUIPEMENT DE SALLE D'ATTENTE)

Spécialisation de l'ÉQUIPEMENT D'ATTENTE pour salle d'attente, classée
par TYPE DE SALLE D'ATTENTE.

→ Partie Accessibilité

## **WHEELCHAIR VEHICLE EQUIPMENT** (ÉQUIPEMENT VÉHICULE POUR FAUTEUILS ROULANTS)

Spécialisation de l'ÉQUIPEMENT VÉHICULE permettant l'accès des fauteuils
roulants à bord d'un VÉHICULE, qui fournit différentes informations (p.
ex : nombre de places pour fauteuils roulants et dimensions de l'accès).

→ Partie Accessibilité

# Partie Tarifs

## **ACCESS RIGHT IN PRODUCT** (DROIT D’ACCÈS D’UN PRODUIT tarifaire)

Un ÉLÉMENT VALIDABLE (VALIDABLE ELEMENT) faisant partie d’un PRODUIT
TARIFAIRE PRÉDÉFINI (PRE-ASSIGNED FARE PRODUCT), éventuellement incluant
un numéro d’ordre dans un ensemble d’ ÉLÉMENTs VALIDABLEs regroupés pour
définir les droits d’accès de ce PRODUIT TARIFAIRE PRÉDÉFINI

→ Partie Tarifs

## **ACCESS RIGHT PARAMETER ASSIGNMENT** (AFFECTATION DES PARAMÈTRES DES DROITS D'ACCÈS)

L'affectation d'un paramètre tarifaire (faisant référence à la
géographie, au temps, à la qualité ou à l'usage) à un élément d'un
système tarifaire (droit d'accès, accès validé, moyen de contrôle,
etc.).

→ Partie Tarifs

## **AMOUNT OF PRICE UNIT** (MONTANT D’UNITÉS TARIFAIRE)

PRODUIT TARIFAIRE constitué d'une valeur stockée d'UNITÉS TARIFAIRE : une
somme d'argent sur un porte-monnaie électronique, une quantité d'unités
transport sur une carte, etc.

→ Partie Tarifs

## **BORDER POINT** (POINT FRONTALIER)

Un POINT sur le Réseau marquant une limite pour le calcul tarifaire.
Peut ou non être un POINT D'ARRÊT PLANIFIÉ.

→ Partie Tarifs

## **CAPPED DISCOUNT RIGHT** (REDUCTION PAR PLAFONNEMENT)

Spécialisation du DROIT A REDUCTION utilisé pour les tarifications de
type « pay-as-you-go », où une fois qu'un certain niveau de consommation
a été atteint dans un intervalle de temps donné, un plafond (tel que
spécifié par une ou plusieurs RÈGLES DE PLAFONNEMENT) est appliqué, par
exemple en limitant le coût, pour toute utilisation au cours d’une même
journée, au prix d'un passe journalier.

→ Partie Tarifs

## **CELL** (CELLULE)

Une combinaison unique de caractéristique au sein d'un GRILLE TARIFAIRE,
utilisée pour associer un prix à un élément de tarif.

→ Partie Tarifs

## **CHARGING MOMENT** (MOMENT DE PAIMENT)

Une classification des PRODUITS TARIFAIRES selon le mode de paiement et
le type de compte : pré-paiement à usage unique, pré-paiement avec débit
sur carte, pré-paiement sans enregistrement de consommation (pass),
post- paiement etc...

→ Partie Tarifs

## **CHARGING POLICY** (POLITIQUE DE PAIEMENT)

Paramètre régissant le montant minimum et le crédit autorisé lors de la
consommation d'un PRODUIT TARIFAIRE.

→ Partie Tarifs

## **CLASS OF USE** (CLASSE D’UTILISATION)

Une classification des tarifs et autres classes de services par
catégorie d'utilisateur autorisé à les utiliser.

→ Partie Tarifs

## **COMMERCIAL PROFILE** (PROFIL COMMERCIALE)

Catégorisation d'utilisateurs en fonction de leurs relations
commerciales avec l'opérateur (fréquence d'utilisation, montant
d'achat…), souvent utilisée pour les remises.

→ Partie Tarifs

## **COMPANION PROFILE** (PROFIL D’ACCOMPAGNATEUR)

Le nombre et les caractéristiques des personnes autorisées à voyager en
tant qu’accompagnateur d'un autre PROFIL UTILISATEUR.

→ Partie Tarifs

## **DISTANCE MATRIX ELEMENT** (ÉLÉMENT DE MATRICE DE DISTANCES)

Une cellule d'une matrice origine-destination pour les ZONES TARIFAIRES
ou POINTS D'ARRÊT, exprimant une distance tarifaire pour le trajet
correspondant : valeur en km, nombre d'unités tarifaires etc.

→ Partie Tarifs

## **DISTRIBUTION ASSIGNMENT** (AFFECTATION DE DISTRIBUTION)

Une affectation du CANAL DE DISTRIBUTION par lequel un produit peut ou
non être distribué.

→ Partie Tarifs

## **DISTRIBUTION CHANNEL** (CANAL DE DISTRIBUTION)

Un type de point de vente pour la vente d'un produit.

→ Partie Tarifs

## **DISTRIBUTION VALIDITY PARAMETERS** (PARAMÈTRE DE VALIDITÉ POUER LA DISTRIBUTION)

Un type de PARAMÈTRE DE VALIDITÉ lié à la distribution des produits
tarifaires.

→ Partie Tarifs

## **ELIGIBILITY CHANGE POLICY** (POLITIQUE POUR LE CHANGEMENT D’ÉLIGIBILITÉ)

La politique à appliquer si l'éligibilité d'un utilisateur, en tant que
PROFIL UTILISATEUR, change.

→ Partie Tarifs

## **ENTITLEMENT GIVEN** (DROIT OBTENU)

Paramètre indiquant si un PRODUIT TARIFAIRE particulier donne le droit
d'acheter ou d'utiliser un droit d'accès.

→ Partie Tarifs

## **ENTITLEMENT PRODUCT** (PRODUIT OUVRANT DES DROITS)

Une condition préalable pour accéder à un service ou pour acheter un
PRODUIT TARIFAIRE délivré par une organisation qui peut ne pas être un
opérateur transport public (par exemple, une carte militaire).

→ Partie Tarifs

## **ENTITLEMENT REQUIRED** (DROIT REQUIS)

Paramètre indiquant si un PRODUIT TARIFAIRE nécessite un droit ou
autorisation particulière pour pouvoir l’acheter ou l’utiliser.

→ Partie Tarifs

## **EXCHANGING** (ÉCHANGE)

Si et comment le droit d'accès peut être échangé contre un autre droit
d'accès.

→ Partie Tarifs

## **FARE DEMAND FACTOR** (FACTEUR TARIFAIRE LIÉ À LA DEMENADE)

Un ensemble nommé de paramètres définissant une période de déplacement
avec un prix donné, par exemple heures creuses, heures pleines, super
heures creuses, etc.

→ Partie Tarifs

## **FARE ELEMENT IN SEQUENCE** (D’ÉLÉMENT TARIFAIRE EN SÉQUENCE)

Un ÉLÉMENT TARIFAIRE faisant partie d'un ensemble, y compris son ordre
éventuel dans la séquence d'ÉLÉMENTS TARIFAIRE.

→ Partie Tarifs

## **FARE POINT IN JOURNEY PATTERN** (POINT TARIFAIRE DANS UN PARCOURS)

Un POINT SUR PARCOURS qui représente le début ou la fin d'une SECTION
TARIFAIRE, ou un point utilisé pour définir une CONTRAINTE DE SÉRIE.

→ Partie Tarifs

## **FARE PRICE** (PRIX)

Caractéristiques de prix définies par défaut caractérisant les
différents GROUPES DE PRIX.

→ Partie Tarifs

## **FARE PRODUCT** (PRODUIT TARIFAIRE)

Un élément commercialisable immatériel (droits d'accès, droits de
remise, etc.), propre à un MOMENT DE PAIEMENT.

→ Partie Tarifs

## **FARE QUOTA FACTOR** (FACTEUR DE QUOTA TARIFAIRE)

Un ensemble paramètres définissant un nombre maximal de tarifs
disponibles pour une dénomination donnée.

→ Partie Tarifs

## **FARE SCHEDULED STOP POINT** (POINT D’ARRÊT TARIFAIRE)

Une spécialisation de POINT D'ARRÊT PLANIFIÉ décrivant un arrêt avec des
caractéristiques tarifaires en lien avec l’itinéraire.

→ Partie Tarifs

## **FARE SECTION** (SECTION TARIFAIRE)

Subdivision d'un PARCOURS constitué de POINTs consécutifs sur ce
PARCOURS, utilisée pour définir un élément de la structure tarifaire.

→ Partie Tarifs

## **FARE STRUCTURE ELEMENT** (ÉLÉMENT DE STRUCTURE TARIFAIRE)

Une séquence ou un ensemble d'éléments tarifaires auxquels sont
appliquées des règles de limitation des droits d'accès et de calcul des
prix (structure tarifaire).

→ Partie Tarifs

## **FARE STRUCTURE ELEMENT IN SEQUENCE** (ÉLÉMENTS DE STRUCTURE TARIFAIRE EN SÉQUENCE)

Un ÉLÉMENT DE STRUCTURE TARIFAIRE faisant partie d'un ÉLÉMENT VALIDABLE,
y compris son ordre éventuel dans la séquence d'ÉLÉMENTS DE STRUCTURE
TARIFAIRE formant cet ÉLÉMENT VALIDABLE, et son éventuelle limitation
quantitative.

→ Partie Tarifs

## **FARE TABLE** (GRILLE TARIFAIRE)

Un regroupement de prix pouvant être associé à tout ou partie des
éléments suivants : ÉLÉMENT DE MATRICE DE DISTANCE, ÉLÉMENT DE STRUCTURE
TARIFAIRE INTERVALLE GÉOGRAPHIQUE, GROUPE DE PARAMÈTRE DE DROIT D'ACCÈS,
CLASSE D'UTILISATION, OPÉRATEUR, MODE VÉHICULE, PRODUIT TARIFAIRE.

→ Partie Tarifs

## **FARE VALIDITY PARAMETERS** (PARAMETRES DE VALIDITÉ TARIFAIRE)

Un type de PARAMÈTRE DE VALIDITÉ lié aux produits tarifaires et/ou à
leur distribution.

→ Partie Tarifs

## **FARE ZONE** (ZONE BILLÉTIQUE)

Specialisation d’une ZONE TARIFAIRE pour inclure les SECTIONs
TARIFAIREs.

→ Partie Tarifs

## **FREQUENCY OF USE** (FÉQUENCE D’UTILISATION)

Limites de fréquence d'utilisation d'un PRODUIT TARIFAIRE (ou d'un de
ses composants) ou d'une OFFRE A LA VENTE pendant une PÉRIODE DE
VALIDITÉ déterminée. Il peut y avoir des tarifications différentes selon
la fréquence de consommation du droit au cours de la période.

→ Partie Tarifs

## **FULFILMENT METHOD** (MÉTHODE DE DÉLIVRANCE)

Le moyen par lequel le billet est remis au CLIENT, par ex. en ligne,
collecte, etc.

→ Partie Tarifs

## **GENERIC PARAMETER ASSIGNMENT** (AFFECTATION GÉNÉRIQUE DES PARAMÈTRES)

Une AFFECTATION DE PARAMETRES DE VALIDITE spécifiant des droits d'accès
génériques pour une classe de produits (par exemple une limite de
tranche horaire - 7h à 10h - pour les trajets effectués avec un titre
étudiant).

→ Partie Tarifs

## **GEOGRAPHICAL INTERVAL** (INTERVAL GÉOGRAPHIQUE)

Un intervalle géographique précisant les droits d'accès pour les
ÉLÉMENTS DE STRUCTURE TARIFAIRE dans la plage de cet intervalle : 0-5
km, 4-6 zones etc.

→ Partie Tarifs

## **GEOGRAPHICAL STRUCTURE FACTOR** (FACTEUR D’INTERVAL GÉOGRAPHIQUE)

La valeur d'un INTERVALLE GEOGRAPHIQUE ou d'un ELEMENT MATRICE DE
DISTANCE exprimée par une UNITÉ GEOGRAPHIQUE.

→ Partie Tarifs

## **GEOGRAPHICAL UNIT** (UNITÉ GÉOGAPHIQUE)

Une unité de calcul des tarifs géographiques dégressifs.

→ Partie Tarifs

## **GROUP OF DISTANCE MATRIX ELEMENTS** (GROUPE D’ÉLÉMENT MATRICES DE DISTANCE)

Un regroupement d'ÉLÉMENTS DE MATRICE DE DISTANCE. Peut être utilisé
pour fournir des paires Origine/Destination réutilisables (et leur
associer un PRIX).

→ Partie Tarifs

## **GROUP OF SALES OFFER PACKAGES** (GROUPE D’OFFRES À LA VENTE)

Un groupement d’OFFREs À LA VENTE

→ Partie Tarifs

## **GROUP TICKET** (TICKET DE GROUPE)

Le nombre et les caractéristiques des personnes autorisées à voyager en
plus du titulaire d'un droit d'accès.

→ Partie Tarifs

## **LUGGAGE ALLOWANCE** (BAGAGES AUTORISÉS)

Le nombre et les caractéristiques (poids, volume) des bagages qu'un
titulaire d'un droit d'accès est autorisé à transporter.

→ Partie Tarifs

## **MINIMUM STAY** (SÉJOUR MINIMUM)

Détails de tout séjour minimum à la destination requis pour utiliser le
produit.

→ Partie Tarifs

## **NETWORK VALIDITY PARAMETERS** (PARAMETRES DE VALIDITÉ DU RESEAU)

Un type de PARAMÈTRE DE VALIDITÉ lié à la structure du réseau.

→ Partie Tarifs

## **ORGANISATIONAL VALIDITY PARAMETERS** (PARAMETRES DE VALIDITÉ ORGANISATIONELS)

Un type de PARAMÈTRE DE VALIDITÉ relatifs à l'organisation.

→ Partie Tarifs

## **PENALTY POLICY** (POLITIQUE D’AMENDE)

Politique concernant différents aspects des frais de pénalité, par
exemple entrée répétée dans la même gare, ne pas avoir de billet, etc.

→ Partie Tarifs

## **PLACE VALIDITY PARAMETERS** (PARAMETRES DE VALIDITÉ DES LIEUX)

Un type de PARAMÈTRE DE VALIDITÉ relatifs aux sites du réseau.

→ Partie Tarifs

## **PRE-ASSIGNED FARE PRODUCT** (PRODUIT TARIFAIRE PRÉDÉFINI)

UN PRODUIT TARIFAIRE composé d'un ou plusieurs ÉLÉMENTS VALIDABLES,
spécifiques à un MODE DE PAIEMENT.

→ Partie Tarifs

## **PRICEABLE OBJECT** (OBJET AVEC PRIX)

Un élément qui peut avoir un PRIX.

→ Partie Tarifs

## **PRODUCT VALIDITY PARAMETERS** (PARAMETRES DE VALIDITÉ DU PRODUIT)

Un type de PARAMÈTRE DE VALIDITÉ lié aux produits tarifaires.

→ Partie Tarifs

## **PURCHASE WINDOW** (FENÊTRE D’ACHAT)

Période pendant laquelle le produit doit être acheté.

→ Partie Tarifs

## **QUALITY STRUCTURE FACTOR** (FACTEUR QUALITATIF)

Un facteur influençant la définition des droits d'accès ou le calcul des
prix, en fonction de la qualité : seuil de congestion du trafic,
réservation anticipée/tardive, etc.

→ Partie Tarifs

## **QUALITY STRUCTURE FACTOR PRICE** (PRIX DE FACTEUR QUALITATIF)

Un ensemble de toutes les caractéristiques de prix possibles d'un
FACTEUR QUALITATIF, par ex. prix total par défaut, etc.

→ Partie Tarifs

## **REFUNDING** (REMBOURSEMENT)

Indique si et comment le produit peut être remboursé.

→ Partie Tarifs

## **REPLACING** (REMPLACEMENT)

Indique si et comment le produit peut être remplacé.

→ Partie Tarifs

## **RESELLING** (REVENTE)

Conditions de revente (c'est-à-dire pour échange ou remboursement)
attachées au produit.

→ Partie Tarifs

## **RESERVING** (RESERVATION)

Indiquer si le droit d'accès nécessite une réservation.

→ Partie Tarifs

## **RESIDENTIAL QUALIFICATION** (QUALIFICATION RÉSIDENTIELLE)

Décrit une exigence de résidence dans une certaine zone géographique.

→ Partie Tarifs

## **ROUND TRIP** (ALLER RETOUR)

Propriétés relatives à l'usage pour un aller simple ou un aller-retour
d'un droit d'accès.

→ Partie Tarifs

## **ROUTING** (ITINÉRAIRE)

Limitations d'un droit d'accès relative à l’itinéraire réalisable.

→ Partie Tarifs

## **ROUTING VALIDITY PARAMETERS** (PARAMETRE DE VALIDITE DE L’ITINERAIRE)

Un type de PARAMÈTRE DE VALIDITÉ lié à un itinéraire spécifique.

→ Partie Tarifs

## **SALE DISCOUNT RIGHT** (DROIT A REDUCTION)

PRODUIT TARIFAIRE (FARE PRODUCT) qui permet à son porteur de bénéficier
d’une déduction lors de l’achat d’OFFREs A LA VENTE (SALES OFFER
PACKAGE) particulières.

→ Partie Tarifs

## **SALE OFFER ENTITLEMENT GIVEN** (DROIT D’ACCES A UNE OFFRE)

DROIT accordé pour utiliser une OFFRE A LA VENTE.

→ Partie Tarifs

## **SALE OFFER ENTITLEMENT REQUIRED** (DROIT NÉCESSAIRE POUR ACCEDER A L’OFFRE)

DROIT nécessaire pour utiliser une OFFRE A LA VENTE.

→ Partie Tarifs

## **SALES NOTICE ASSIGNMENT** (AFFECTATION D’UNE NOTE)

Affectation d’une NOTE à un une OFFRE A LA VENTE ou à un GROUPE D’OFFREs
A LA VENTE.

→ Partie Tarifs

## **SALES OFFER PACKAGE** (OFFRE A LA VENTE)

Une offre à la vente dans son ensemble, composé d'un ou plusieurs
PRODUITS TARIFAIRES matérialisé grâce à un ou plusieurs DOCUMENTS DE
VOYAGE. Les PRODUITS TARIFAIRES peuvent être soit directement attachés
aux DOCUMENTS DE VOYAGE, soit être rechargeables sur les DOCUMENTS DE
VOYAGE.

→ Partie Tarifs

## **SALES OFFER PACKAGE ELEMENT** (ÉLÉMENT D’OFFRE A LA VENTE)

L'affectation d'un PRODUIT TARIFAIRE à un TYPE DE DOCUMENT DE VOYAGE
afin de définir une OFFRE A LA VENTE, réalisé sous forme d'affectation
fixe (impression, stockage magnétique etc.) ou par la possibilité de
recharger le PRODUIT TARIFAIRE sur le TYPE DU DOCUMENT DE VOYAGE.

→ Partie Tarifs

## **SALES OFFER PACKAGE PRICE** (PRIX D’UNE OFFRE A LA VENTE)

Un ensemble de toutes les caractéristiques de prix possibles d'une OFFRE
A LA VENTE : prix total par défaut, etc.

→ Partie Tarifs

## **SCOPING VALIDITY PARAMETERS** (CIBLAGE DES PARAMÈTRES DE VALIDITÉ)

Regroupement des affectations de PARAMETRE DE VALIDITÉ aux éléments pour
les associer à un ensemble de cibles (éléments auxquels ils
s’appliquent).

→ Partie Tarifs

## **SEATING VALIDITY PARAMETERS** (PARAMÈTRES DE VALIDITÉ DES SIÈGES)

Type de PARAMÈTRE DE VALIDITÉ lié aux caractéristiques des sièges (par
exemple, siège d'autocar ou de passager).

→ Partie Tarifs

## **SERIES CONSTRAINT** (CONTRAINTE DE SÉRIE)

Extension d'un ÉLÉMENT DE MATRICE DE DISTANCE (une cellule d'une matrice
origine-destination pour les ZONES TARIFAIRES ou les POINTS D'ARRÊT
PLANIFIÉS) exprimant une distance tarifaire pour le trajet correspondant
(valeur en km, nombre d'unités tarifaires, etc.), limitée à des
itinéraires spécifiques. Les CONTRAINTES DE SÉRIE sont principalement
utilisées pour les tarifs ferroviaires.

→ Partie Tarifs

## **SERVICE ACCESS RIGHT** (DROIT D’ACCÈS AU SERVICE)

Un élément commercialisable immatériel dédié à l'accès à certains
services.

→ Partie Tarifs

## **SERVICE VALIDITY PARAMETERS** (PARAMÈTRE DE VALIDITÉ DU SERVICE)

Un type de PARAMÈTRE DE VALIDITÉ lié aux caractéristiques du service
(par exemple, la classe).

→ Partie Tarifs

## **SITE VALIDITY PARAMETERS** (PARAMÈTRE DE VALIDITÉ DU SITE)

Un type de PARAMÈTRE DE VALIDITÉ lié aux caractéristiques du SITE.

→ Partie Tarifs

## **START TIME AT STOP POINT** (HORAIRE DE DÉBUT AU POINT D’ARRÊT)

Heure à laquelle une tranche horaire tarifaire (tranche horaire pointe,
heures creuses) commence pour les trajets au départ d'une gare
particulière.

→ Partie Tarifs

## **STEP LIMIT** (LIMITATION DU NOMBRE D’ÉTAPES)

Paramètre géographique limitant les droits d'accès par comptage
d'arrêts, de tronçons ou de zones.

→ Partie Tarifs

## **SUBSCRIBING** (SOUSCRIPTION)

Paramètres régissant la souscription à un produit permettant un paiement
à intervalles réguliers.

→ Partie Tarifs

## **SUPPLEMENT PRODUCT** (SUPPLÉMENT)

PRODUIT TARIFAIRE PRÉAFFECTÉ qui offrira un droit supplémentaire
lorsqu'il est utilisé avec (en complément) d'un autre (siège réservé,
surclassement de deuxième à première classe, etc.). PRODUIT
SUPPLÉMENTAIRE signifie aussi généralement prix de supplément.

→ Partie Tarifs

## **SUSPENDING** (SUSPENSION)

Conditions de suspension d'un PRODUIT TARIFAIRE, par ex. forfait période
ou abonnement.

→ Partie Tarifs

## **TARIFF** (TARIF)

Un tarif particulier, décrit par une combinaison de paramètres.

→ Partie Tarifs

## **TARIFF VALIDITY PARAMETERS** (PARAMÈTRES DE VALIDITÉ DU TARIF)

Un type de PARAMÈTRE DE VALIDITÉ lié aux TARIFs.

→ Partie Tarifs

## **TARIFF ZONE** (ZONE TARIFAIRE)

Une ZONE utilisée pour définir une structure tarifaire zonale dans un
système de comptage de zones ou de matrice de zones.

→ Partie Tarifs

## **TEMPORAL VALIDITY PARAMETERS** (PARAMÈTRES DE VALIDITÉ TEMPORELS)

Regroupement des paramètres de validité temporelle.

→ Partie Tarifs

## **THIRD PARTY PRODUCT** (PRODUIT TARIFAIRE TIER)

PRODUIT TARIFAIRE (non lié au transport public) commercialisé avec un
PRODUIT TARIFAIRE de transport public.

→ Partie Tarifs

## **TIME BAND** (PLAGE HORAIRE)

Une période dans une journée, importante pour certains aspects des
transports publics, par ex. conditions de circulation ou catégorie
tarifaire similaires.

→ Partie Tarifs

## **TIME DEMAND TYPE** (NIVEAU DE SERVICE)

Un indicateur des conditions de circulation ou d'autres facteurs (heure
de pointe, heure creuse, etc.) qui peuvent affecter les temps de
parcours ou d'attente des véhicules. Elle peut être saisie directement
par la planification ou définie par l'utilisation de PLAGEs HORAIRES.

→ Partie Tarifs

## **TIME INTERVAL** (INTERVAL TEMPOREL)

Un intervalle temporel précisant les droits d'accès aux ÉLÉMENTS DE
STRUCTURE TARIFAIRE dans la plage de cet intervalle : 0-1 heure, 1-3
jours etc.

→ Partie Tarifs

## **TIME STRUCTURE FACTOR** (FACTEUR DE STRUCTURE TEMPORELLE)

La valeur d'un INTERVAL TEMPOREL exprimée par une UNITÉs TEMPORELLE.

→ Partie Tarifs

## **TIME UNIT** (UNITÉs TEMPORELLE)

Unité temporelle de calcul des tarifs progressifs en fonction du temps.

→ Partie Tarifs

## **TRANSFERABILITY** (TRANSFÉRABILITÉ)

Le nombre et les caractéristiques des personnes autorisées à utiliser le
service de transport public à la place du client d'origine.

→ Partie Tarifs

## **TYPE OF CONCESSION** (TYPE DE CONCESSION)

Une classification du PROFIL D'UTILISATEUR par type de personne éligible
pour y correspondre.

→ Partie Tarifs

## **TYPE OF FARE PRODUCT** (TYPE DE PRODUIT TARIFAIRE)

Classification de PRODUIT TARIFAIRE.

→ Partie Tarifs

## **TYPE OF PAYMENT METHOD** (TYPE DE MÉTHODE DE PAIEMENT)

Une classification du mode de paiement (par exemple, espèces, carte de
crédit, carte de débit, carte de voyage, carte de voyage sans contact,
téléphone portable, jeton, etc.).

→ Partie Tarifs

## **TYPE OF TRAVEL DOCUMENT** (TYPE DE DOCUMENT DE VOYAGE)

Une classification des DOCUMENTS DE VOYAGE exprimant leur fonctionnement
et les caractéristiques fonctionnelles locales propres à l'opérateur.
Des TYPEs DE DOCUMENTS DE VOYAGE comme par ex. ticket jetable, bloc
ticket jetable, carte de valeur, porte-monnaie électronique permettant
l'accès, carte de crédit de transport en commun, etc. peuvent être
utilisés pour définir ces catégories.

→ Partie Tarifs

## **USAGE DISCOUNT RIGHT** (DROIT À RÉDUCTION LIÉ À L’USAGE)

PRODUIT TARIFAIRE permettant à un client de bénéficier de remises lors
de la consommation d'ÉLÉMENTS VALIDABLES.

→ Partie Tarifs

## **USAGE PARAMETER** (PARAMÈTRE D’UTILISATION)

Paramètre utilisé pour spécifier l'utilisation d'une OFFRE À LA VENTE ou
d'un PRODUIT TARIFAIRE.

→ Partie Tarifs

## **USAGE VALIDITY PERIOD** (PÉRIODE DE VALIDITÉ D’UTILISATON)

Une limitation dans le temps de la validité d'un PRODUIT TARIFAIRE ou
d'une OFFRE À LA VENTE. Il peut être composé d'une durée standard (par
exemple 3 jours, 1 mois) et/ou de dates et heures de début/fin fixes.

→ Partie Tarifs

## **USER PROFILE** (PROFIL UTILISATEUR)

Profil social d'un passager, basé sur la tranche d'âge, l'éducation, la
profession, le statut social, le sexe etc., souvent utilisé pour
permettre des réductions : 18-40 ans, diplômés, chauffeurs, chômeurs,
femmes etc.

→ Partie Tarifs

## **VALIDABLE ELEMENT** (ÉLÉMENT VALIDABLE)

Une séquence ou un ensemble d'ÉLÉMENTS DE STRUCTURE TARIFAIRE, regroupés
pour être validés en une seule fois.

→ Partie Tarifs

## **VALIDITY PARAMETER ASSIGNMENT** (AFFECTATION DE PARAMÈTRES DE VALIDITÉ)

Une AFFECTATION DE PARAMÈTRES DE DROIT D'ACCÈS associant un paramètre de
perception tarifaire à un PRODUIT TARIFAIRE (ou à l'un de ses
composants) ou à une OFFRE À LA VENTE.

→ Partie Tarifs

