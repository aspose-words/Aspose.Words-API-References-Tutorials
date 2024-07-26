---
title: SDT an benutzerdefiniertes XML-Teil binden
linktitle: SDT an benutzerdefiniertes XML-Teil binden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein SDT an ein benutzerdefiniertes XML-Teil binden.
type: docs
weight: 10
url: /de/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Dieses Tutorial zeigt, wie Sie mit Aspose.Words für .NET ein Structured Document Tag (SDT) an ein benutzerdefiniertes XML-Teil binden. Mit SDTs können Sie einem Word-Dokument strukturierte Inhaltssteuerelemente hinzufügen, und CustomXmlParts bieten eine Möglichkeit, benutzerdefinierte XML-Daten zu speichern, die mit dem Dokument verknüpft sind.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und XML.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen eines Dokuments und eines CustomXmlPart
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`CustomXmlPart` zum Speichern der benutzerdefinierten XML-Daten. Das benutzerdefinierte XML sollte in einem gültigen XML-Format vorliegen. In diesem Beispiel verwenden wir eine einfache XML-Zeichenfolge`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Schritt 3: Fügen Sie dem Dokument einen StructuredDocumentTag (SDT) hinzu
 Füge hinzu ein`StructuredDocumentTag`zum Dokument, das als Inhaltssteuerelement dienen soll. Geben Sie die`SdtType` als`PlainText` und das`MarkupLevel` als`Block` um ein SDT auf Blockebene zu erstellen.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Schritt 4: Festlegen der XML-Zuordnung für das SDT
 Ordnen Sie das SDT dem`CustomXmlPart` mithilfe der`SetMapping` Methode der`XmlMapping` Eigenschaft. Geben Sie die`CustomXmlPart` , den XPath-Ausdruck zum Auffinden des gewünschten XML-Knotens und ggf. das Namespace-Präfix. In diesem Beispiel wird das SDT abgebildet auf`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.BindSDTtoCustomXmlPart.doc“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Beispielquellcode für Bind Sd Tto Custom Xml Part mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein SDT an ein CustomXmlPart in Ihrem Word-Dokument gebunden.