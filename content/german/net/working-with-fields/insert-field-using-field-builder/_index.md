---
title: Feld mit Field Builder einfügen
linktitle: Feld mit Field Builder einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET benutzerdefinierte Felder in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-field-using-field-builder/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Feld mit FieldBuilder einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

## Schritt 1: Einrichten des Dokumentenverzeichnisses

Im bereitgestellten Code müssen Sie das Verzeichnis Ihrer Dokumente angeben. Ersetzen Sie den Wert „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad zu Ihrem Dokumentenverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen des Dokuments

Wir beginnen mit der Erstellung eines neuen Dokuments.

```csharp
Document doc = new Document();
```

## Schritt 3: Erstellen des IF-Felds mit FieldBuilder

Wir verwenden die FieldBuilder-Klasse, um ein IF-Feld mit zwei verschachtelten MERGEFIELD-Feldern zu erstellen. In diesem Beispiel zeigt das IF-Feld den Vor- und Nachnamen basierend auf einer Bedingung an.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Schritt 4: Einfügen des IF-Feldes in das Dokument

 Wir benutzen das`BuildAndInsert()` Methode zum Erstellen und Einfügen des IF-Felds an einer bestimmten Stelle im Dokument.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Beispielquellcode zum Einfügen eines Feldes mit FieldBuilder mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Dokumentenerstellung.
Document doc = new Document();

// Aufbau des IF-Feldes mit FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Fügen Sie das IF-Feld in das Dokument ein.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, ein IF-Feld mit verschachtelten MERGEFIELD-Feldern erstellt und dieses Feld dann an einer angegebenen Stelle in das Dokument eingefügt. Das Dokument wird dann unter einem bestimmten Dateinamen gespeichert.

### FAQs

#### F: Was ist ein Feldkonstruktor in Aspose.Words?

A: Ein Field Builder in Aspose.Words ist ein leistungsstarkes Tool zum Erstellen und Bearbeiten von Feldern in einem Word-Dokument. Es bietet erweiterte Funktionen zum Erstellen und Anpassen von Feldern, einschließlich des Einfügens von Feldcodes und der Verwaltung von Formatierungsoptionen.

#### F: Welche Arten von Feldern können mit dem Feld-Builder eingefügt werden?

A: Mit dem Feld-Builder in Aspose.Words können Sie verschiedene Feldtypen in ein Word-Dokument einfügen. Hier sind einige Beispiele für häufig verwendete Feldtypen:

- MERGEFIELD: Wird zum Zusammenführen von Daten aus externen Quellen verwendet.
- DATUM: Zeigt das aktuelle Datum an.
- SEITE: Zeigt die aktuelle Seitenzahl an.
- IF: ermöglicht es, die Anzeige eines Inhalts entsprechend einer Bedingung zu konditionieren.
- Inhaltsverzeichnis: generiert automatisch ein Inhaltsverzeichnis basierend auf den Dokumenttitelstilen.

#### F: Wie kann ich die mit dem Feld-Builder eingefügten Felder anpassen?

A: Der Feld-Builder bietet Anpassungsoptionen für eingefügte Felder. Sie können Feldkonstruktormethoden und -eigenschaften verwenden, um Optionen wie Feldformatierung, Argumente, Schalter und Standardwerte festzulegen. Sie können beispielsweise das Datumsformat, das Zahlenformat, das Tausendertrennzeichen usw. festlegen.
  