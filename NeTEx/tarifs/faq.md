# Foire aux Questions NeTEx France partie tarifaire
Ce document explicite certains points du profil France, mais n'a pas vocation à le remplacer.
En cas de différence entre ce document et le texte du profil France, c'est ce dernier qui fait foi.

## Quelle structuration donner à mon export de tarifs en Netex France ?
<!-- A confirmer: utilisation du SalesOfferPackagePrice -->

Le profil France a fait le choix de passer par la notion de `FareTable` et ses cellules (`Cell`) pour exposer
les données. Chaque `Cell` du tableau tarifaire fait le lien entre un `SalesOfferPackage`, un profil utilisateur `UserProfile` et le prix `SalesOfferPackagePrice` associé au `SalesOfferPackage`.
Le profil France fait le choix d'utiliser le `SalesOfferPackage` et non pas directement le `PreassignedFareProduct` afin de permettre de spécifier les canaux de distribution des offres à la vente et augmenter ainsi les cas d'usages des données publiées sur le PAN.

Voici un extrait de fichier XML reprenant les informations ci-dessus:
```xml
<FareTable id="fr:faretable:template:01" version="any">
    <Name>FareTable name</Name>
    <cells>
        <Cell id="fr:faretablecell:template:01" version="any">
            <Name>Nom du titre mis à la vente</Name>
            <SalesOfferPackagePrice id="fr:salesofferpackageprice:template:01" version="any">
                <Amount>38.80</Amount>
                <Currency>EUR</Currency>
            </SalesOfferPackagePrice>
            <SalesOfferPackageRef ref="fr:salesofferpackage:template:01" />
            <UserProfileRef ref="fr:userprofile:template:01" version="any" />
        </Cell>
    <cells>
</FareTable>
```
## Que contient un UserProfile ?
Le document du profil France présente plusieurs exemples.
Voici un exemple avec un profile enfant donnant une réduction de 50% pour les enfants de 4 à 10 ans :
```xml
<UserProfile id="FR-Tarif-Example:UserProfile:003:LOC" version="any">
  <!--50% pour les enfants entre 4 et 10 ans -->
  <Name>Tarif Enfant</Name>
  <Description>50%de r&#xE9;duction pour les enfants entre 4 et 10 ans </Description>
  <prices>
    <UsageParameterPrice>
      <LimitingRule>
        <DiscountAsPercentage>0.50</DiscountAsPercentage>
        <CanBeCumulative>false</CanBeCumulative>
      </LimitingRule>
    </UsageParameterPrice>
  </prices>
  <MinimumAge>4</MinimumAge>
  <MaximumAge>10</MaximumAge>
  <DiscountBasis>discount</DiscountBasis>
</UserProfile>
```

## Que contient un SalesOfferPackage ?

Il est important pour un `SalesOfferPackage` de présenter :
- un nom décrivant le ou les titres couverts par l'offre à la vente
- un résumé des principales propriétés (la liste est renseignée au niveau du profile) <!-- a confirmer -->
- les cannaux de distribution (optionnel)
- les éléments de l'offre (`SalesOfferPackageElement`), contenant en particulier le produit tarifaire (`FareProduct`) et le support du titre (`TypeOfTravelDocument`)

```xml
<SalesOfferPackage id="fr:salesofferpackage:SMTAML:01" version="any">
    <Name>T-Libr S - Côtière</Name>
    <noticeAssignments>
        <NoticeAssignment id="fr:fareproduct:SMTAML:01-02" version="any">
            <NoticeRef ref="fr:notice:SMTAML:01" version="any" />
        </NoticeAssignment>
    </noticeAssignments>
    <ConditionSummary>
        <GoesOnCard>true</GoesOnCard>
        <IsPersonal>true</IsPersonal>
        <RequiresPhoto>true</RequiresPhoto>
        <MustCarry>true</MustCarry>
        <RequiresAccount>false</RequiresAccount>
        <IsRefundable>false</IsRefundable>
        <IsExchangable>false</IsExchangable>
        <AvailableOnSubscription>true</AvailableOnSubscription>
    </ConditionSummary>
    <distributionAssignments>
        <DistributionAssignment id="fr:fareproduct:SMTAML:01-03" version="any">
            <DistributionChannelRef ref="fr:distributionchannel:SMTAML:01" />
        </DistributionAssignment>
    </distributionAssignments>
    <salesOfferPackageElements>
        <SalesOfferPackageElementRef ref="fr:salesofferpackageelement:SMTAML:01" />
    </salesOfferPackageElements>
</SalesOfferPackage>
```

