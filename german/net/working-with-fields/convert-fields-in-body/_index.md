---
title: Felder im Textkörper konvertieren
linktitle: Felder im Textkörper konvertieren
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Seitenfelder in Text im Hauptteil eines Word-Dokuments konvertieren.
type: docs
weight: 10
url: /de/net/working-with-fields/convert-fields-in-body/
---

In diesem Schritt-für-Schritt-Tutorial führen wir Sie durch die Verwendung der ConvertFieldsInBody-Funktion von Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes. Mit dieser Funktion können Sie bestimmte Felder im Hauptteil Ihres Dokuments in einfachen Text umwandeln und so die Verarbeitung Ihrer Dokumente erleichtern. Befolgen Sie die nachstehenden Schritte, um diese Funktion effektiv zu nutzen.

## Schritt 1: Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Aspose.Words für .NET installiert haben und ein Dokument zur Verarbeitung bereit haben. Stellen Sie außerdem sicher, dass Sie den Verzeichnispfad zu Ihren Dokumenten haben.

## Schritt 2: Laden Sie das Dokument

Deklarieren Sie zunächst eine Variable für den Pfad zu Ihrem Dokumentenverzeichnis und verwenden Sie diese Variable dann, um ein Document-Objekt aus dem angegebenen Dokument zu initialisieren. In unserem Beispiel heißt das Dokument „Verknüpfte Felder.docx“.

```csharp
// Der Pfad zu Ihrem Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Laden Sie das Dokument
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Schritt 3: Konvertieren Sie Seitenfelder in einfachen Text

Nachdem das Dokument nun geladen ist, können wir mit den Konvertierungsschritten fortfahren. Um die Seitenfelder im Hauptteil des ersten Abschnitts in einfachen Text umzuwandeln, können Sie die verwenden`Range.Fields` Methode, um alle Felder im angegebenen Bereich abzurufen und dann Felder des Typs herauszufiltern`FieldType.FieldPage` . Dann können Sie das verwenden`ForEach` Methode, um jedes Feld zu durchlaufen und aufzurufen`Unlink()` Methode, um es in einfachen Text umzuwandeln.

```csharp
// Übergeben Sie die entsprechenden Parameter, um die Seitenfelder im Hauptteil des ersten Abschnitts in einfachen Text umzuwandeln.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Schritt 4: Speichern Sie das geänderte Dokument

 Nachdem Sie die Seitenfelder in einfachen Text umgewandelt haben, können Sie das geänderte Dokument mit speichern`Save()` -Methode und Angabe des Pfads und Namens der Ausgabedatei. In unserem Beispiel speichern wir es als „WorkingWithFields.ConvertFieldsInBody.docx“.

```csharp
// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Beispielquellcode zum Konvertieren von Feldern im Textkörper mit Aspose.Words für .NET

Hier ist das vollständige Quellcodebeispiel für die Konvertierung von Feldern in den Textkörper mithilfe von Aspose.Words für .NET:

```csharp
// Der Pfad zu Ihrem Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Laden Sie das Dokument
Document doc = new Document(dataDir + "Linked fields.docx");

// Übergeben Sie die entsprechenden Parameter, um die Seitenfelder im Hauptteil des ersten Abschnitts in einfachen Text umzuwandeln.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```