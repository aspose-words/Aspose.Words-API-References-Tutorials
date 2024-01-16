---
title: Velden verwijderen
linktitle: Velden verwijderen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het verwijderen van samenvoegvelden in uw Word-documenten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/delete-fields/
---

Om uit te leggen hoe u de functie "Velden verwijderen" in Aspose gebruikt. Woorden voor .NET, we hebben hieronder een stapsgewijze handleiding gemaakt. 

Het is belangrijk om elke stap nauwkeurig te volgen om de gewenste resultaten te bereiken. 

## Stap 1: Een nieuw document maken

In dit codefragment beginnen we met het maken van een nieuw leeg document met behulp van de volgende regel: 

```csharp
Document doc = new Document();
```

## Stap 2: Samenvoegvelden verwijderen

 Om alle samenvoegvelden in het document te verwijderen, gebruiken we de`DeleteFields()` functie. 

Dit is vooral handig als u alleen de statische inhoud wilt behouden en eventuele samenvoeginformatie wilt verwijderen. 

### Broncodevoorbeeld voor het verwijderen van velden met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Bestaand document laden.
Document doc = new Document(dataDir + "YourDocument.docx");

// Samenvoegvelden verwijderen.
doc.MailMerge.DeleteFields();

// Sla het gewijzigde document op.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 In ons voorbeeld laden we eerst een bestaand document voordat we bellen`DeleteFields()`. Ten slotte slaan we het gewijzigde document op met een nieuwe bestandsnaam. 

Om samenvoegvelden effectief uit een document te verwijderen met behulp van Aspose.Words voor de functie "Velden verwijderen" van .NET, volgt u dit voorbeeld. 

Vergeet niet om "UW DOCUMENTENDIRECTORY" te vervangen door uw specifieke mappad. 

Onze handleiding over het implementeren van de functionaliteit "Velden verwijderen" via Aspose.Words voor .NET is daarmee afgerond.

### Veelgestelde vragen

#### Vraag: Wat is een veld in Aspose.Words?

A: Een veld in Aspose.Words is een documentstructuur die automatisch gegenereerde tekst of een berekende waarde vertegenwoordigt. Velden worden gebruikt om dynamische informatie in een document weer te geven, zoals paginanummers, datums, samenvoegvelden, enz.

#### Vraag: Hoe verwijder ik een veld in een Word-document met Aspose.Words?

A: Om een veld in een Word-document te verwijderen met Aspose.Words, kunt u deze stappen volgen:

1. Importeer de Document-klasse uit de Aspose.Words-naamruimte.
2. Maak een exemplaar van Document door uw bestaande document te laden.
3. Gebruik de RemoveFields-methode om alle velden uit het document te verwijderen.

#### Vraag: Kan ik specifieke velden verwijderen in plaats van alle velden uit een document te verwijderen?

A: Ja, u kunt specifieke velden verwijderen in plaats van alle velden uit een document te verwijderen. Om dit te doen, moet u elk veld afzonderlijk openen en de methode Verwijderen gebruiken om het te verwijderen.

#### Vraag: Hoe kan ik controleren of een veld bestaat in een Word-document voordat ik het verwijder?

A: Om te controleren of een veld in een Word-document bestaat voordat u het verwijdert, kunt u de methode Bevat van de verzameling Velden gebruiken om het opgegeven veld te vinden. Deze methode retourneert een Booleaanse waarde die aangeeft of het veld bestaat of niet.

#### Vraag: Wat zijn de gevolgen van het verwijderen van een veld voor de rest van het document?

A: Wanneer u een veld in een Word-document verwijdert, wordt het veld uit het document verwijderd en wordt de gegenereerde tekst of berekende waarde die aan het veld is gekoppeld, verwijderd. Dit kan van invloed zijn op de documentindeling, omdat de door het veld gegenereerde inhoud wordt verwijderd.