---
title: Zusammenführungsfeld mithilfe von DOM einfügen
linktitle: Zusammenführungsfeld mithilfe von DOM einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET benutzerdefinierte Feldzusammenführungsfelder in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-merge-field-using-dom/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und DocumentBuilder

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Bewegen Sie den Cursor zum Absatz

 Wir benutzen das`MoveTo()` -Methode des DocumentBuilders, um den Cursor zu dem Absatz zu bewegen, in dem wir das Feldzusammenführungsfeld einfügen möchten.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Schritt 4: Einfügen des Feldzusammenführungsfelds

 Wir verwenden den DocumentBuilder`InsertField()` Methode zum Einfügen eines Feldzusammenführungsfelds in den Absatz.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Anschließend konfigurieren wir die Eigenschaften des Feldzusammenführungsfelds, indem wir die entsprechenden Optionen angeben, z. B. den Feldnamen, den Text vor und nach dem Feld sowie Optionen für die vertikale Formatierung.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispielquellcode zum Einfügen eines Feldzusammenführungsfelds mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bewegen Sie den Cursor zum Absatz.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Feldzusammenführungsfeld einfügen.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Aktualisieren Sie das Feld.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, den Cursor auf den gewünschten Absatz bewegt und dann ein Feldzusammenführungsfeld in das Dokument eingefügt.

### FAQs

#### F: Wie kann ich mit Aspose.Words für .NET mit dem DOM ein Briefvorlagenfeld in ein Word-Dokument einfügen?

A: Um mit Aspose.Words für .NET mit DOM ein Zusammenführungsfeld in ein Word-Dokument einzufügen, können Sie die folgenden Schritte ausführen:

1. Navigieren Sie zu dem Absatz, in den Sie das Serienbrieffeld einfügen möchten.
2.  Ein ... kreieren`FieldMergeField` Objekt.
3. Legen Sie die Eigenschaften des Zusammenführungsfelds fest, z. B. Feldnamen und Formatierungsoptionen.
4.  Fügen Sie das Zusammenführungsfeld mithilfe von zum Absatz hinzu`Paragraph.AppendChild` Methode.

#### F: Wie kann ich Quelldaten für das Zusammenführungsfeld in Aspose.Words für .NET angeben?

A: Um die Quelldaten für das Zusammenführungsfeld in Aspose.Words für .NET anzugeben, können Sie die verwenden`FieldMergeField.FieldName` Methode zum Festlegen des Namens des Zusammenführungsfelds, bei dem es sich um den Namen eines Felds in einer externen Datenquelle wie einer CSV-Datei, einer Datenbank usw. handelt. Sie können auch die verwenden`FieldMergeField.Text` Methode zum direkten Festlegen des Zusammenführungsfeldwerts.

#### F: Kann ich das Erscheinungsbild des Serienbrieffelds in einem Word-Dokument mit Aspose.Words für .NET anpassen?

 A: Ja, Sie können das Erscheinungsbild des Zusammenführungsfelds in einem Word-Dokument mit Aspose.Words für .NET anpassen. Sie können die Formatierungsoptionen wie Groß-/Kleinschreibung, Schriftart, Farbe usw. mithilfe der Eigenschaften festlegen`FieldMergeField` Objekt.

#### F: Wie kann ich mit Aspose.Words für .NET überprüfen, ob ein Zusammenführungsfeld erfolgreich in ein Word-Dokument eingefügt wurde?

 A: Um zu überprüfen, ob ein Zusammenführungsfeld erfolgreich eingefügt wurde, können Sie den Dokumentinhalt durchsuchen und nach Zusammenführungsfeldinstanzen suchen. Sie können die Methoden und Eigenschaften von verwenden`Document` Objekt, um auf Absätze, Felder und andere Elemente des Dokuments zuzugreifen.

#### F: Beeinflusst das Einfügen eines Briefvorlagenfelds mithilfe von DOM die Word-Dokumentstruktur mit Aspose.Words für .NET?

A: Das Einfügen eines Serienbrieffelds mithilfe des DOM hat keinen direkten Einfluss auf die Struktur des Word-Dokuments. Allerdings wird dem Dokumentinhalt ein neues Feldelement hinzugefügt. Sie können die Dokumentstruktur bearbeiten, indem Sie die vorhandenen Elemente entsprechend Ihren Anforderungen hinzufügen, löschen oder ändern.