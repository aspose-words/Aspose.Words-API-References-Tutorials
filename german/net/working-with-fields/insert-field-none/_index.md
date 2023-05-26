---
title: Feld „Keine“ einfügen
linktitle: Feld „Keine“ einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie AUCUN-Werte in Ihre Word-Dokumente mit Aspose.Words für .NET einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field-none/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „KEINES Feld einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Einfügen des NONE-Feldes

 Wir benutzen das`InsertField()` Methode des DocumentBuilders, um ein NONE-Feld in das Dokument einzufügen.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Quellcode-Beispiel zum Einfügen eines NONE-Feldes mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das NONE-Feld ein.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, einen DocumentBuilder initialisiert und dann ein NONE-Feld eingefügt. Das Dokument wird dann unter einem angegebenen Dateinamen gespeichert.

Damit ist unser Leitfaden zur Verwendung der Funktion „KEIN Feld einfügen“ mit Aspose.Words für .NET abgeschlossen.