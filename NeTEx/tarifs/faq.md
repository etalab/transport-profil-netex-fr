# Foire aux Questions NeTEx France partie tarifaire
Ce document explicite certains points du profil France, mais n'a pas vocation à le remplacer.
En cas de différence entre ce document et le texte du profil France, c'est ce dernier qui fait foi.
Cette FAQ est en cours d'enrichissement par les membres du GT7.

## Quelle structuration donner à mon export de tarifs en Netex France ?

Le profil France a fait le choix de passer par la notion de `FareTable` et ses cellules (`Cell`) pour exposer
les données. Chaque `Cell` du tableau tarifaire fait le lien entre un `SalesOfferPackage`, un profil utilisateur `UserProfile` et le prix `SalesOfferPackagePrice` associé au `SalesOfferPackage`.
Le profil France fait le choix d'utiliser le `SalesOfferPackage` et non pas directement le `PreassignedFareProduct` afin de permettre de spécifier les canaux de distribution des offres à la vente et augmenter ainsi les cas d'usages des données publiées sur le PAN.

Voici un extrait de fichier XML reprenant les informations ci-dessus:
```xml
<FareTable id="exemple:FareTable:template:01" version="any">
    <Name>FareTable name</Name>
    <cells>
        <Cell id="exemple:Cell:01" version="any">
            <Name>Nom du titre mis à la vente</Name>
            <SalesOfferPackagePrice id="exemple:SalesOfferPackagePrice:01" version="any">
                <Amount>38.80</Amount>
                <Currency>EUR</Currency>
            </SalesOfferPackagePrice>
            <SalesOfferPackageRef ref="exemple:SalesOfferPackageRef:01" />
            <UserProfileRef ref="exemple:UserProfile:01" version="any" />
        </Cell>
    </cells>
</FareTable>
```
## Que contient un UserProfile ?
Le document du profil France présente plusieurs exemples. Le profil France ne retient pas la notion de réduction au niveau du UserProfile. 
Le fait qu'un voyageur doive être accompagné est indiqué au travers d'une notice.

Voici un exemple avec un profile moins de 26 ans :
```xml
<UserProfile id="exemple:UserProfile:01" version="any">
    <!--50% pour les enfants entre 4 et 10 ans -->
    <Name>Tarif -26 ans</Name>
    <Description>Profil jeune adulte (moinsde 26 ans)</Description>
    <noticeAssignments>
        <NoticeAssignment id="exemple:NoticeAssignment:01" version="any">
            <NoticeRef ref="exemple:Notice:01" version="any" />
        </NoticeAssignment>
    </noticeAssignments>
    <UserType>youngPerson</UserType>  
    <MinimumAge>4</MinimumAge>
    <MaximumAge>10</MaximumAge>
    <ProofRequired>identityDocument</ProofRequired>
</UserProfile>
```

## Que contient un SalesOfferPackage ?

Il est important pour un `SalesOfferPackage` de présenter :
- un nom décrivant le ou les titres couverts par l'offre à la vente
- un résumé des principales propriétés (la liste est renseignée au niveau du profil)
- les canaux de distribution (requis dans le profil France)
- les éléments de l'offre (`SalesOfferPackageElement`), contenant en particulier le produit tarifaire (`FareProduct`) et le support du titre (`TypeOfTravelDocument`)

```xml
<SalesOfferPackage id="exemple:SalesOfferPackage:01" version="any">
    <Name>Nom de l'offre mise à la vente</Name>
    <noticeAssignments>
        <NoticeAssignment id="exemple:NoticeAssignment:01" version="any">
            <NoticeRef ref="exemple:Notice:01" version="any" />
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
        <DistributionAssignment id="exemple:DistributionAssignment:01" version="any">
            <DistributionChannelRef ref="exemple:DistributionChannel:01" />
        </DistributionAssignment>
    </distributionAssignments>
    <salesOfferPackageElements>
        <SalesOfferPackageElementRef ref="exemple:SalesOfferPackageElement:01" />
    </salesOfferPackageElements>
</SalesOfferPackage>
```

## Comment modéliser les informations temporelles ?
Le sujet de la variation du prix en fonction de la durée n'est pas traité dans ce paragraphe.

### Disponibilité des titres (= période de vente)
Afin d'indiquer une periode de vente, il convient d'utiliser `ValidityConditions/AvailabilityConditions` sur l'offre à la vente (`SalesOfferPackage`).
Cette information  permet d'indiquer qu'un titre mensuel est mis à la vente à partir du 15 septembre.