## Comment modéliser les informations temporelles ?
Le sujet de la variation du prix en fonction de la durée n'est pas traité dans ce paragraphe.

### Disponibilité des titres (= période de vente)
Afin d'indiquer une periode de vente, il convient d'utiliser `ValidityConditions/AvailabilityConditions` sur l'offre à la vente (`SalesOfferPackage`).

Exemple :
```xml
<SalesOfferPackage id="fr:salesofferpackage:template:01" version="any">
    <validityConditions>
        <AvailabilityCondition id="fr:availabilityconditions:template:01">
            <FromDate>2025-01-01</FromDate>
            <ToDate>2025-12-31</ToDate>
        </AvailabilityCondition>
    </validityConditions>
    <!-- autres informations -->
</SalesOfferPackage>
```
### Periode d'utilisation autorisée des titres
Afin d'indiquer une periode d'utilisation, il convient d'utiliser `ValidityConditions/ValidBetween` sur l'offre à la vente (`SalesOfferPackage`).

**QUESTION : uniquement sur SalesOfferPackage ? ou sur PreassignedFareProduct ? ou les deux ?**

Exemple :
```xml
<SalesOfferPackage id="fr:salesofferpackage:template:01" version="any">
    <validityConditions>
        <ValidBetween>
            <FromDate>2025-01-01</FromDate>
            <ToDate>2025-12-31</ToDate>
        </ValidBetween>
    </validityConditions>
    <!-- autres informations -->
</SalesOfferPackage>
```

### Durée de validité du titre une fois validé
**A TRAVAILLER, rentre en conflit avec le cas ci-dessous :**
- l'utilisation de `UsageValidityPeriod` a été discuté en réunion
- FareStructureElement/TimeInterval a été indiqué dans `FareStructureElement - List`

Question :
- TimeInterval semble pouvoir indiquer une durée de validité de titre, une durée de validité de carte de réduction.
- UsageValidityPeriod semble permettre d'être plus précis, en indiquant des débuts (par date ou à validation)
=> comment choisir quoi dans quelle situation?

### Période pendant laquelle le titre peut être utilisé (ou "consommé") après l’achat
Cette information est associée au produit tarifaire (`PreassignedFareProduct`) contenu dans l'offre à la vente (`SalesOfferPackage`). Pour indiquer cette information, il convient d'utiliser `ValidableElement/FareStructureElement` (ex. time Interval)
```xml
<TimeInterval id="fr:timeinterval:template:01" version="any">
    <Description>2h de trajet sur l'ensemble de la zone</Description>
    <Duration>PT2H</Duration> <!-- Si confirmé, modifier la durée pour indiquer un nombre de mois ou 1 an -->
</TimeInterval>
<FareStructureElement id="fr:farestructureelement:template:01" version="any">
    <TimeIntervalRef ref="fr:timeinterval:template:01"/>
</FareStructureElement>
<PreassignedFareProduct id="fr:fareproduct:template:01" version="any">
<!-- -->
    <validableElements>
        <ValidableElement id="fr:validableelement:template:01" version="any">
            <fareStructureElements>
                <FareStructureElementRef ref="fr:farestructureelement:template:01" version="any" />
            </fareStructureElements>
        </ValidableElement>
    </validableElements>
<!-- -->
</PreassignedFareProduct>
```

