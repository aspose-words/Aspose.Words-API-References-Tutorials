---
title: Bevorzugter Steuerelementtyp im Word-Dokument
linktitle: Bevorzugter Steuerelementtyp im Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen des bevorzugten Steuerelementtyps im Word-Dokument beim Laden eines HTML-Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-htmlloadoptions/preferred-control-type/
---
Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Funktion „Bevorzugter Steuerelementtyp“ mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie beim Laden eines HTML-Dokuments den bevorzugten Steuerelementtyp angeben.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Definieren Sie den HTML-Code

 Zunächst müssen Sie den HTML-Code definieren, den Sie als Dokument laden möchten. In diesem Beispiel haben wir ein`html` Variable, die den HTML-Code eines Selektors mit Optionen enthält.

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

## Schritt 2: HTML-Ladeoptionen festlegen

 Als nächstes erstellen wir ein`HtmlLoadOptions` Objekt und setzen Sie den`PreferredControlType`Eigentum an`HtmlControlType.StructuredDocumentTag`. Dies weist Aspose.Words an, beim Laden StructuredDocumentTags zur Darstellung von HTML zu verwenden.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Schritt 3: Dokument laden und speichern

 Wir benutzen das`Document` Klasse, um HTML-Code aus einem Speicherstrom mit den zuvor definierten Ladeoptionen zu laden. Anschließend speichern wir das Dokument im angegebenen Verzeichnis mit dem`.docx`Datei Format.

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
	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Das ist alles! Sie haben beim Laden eines HTML-Dokuments mit Aspose.Words für .NET erfolgreich den bevorzugten Steuerelementtyp angegeben.

## Abschluss

 Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, haben Sie gelernt, wie Sie die Funktion „Bevorzugter Steuerelementtyp“ in Aspose.Words für .NET verwenden, um beim Laden eines HTML-Dokuments den gewünschten Steuerelementtyp anzugeben. Festlegen des`PreferredControlType`Eigentum an`HtmlControlType.StructuredDocumentTag` ermöglicht Aspose.Words die Verwendung von StructuredDocumentTags (SDT) zur besseren Darstellung und Verarbeitung von HTML-Inhalten. Sie können auch andere Steuerelementtypen erkunden, die Ihren spezifischen Anforderungen entsprechen. Die Verwendung dieser Funktion trägt dazu bei, eine genaue und effiziente Verarbeitung von HTML-Dokumenten in Ihrer C#-Anwendung mit Aspose.Words sicherzustellen.

### FAQs zum bevorzugten Steuerelementtyp im Word-Dokument

#### F: Was ist die Funktion „Bevorzugter Steuerelementtyp“ in Aspose.Words für .NET?

A: Mit der Funktion „Bevorzugter Steuerelementtyp“ können Sie den bevorzugten Steuerelementtyp angeben, der beim Laden eines HTML-Dokuments zur Darstellung von HTML-Elementen verwendet werden soll. Dies hilft bei der Auswahl des geeigneten Steuerelementtyps für eine bessere Darstellung und Verarbeitung des HTML-Inhalts.

#### F: Wie stelle ich den bevorzugten Steuerungstyp beim Laden eines HTML-Dokuments ein?

 A: Um den bevorzugten Steuerungstyp festzulegen, müssen Sie ein`HtmlLoadOptions` Objekt und legen Sie dessen`PreferredControlType` Eigenschaft auf die gewünschte`HtmlControlType` Im angegebenen Beispiel`HtmlControlType.StructuredDocumentTag` wird eingesetzt.

#### F: Welche Bedeutung hat die Verwendung von StructuredDocumentTags (SDT) als bevorzugter Steuerelementtyp?

A: StructuredDocumentTags (SDT) sind XML-basierte Elemente, die zur Darstellung komplexer Inhalte und Steuerelemente in einem Word-Dokument verwendet werden können. Die Verwendung von SDTs als bevorzugter Steuerelementtyp kann eine bessere Kompatibilität und Darstellung von HTML-Inhalten bieten.

#### F: Wie kann ich sicherstellen, dass Aspose.Words beim Laden des HTML-Dokuments den bevorzugten Steuerelementtyp verwendet?

 A: Durch die Einstellung der`PreferredControlType`Eigentum an`HtmlControlType.StructuredDocumentTag`Wie im Beispielquellcode gezeigt, verwendet Aspose.Words beim Laden des Dokuments SDTs zur Darstellung von HTML-Elementen.

#### F: Kann ich andere Steuerungstypen als bevorzugte Option verwenden?

 A: Ja, abgesehen von`HtmlControlType.StructuredDocumentTag` , Aspose.Words für .NET unterstützt andere Steuerelementtypen wie`HtmlControlType.ContentControl`Und`HtmlControlType.CustomXmlMarkup`.