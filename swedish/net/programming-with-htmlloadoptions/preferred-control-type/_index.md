---
title: Föredragen kontrolltyp
linktitle: Föredragen kontrolltyp
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ange den föredragna kontrolltypen när du laddar ett HTML-dokument med Aspose.Words för .NET.
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

 Vi använder`Document` klass för att ladda HTML-kod från en minnesström med de laddningsalternativ som definierats tidigare. Sedan sparar vi dokumentet i den angivna katalogen med`.docx` filformat.

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