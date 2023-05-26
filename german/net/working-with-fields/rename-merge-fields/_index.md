---
title: Zusammenführungsfelder umbenennen
linktitle: Zusammenführungsfelder umbenennen
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie Zusammenführungsfelder in einem Dokument mit Aspose.Words für .NET umbenennen.
type: docs
weight: 10
url: /de/net/working-with-fields/rename-merge-fields/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion zum Umbenennen von Zusammenführungsfeldern von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und Einfügen der Zusammenführungsfelder

 Wir beginnen damit, ein neues Dokument zu erstellen und ein zu verwenden`DocumentBuilder` um die Zusammenführungsfelder einzufügen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Schritt 3: Zusammenführungsfelder umbenennen

Wir durchlaufen jedes Feld im Dokumentbereich, und wenn es sich um ein Zusammenführungsfeld handelt, benennen wir das Feld um, indem wir das „“ hinzufügen._Suffix „umbenannt“.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Schritt 4: Speichern des Dokuments

 Abschließend nennen wir die`Save()` Methode zum Speichern des geänderten Dokuments.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Quellcode-Beispiel zum Umbenennen von Zusammenführungsfeldern mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und fügen Sie die Zusammenführungsfelder ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Benennen Sie Zusammenführungsfelder um.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Speichern Sie das Dokument.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Befolgen Sie diese Schritte, um Briefvorlagenfelder in Ihrem Dokument mit Aspose.Words für .NET umzubenennen.