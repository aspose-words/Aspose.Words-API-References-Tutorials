---
title: Geben Sie das Gebietsschema auf Feldebene an
linktitle: Geben Sie das Gebietsschema auf Feldebene an
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Lokalisierung auf Feldebene in Word-Dokumenten festlegen.
type: docs
weight: 10
url: /de/net/working-with-fields/specify-locale-at-field-level/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Angabe der Lokalisierung auf Feldebene mithilfe der Funktion „Aspose.Words für .NET“ ermöglicht. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt eingebunden haben, bevor Sie diesen Code verwenden.

## Schritt 1: Legen Sie den Pfad zum Dokumentverzeichnis fest

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrem Dokumentenverzeichnis angeben, in dem das bearbeitete Dokument gespeichert wird.

## Schritt 2: Erstellen Sie einen Dokumentengenerator

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Hier erstellen wir eine Instanz von`DocumentBuilder` Klasse, die es uns ermöglicht, dem Dokument Felder hinzuzufügen.

## Schritt 3: Fügen Sie ein Datumsfeld mit einem bestimmten Ort ein

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Wir verwenden den Dokumentengenerator, um ein Feld vom Typ einzufügen`FieldType.FieldDate` in das Dokument ein. Durch Einstellen der`LocaleId` Eigentum zu`1049`, geben wir die russische Lokalisierung für dieses Feld an.

## Schritt 4: Speichern Sie das geänderte Dokument

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Abschließend speichern wir das geänderte Dokument am angegebenen Speicherort in einer angegebenen Datei.

### Beispielquellcode zur Angabe der Lokalisierung auf Feldebene mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Dies war ein Beispielquellcode zur Angabe der Lokalisierung auf Feldebene in einem Dokument mithilfe von Aspose.Words für .NET. Mit diesem Code können Sie Datumsfelder mit bestimmten Positionen in Ihre Word-Dokumente einfügen.

### FAQs

#### F: Wie kann ich das Gebietsschema auf Feldebene in Aspose.Words für .NET angeben?

 A: Um das Gebietsschema auf Feldebene in Aspose.Words für .NET anzugeben, können Sie Folgendes verwenden`FieldOptions` Klasse und ihre`FieldLocale` -Eigenschaft, um das gewünschte Gebietsschema festzulegen. Sie können zum Beispiel verwenden`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` um das Gebietsschema Französisch (Frankreich) anzugeben.

#### F: Ist es möglich, für jedes Feld in Aspose.Words für .NET ein anderes Gebietsschema anzugeben?

 A: Ja, es ist möglich, für jedes Feld in Aspose.Words für .NET ein anderes Gebietsschema anzugeben. Du kannst den ... benutzen`FieldOptions.FieldLocale` Eigenschaft, bevor Sie ein bestimmtes Feld erstellen oder aktualisieren, um ihm ein anderes Gebietsschema zuzuweisen.

#### F: Wie kann ich das aktuell verwendete Gebietsschema für ein Feld in Aspose.Words für .NET abrufen?

 A: Um das aktuell verwendete Gebietsschema für ein Feld in Aspose.Words für .NET abzurufen, können Sie das Feld verwenden`Field.LocaleId` Eigentum. Dadurch können Sie die mit dem Feld verknüpfte Gebietsschemakennung abrufen.