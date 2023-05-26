---
title: Feld einfügen
linktitle: Feld einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Feld in Ihre Word-Dokumente einfügen. Personalisieren Sie Ihre Dokumente mit dynamischen Feldern.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Ein Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Einfügen des Feldes

 Wir benutzen das`InsertField()` Methode des DocumentBuilders, um ein Feld in das Dokument einzufügen. In diesem Beispiel fügen wir ein Zusammenführungsfeld (MERGEFIELD) mit dem Feldnamen „MyFieldName“ und dem Zusammenführungsformat ein.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Beispiel des Quellcodes zum Einfügen eines Feldes mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Feld ein.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen DocumentBuilder initialisiert und dann ein Zusammenführungsfeld mit dem Feldnamen „MyFieldName“ und dem Zusammenführungsformat eingefügt. Das Dokument wird dann unter einem angegebenen Dateinamen gespeichert.

Damit ist unser Leitfaden zur Verwendung der Funktion „Ein Feld einfügen“ mit Aspose.Words für .NET abgeschlossen.
