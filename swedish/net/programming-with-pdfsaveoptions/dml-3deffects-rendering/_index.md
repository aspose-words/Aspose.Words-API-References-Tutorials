---
title: Dml 3DEffects Rendering
linktitle: Dml 3DEffects Rendering
second_title: Aspose.Words för .NET API Referens
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



