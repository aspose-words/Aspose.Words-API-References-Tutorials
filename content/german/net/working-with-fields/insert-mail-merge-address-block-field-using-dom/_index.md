---
title: Serienbrief-Adressblockfeld mithilfe von DOM einfügen
linktitle: Serienbrief-Adressblockfeld mithilfe von DOM einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Serienbrief-Adressblockfeld in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Hier ist eine Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes unten, der die Funktion „Seriendruck-Adressblockfeld einfügen“ von Aspose.Words für .NET verwendet. Befolgen Sie jeden Schritt sorgfältig, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentverzeichnisses

Im angegebenen Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments und des DocumentBuilder

Wir beginnen mit der Erstellung eines neuen Dokuments und der Initialisierung eines DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Cursor zum Absatz bewegen

 Wir verwenden die DocumentBuilder`MoveTo()` Methode, um den Cursor zu dem Absatz zu bewegen, in dem wir das Serienbrief-Adressblockfeld einfügen möchten.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Schritt 4: Einfügen des Serienbrief-Adressblockfelds

 Wir verwenden die DocumentBuilder`InsertField()` Methode zum Einfügen eines Serienbrief-Adressblockfelds in den Absatz.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Anschließend konfigurieren wir die Eigenschaften des Adressblockfelds und geben die entsprechenden Optionen an, wie z. B. die Einbeziehung des Länder-/Regionsnamens, die Formatierung der Adresse entsprechend dem Land/der Region, den Ausschluss von Länder-/Regionsnamen, das Namens- und Adressformat und die Sprachkennung.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Schließlich nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispielquellcode zum Einfügen eines Serienbrief-Adressblockfelds mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Wir möchten einen Serienbrief-Adressblock wie diesen einfügen:
// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { ADRESSBLOCK \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { ADRESSBLOCK \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ADRESSBLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### Häufig gestellte Fragen

#### F: Wie kann ich mit Aspose.Words für .NET das Format der Postanschrift in einem Word-Dokument anpassen?

 A: Sie können das Format der Postanschrift in einem Word-Dokument mit Aspose.Words für .NET anpassen, indem Sie die Eigenschaften des`FieldAddressBlock`Objekt. Sie können die Formatierungsoptionen wie Adressstil, Trennzeichen, optionale Elemente usw. festlegen, um das gewünschte Format zu erhalten.

#### F: Wie kann ich die Quelldaten für das Feld „Postanschrift“ in Aspose.Words für .NET angeben?

 A: Um die Quelldaten für das Feld „Postanschrift“ in Aspose.Words für .NET anzugeben, können Sie den`FieldAddressBlock.StartAddress`Und`FieldAddressBlock.EndAddress` Eigenschaften. Diese Eigenschaften werden verwendet, um die Adressbereiche in der externen Datenquelle, beispielsweise einer CSV-Datei, einer Datenbank usw., zu definieren.

#### F: Kann ich mit Aspose.Words für .NET optionale Elemente in das Feld „Postanschrift“ einschließen?

 A: Ja, Sie können optionale Elemente in das Feld für die Postanschrift mit Aspose.Words für .NET aufnehmen. Sie können optionale Elemente definieren, indem Sie`FieldAddressBlock.OmitOptional` Methode, um anzugeben, ob optionale Elemente wie Empfängername, Firmenname usw. ein- oder ausgeschlossen werden sollen.

#### F: Hat das Einfügen eines Postanschriftfelds mithilfe des DOM Auswirkungen auf die Word-Dokumentstruktur mit Aspose.Words für .NET?

A: Das Einfügen eines Postanschriftfelds mithilfe des DOM hat keine direkten Auswirkungen auf die Struktur des Word-Dokuments. Es fügt dem Dokumentinhalt jedoch ein neues Feldelement hinzu. Sie können die Dokumentstruktur bearbeiten, indem Sie die vorhandenen Elemente nach Bedarf hinzufügen, löschen oder ändern.