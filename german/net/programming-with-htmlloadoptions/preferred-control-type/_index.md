---
title: Bevorzugter Steuerungstyp
linktitle: Bevorzugter Steuerungstyp
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen des bevorzugten Steuerelementtyps beim Laden eines HTML-Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlloadoptions/preferred-control-type/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Bevorzugter Steuerelementtyp“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials erfahren Sie, wie Sie beim Laden eines HTML-Dokuments den bevorzugten Steuerelementtyp angeben.

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Die Bibliothek und Installationsanweisungen finden Sie auf der Aspose-Website.

## Schritt 1: Definieren Sie den HTML-Code

 Zunächst müssen Sie den HTML-Code definieren, den Sie als Dokument laden möchten. In diesem Beispiel haben wir eine definiert`html` Variable, die den HTML-Code eines Selektors mit Optionen enthält.

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

## Schritt 2: Legen Sie die HTML-Ladeoptionen fest

 Als nächstes erstellen wir eine`HtmlLoadOptions` Objekt und legen Sie das fest`PreferredControlType` Eigentum zu`HtmlControlType.StructuredDocumentTag`. Dadurch wird Aspose.Words angewiesen, beim Laden StructuredDocumentTags zur Darstellung von HTML zu verwenden.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Schritt 3: Laden und speichern Sie das Dokument

 Wir benutzen das`Document` Klasse zum Laden von HTML-Code aus einem Speicherstream mit den zuvor definierten Ladeoptionen. Anschließend speichern wir das Dokument im angegebenen Verzeichnis mit`.docx` Datei Format.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Beispielquellcode für bevorzugten Steuerelementtyp mit Aspose.Words für .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Das ist alles ! Sie haben den bevorzugten Steuerelementtyp beim Laden eines HTML-Dokuments mit Aspose.Words für .NET erfolgreich angegeben.