### Date de validité du tarif
Dans la cellule (`Cell`), le prix est porté par l'objet `SalesOfferPackagePrice`. La plage de validité du tarif peut être indiquée sur l'objet (voir l'exemple ci-dessous). Une cellule ne pouvant comporter qu'un seul prix, il conviendra de
créer des cellules différentes pour les différents prix des associations entre `SalesOfferPackage` et `UserProfile`.

```xml
<SalesOfferPackagePrice id="fr:faretable:SMTAML:01-02" version="any">
    <ValidBetween>
        <FromDate>2025-01-01</FromDate>
        <ToDate>2025-12-31</ToDate>
    </ValidBetween>
    <Amount>38.80</Amount>
    <Currency>EUR</Currency>
</SalesOfferPackagePrice>
```

### Date de validité d'un bon d'achat
[A COMPLETER : comment modéliser un bon d'achat ? Utiliser des TypeOfProduct avec une liste spécifiée dans le profil France ?]


**Information complémentaire :**
Le champ `ValidDayBits` a été rendu obligatoire au niveau européen, afin d'éviter toute difficulté de compréhention des periodes
d'application. En effet, des periodes de type "vacances" ou "jours feriés" peuvent être locales et sont inexploitables par les systèmes informatiques.
Il est possible que ce champ `ValidDayBits` devienne obligtaoire en France pour des questions d'interopérabilité, il est donc recommandé de préciser cette
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
- la zone géographique pour des représentations sur une carte

## Comment modéliser un carnet de titres (5 ou 10 tickets) ?

La notion de carnet de tickets est représentée par un object `FareStructureElement` contenant :
- un `QualityStructureFactor` contenant le nombre de tickets
- le type de produit (ticket simple, cartnet, abonnement, etc.) est indiqué dans `UsageValidityPeriod/ValidityPeriodType` indiqué dans `validityParameterAssignments/GenericParameterAssignment/limitations`

Voici un exemple :
```xml
    <FareStructureElement version="1.0" id="idfm:t_plus_carnet@conditions_of_sale">
        <Name>Carnet de 10 Ticket</Name>
        <TypeOfFareStructureElementRef versionRef="efp:v1.0" ref="efp:conditions_of_sale"/>
        <qualityStructureFactors>
            <QualityStructureFactor version="1.0" id="idfm:t_plus_carnet@10_units">
                <Name>10 T+ tickets</Name>
                <Url>https://www.iledefrance-mobilites.fr/titres-et-tarifs/detail/ticket-t-sur-passe-navigo-easy-et-sur-telephone</Url>
                <Value>10</Value>
            </QualityStructureFactor>
        </qualityStructureFactors>
        <validityParameterAssignments>
            <GenericParameterAssignment id="FR-Tarif-Example:GenericParameterAssignment:002:LOC" version="any" order="1">
                <limitations>
                    <UsageValidityPeriod id="FR-Tarif-Example:UsageValidityPeriod:001:LOC" version="any">
                        <ValidityPeriodType>carnet</ValidityPeriodType>
                    </UsageValidityPeriod>
                </limitations>
            </GenericParameterAssignment>
        </validityParameterAssignments>
    </FareStructureElement>
```

## Comment modéliser la validité d'un titre pour plusieurs déplacements ?
Cette situation se rencontre dans le cas d'un ticket autorisant les correspondances avec une durée maximale.
Deux cas de figures sont possibles :
- un ticket autorisant les correspondances, avec une durée maximale (par exemple 1h)
- un ticket de type "journée" permettant autant de trajet que souhaité durant une periode

**A COMPLETER**

## Comment indiquer la TVA ?

Le profil France propose des tarifs TTC. Pour indiquer la TVA, il est possible d'utiliser dans un `SalesOfferPackagePrice`
un `RuleStepResult`.

[Note : il faut ajouter DiscountingRule à la Frame]
```xml
<DiscountingRule version="any" id="fr:discountingrule:template:01">
    <Name>TVA 10%</Name>
    <DiscountAsPercentage>0.10</DiscountAsPercentage>
</DiscountingRule>
<SalesOfferPackagePrice id="fr:faretable:SMTAML:01-02" version="any">
    <ValidBetween>
        <FromDate>2025-01-01</FromDate>
        <ToDate>2025-12-31</ToDate>
    </ValidBetween>
    <Amount>40.00</Amount>
    <Currency>EUR</Currency>
    <ruleStepResults>
        <RuleStepResult>
            <Amount>4.00</Amount>
            <DiscountingRuleRef ref="fr:discountingrule:template:01"/>
        </RuleStepResult>
    </ruleStepResults>
</SalesOfferPackagePrice>
```

