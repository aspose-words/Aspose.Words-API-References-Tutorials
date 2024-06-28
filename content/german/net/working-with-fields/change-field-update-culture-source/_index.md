---
title: Ändern Sie die Quelle der Feldaktualisierungskultur
linktitle: Ändern Sie die Quelle der Feldaktualisierungskultur
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Kulturquelle für Feldaktualisierung ändern, Schritt-für-Schritt-Anleitung zum Ändern der Kulturquelle in Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/change-field-update-culture-source/
---

In diesem Tutorial führen wir Sie durch den Prozess der Änderung der Feldaktualisierungskulturquelle in Word-Dokumenten mithilfe von Aspose.Words für .NET. Durch Ändern der Kulturquelle können Sie die Datumsformatierung während Feldaktualisierungs- und Seriendruckvorgängen steuern. Wir stellen Ihnen den notwendigen C#-Quellcode und eine Schritt-für-Schritt-Anleitung zur Verfügung, um dies zu erreichen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein Dokument und einen DocumentBuilder
Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie Inhalte mit einem bestimmten Gebietsschema ein
Als nächstes stellen Sie das Gebietsschema auf Deutsch ein und fügen Felder mit Datumsformatierung ein:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Im obigen Code setzen wir das Schriftgebietsschema auf Deutsch (Gebietsschema-ID 1031) und fügen zwei Felder mit spezifischer Datumsformatierung ein.

## Schritt 3: Ändern Sie die Feldaktualisierungskulturquelle
Um die Quelle der Feldaktualisierungskultur zu ändern, verwenden Sie die FieldOptions-Klasse:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

In diesem Beispiel legen wir fest, dass die während der Feldaktualisierung verwendete Kultur aus der vom Feld verwendeten Kultur ausgewählt wird.

## Schritt 4: Führen Sie den Serienbrief durch
Führen Sie einen Seriendruckvorgang durch und geben Sie den Datumswert für das Feld „Datum2“ an:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

In diesem Codeausschnitt führen wir den Seriendruckvorgang aus und stellen einen DateTime-Wert für das Feld „Date2“ bereit.

## Schritt 5: Speichern Sie das Dokument
Speichern Sie das geänderte Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Beispielquellcode zum Ändern der Feldaktualisierungskulturquelle mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Ändern der Feldaktualisierungskulturquelle in Word-Dokumenten mit Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET die Quelle der Feldaktualisierungskultur in Word-Dokumenten ändern. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt die Kultur steuern, die für die Datumsformatierung bei Feldaktualisierungen und Seriendruckvorgängen verwendet wird. Passen Sie die Kulturquelle entsprechend Ihren Anforderungen an, um ein genaues und konsistentes Datum sicherzustellen.

### FAQs

#### F: Wie kann ich die Quelle der Feldaktualisierungskultur in Aspose.Words für .NET ändern?

 A: Um die Quelle der Feldaktualisierungskultur in Aspose.Words für .NET zu ändern, können Sie die verwenden`Document.FieldOptions.CultureSource` Eigenschaft und setzen Sie ihren Wert auf`FieldCultureSource.FieldCode` oder`FieldCultureSource.CurrentThread` . Sie können zum Beispiel verwenden`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` um die im Feldcode definierte Kultur zu verwenden.

#### F: Wie kann ich eine bestimmte Kultur zum Aktualisieren von Feldern in Aspose.Words für .NET angeben?

 A: Um eine bestimmte Kultur für die Aktualisierung von Feldern in Aspose.Words für .NET anzugeben, können Sie die verwenden`Document.FieldOptions.FieldUpdateCultureInfo` Eigenschaft und legen Sie die fest`CultureInfo` Objekt, das der gewünschten Kultur entspricht. Sie können zum Beispiel verwenden`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` um die französische (französische) Kultur zu spezifizieren.

#### F: Ist es möglich, die automatische Feldaktualisierung in Aspose.Words für .NET zu deaktivieren?

 A: Ja, es ist möglich, die automatische Feldaktualisierung in Aspose.Words für .NET zu deaktivieren. Du kannst den ... benutzen`Document.FieldOptions.UpdateFields` Eigenschaft und setzen Sie sie auf`false` um zu verhindern, dass Felder automatisch aktualisiert werden. Dadurch können Sie die Aktualisierung von Feldern nach Bedarf manuell steuern.

#### F: Wie kann ich Dokumentfelder in Aspose.Words für .NET manuell aktualisieren?

 A: Um Felder in einem Dokument in Aspose.Words für .NET manuell zu aktualisieren, können Sie die verwenden`Field.Update` Methode für jedes Feld einzeln festlegen. Sie können zum Beispiel verwenden`field.Update()` um das spezifische Feld zu aktualisieren.