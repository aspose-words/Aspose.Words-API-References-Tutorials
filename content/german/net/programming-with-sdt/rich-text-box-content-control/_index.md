---
title: Rich-Text-Box-Inhaltssteuerung
linktitle: Rich-Text-Box-Inhaltssteuerung
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Rich-Text-Inhaltssteuerelement in einem Word-Dokument erstellen und dabei die Textformatierung und -gestaltung ermöglichen.
type: docs
weight: 10
url: /de/net/programming-with-sdt/rich-text-box-content-control/
---

Dieses Tutorial zeigt, wie Sie mit Aspose.Words für .NET ein Rich-Text-Inhaltssteuerelement in einem Word-Dokument erstellen. Mit Rich-Text-Inhaltssteuerelementen können Benutzer Text mit verschiedenen Stilen und Formatierungsoptionen eingeben und formatieren.

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
 Erstellen Sie eine neue Instanz des`Document` Klasse und eine`StructuredDocumentTag` um das Rich-Text-Inhaltssteuerelement darzustellen. Geben Sie`SdtType.RichText` als Typ und`MarkupLevel.Block` als Markup-Ebene zum Erstellen eines Rich-Text-Felds auf Blockebene.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Schritt 3: Erstellen und Formatieren des Rich-Text-Inhalts
Erstellen Sie einen Absatz und führen Sie ihn aus, um den Rich-Text-Inhalt darzustellen. Legen Sie den Text und die Formatierungsoptionen wie Farbe, Schriftart usw. fest.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Schritt 4: Rich-Text-Inhalt zum Inhaltssteuerelement hinzufügen
 Fügen Sie den Absatz mit dem Rich-Text-Inhalt zum`ChildNodes` Sammlung des Rich-Text-Feld-Inhaltssteuerelements.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Schritt 5: Anfügen des Inhaltssteuerelements an das Dokument
 Fügen Sie das Rich-Text-Feld-Inhaltssteuerelement an den Textkörper des Dokuments an, indem Sie das`AppendChild` Methode des Hauptteils des ersten Abschnitts des Dokuments.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument im angegebenen Verzeichnis mit dem`Save`Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.RichTextBoxContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Beispielquellcode für Rich Text Box Content Control mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Rich-Text-Inhaltssteuerelement in Ihrem Word-Dokument erstellt.