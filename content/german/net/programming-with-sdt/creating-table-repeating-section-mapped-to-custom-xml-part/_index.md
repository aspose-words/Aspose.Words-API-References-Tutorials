---
title: Erstellen eines sich wiederholenden Tabellenabschnitts, der einem benutzerdefinierten XML-Teil zugeordnet ist
linktitle: Erstellen eines sich wiederholenden Tabellenabschnitts, der einem benutzerdefinierten XML-Teil zugeordnet ist
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET eine Tabelle mit einem sich wiederholenden Abschnitt erstellen, der einem CustomXmlPart in einem Word-Dokument zugeordnet ist.
type: docs
weight: 10
url: /de/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Dieses Tutorial zeigt, wie Sie mit Aspose.Words für .NET eine Tabelle mit einem sich wiederholenden Abschnitt erstellen, der einem benutzerdefinierten XML-Teil in einem Word-Dokument zugeordnet ist. Der sich wiederholende Abschnitt ermöglicht Ihnen das dynamische Hinzufügen von Zeilen basierend auf den im benutzerdefinierten XML-Teil gespeicherten XML-Daten.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und einen DocumentBuilder
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`DocumentBuilder` um den Inhalt des Dokuments zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Hinzufügen benutzerdefinierter XML-Daten zu einem CustomXmlPart
 Ein ... kreieren`CustomXmlPart` und fügen Sie ihm benutzerdefinierte XML-Daten hinzu. In diesem Beispiel erstellen wir eine XML-Zeichenfolge, die eine Sammlung von Büchern mit ihren Titeln und Autoren darstellt.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Schritt 4: Erstellen einer Tabelle und einer Tabellenstruktur
 Beginnen Sie mit dem Erstellen einer Tabelle mit dem`StartTable` Methode der`DocumentBuilder` . Fügen Sie Tabellenzellen und Inhalt hinzu mit dem`InsertCell` Und`Write` Methoden.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Schritt 5: Erstellen Sie den sich wiederholenden Abschnitt, der benutzerdefiniertem XML zugeordnet ist.
 Ein ... kreieren`StructuredDocumentTag` mit`SdtType.RepeatingSection` um den sich wiederholenden Abschnitt darzustellen. Legen Sie die XML-Zuordnung für den sich wiederholenden Abschnitt mithilfe der`SetMapping` Methode der`XmlMapping` Eigenschaft. In diesem Beispiel ordnen wir den sich wiederholenden Abschnitt zu`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Schritt 6: Erstellen Sie das sich wiederholende Abschnittselement und fügen Sie Zellen hinzu
 Ein ... kreieren`StructuredDocumentTag` mit`SdtType.RepeatingSectionItem` um das sich wiederholende Abschnittselement darzustellen. Hängen Sie es als untergeordnetes Element an den sich wiederholenden Abschnitt an.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Ein ... kreieren`Row`um jedes Element im sich wiederholenden Abschnitt darzustellen und es an das sich wiederholende Abschnittselement anzuhängen.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Schritt 7: Inhaltssteuerelemente im Wiederholungsbereich hinzufügen
 Erstellen`StructuredDocumentTag` Objekte mit`SdtType.PlainText`

  um die Inhaltssteuerelemente „Titel“ und „Autor“ darzustellen. Legen Sie die XML-Zuordnung für jedes Inhaltssteuerelement mithilfe der`SetMapping` Methode der`XmlMapping` Eigenschaft. In diesem Beispiel ordnen wir das Titelsteuerelement zu`/books[1]/book[1]/title[1]` und der Autor Kontrolle zu`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Schritt 8: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Beispielquellcode zum Erstellen eines sich wiederholenden Tabellenabschnitts, der einem benutzerdefinierten XML-Teil zugeordnet ist, mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Das ist es! Sie haben erfolgreich eine Tabelle mit einem sich wiederholenden Abschnitt erstellt, der mit Aspose.Words für .NET einem CustomXmlPart in Ihrem Word-Dokument zugeordnet ist.