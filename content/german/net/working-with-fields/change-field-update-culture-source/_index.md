---
title: Feld „Kulturquelle aktualisieren“ ändern
linktitle: Feld „Kulturquelle aktualisieren“ ändern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Feld „Kulturquelle ändern“ aktualisieren, Schritt-für-Schritt-Anleitung zum Ändern der Kulturquelle in Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fields/change-field-update-culture-source/
---

In diesem Tutorial führen wir Sie durch den Prozess zum Ändern der Kulturquelle für Feldaktualisierungen in Word-Dokumenten mit Aspose.Words für .NET. Durch Ändern der Kulturquelle können Sie die Datumsformatierung während Feldaktualisierungs- und Seriendruckvorgängen steuern. Wir stellen Ihnen den erforderlichen C#-Quellcode und schrittweise Anweisungen zur Verfügung, um dies zu erreichen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Auf Ihrem System ist die Bibliothek Aspose.Words für .NET installiert.

## Schritt 1: Erstellen Sie ein Dokument und einen DocumentBuilder
Erstellen Sie zunächst eine Instanz der Document-Klasse und ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Inhalte mit spezifischem Gebietsschema einfügen
Stellen Sie als nächstes die Sprache auf Deutsch ein und fügen Sie Felder mit Datumsformatierung ein:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

Im obigen Code stellen wir das Schriftgebietsschema auf Deutsch ein (Gebietsschema-ID 1031) und fügen zwei Felder mit spezifischer Datumsformatierung ein.

## Schritt 3: Kulturquelle für Feldaktualisierung ändern
Um die Kulturquelle der Feldaktualisierung zu ändern, verwenden Sie die Klasse FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

In diesem Beispiel legen wir fest, dass die während der Feldaktualisierung verwendete Kultur aus der vom Feld verwendeten Kultur ausgewählt wird.

## Schritt 4: Serienbrief erstellen
Führen Sie einen Serienbriefvorgang durch und geben Sie den Datumswert für das Feld „Datum2“ an:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

In diesem Codeausschnitt führen wir den Serienbriefvorgang aus und stellen einen DateTime-Wert für das Feld „Date2“ bereit.

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
Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie die Kulturquelle für Feldaktualisierungen in Word-Dokumenten mit Aspose.Words für .NET ändern. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt die Kultur steuern, die für die Datumsformatierung während Feldaktualisierungs- und Seriendruckvorgängen verwendet wird. Passen Sie die Kulturquelle entsprechend Ihren Anforderungen an, um genaue und konsistente Daten sicherzustellen.

### Häufig gestellte Fragen

#### F: Wie kann ich die Kulturquelle der Feldaktualisierung in Aspose.Words für .NET ändern?

 A: Um die Kulturquelle für das Feldupdate in Aspose.Words für .NET zu ändern, können Sie den`Document.FieldOptions.CultureSource` und legen Sie den Wert fest auf`FieldCultureSource.FieldCode` oder`FieldCultureSource.CurrentThread` Sie können beispielsweise`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` um die im Feldcode definierte Kultur zu verwenden.

#### F: Wie kann ich eine bestimmte Kultur zum Aktualisieren von Feldern in Aspose.Words für .NET angeben?

 A: Um eine bestimmte Kultur für die Aktualisierung von Feldern in Aspose.Words für .NET anzugeben, können Sie den`Document.FieldOptions.FieldUpdateCultureInfo` und legen Sie die`CultureInfo` Objekt, das der gewünschten Kultur entspricht. Sie können beispielsweise`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` um die französische (französische) Kultur anzugeben.

#### F: Ist es möglich, die automatische Feldaktualisierung in Aspose.Words für .NET zu deaktivieren?

 A: Ja, es ist möglich, die automatische Feldaktualisierung in Aspose.Words für .NET zu deaktivieren. Sie können die`Document.FieldOptions.UpdateFields` und legen Sie sie auf`false` um die automatische Aktualisierung von Feldern zu verhindern. So können Sie die Aktualisierung von Feldern nach Bedarf manuell steuern.

#### F: Wie kann ich Dokumentfelder in Aspose.Words für .NET manuell aktualisieren?

 A: Um Felder in einem Dokument in Aspose.Words für .NET manuell zu aktualisieren, können Sie den`Field.Update` Methode für jedes Feld einzeln. Sie können beispielsweise`field.Update()` um das jeweilige Feld zu aktualisieren.