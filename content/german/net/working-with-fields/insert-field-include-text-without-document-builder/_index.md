---
title: Feld einfügen, Text einschließen ohne Dokumentgenerator
linktitle: FieldIncludeText ohne Document Builder einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein FieldIncludeText-Feld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „FieldIncludeText-Feld einfügen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des Absatzes

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines Absatzes.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Schritt 3: Einfügen des FieldIncludeText-Felds

 Wir benutzen das`AppendField()` Methode, um ein FieldIncludeText-Feld in den Absatz einzufügen.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Anschließend konfigurieren wir die Eigenschaften des Felds FieldIncludeText, indem wir den Namen des Lesezeichens und den Namen der Quelldatei angeben.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Als Nächstes fügen wir den Absatz zum Hauptteil des Dokuments hinzu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Schließlich nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
fieldIncludeText.Update();
```

### Beispiel des Quellcodes zum Einfügen eines FieldIncludeText-Felds mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den Absatz.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Fügen Sie das Feld FieldIncludeText ein.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen Absatz initialisiert, ein FieldIncludeTexten mit dem Lesezeichennamen und dem Quelldateinamen eingefügt und das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „FieldIncludeText einfügen“ mit Aspose.Words für .NET ab.

### Häufig gestellte Fragen

#### F: Wie kann ich die Quelldatei für das Texteinschlussfeld in Aspose.Words für .NET angeben?

 A: Um die Quelldatei für das Text-Inklusionsfeld in Aspose.Words für .NET anzugeben, können Sie den`FieldIncludeText.SourceFullName`-Eigenschaft, um den vollständigen Pfad der Quelldatei festzulegen. Stellen Sie sicher, dass die Quelldatei zugänglich ist und den Inhalt enthält, den Sie in das Texteinschlussfeld aufnehmen möchten.

#### F: Kann ich mit Aspose.Words für .NET Text aus einem Makro in das Texteinschlussfeld einfügen?

 A: Ja, Sie können Text aus einem Makro in das Text-Einschlussfeld mit Aspose.Words für .NET einbinden. Sie können das`FieldIncludeText.IncludeText` um den Namen des Makros anzugeben, dessen Inhalt in das Feld aufgenommen werden soll.

#### F: Hat das Einfügen eines Text-Include-Felds ohne den Dokument-Generator Auswirkungen auf die Word-Dokumentstruktur mit Aspose.Words für .NET?

A: Das Einfügen eines Text-Include-Felds ohne den Dokument-Generator hat keine direkten Auswirkungen auf die Struktur des Word-Dokuments. Es fügt dem Dokumentinhalt jedoch ein neues Feldelement hinzu. Sie können die Dokumentstruktur bearbeiten, indem Sie die vorhandenen Elemente nach Bedarf hinzufügen, löschen oder ändern.

#### F: Kann ich das Erscheinungsbild des Texteinschlussfelds in einem Word-Dokument mit Aspose.Words für .NET anpassen?

A: Das Texteinschlussfeld passt sein Erscheinungsbild in einem Word-Dokument nicht direkt an. Sie können den eingefügten Text jedoch mithilfe der Absatzeigenschaften, Schrifteigenschaften und anderer Formatierungsobjekte formatieren, die in Aspose.Words für .NET verfügbar sind.