Exemple pour une période de vente du 15/09/2025 au 30/10/2025 :
```xml
<SalesOfferPackage id="exemple:SalesOfferPackage:01" version="any">
    <validityConditions>
        <AvailabilityCondition id="exemple:AvailabilityCondition:01" version="any">
            <FromDate>2025-09-15T00:00:00</FromDate>
            <ToDate>2025-10-30T23:59:59</ToDate>
        </AvailabilityCondition>
    </validityConditions>
    <!-- autres informations -->
</SalesOfferPackage>
```

### Periode d'utilisation autorisée des titres
Afin d'indiquer une periode d'utilisation, le profile France fait le choix d'utiliser `ValidityConditions/ValidBetween` sur l'offre à la vente (`SalesOfferPackage`).
Cette information est portée par le SalesOfferPackage, car la periode d'utilisation peut varier en fonction du support ou du canal de distribution.
Par exemple, le produit vendu à bord à consommation immédiate ou le produit mensuel qui commence le mois suivant l'achat.
Cette information ne doit pas être indiquée sur le FareProduct.

- ticket dans la durée : Periode d'utilisation d'un titre (ex : scolaire valable du lundi au vendredi)
- ticket unitaire : Periode pendant laquelle le titre peut être consommé

Exemple :
```xml
<SalesOfferPackage id="exemple:SalesOfferPackage:01" version="any">
    <validityConditions>
        <ValidBetween>
            <FromDate>2025-01-01T00:00:00</FromDate>
            <ToDate>2025-12-31T23:59:59</ToDate>
        </ValidBetween>
    </validityConditions>
    <!-- autres informations -->
</SalesOfferPackage>
```

### Période pendant laquelle le titre peut être utilisé (ou "consommé") après l’achat

Cette information est associée au produit tarifaire (`PreassignedFareProduct`) contenu dans l'offre à la vente (`SalesOfferPackage`). Pour indiquer cette information, il convient d'utiliser `ValidableElement/FareStructureElement` (ex. TimeInterval).

```xml
<TimeInterval id="exemple:TimeInterval:template:01" version="any">
    <Description>2h de trajet sur l'ensemble de la zone</Description>
    <Duration>PT2H</Duration> 
</TimeInterval>
<FareStructureElement id="exemple:FareStructureElement:01" version="any">
    <TimeIntervalRef ref="exemple:TimeInterval:01"/>
</FareStructureElement>
<PreassignedFareProduct id="exemple:PreassignedFareProduct:01" version="any">
<!-- -->
    <validableElements>
        <ValidableElement id="exemple:ValidableElement:01" version="any">
            <fareStructureElements>
                <FareStructureElementRef ref="exemple:FareStructureElement:01" version="any" />
            </fareStructureElements>
        </ValidableElement>
    </validableElements>
<!-- -->
</PreassignedFareProduct>
```

### Durée de validité du titre dans les autres cas (semaine, mensuel, etc.)

```xml
<FareStructureElement id="exemple:FareStructureElement:01" version="any">
    <Name>Abonnement 30 jours</Name>
    <TypeOfFareStructureElementRef ref="exemple:TypeOfFareStructureElement:usage_period" versionRef="any" />
    <validityParameterAssignments>
        <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any">
            <limitations>
                <UsageValidityPeriod id="exemple:UsageValidityPeriod:01" version="any">
                    <ValidityPeriodType>monthlyPass</ValidityPeriodType>
                    <UsageTrigger>startOfPeriod</UsageTrigger>
                    <StandardDuration>PT1M</StandardDuration>
                </UsageValidityPeriod>
            </limitations>
        </GenericParameterAssignment>
    </validityParameterAssignments>
</FareStructureElement>
```

