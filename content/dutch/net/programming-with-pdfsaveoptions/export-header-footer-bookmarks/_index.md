---
title: Exporteer Word-documentkoptekst en voettekstbladwijzers naar PDF-document
linktitle: Exporteer Word-documentkoptekst en voettekstbladwijzers naar PDF-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voettekstbladwijzers van een Word-document naar PDF kunt exporteren met behulp van Aspose.Words voor .NET met onze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## Invoering

Het converteren van Word-documenten naar PDF is een veel voorkomende taak, vooral als u documenten wilt delen of archiveren met behoud van hun opmaak. Soms bevatten deze documenten belangrijke bladwijzers in de kop- en voetteksten. In deze zelfstudie doorlopen we het proces van het exporteren van deze bladwijzers van een Word-document naar een PDF met behulp van Aspose.Words voor .NET.

## Vereisten

Voordat we erin duiken, zorg ervoor dat je het volgende hebt:

- Aspose.Words voor .NET: Aspose.Words voor .NET moet geïnstalleerd zijn. Je kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Stel uw ontwikkelomgeving in. U kunt Visual Studio of een andere .NET-compatibele IDE gebruiken.
- Basiskennis van C#: Bekendheid met programmeren in C# is vereist om de codevoorbeelden te kunnen volgen.

## Naamruimten importeren

Allereerst moet u de benodigde naamruimten in uw C#-project importeren. Voeg deze regels toe bovenaan uw codebestand:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Laten we het proces opsplitsen in eenvoudig te volgen stappen.

## Stap 1: Initialiseer het document

De eerste stap is het laden van uw Word-document. Hier ziet u hoe u het kunt doen:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

In deze stap geeft u eenvoudigweg het pad naar uw documentmap op en laadt u het Word-document.

## Stap 2: Configureer de PDF-opslagopties

Vervolgens moet u de PDF-opslagopties configureren om ervoor te zorgen dat bladwijzers in de kop- en voetteksten correct worden geëxporteerd.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Hier zijn we bezig met het opzetten van de`PdfSaveOptions` . De`DefaultBookmarksOutlineLevel` eigenschap stelt het overzichtsniveau voor bladwijzers in, en de`HeaderFooterBookmarksExportMode` eigenschap zorgt ervoor dat alleen de eerste bladwijzers in kop- en voetteksten worden geëxporteerd.

## Stap 3: Sla het document op als PDF

Sla ten slotte uw document op als PDF met de geconfigureerde opties.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

In deze stap slaat u het document op in het opgegeven pad met de opties die u heeft geconfigureerd.

## Conclusie

En daar heb je het! Door deze stappen te volgen, kunt u eenvoudig bladwijzers uit de kop- en voetteksten van een Word-document naar een PDF exporteren met behulp van Aspose.Words voor .NET. Deze methode zorgt ervoor dat belangrijke navigatiehulpmiddelen binnen uw document in het PDF-formaat behouden blijven, waardoor het voor lezers gemakkelijker wordt om door uw document te navigeren.

## Veelgestelde vragen

### Kan ik alle bladwijzers van het Word-document naar PDF exporteren?

 Ja, dat kan. In de`PdfSaveOptions`, kunt u indien nodig de instellingen aanpassen zodat alle bladwijzers worden opgenomen.

### Wat moet ik doen als ik bladwijzers ook uit de hoofdtekst van het document wil exporteren?

 U kunt de configureren`OutlineOptions` in`PdfSaveOptions` om bladwijzers uit de hoofdtekst van het document op te nemen.

### Is het mogelijk om de bladwijzerniveaus in de PDF aan te passen?

 Absoluut! U kunt de`DefaultBookmarksOutlineLevel` eigenschap om verschillende overzichtsniveaus voor uw bladwijzers in te stellen.

### Hoe ga ik om met documenten zonder bladwijzers?

Als uw document geen bladwijzers heeft, wordt de PDF gegenereerd zonder bladwijzeroverzicht. Zorg ervoor dat uw document bladwijzers bevat als u deze nodig heeft in de PDF.

### Kan ik deze methode gebruiken voor andere documenttypen zoals DOCX of RTF?

Ja, Aspose.Words voor .NET ondersteunt verschillende documenttypen, waaronder DOCX, RTF en andere.