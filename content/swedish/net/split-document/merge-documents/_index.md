---
title: Slå samman Word-dokument
linktitle: Slå samman dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du slår samman flera Word-dokument med Aspose.Words för .NET. Detta kraftfulla API förenklar processen att sammanfoga dokument, vilket gör det effektivt och enkelt.
type: docs
weight: 10
url: /sv/net/split-document/merge-documents/
---

I den här handledningen kommer vi att gå igenom hur du slår samman flera Word-dokument med funktionen Merge Documents i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och få ett sammanslaget dokument som innehåller alla källdokument.

## Steg 1: Sök efter dokument som ska sammanfogas

Innan vi slår samman dokumenten måste vi hitta källdokumenten som ska slås samman. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Sök efter dokument som ska sammanfogas.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Steg 2: Slå samman dokument

Nu kommer vi att slå samman dokumenten ett efter ett för att skapa ett slutgiltigt sammanslaget dokument. Här är hur:

```csharp
// Öppna den första delen av det resulterande dokumentet.
Document sourceDoc = new Document(sourceDocumentPath);

// Skapa ett nytt resulterande dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Slå samman dokumenten ett efter ett.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Exempel på källkod för Merge Documents med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Merge Documents i Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Hitta dokument med för sammanfogning.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Öppna den första delen av det resulterande dokumentet.
Document sourceDoc = new Document(sourceDocumentPath);

// Skapa ett nytt resulterande dokument.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Slå samman dokumentdelar en efter en.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Slutsats

Grattis! Du har lärt dig hur du slår samman flera Word-dokument med funktionen Merge Documents i Aspose.Words för .NET. Genom att följa den medföljande källkoden kan du kombinera separata dokument till ett enda sammanslaget dokument samtidigt som du behåller formateringen av varje källdokument.

Sammanfogning av dokument kan vara användbart när du vill konsolidera information från flera källor eller skapa ett enhetligt dokument från enskilda delar. Aspose.Words för .NET tillhandahåller ett kraftfullt API som förenklar processen att sammanfoga dokument, vilket gör det effektivt och enkelt.

Utforska gärna andra funktioner som erbjuds av Aspose.Words för .NET för att förbättra dina dokumentbehandlingsmöjligheter och effektivisera ditt arbetsflöde.

### Vanliga frågor

#### Hur kan jag slå samman dokument med olika formatering?

 Vid sammanslagning av dokument ger Aspose.Words för .NET möjligheten att bevara formateringen av varje källdokument. Genom att använda`ImportFormatMode.KeepSourceFormatting` alternativet kommer det sammanslagna dokumentet att behålla formateringen av originaldokumenten. Om du vill tillämpa konsekvent formatering genom hela det sammanslagna dokumentet kan du ändra formateringen med Aspose.Words API efter att ha slagit samman dokumenten.

#### Kan jag slå samman dokument i olika format?

Ja, Aspose.Words för .NET stöder sammanslagning av dokument i olika format, inklusive DOCX, DOC, RTF och mer. Du kan ladda dokument av olika format till Aspose.Words API och slå samman dem till ett enda dokument oavsett deras ursprungliga format.

#### Kan jag slå samman dokument med komplexa strukturer, som tabeller och bilder?

Absolut! Aspose.Words för .NET kan slå samman dokument med komplexa strukturer, inklusive tabeller, bilder, sidhuvuden, sidfötter och mer. API:t hanterar sammanslagningsprocessen samtidigt som integriteten och layouten av innehållet i varje dokument bevaras.

#### Är det möjligt att slå samman dokument med olika sidorientering eller storlek?

Ja, Aspose.Words för .NET hanterar dokument med olika sidorientering eller -storlekar under sammanslagningsprocessen. Det resulterande sammanslagna dokumentet kommer att rymma de olika sidorienteringarna och storlekarna på källdokumenten.