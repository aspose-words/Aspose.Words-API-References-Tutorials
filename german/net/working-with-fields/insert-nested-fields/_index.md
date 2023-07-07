---
title: Verschachtelte Felder einfügen
linktitle: Verschachtelte Felder einfügen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ganz einfach verschachtelte Felder in Ihre Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/working-with-fields/insert-nested-fields/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Funktion „Verschachtelte Felder einfügen“ von Aspose.Words für .NET verwendet. Stellen Sie sicher, dass Sie jeden Schritt sorgfältig befolgen, um die gewünschten Ergebnisse zu erzielen.

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

## Schritt 3: Seitenumbrüche einfügen

Wir verwenden eine Schleife, um mehrere Seitenumbrüche in das Dokument einzufügen.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Schritt 4: Zur Fußzeile wechseln

 Wir benutzen das`MoveToHeaderFooter()` -Methode des DocumentBuilders, um den Cursor in die Hauptfußzeile zu bewegen.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Schritt 5: Einfügen des verschachtelten Feldes

 Wir verwenden den DocumentBuilder`InsertField()`Methode zum Einfügen eines verschachtelten Felds in die Fußzeile.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Abschließend nennen wir die`Update()` Methode zum Aktualisieren des Felds.

```csharp
field. Update();
```

### Beispielquellcode zum Einfügen verschachtelter Felder mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und den DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Seitenumbrüche einfügen.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Zur Fußzeile wechseln.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Verschachteltes Feld einfügen.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Aktualisieren Sie das Feld.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

In diesem Beispiel haben wir ein neues Dokument erstellt, Seitenumbrüche eingefügt, den Cursor in die Fußzeile bewegt und dann ein verschachteltes Feld in die Fußzeile eingefügt.

### FAQs

#### F: Wie kann ich mit Aspose.Words für .NET verschachtelte Felder in ein Word-Dokument einfügen?

A: Um verschachtelte Felder mit Aspose.Words für .NET in ein Word-Dokument einzufügen, können Sie die folgenden Schritte ausführen:

1. Rufen Sie den Absatz auf, in den Sie die verschachtelten Felder einfügen möchten.
2.  Ein ... kreieren`FieldStart` Objekt für das übergeordnete Feld.
3.  Fügen Sie die untergeordneten Felder mit hinzu`FieldStart.NextSibling` Methode, die das entsprechende übergibt`FieldStart` Objekte als Parameter.

#### F: Welche Vorteile bietet die Verwendung verschachtelter Felder in einem Word-Dokument mit Aspose.Words für .NET?

A: Die Verwendung verschachtelter Felder bietet in einem Word-Dokument mit Aspose.Words für .NET mehrere Vorteile. Dies ermöglicht eine größere Flexibilität bei der Erstellung dynamischer Dokumentvorlagen, indem variable Werte und Berechnungen in verschachtelte Felder eingefügt werden können. Verschachtelte Felder können auch die automatisierte Inhaltsgenerierung erleichtern, z. B. die Generierung von Inhaltsverzeichnissen, Seitenzahlen usw.

#### F: Kann ich mit Aspose.Words für .NET mehrstufige verschachtelte Felder in einem Word-Dokument haben?

 A: Ja, es ist möglich, mit Aspose.Words für .NET mehrstufige verschachtelte Felder in einem Word-Dokument zu haben. Mithilfe von können Sie komplexe Hierarchien verschachtelter Felder erstellen`FieldStart.NextSibling` Methode zum Hinzufügen untergeordneter Felder zu vorhandenen übergeordneten Feldern.

#### F: Wie kann ich die Eigenschaften verschachtelter Felder in einem Word-Dokument mit Aspose.Words für .NET anpassen?

 A: Um die Eigenschaften verschachtelter Felder in einem Word-Dokument mit Aspose.Words für .NET anzupassen, können Sie auf das entsprechende zugreifen`FieldStart`Objekte und ändern Sie deren Eigenschaften nach Bedarf. Sie können Formatierungsoptionen, Werte, Berechnungen usw. für verschachtelte Felder festlegen, um das gewünschte Ergebnis zu erzielen.

#### F: Beeinträchtigt das Einfügen verschachtelter Felder die Leistung von Word-Dokumenten mit Aspose.Words für .NET?

A: Das Einfügen verschachtelter Felder kann sich auf die Leistung von Word-Dokumenten mit Aspose.Words für .NET auswirken, insbesondere wenn das Dokument eine große Anzahl verschachtelter Felder oder komplexe Hierarchien enthält. Es wird empfohlen, den Code zu optimieren und unnötige oder wiederholte Vorgänge an verschachtelten Feldern zu vermeiden, um die Leistung zu verbessern.