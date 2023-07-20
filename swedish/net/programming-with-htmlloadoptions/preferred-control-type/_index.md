---
title: Föredragen kontrolltyp i Word-dokument
linktitle: Föredragen kontrolltyp i Word-dokument
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ange den föredragna kontrolltypen i word-dokument när du laddar ett HTML-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlloadoptions/preferred-control-type/
---
Den här artikeln ger en steg-för-steg-guide om hur du använder den föredragna kontrolltypens funktion med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du anger den föredragna kontrolltypen när du laddar ett HTML-dokument.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera HTML-koden

 För att börja måste du definiera HTML-koden du vill ladda som ett dokument. I det här exemplet har vi definierat en`html` variabel som innehåller HTML-koden för en väljare med alternativ.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Steg 2: Ställ in HTML-laddningsalternativ

 Därefter skapar vi en`HtmlLoadOptions` objekt och ställ in`PreferredControlType` egendom till`HtmlControlType.StructuredDocumentTag`. Detta säger till Aspose.Words att använda StructuredDocumentTags för att representera HTML vid inläsning.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Steg 3: Ladda och spara dokumentet

 Vi använder`Document` klass för att ladda HTML-kod från en minnesström med de laddningsalternativ som definierats tidigare. Sedan sparar vi dokumentet i den angivna katalogen med`.docx`filformat.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Exempel på källkod för föredragen kontrolltyp med Aspose.Words för .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Det är allt ! Du har angett den föredragna kontrolltypen när du laddar ett HTML-dokument med Aspose.Words för .NET.

## Slutsats

 Genom att följa den här steg-för-steg-guiden har du lärt dig hur du använder funktionen "Preferred Control Type" i Aspose.Words för .NET för att ange önskad kontrolltyp när du laddar ett HTML-dokument. Ställa in`PreferredControlType` egendom till`HtmlControlType.StructuredDocumentTag` tillåter Aspose.Words att använda StructuredDocumentTags (SDT) för bättre representation och bearbetning av HTML-innehåll. Du kan även utforska andra styrtyper för att passa dina specifika krav. Att använda den här funktionen hjälper till att säkerställa korrekt och effektiv hantering av HTML-dokument i din C#-applikation med Aspose.Words.

### Vanliga frågor för föredragen kontrolltyp i word-dokument

#### F: Vad är funktionen "Preferred Control Type" i Aspose.Words för .NET?

S: Funktionen "Önskad kontrolltyp" låter dig ange den föredragna typen av kontroll för att representera HTML-element när du laddar ett HTML-dokument. Det hjälper till att välja lämplig kontrolltyp för bättre representation och bearbetning av HTML-innehållet.

#### F: Hur ställer jag in önskad kontrolltyp när jag laddar ett HTML-dokument?

 S: För att ställa in önskad kontrolltyp måste du skapa en`HtmlLoadOptions` objekt och ställ in dess`PreferredControlType` egendom till önskad`HtmlControlType` . I det angivna exemplet,`HtmlControlType.StructuredDocumentTag` är använd.

#### F: Vad är betydelsen av att använda StructuredDocumentTags (SDT) som den föredragna kontrolltypen?

S: StructuredDocumentTags (SDT) är XML-baserade element som kan användas för att representera komplext innehåll och kontroller i ett Word-dokument. Att använda SDT som den föredragna kontrolltypen kan ge bättre kompatibilitet och representation av HTML-innehåll.

#### F: Hur kan jag säkerställa att Aspose.Words använder den föredragna kontrolltypen när jag laddar HTML-dokumentet?

 S: Genom att ställa in`PreferredControlType` egendom till`HtmlControlType.StructuredDocumentTag`som visas i exemplet på källkoden, kommer Aspose.Words att använda SDT:er för att representera HTML-element när dokumentet laddas.

#### F: Kan jag använda andra kontrolltyper som det föredragna alternativet?

 A: Ja, förutom`HtmlControlType.StructuredDocumentTag` , Aspose.Words för .NET stöder andra kontrolltyper som t.ex`HtmlControlType.ContentControl` och`HtmlControlType.CustomXmlMarkup`.