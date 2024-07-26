---
title: Kombinationsfeld-Inhaltssteuerelement
linktitle: Kombinationsfeld-Inhaltssteuerelement
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Kombinationsfeld-Inhaltssteuerelement in einem Word-Dokument erstellen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/combo-box-content-control/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET ein Kombinationsfeld-Inhaltssteuerelement in einem Word-Dokument erstellen. Kombinationsfeld-Inhaltssteuerelemente ermöglichen Benutzern die Auswahl eines Elements aus einer Dropdown-Liste.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem Sie das Dokument speichern möchten.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen Sie ein Dokument und ein StructuredDocumentTag
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`StructuredDocumentTag` zur Darstellung des Inhaltssteuerelements des Kombinationsfelds. Geben Sie`SdtType.ComboBox` als Typ und`MarkupLevel.Block` als Markup-Ebene, um ein Kombinationsfeld auf Blockebene zu erstellen.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Schritt 3: Elemente zur Kombinationsbox hinzufügen
 Fügen Sie Elemente zur Combobox hinzu, indem Sie das`ListItems` Eigentum der`StructuredDocumentTag` Jedes Element wird durch ein`SdtListItem` Objekt, das einen Anzeigetext und einen Wert annimmt. In diesem Beispiel fügen wir der Kombinationsbox drei Elemente hinzu.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Schritt 4: Anhängen des StructuredDocumentTag an das Dokument
 Fügen Sie das Kombinationsfeld-Inhaltssteuerelement an den Hauptteil des Dokuments an, indem Sie das`AppendChild` Methode des Hauptteils des ersten Abschnitts des Dokuments.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Schritt 5: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.ComboBoxContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Beispielquellcode für Combo Box Content Control mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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