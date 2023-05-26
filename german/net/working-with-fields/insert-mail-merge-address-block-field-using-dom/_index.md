---
title: Fügen Sie ein Serienbrief-Adressblockfeld mithilfe von DOM ein
linktitle: Fügen Sie ein Serienbrief-Adressblockfeld mithilfe von DOM ein
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Mail-Merge-Adressblockfeld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Mail Merge Address Block Field einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Bewegen Sie den Cursor zum Absatz

 Wir verwenden den DocumentBuilder`MoveTo()` -Methode, um den Cursor zu dem Absatz zu bewegen, in dem wir das Feld für den Serienbrief-Adressblock einfügen möchten.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Schritt 4: Einfügen des Serienbrief-Adressblockfelds

 Wir verwenden den DocumentBuilder`InsertField()` Methode zum Einfügen eines Mail-Merge-Adressblockfelds in den Absatz.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Anschließend konfigurieren wir die Eigenschaften des Adressblockfelds und geben die entsprechenden Optionen an, z. B. die Einbeziehung des Länder-/Regionsnamens, die Formatierung der Adresse nach Land/Region, ausgeschlossene Länder-/Regionsnamen, Namens- und Adressformat und Sprachkennung.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispielquellcode zum Einfügen eines Mail-Merge-Adressblockfelds mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Wir möchten einen Serienbrief-Adressblock wie diesen einfügen:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADDRESSBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADDRESSBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
