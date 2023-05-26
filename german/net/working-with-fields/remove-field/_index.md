---
title: Feld entfernen
linktitle: Feld entfernen
second_title: Aspose.Words für .NET API-Referenz
description: In dieser Anleitung erfahren Sie, wie Sie mit Aspose.Words für .NET ein bestimmtes Feld in einem Dokument löschen.
type: docs
weight: 10
url: /de/net/working-with-fields/remove-field/
---
Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Feldentfernung“ von Aspose.Words für .NET nutzt. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden des Dokuments

Wir beginnen mit dem Laden des vorhandenen Dokuments aus der angegebenen Datei.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Schritt 3: Löschen des Feldes

 Wir wählen das erste Feld im Dokumentbereich aus und verwenden das`Remove()` Methode, um es zu entfernen.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Schritt 4: Speichern des Dokuments

 Abschließend nennen wir die`Save()` Methode zum Speichern des geänderten Dokuments.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Beispielquellcode für die Feldlöschung mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument.
Document doc = new Document(dataDir + "Various fields.docx");

// Auswahl des zu löschenden Feldes.
Field field = doc.Range.Fields[0];
field. Remove();

// Speichern Sie das Dokument.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Befolgen Sie diese Schritte, um mit Aspose.Words für .NET ein bestimmtes Feld in Ihrem Dokument zu löschen.
