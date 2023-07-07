---
title: Autorenfeld einfügen
linktitle: Autorenfeld einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein AUTHOR-Feld in Ihre Word-Dokumente einfügen. Geben Sie den Namen des Autors an, um Ihre Dokumente zu personalisieren.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-author-field/
---


Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Ein AUTHOR-Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Dokument und Absatz erstellen

Wir beginnen damit, ein neues Dokument zu erstellen und den ersten Absatz abzurufen.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Schritt 3: Fügen Sie das Feld AUTOR ein

 Wir benutzen das`AppendField()` Methode zum Einfügen eines AUTHOR-Felds in den Absatz.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Anschließend konfigurieren wir die Felder`AuthorName` -Eigenschaft, um den Namen des Autors anzugeben.

```csharp
field. AuthorName = "Test1";
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispiel des Quellcodes zum Einfügen eines AUTHOR-Feldes mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Fügen Sie das Feld AUTOR ein.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein AUTHOR-Feld eingefügt, den Autorennamen konfiguriert und das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit ist unser Leitfaden zur Verwendung der Funktion „Autorenfeld einfügen“ mit Aspose.Words für .NET abgeschlossen.

### FAQs

#### F: Was ist ein Autorenfeld in Aspose.Words?

A: Ein Autorenfeld in Aspose.Words ist ein spezielles Feld, das den Namen des Autors automatisch in ein Word-Dokument einfügt und aktualisiert. Es wird häufig verwendet, um anzugeben, wer das Dokument erstellt oder geändert hat.

#### F: Wie aktualisiere ich das Autorenfeld in einem Word-Dokument mit Aspose.Words?

A: Das Feld „Autor“ in einem Word-Dokument kann aktualisiert werden, um den Namen des aktuellen Autors anzuzeigen. Hierzu können Sie die in der Document-Klasse verfügbare UpdateFields-Methode verwenden. Diese Methode aktualisiert alle Felder im Dokument, einschließlich des Feldes „Autor“.

#### F: Ist es möglich, das Format des Autorenfelds in einem Word-Dokument anzupassen?

A: Ja, es ist möglich, das Format des Autorenfelds in einem Word-Dokument anzupassen. Standardmäßig wird im Feld „Autor“ lediglich der Name des Autors angezeigt. Sie können jedoch mithilfe der in Aspose.Words verfügbaren Formatierungsoptionen zusätzliche Informationen wie Datum und Uhrzeit der Änderung hinzufügen.

#### F: Reagiert das Feld „Autor“ auf spätere Änderungen des Autorennamens?

A: Ja, das Feld „Autor“ reagiert empfindlich auf spätere Änderungen des Autorennamens. Wenn Sie den Namen des Autors in den Dokumenteigenschaften ändern, wird das Feld „Autor“ beim Aktualisieren der Dokumentfelder automatisch mit dem neuen Namen aktualisiert.