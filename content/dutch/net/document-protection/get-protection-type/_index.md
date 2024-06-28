---
title: Beschermingstype ophalen in Word-document
linktitle: Beschermingstype ophalen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de functie Beschermingstype ophalen in Word-document van Aspose.Words voor .NET gebruikt om het beschermingstype van een document te bepalen.
type: docs
weight: 10
url: /nl/net/document-protection/get-protection-type/
---
Welkom bij deze stapsgewijze handleiding waarin de C#-broncode wordt uitgelegd voor de functie Get Protection Type van Aspose.Words voor .NET. In dit artikel laten we u zien hoe u deze krachtige functie kunt gebruiken om het beveiligingstype van een document te bepalen. Documentbescherming is essentieel om de vertrouwelijkheid en integriteit van uw bestanden te waarborgen. We begeleiden u door de stappen die nodig zijn om Aspose.Words voor .NET te integreren en de functie Get Protection Type te gebruiken.

## Stap 1: Het document laden

De eerste stap bij het gebruik van de functie Beschermingstype ophalen is het uploaden van het document waaraan u wilt werken. U kunt dit doen met behulp van de Document-klasse van Aspose.Words voor .NET. Hier is een voorbeeldcode om een document uit een bestand te laden:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Zorg ervoor dat u het juiste pad naar uw documentbestand opgeeft.

## Stap 2: Het beschermingstype ophalen

Nadat het document is geüpload, kunt u de eigenschap ProtectionType van het Document-object gebruiken om het type beveiliging op te halen dat op het document is toegepast. Hier ziet u hoe u het kunt doen:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Voorbeeldbroncode voor het ophalen van beveiligingstype met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Get Protection Type met behulp van Aspose.Words voor .NET:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## Conclusie

In dit artikel hebben we uitgelegd hoe u de functie Get Protection Type van Aspose.Words voor .NET kunt gebruiken om het beveiligingstype van een document te bepalen. Door de beschreven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw eigen C#-projecten integreren en beveiligde documenten efficiënt manipuleren. Aspose.Words voor .NET biedt grote flexibiliteit

### Veelgestelde vragen

#### Vraag: Wat is de eigenschap ProtectionType in Aspose.Words voor .NET?

 EEN: De`ProtectionType` eigenschap in Aspose.Words voor .NET is een functie waarmee u kunt bepalen welk type beveiliging op een Word-document wordt toegepast. Het biedt informatie over het niveau van documentbeveiliging, bijvoorbeeld of het document is beveiligd tegen opmerkingen, revisies, formulieren of andere soorten beperkingen.

#### Vraag: Hoe kan ik het beveiligingstype van een document ophalen met Aspose.Words voor .NET?

A: Om het beveiligingstype van een document op te halen met Aspose.Words voor .NET, kunt u deze stappen volgen:
1.  Laad het document met behulp van de`Document` klas.
2.  Toegang krijgen tot`ProtectionType` eigendom van de`Document` object om het beveiligingstype op te halen.

#### Vraag: Kan ik bepalen of een document is beveiligd voor formulieren of formuliervelden met behulp van de eigenschap ProtectionType?

 A: Ja, u kunt bepalen of een document is beveiligd voor formulieren of formuliervelden met behulp van de`ProtectionType` eigenschap in Aspose.Words voor .NET. Als het beveiligingstype is ingesteld op`AllowOnlyFormFields`geeft dit aan dat het document beveiligd is en dat alleen formuliervelden kunnen worden bewerkt.

#### Vraag: Welke andere beveiligingstypen kan de eigenschap ProtectionType retourneren?

 EEN: De`ProtectionType` eigenschap in Aspose.Words voor .NET kan verschillende beveiligingstypen retourneren, waaronder:
- `NoProtection`: Het document is niet beveiligd.
- `AllowOnlyRevisions`: Het document is beveiligd en er kunnen alleen revisies worden aangebracht.
- `AllowOnlyComments`: het document is beveiligd en er kunnen alleen opmerkingen worden toegevoegd.
- `AllowOnlyFormFields`: het document is beveiligd en alleen formuliervelden kunnen worden bewerkt.
- `ReadOnly`: het document is beveiligd en ingesteld als alleen-lezen.

#### Vraag: Kan ik het beveiligingstype van een document wijzigen met de eigenschap ProtectionType?

 Antwoord: Nee, de`ProtectionType`eigenschap in Aspose.Words voor .NET is een alleen-lezen eigenschap. Hiermee kunt u het huidige beveiligingstype van een document ophalen, maar het biedt geen directe manier om het beveiligingstype te wijzigen. Om het beveiligingstype te wijzigen, moet u andere methoden en eigenschappen gebruiken die beschikbaar zijn in de`Document` klasse, zoals`Protect` of`Unprotect`.

#### Vraag: Is het mogelijk om een document met meerdere beveiligingstypes tegelijk te beveiligen?

A: Nee, met Aspose.Words voor .NET kan slechts één beveiligingstype tegelijk op een document worden toegepast. U kunt echter verschillende beveiligingstypen combineren door de beveiliging in te schakelen, één type in te stellen, de beveiliging uit te schakelen en deze vervolgens weer in te schakelen met een ander type.

