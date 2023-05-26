---
title: Feldaktualisierungskultur
linktitle: Feldaktualisierungskultur
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie die Feldkultur in Ihren Word-Dokumenten mit Aspose.Words für .NET aktualisieren.
type: docs
weight: 10
url: /de/net/working-with-fields/field-update-culture/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Field Culture Update“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des Dokumentengenerators

Wir beginnen mit der Erstellung eines neuen Dokuments und eines Dokumentengenerators.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Einfügen des Zeitfeldes

 Wir benutzen das`InsertField()` Methode zum Einfügen eines Zeitfelds in das Dokument.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Dadurch wird ein Zeitfeld in das Dokument eingefügt.

## Schritt 4: Konfigurieren der Feldaktualisierungskultur

Wir konfigurieren die Feldoptionen, um anzugeben, dass die Feldaktualisierungskultur auf dem Feldcode basieren soll.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Diese Optionen bestimmen die Kultur, die zum Aktualisieren von Feldern verwendet wird.

### Beispielquellcode zum Aktualisieren der Feldkultur mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den Dokumentengenerator.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie das Zeitfeld ein.
builder. InsertField(FieldType.FieldTime, true);

// Konfigurieren Sie die Feldaktualisierungskultur.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Speichern Sie das Dokument.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein Zeitfeld eingefügt und die Feldaktualisierungskultur konfiguriert. Anschließend haben wir das Dokument unter einem angegebenen Dateinamen gespeichert.

Damit ist unser Leitfaden zur Verwendung der Funktion „Feldkultur aktualisieren“ mit Aspose.Words für .NET abgeschlossen.