---
title: Rendera 3D DML 3DEffects i ett PDF-dokument
linktitle: Rendera 3D DML 3DEffects i ett PDF-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du aktiverar rendering av 3D DML-effekter när du konverterar till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

I den här handledningen går vi igenom stegen för att aktivera rendering av 3D DML-effekter när du konverterar till PDF med Aspose.Words för .NET. Detta behåller 3D-effekterna i det genererade PDF-dokumentet. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Konfigurera PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och aktivera avancerad rendering av 3D DML-effekter:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Det här alternativet behåller 3D-effekterna i det genererade PDF-dokumentet.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av sparalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för Dml 3DEffects Rendering med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Genom att följa dessa steg kan du enkelt aktivera rendering av 3D DML-effekter när du konverterar till PDF med Aspose.Words för .NET.

## Slutsats

den här handledningen förklarade vi hur du aktiverar rendering av 3D DML-effekter när du konverterar till PDF med Aspose.Words för .NET. Genom att följa de beskrivna stegen kan du enkelt behålla 3D-effekterna i det genererade PDF-dokumentet. Använd den här funktionen för att bevara de viktiga visuella effekterna av ditt originaldokument.


### Vanliga frågor

#### F: Vad är att rendera 3D DML-effekter i ett PDF-dokument?
S: Att rendera 3D DML-effekter i ett PDF-dokument avser möjligheten att behålla 3D-effekter när du konverterar ett dokument till PDF-format. Detta bevarar de visuella effekterna och säkerställer att det genererade PDF-dokumentet ser ut som originaldokumentet.

#### F: Hur kan jag aktivera rendering av 3D DML-effekter när jag konverterar till PDF med Aspose.Words för .NET?
S: För att aktivera rendering av 3D DML-effekter vid konvertering till PDF med Aspose.Words för .NET, följ dessa steg:

 Skapa en instans av`Document` klass som anger sökvägen till Word-dokumentet.

 Skapa en instans av`PdfSaveOptions` klass och ställ in`Dml3DEffectsRenderingMode` egendom till`Dml3DEffectsRenderingMode.Advanced` för att möjliggöra avancerad rendering av 3D DML-effekter.

 Använd`Save` metod för`Document`klass för att spara dokumentet i PDF-format genom att ange sparalternativ.

#### F: Hur kan jag kontrollera om 3D DML-effekter har renderats i det genererade PDF-dokumentet?
S: För att kontrollera om 3D DML-effekterna har renderats i det genererade PDF-dokumentet, öppna PDF-filen med en kompatibel PDF-visare, som Adobe Acrobat Reader, och granska dokumentet. Du bör se 3D-effekterna som de visas i originaldokumentet.



