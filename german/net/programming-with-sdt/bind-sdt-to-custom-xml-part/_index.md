---
title: Binden Sie SDT an ein benutzerdefiniertes XML-Teil
linktitle: Binden Sie SDT an ein benutzerdefiniertes XML-Teil
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein SDT an einen benutzerdefinierten XML-Teil binden.
type: docs
weight: 10
url: /de/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

In diesem Tutorial wird gezeigt, wie Sie mithilfe von Aspose.Words für .NET ein strukturiertes Dokument-Tag (SDT) an einen benutzerdefinierten XML-Teil binden. Mit SDTs können Sie einem Word-Dokument strukturierte Inhaltssteuerelemente hinzufügen, und CustomXmlParts bieten eine Möglichkeit, mit dem Dokument verknüpfte benutzerdefinierte XML-Daten zu speichern.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und XML.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"`mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und ein CustomXmlPart
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`CustomXmlPart` um die benutzerdefinierten XML-Daten zu speichern. Das benutzerdefinierte XML sollte in einem gültigen XML-Format vorliegen. In diesem Beispiel verwenden wir einen einfachen XML-String`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Schritt 3: Fügen Sie dem Dokument ein StructuredDocumentTag (SDT) hinzu
 Füge hinzu ein`StructuredDocumentTag`zum Dokument hinzugefügt, um als Inhaltskontrolle zu dienen. Präzisiere das`SdtType` als`PlainText` und das`MarkupLevel` als`Block` um ein SDT auf Blockebene zu erstellen.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Schritt 4: Legen Sie die XML-Zuordnung für das SDT fest
 Ordnen Sie das SDT dem zu`CustomXmlPart` durch die Verwendung der`SetMapping` Methode der`XmlMapping` Eigentum. Präzisiere das`CustomXmlPart` , den XPath-Ausdruck zum Suchen des gewünschten XML-Knotens und ggf. das Namespace-Präfix. In diesem Beispiel ordnen wir das SDT zu`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das geänderte Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.BindSDTtoCustomXmlPart.doc“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Beispielquellcode für Bind Sd Tto Custom Xml Part mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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