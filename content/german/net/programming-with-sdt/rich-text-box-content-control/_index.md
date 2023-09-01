---
title: Inhaltskontrolle für Rich-Text-Boxen
linktitle: Inhaltskontrolle für Rich-Text-Boxen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Rich-Text-Box-Inhaltssteuerelement in einem Word-Dokument erstellen, das Textformatierung und -stil ermöglicht.
type: docs
weight: 10
url: /de/net/programming-with-sdt/rich-text-box-content-control/
---

In diesem Tutorial wird gezeigt, wie Sie mit Aspose.Words für .NET ein Rich-Text-Box-Inhaltssteuerelement in einem Word-Dokument erstellen. Mit den Inhaltssteuerelementen von Rich-Text-Feldern können Benutzer Text mit verschiedenen Stilen und Formatierungsoptionen eingeben und formatieren.

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
 Erstellen Sie eine neue Instanz von`Document` Klasse und a`StructuredDocumentTag` um das Rich-Text-Feld-Inhaltssteuerelement darzustellen. Angeben`SdtType.RichText` als Typ und`MarkupLevel.Block` als Markup-Ebene zum Erstellen eines Rich-Text-Felds auf Blockebene.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Schritt 3: Erstellen und formatieren Sie den Rich-Text-Inhalt
Erstellen Sie einen Absatz und führen Sie ihn aus, um den Rich-Text-Inhalt darzustellen. Legen Sie die Text- und Formatierungsoptionen wie Farbe, Schriftart usw. fest.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Schritt 4: Fügen Sie den Rich-Text-Inhalt zum Inhaltssteuerelement hinzu
Fügen Sie den Absatz mit dem Rich-Text-Inhalt zum hinzu`ChildNodes` Sammlung der Rich-Text-Box-Inhaltssteuerung.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Schritt 5: Hängen Sie das Inhaltssteuerelement an das Dokument an
 Hängen Sie das Rich-Text-Feld-Inhaltssteuerelement mithilfe von an den Hauptteil des Dokuments an`AppendChild` Methode des Hauptteils des ersten Abschnitts des Dokuments.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Schritt 6: Speichern Sie das Dokument
 Speichern Sie das Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.RichTextBoxContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Beispielquellcode für Rich Text Box Content Control mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich ein Rich-Text-Box-Inhaltssteuerelement in Ihrem Word-Dokument erstellt.