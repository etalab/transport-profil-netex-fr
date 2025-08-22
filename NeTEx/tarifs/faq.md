# Foire aux Questions NeTEx France partie tarifaire

## Comment modéliser les informations temporelles ?
Le sujet de la variation du prix en fonction de la durée n'est pas traité dans ce paragraphe.

Les principaux concepts de temporalité d'un titre sont les suivants : 
- la disponibilité des titres (= période de vente). Utiliser `ValidityConditions (AvailabilityConditions)` pour renseigner cette information.
- la durée de validité du titre une fois validé. Utiliser `UsageValidityPeriod` pour la renseigner.
- la période pendant laquelle le titre peut être utilisé (ou "consommé") après l’achat . Utiliser `ValidableElement - FareStructureElement` (ex. time Interval)

Des informations temporelles peuvent également être ajoutées à l'offre à la vente (`SALES OFFER PACKAGE`) : 
- Date de début et de fin de vente autorisée
- Date de début et de fin d'utilisation authorisée
Ces informations sont à indiquer au niveau de `ValidityPeriod` du `SALES OFFER PACKAGE`

Tarif (A CONFIRMER A QUOI RATTACHER CES INFOS) :
- Date de début-fin d’application du tarif
- Date de début d'application du taux de TVA
- Date de fin de validité du bon d’achat
- Échéances : date de l’échéance, dates d’application des échéanciers
Ces informations sont à placer dans `ValidityConditions`


Droit à voyager : => données de vente
Date d’émission des droits 
Date - heure de début et de fin de validité des droits
Date limite d’utilisation du contrat
Profil commercial – statut : date de début et de fin OU durée de validité
Document de voyage :
- Date extrême de validité du support => Validity conditions 
- Date limite de fabrication => donnée d’exploitation
Périodes :
- Période de gratuité (dates début-fin – heures de début – fin en tranches horaires)
- Tables de consommation par tranche horaires + leurs dates d’application
- Où spécifier les horaires de pointe ? ⇒ Pas d’usage clarifié à ce jour, avec des situations où ces horaires peuvent être mouvants ⇒ À spécifier dans le Profil France
- Période de pic de pollution ou Évènements (ex. Fête de la Musique) : validityConditions > ValidityTrigger (à spécifier dans le profil car ce type d’information n’existe pas a priori en NeTEx)
ou QUALITY STRUCTURE FACTOR 
⇒ Choix à expliciter dans le Profil France.


**Information complémentaire :**
Le champ `ValidDayBits` a été rendu obligatoire au niveau européen, afin d'éviter toute difficulté de compréhention des periodes 
d'application. En effet, des periodes de type "vacances" ou "jours feriés" peuvent être locales et sont inexploitables par les systèmes informatiques.
Il est possible qu'il devienne obligtaoire en France pour des questions d'interopérabilité, il est donc recommandé de préciser cette
 information dans les exports.

## Comment modéliser un prix qui varie en fonction de la durée ?

La durée est rattachée à un `FARE STRUCTURE ELEMENT`.


## Est-ce que la zone tarifaire décrit deux fois la situation ?
La zone tarifaire `FareZone` peut contenir :
- la description géographique de la zone tarifaire, en général avec une liste de communes couvertes,
- la liste des arrêts associés à la zone tarifaire.

Les arrêts étant géographiquement positionnés, il est possible de faire cette association géographique. Il arrive cependant que 
des points d'arrêts soient rattachés à une commune, mais positionnés géographiquement dans la commune d'à côté. Les deux informations 
sont donc utiles :
- la liste des arrêts pour avoir une information très précise, par exemple pour la mise en place d'un calculateur tarifaire
- la zone géographique pour des représentation sur une carte

===============================
cas d'usages à explicter : 

-	Multi déplacement pour un seul usager (correspondances autorisées, 1h)
-	Carnet de ce titre (5 ou 10)
-	Abonnement avec dates fixes : 1 à la fin du mois avec 2 jours de tolérance
-	Dates glissantes à la vente ou à la validation : date de début et de fin (par déduction de la durée autorisée) décidées à la vente ou à la validation . exemple : touriste 7 jours
-	Date limite d’utilisation
-	Titre Week end : valable le samedi – dimanche et jours fériés pendant 2 mois.
-	Titre pause déjeuner : entre 12h et 14h tous les jours par carnet de 10 jetons
-	Titre de transport support (achat d’une Carte sans contact)
-	Souscription à un service (adhésion / souscription / ) payante 
-	Groupe avec nombre de passagers saisis à la vente / défini dans le produit
-	Zones de tarification autorisées
-	Définir des périodes payantes et des périodes gratuites pour les produits à tacite reconduction.
-	Interdiction de retour sur une même ligne