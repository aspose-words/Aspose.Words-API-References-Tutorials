---
title: Autorenfeld einfügen
linktitle: Autorenfeld einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein AUTOR-Feld in Ihre Word-Dokumente einfügen. Geben Sie den Namen des Autors an, um Ihre Dokumente zu personalisieren.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-author-field/
---


Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „AUTHOR-Feld einfügen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des Absatzes

Wir beginnen mit der Erstellung eines neuen Dokuments und dem Abrufen des ersten Absatzes.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Schritt 3: Feld AUTOR einfügen

 Wir benutzen das`AppendField()` Methode, um ein AUTOR-Feld in den Absatz einzufügen.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Anschließend konfigurieren wir die`AuthorName` -Eigenschaft, um den Namen des Autors anzugeben.

```csharp
field. AuthorName = "Test1";
```

 Schließlich nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispiel des Quellcodes zum Einfügen eines AUTHOR-Felds mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumenterstellung.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Fügen Sie das Feld AUTOR ein.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein AUTOR-Feld eingefügt, den Autorennamen konfiguriert und das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit schließen wir unsere Anleitung zur Verwendung der Funktion „AUTHOR-Feld einfügen“ mit Aspose.Words für .NET ab.

### Häufig gestellte Fragen

#### F: Was ist ein Autorenfeld in Aspose.Words?

A: Ein Autorenfeld in Aspose.Words ist ein spezielles Feld, das den Namen des Autors automatisch in ein Word-Dokument einfügt und aktualisiert. Es wird häufig verwendet, um anzugeben, wer das Dokument erstellt oder geändert hat.

#### F: Wie aktualisiere ich das Autorenfeld in einem Word-Dokument mit Aspose.Words?

A: Das Autorenfeld in einem Word-Dokument kann aktualisiert werden, um den Namen des aktuellen Autors anzuzeigen. Hierzu können Sie die in der Document-Klasse verfügbare Methode UpdateFields verwenden. Diese Methode aktualisiert alle Felder im Dokument, einschließlich des Autorenfelds.

#### F: Ist es möglich, das Format des Autorenfelds in einem Word-Dokument anzupassen?

A: Ja, es ist möglich, das Format des Autorfelds in einem Word-Dokument anzupassen. Standardmäßig zeigt das Autorfeld einfach den Namen des Autors an. Sie können jedoch mithilfe der in Aspose.Words verfügbaren Formatierungsoptionen zusätzliche Informationen wie Datum und Uhrzeit der Änderung hinzufügen.

#### F: Ist das Autorenfeld sensibel gegenüber späteren Änderungen des Autorennamens?

A: Ja, das Autorenfeld reagiert empfindlich auf nachträgliche Änderungen des Autorennamens. Wenn Sie den Autorennamen in den Dokumenteigenschaften ändern, wird das Autorenfeld beim Aktualisieren von Dokumentfeldern automatisch mit dem neuen Namen aktualisiert.