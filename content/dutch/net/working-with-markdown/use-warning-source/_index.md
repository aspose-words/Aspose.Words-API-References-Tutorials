---
title: Gebruik waarschuwingsbron
linktitle: Gebruik waarschuwingsbron
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de waarschuwingsbron gebruikt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/use-warning-source/
---

In dit voorbeeld laten we u zien hoe u de waarschuwingsbron gebruikt met Aspose.Words voor .NET. De waarschuwingsbron geeft de oorsprong van de waarschuwing aan bij gebruik van de callback-functie.

## Stap 1: Het document laden

 We laden een bestaand document dat waarschuwingen bevat met behulp van de`Load` werkwijze van de`Document` klas.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Stap 3: De waarschuwingsbron gebruiken

 We gebruiken de waarschuwingsbron door het document in te stellen`WarningCallback` eigendommen tot een verzameling van`WarningInfo` voorwerpen.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Stap 4: Het document opslaan

Ten slotte kunnen we het document in het gewenste formaat opslaan.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Voorbeeldbroncode voor het gebruik van waarschuwingsbron met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Gefeliciteerd! U hebt nu geleerd hoe u de waarschuwingsbron kunt gebruiken met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Kunnen we het uiterlijk van de 'Waarschuwing'-tag aanpassen?

 A: De opmaak van de tag "Warning" is afhankelijk van de gebruikte Markdown-renderer. In de meeste gevallen kunt u het uiterlijk aanpassen door CSS te gebruiken om de`blockquote` tag in uw document.

#### Vraag: Is het mogelijk om pictogrammen toe te voegen aan de tag "Waarschuwing"?

A: Ja, het is mogelijk om pictogrammen toe te voegen aan de "Waarschuwing"-tag met behulp van HTML-code in uw Markdown-document. U kunt een invoegen`span` tag met de juiste klasse om een pictogram naast de waarschuwingstekst weer te geven.

#### Vraag: Is de tag "Waarschuwing" compatibel met alle Markdown-lezers?

 A: De compatibiliteit van de tag "Waarschuwing" hangt af van de gebruikte Markdown-rendering. De meeste Markdown-lezers zullen de`blockquote` tag om gemarkeerde tekst weer te geven, maar het exacte uiterlijk kan variëren.