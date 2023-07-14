---
title: Inhaltskontrolle für Kombinationsfelder
linktitle: Inhaltskontrolle für Kombinationsfelder
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Kombinationsfeld-Inhaltssteuerelement in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/combo-box-content-control/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET ein Kombinationsfeld-Inhaltssteuerelement in einem Word-Dokument erstellen. Mit den Inhaltssteuerelementen von Kombinationsfeldern können Benutzer ein Element aus einer Dropdown-Liste auswählen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und ein StructuredDocumentTag
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`StructuredDocumentTag` um die Inhaltssteuerung des Kombinationsfelds darzustellen. Angeben`SdtType.ComboBox` als Typ und`MarkupLevel.Block` als Markup-Ebene, um ein Kombinationsfeld auf Blockebene zu erstellen.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Schritt 3: Elemente zum Kombinationsfeld hinzufügen
 Fügen Sie Elemente zum Kombinationsfeld hinzu, indem Sie verwenden`ListItems`Eigentum der`StructuredDocumentTag` Jedes Element wird durch ein dargestellt`SdtListItem` Objekt, das einen Anzeigetext und einen Wert annimmt. In diesem Beispiel fügen wir drei Elemente zum Kombinationsfeld hinzu.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Schritt 4: Hängen Sie das StructuredDocumentTag an das Dokument an
 Hängen Sie das Inhaltssteuerelement des Kombinationsfelds mithilfe von an den Hauptteil des Dokuments an`AppendChild` Methode des Hauptteils des ersten Abschnitts des Dokuments.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.ComboBoxContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Beispielquellcode für die Inhaltssteuerung von Kombinationsfeldern mit Aspose.Words für .NET 

```csharp
	//Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Kombinationsfeld-Inhaltssteuerelement in Ihrem Word-Dokument erstellt.