---
title: Controleer het gecodeerde Word-document
linktitle: Controleer het gecodeerde Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om te verifiëren dat een Word-document is gecodeerd met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-fileformat/verify-encrypted-document/
---

Dit artikel biedt een stapsgewijze handleiding voor het gebruik van de functie Versleutelde Word-documentverificatie met Aspose.Words voor .NET. We zullen elk deel van de code in detail uitleggen. Aan het einde van deze tutorial begrijpt u hoe u kunt controleren of een document gecodeerd is.

Zorg ervoor dat u, voordat u begint, de Aspose.Words voor .NET-bibliotheek in uw project hebt geïnstalleerd en geconfigureerd. U kunt de bibliotheek en installatie-instructies vinden op de Aspose-website.

## Stap 1: Definieer de documentmap

 Om te beginnen moet u het pad definiëren naar de map waar uw documenten zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Detecteer het bestandsformaat

 Vervolgens gebruiken we de`DetectFileFormat` werkwijze van de`FileFormatUtil` klasse om informatie over het bestandsformaat te detecteren. In dit voorbeeld gaan we ervan uit dat het gecodeerde document "Encrypted.docx" heet en zich in de opgegeven documentenmap bevindt.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Stap 3: Controleer of het document gecodeerd is

 Wij gebruiken de`IsEncrypted` eigendom van de`FileFormatInfo`object om te controleren of het document gecodeerd is. Deze eigenschap keert terug`true` als het document gecodeerd is, keert het terug`false`. We geven het resultaat weer in de console.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Dat is alles ! U hebt met succes gecontroleerd of een document is gecodeerd met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het verifiëren van gecodeerde documenten met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Veel Gestelde Vragen

### Vraag: Wat zijn de stappen om een gecodeerd Word-document te verifiëren?

De stappen om een gecodeerd Word-document te verifiëren zijn als volgt:

Definieer de documentmap.

Detecteer het bestandsformaat.

Controleer of het document gecodeerd is.

### Vraag: Hoe kan ik de documentmap instellen?
 Om de documentenmap in te stellen, moet u vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad van uw documentenmap in de volgende code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Vraag: Hoe kan ik het bestandsformaat detecteren?
 U kunt gebruik maken van de`DetectFileFormat` werkwijze van de`FileFormatUtil`klasse om informatie over het bestandsformaat te detecteren. In het volgende voorbeeld gaan we ervan uit dat het gecodeerde document "Encrypted.docx" heet en zich in de opgegeven documentenmap bevindt:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Vraag: Hoe controleer ik of het document gecodeerd is?
 U kunt gebruik maken van de`IsEncrypted` eigendom van de`FileFormatInfo`object om te controleren of het document gecodeerd is. Deze eigenschap keert terug`true` als het document gecodeerd is, keert het terug`false`. Het resultaat wordt weergegeven in de console:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Vraag: Hoe controleer ik of een document is gecodeerd met Aspose.Words voor .NET?
Door de stappen in deze tutorial te volgen en de meegeleverde broncode uit te voeren, kunt u controleren of een document is gecodeerd met Aspose.Words voor .NET.
