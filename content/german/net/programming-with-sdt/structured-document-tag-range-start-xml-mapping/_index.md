---
title: Strukturierter Dokument-Tag-Bereich, Start-XML-Zuordnung
linktitle: Strukturierter Dokument-Tag-Bereich, Start-XML-Zuordnung
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mithilfe von Aspose.Words für .NET eine XML-Zuordnung für den Tag-Bereichsanfang eines strukturierten Dokuments in einem Word-Dokument einrichten.
type: docs
weight: 10
url: /de/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

In diesem Tutorial wird erläutert, wie Sie mithilfe von Aspose.Words für .NET eine XML-Zuordnung für den Tag-Bereichsanfang eines strukturierten Dokuments in einem Word-Dokument einrichten. Mit der XML-Zuordnung können Sie bestimmte Teile einer XML-Datenquelle innerhalb des Inhaltssteuerelements anzeigen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und erstellen Sie einen XML-Teil
 Laden Sie das Word-Dokument mit`Document` Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Erstellen Sie einen XML-Teil, der die Daten enthält, die Sie im strukturierten Dokument-Tag anzeigen möchten.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Schritt 3: Legen Sie die XML-Zuordnung für das strukturierte Dokument-Tag fest
Rufen Sie den Tag-Bereich des strukturierten Dokuments ab dem Dokument ab. Legen Sie dann mithilfe eines XPath-Ausdrucks die XML-Zuordnung für das Tag des strukturierten Dokuments fest, um einen bestimmten Teil des benutzerdefinierten XML-Teils anzuzeigen.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Schritt 4: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Beispielquellcode für Structured Document Tag Range Start XML Mapping mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
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
	// Es wird nur ein Teil des CustomXmlPart angezeigt, auf den der XPath verweist.
	// Dieser XPath verweist auf den Inhalt des zweiten „<text>“-Elements des ersten „<root>“-Elements unseres CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Das ist es! Sie haben die XML-Zuordnung für den Beginn eines strukturierten Dokument-Tag-Bereichs in Ihrem Word-Dokument mit Aspose.Words für .NET erfolgreich eingerichtet.