### Date de validité du tarif
Dans la cellule (`Cell`), le prix est porté par l'objet `SalesOfferPackagePrice`. La plage de validité du tarif peut être indiquée sur l'objet (voir l'exemple ci-dessous). Une cellule ne pouvant comporter qu'un seul prix, il conviendra de
créer des cellules différentes pour les différents prix des associations entre `SalesOfferPackage` et `UserProfile`.

```xml
<SalesOfferPackagePrice id="exemple:SalesOfferPackagePrice:01" version="any">
    <ValidBetween>
        <FromDate>2025-01-01T00:00:00</FromDate>
        <ToDate>2025-12-31T23:59:59</ToDate>
    </ValidBetween>
    <Amount>38.80</Amount>
    <Currency>EUR</Currency>
</SalesOfferPackagePrice>
```

### Date de validité d'un bon d'achat
Un bon d'achat est décrit par un objet `SaleDiscountRight` qui hérite de `FareProduct`. 
La date de validité du bon d'achat se représente comme la date de validité d'un produit tarifaire (voir ci-dessus).
Le profil France ne retient pas pour le moment ce type d'informations. 
L'exemple ci-dessous est extrait des exemples de NeTEx, et n'est pas nécessairement compatible avec le profil France.

```xml
<SaleDiscountRight id="atc:ATOC@Products@Pass@Photocard" version="01">
    <Name>Rail Photocard</Name>
    <Url>https://public.greenrailtravel.co.uk/scholars/photocard-information.html</Url>
    <OperatorRef ref="uic:1170" version="any">ATOC</OperatorRef>
    <ConditionSummary>
        <FareStructureType>networkFlatFare</FareStructureType>
        <TariffBasis>flat</TariffBasis>
        <RequiresPhoto>true</RequiresPhoto>
        <MustCarry>true</MustCarry>
        <GivesEntitlement>true</GivesEntitlement>
    </ConditionSummary>
    <validableElements>
        <ValidableElementRef ref="atc:ATOC@Products@Pass@Photocard@holder"/>
    </validableElements>
</SaleDiscountRight>
```

## Comment modéliser un prix qui varie ?
### Pour les prix qui dépendent de la durée 
La durée est rattachée à un `FareStructureElement` en utilisant un `TimeStructureFactor`, c'est par exemple le cas des Taxi.
Pour le moment, la partie nouveaux modes du profil France n'est pas encore publiée, la FAQ ne décrit pas encore ces tarifs.

### Pour les prix qui dépendent de la distance (en transport en communs)
Dans ce cas des transports en communs, il est recommandé de fournir les tarifs sur une OD.

```xml
<DistanceMatrixElement id="exemple:DistanceMatrixElement:01" version="any"> 
    <InverseAllowed>true</InverseAllowed>
    <!--Exemple d'OD Arrêt vers Zone -->
    <StartStopPointRef versionRef="any" ref="exemple:ScheduledStopPoint:01"/>
    <EndTariffZoneRef versionRef="any" ref="exemple:TariffZone:Zone01"/>
</DistanceMatrixElement>

<FareStructureElement id="exemple:FareStructureElement:01" version="any">
    <DistanceMatrixElementRef ref="exemple:DistanceMatrixElement:01"/>
    <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any" order="1"> 
        <limitations>
            <UsageValidityPeriod id="exemple:UsageValidityPeriod:01" version="any"> 							
                <UsageTrigger>purchase</UsageTrigger> 		
                <StandardDuration>PT180M</StandardDuration>
            </UsageValidityPeriod>
        </limitations> 
    </GenericParameterAssignment> 
</FareStructureElement>
```

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
<FareStructureElement version="1.0" id="exemple:FareStructureElement:01">
    <Name>Carnet de 10 Ticket</Name>
    <TypeOfFareStructureElementRef ref="exemple:TypeOfFareStructureElement" versionRef="any"/>
    <qualityStructureFactors>
        <QualityStructureFactor version="1.0" id="exemple:QualityStructureFactor:01">
            <Value>10</Value>
        </QualityStructureFactor>
    </qualityStructureFactors>
    <validityParameterAssignments>
        <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any" order="1">
            <limitations>
                <UsageValidityPeriod id="exemple:UsageValidityPeriod:01" version="any">
                    <ValidityPeriodType>carnet</ValidityPeriodType>
                </UsageValidityPeriod>
            </limitations>
        </GenericParameterAssignment>
    </validityParameterAssignments>
</FareStructureElement>
```

## Comment modéliser la validité d'un titre pour plusieurs déplacements ?
Cette situation se rencontre dans le cas d'un ticket autorisant les correspondances avec une durée maximale.
Les exemples ci-dessous n'indiquent que l'autorisation de la correspondance, les informations temporelles sont décrites plus haut.

Cas d'un ticket autorisant les correspondances, avec une durée maximale (par exemple 30min) : 
```xml
<FareStructureElement id="exemple:FareStructureElement:01" version="any">
    <Name>Trajets avec correspondance</Name>
    <TypeOfFareStructureElementRef ref="FR:Interchanging" versionRef="any" />
    <validityParameterAssignments>
        <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any">
            <LimitationGroupingType>AND</LimitationGroupingType>
            <limitations>
                <Interchanging id="exemple:Interchanging:01" version="any">
                    <CanInterchange>true</CanInterchange>
                    <MaximumNumberOfInterchanges>3</MaximumNumberOfInterchanges> <!-- Optionel -->
                    <MaximumTimeToMakeATransfer>PT30M</MaximumTimeToMakeATransfer>  <!-- Optionel -->
                </Interchanging>
            </limitations>
        </GenericParameterAssignment>
    </validityParameterAssignments>
</FareStructureElement>
```

Cas d'un ticket de type "journée" permettant autant de trajet que souhaité durant une periode :
```xml
<FareStructureElement id="exemple:FareStructureElement:01" version="any">
    <Name>Usage illimté</Name>
    <TypeOfFareStructureElementRef ref="FR:TypeOfFareStructureElement:01" versionRef="any" />
    <validityParameterAssignments>
        <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any">
            <limitations>
                <FrequencyOfUse id="exemple:FrequencyOfUse:01" version="any">
                    <FrequencyOfUseType>unlimited</FrequencyOfUseType>
                </FrequencyOfUse>
            </limitations>
        </GenericParameterAssignment>
    </validityParameterAssignments>
</FareStructureElement>
```

## Comment indiquer la TVA ?

Le profil France propose des tarifs TTC. La communication sur les informations de TVA peut 
entrainer des risques de mauvaise comprehension sur les informations financières. Les informations 
de TVA ne sont donc pas requises par le profil France.

Dans le cas du choix de commniquer tout de même sur le taux de TVA,  il est possible d'utiliser dans un `SalesOfferPackagePrice`
un `RuleStepResult`. Le pourcentage est direct (sans le signe % et sans signe négatif) et il est fortement recommandé 
de communiquer sur la valorisation du montant de la TVA.
Ce principe est commun sur tout les types de taxes. 

```xml
<TypeOfPricingRule id="FR:TypeOfPricingRule:TVA" version="any"/> <!-- Cette valeur sera à uniformiser dans le profil France pour identifier les taux de TVA -->
<DiscountingRule version="any" id="exemple:DiscountingRule:01">
    <Name>TVA 10%</Name>
    <TypeOfPricingRuleRef ref="FR:TypeOfPricingRule:TVA" />
    <DiscountAsPercentage>10</DiscountAsPercentage>
    <DiscountAsValue>1.3</DiscountAsValue>
</DiscountingRule>
<!-- SalesOfferPackagePrice doit être inclus dans une Cell de la FareTable -->
<SalesOfferPackagePrice id="exemple:SalesOfferPackagePrice:012" version="any">
    <ValidBetween>
        <FromDate>2025-01-01T00:00:00</FromDate>
        <ToDate>2025-12-31T23:59:59</ToDate>
    </ValidBetween>
    <Amount>40.00</Amount>
    <Currency>EUR</Currency>
    <ruleStepResults>
        <RuleStepResult>
            <Amount>4.00</Amount>
            <DiscountingRuleRef ref="exemple:DiscountingRuleRef:01"/>
        </RuleStepResult>
    </ruleStepResults>
</SalesOfferPackagePrice>
```

## Comment indiquer que la validation d'un titre est obligatoire ?
La validation obligatoire est à indiquer par la propriété `ActivationMeans` dans un `FareStructureElement` contenant un `GenericParameterAssignment/UsageValidityPeriod`.

```xml
<FareStructureElement id="exemple:FareStructureElement:01" version="any">
    <Name>Validation sur valideur</Name>
    <TypeOfFareStructureElementRef ref="fr:id_en_cours_de_definition_en_GT7" versionRef="any" />
    <validityParameterAssignments>
        <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any">						
            <limitations>
                <UsageValidityPeriod id="exemple:UsageValidityPeriod:01" version="any">
                    <Name>Activation sur valideur</Name>
                    <ActivationMeans>useOfValidator</ActivationMeans>
                </UsageValidityPeriod>
            </limitations>
        </GenericParameterAssignment>
    </validityParameterAssignments>		
</FareStructureElement>
```

Pour préciser que l'absence de validation peut entraine une verbalisation : 
```xml
<FareStructureElement id="exemple:FareStructureElement:01" version="any"> 
    <Name>Verbalisation en cas de non validation</Name>
    <TypeOfFareStructureElementRef ref="fr:id_en_cours_de_definition_en_GT7" versionRef="any" />
    <validityParameterAssignments>
        <GenericParameterAssignment id="exemple:GenericParameterAssignment:01" version="any">
            <limitations>
                <PenaltyPolicy id="exemple:PenaltyPolicy:01" version="any">
                    <PenaltyPolicyType>noValidation</PenaltyPolicyType>
                </PenaltyPolicy>
            </limitations>
        </GenericParameterAssignment>
    </validityParameterAssignments>
</FareStructureElement>
```
