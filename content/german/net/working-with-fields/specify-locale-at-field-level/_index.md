---
title: Angeben des Gebietsschemas auf Feldebene
linktitle: Angeben des Gebietsschemas auf Feldebene
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Lokalisierung auf Feldebene in Word-Dokumenten angeben.
type: docs
weight: 10
url: /de/net/working-with-fields/specify-locale-at-field-level/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Angabe der Lokalisierung auf Feldebene mithilfe der Funktion Aspose.Words für .NET ermöglicht. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek in Ihr Projekt aufgenommen haben, bevor Sie diesen Code verwenden.

## Schritt 1: Dokumentverzeichnispfad festlegen

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Geben Sie unbedingt den richtigen Pfad zu Ihrem Dokumentverzeichnis an, in dem das bearbeitete Dokument gespeichert wird.

## Schritt 2: Erstellen Sie einen Dokumentgenerator

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Hier erstellen wir eine Instanz des`DocumentBuilder` Klasse, die es uns ermöglicht, dem Dokument Felder hinzuzufügen.

## Schritt 3: Einfügen eines Datumsfelds mit einem bestimmten Ort

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Wir verwenden den Dokumentgenerator, um ein Feld vom Typ`FieldType.FieldDate` in das Dokument. Durch das Setzen der`LocaleId`Eigentum an`1049`, wir geben für dieses Feld die russische Lokalisierung an.

## Schritt 4: Speichern Sie das geänderte Dokument

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Abschließend speichern wir das geänderte Dokument am angegebenen Speicherort in einer angegebenen Datei.

### Beispielquellcode zum Festlegen der Lokalisierung auf Feldebene mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Dies war ein Beispielquellcode zum Festlegen der Lokalisierung auf Feldebene in einem Dokument mit Aspose.Words für .NET. Sie können diesen Code verwenden, um Datumsfelder mit bestimmten Positionen in Ihre Word-Dokumente einzufügen.

### Häufig gestellte Fragen

#### F: Wie kann ich das Gebietsschema auf Feldebene in Aspose.Words für .NET angeben?

 A: Um das Gebietsschema auf Feldebene in Aspose.Words für .NET anzugeben, können Sie den`FieldOptions` Klasse und ihre`FieldLocale` , um das gewünschte Gebietsschema festzulegen. Sie können beispielsweise`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` um das französische Gebietsschema (Frankreich) anzugeben.

#### F: Ist es möglich, für jedes Feld in Aspose.Words für .NET ein anderes Gebietsschema anzugeben?

 A: Ja, es ist möglich, für jedes Feld in Aspose.Words für .NET ein anderes Gebietsschema anzugeben. Sie können das`FieldOptions.FieldLocale` -Eigenschaft, bevor Sie ein bestimmtes Feld erstellen oder aktualisieren, um ihm ein anderes Gebietsschema zuzuweisen.

#### F: Wie kann ich das aktuell verwendete Gebietsschema für ein Feld in Aspose.Words für .NET abrufen?

 A: Um das aktuell verwendete Gebietsschema für ein Feld in Aspose.Words für .NET zu erhalten, können Sie das Feld verwenden`Field.LocaleId`Eigenschaft. Dadurch können Sie die mit dem Feld verknüpfte Gebietsschemakennung abrufen.