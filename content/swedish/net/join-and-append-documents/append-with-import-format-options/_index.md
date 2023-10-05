---
title: Lägg till med importformatalternativ
linktitle: Lägg till med importformatalternativ
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till ett dokument med importformatalternativ med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/append-with-import-format-options/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att lägga till innehållet i ett dokument till ett annat med importformatalternativ. Den medföljande källkoden visar hur du öppnar käll- och måldokumenten, anger importformatalternativ och lägger till källdokumentet till måldokumentet.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

-  Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från[Aspose.Releases]https://releases.aspose.com/words/net/ eller använd NuGet-pakethanteraren för att installera den.
- En dokumentkatalogsökväg där käll- och måldokumenten finns.

## Steg 2: Öppna käll- och måldokumenten

 Öppna käll- och måldokumenten med hjälp av`Document` klass konstruktör. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Steg 3: Ange alternativ för importformat

 Skapa en instans av`ImportFormatOptions` klass för att ange alternativ för importformat. I det här exemplet använder vi`KeepSourceNumbering` egenskapen för att säkerställa att numrering från källdokumentet används om det finns konflikter med måldokumentet.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Steg 4: Lägg till källdokumentet till måldokumentet

 Använd`AppendDocument` metod för måldokumentet för att lägga till källdokumentet. Passera`ImportFormatMode.UseDestinationStyles` som den andra parametern för att använda måldokumentets stilar och formatering.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Steg 5: Spara måldokumentet

 Slutligen sparar du det ändrade måldokumentet med hjälp av`Save` metod för`Document` objekt.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Detta slutför implementeringen av att lägga till ett dokument med importformatalternativ med Aspose.Words för .NET.

### Exempel på källkod för Lägg till med importformatalternativ med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ange att om numrering krockar i käll- och måldokument,
	//då kommer numrering från källdokumentet att användas.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```