---
title: Strukturiertes Dokument Tag-Bereich Start Xml Mapping
linktitle: Strukturiertes Dokument Tag-Bereich Start Xml Mapping
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die XML-Zuordnung für den Anfang eines strukturierten Dokument-Tagbereichs in einem Word-Dokument einrichten.
type: docs
weight: 10
url: /de/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET eine XML-Zuordnung für den Beginn eines strukturierten Dokument-Tagbereichs in einem Word-Dokument einrichten. Mithilfe der XML-Zuordnung können Sie bestimmte Teile einer XML-Datenquelle innerhalb des Inhaltssteuerelements anzeigen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und erstellen Sie den XML-Teil
 Laden Sie das Word-Dokument mit dem`Document`Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Erstellen Sie einen XML-Teil, der die Daten enthält, die Sie innerhalb des strukturierten Dokumenttags anzeigen möchten.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Schritt 3: XML-Mapping für strukturiertes Dokument-Tag festlegen
Rufen Sie den Bereich des strukturierten Dokumenttags ab, beginnend beim Dokument. Legen Sie dann die XML-Zuordnung für den strukturierten Dokumenttag fest, um mithilfe eines XPath-Ausdrucks einen bestimmten Teil des benutzerdefinierten XML-Teils anzuzeigen.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Beispielquellcode für Structured Document Tag Range Start Xml Mapping mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Erstellen Sie einen XML-Teil, der Daten enthält, und fügen Sie ihn der CustomXmlPart-Sammlung des Dokuments hinzu.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Erstellen Sie ein StructuredDocumentTag, das den Inhalt unseres CustomXmlPart im Dokument anzeigt.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Wenn wir eine Zuordnung für unser StructuredDocumentTag festlegen,
	//Es wird nur ein Teil des CustomXmlPart angezeigt, auf den der XPath verweist.
	// Dieser XPath verweist auf den Inhalt des zweiten „<text>“-Elements des ersten „<root>“-Elements unseres CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich die XML-Zuordnung für einen strukturierten Dokument-Tagbereichsanfang in Ihrem Word-Dokument eingerichtet.