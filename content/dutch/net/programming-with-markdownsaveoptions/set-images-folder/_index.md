---
title: Stel de map Afbeeldingen in
linktitle: Stel de map Afbeeldingen in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de map afbeeldingen instelt bij het exporteren naar Markdown met Aspose.Words voor .NET. Pas de plaatsing van afbeeldingen aan voor een betere organisatie en integratie.
type: docs
weight: 10
url: /nl/net/programming-with-markdownsaveoptions/set-images-folder/
---

Hier is een stapsgewijze handleiding om de volgende C#-broncode uit te leggen die helpt bij het instellen van de afbeeldingenmap voor Markdown-exportopties met behulp van de Aspose.Words-bibliotheek voor .NET. Zorg ervoor dat u de Aspose.Words-bibliotheek in uw project hebt opgenomen voordat u deze code gebruikt.

## Stap 1: Stel het documentmappad in

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Zorg ervoor dat u het juiste pad opgeeft naar uw documentenmap waar het document met de afbeeldingen zich bevindt.

## Stap 2: Laad het document met de afbeeldingen

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

We laden het opgegeven document dat de afbeeldingen bevat die we willen exporteren met Markdown-opties.

## Stap 3: Stel de afbeeldingenmap in voor Markdown-exportopties

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 We maken een exemplaar van`MarkdownSaveOptions` en stel het pad naar de map afbeeldingen in met behulp van de`ImagesFolder` eigendom. Zorg ervoor dat u het juiste pad opgeeft naar de map waarin u de geëxporteerde afbeeldingen wilt opslaan.

## Stap 4: Sla het document op met Markdown-exportopties

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

We slaan het document op in een geheugenstroom met behulp van de opgegeven Markdown-exportopties. U kunt de stroom vervolgens gebruiken om andere bewerkingen uit te voeren, zoals het opslaan van Markdown-inhoud in een bestand.

### Voorbeeldbroncode om de afbeeldingenmap in te stellen voor MarkdownSaveOptions met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Deze broncode laat zien hoe u een document laadt dat afbeeldingen bevat en vervolgens de map afbeeldingen instelt voor Markdown-exportopties. Met behulp van de opgegeven opties wordt het document vervolgens opgeslagen in een geheugenstroom. Hiermee kunt u de locatie van de afbeeldingenmap aanpassen wanneer u Markdown-inhoud exporteert.