---
title: Inhaltsverzeichnis in Word-Dokument einfügen
linktitle: Inhaltsverzeichnis in Word-Dokument einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Inhaltsverzeichnis in Word-Dokumente einfügen.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-table-of-contents/
---
In diesem umfassenden Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET ein Inhaltsverzeichnis in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, ein Inhaltsverzeichnis mit den entsprechenden Überschriften und Seitenzahlen zu erstellen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie ein Inhaltsverzeichnis ein
Als nächstes verwenden Sie die Methode „InsertTableOfContents“ der Klasse „DocumentBuilder“, um ein Inhaltsverzeichnis einzufügen. Geben Sie die erforderlichen Formatierungsoptionen innerhalb der Methode an:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Schritt 3: Dokumentinhalt hinzufügen
Fügen Sie nach dem Einfügen des Inhaltsverzeichnisses den eigentlichen Dokumentinhalt hinzu. Legen Sie die entsprechenden Überschriftenstile mit StyleIdentifier fest:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Schritt 4: Aktualisieren Sie das Inhaltsverzeichnis
Das neu eingefügte Inhaltsverzeichnis ist zunächst leer. Um es auszufüllen, aktualisieren Sie die Felder im Dokument:

```csharp
doc.UpdateFields();
```

## Schritt 5: Speichern Sie das Dokument
Nachdem Sie das Inhaltsverzeichnis eingefügt und die Felder aktualisiert haben, speichern Sie das Dokument mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Beispielquellcode zum Einfügen eines Inhaltsverzeichnisses mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen eines Inhaltsverzeichnisses mit Aspose.Words für .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialisieren Sie DocumentBuilder mit dem Document-Objekt
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inhaltsverzeichnis einfügen
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Beginnen Sie mit dem eigentlichen Dokumentinhalt auf der zweiten Seite.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Das neu eingefügte Inhaltsverzeichnis ist zunächst leer.
// Es muss ausgefüllt werden, indem die Felder im Dokument aktualisiert werden.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET ein Inhaltsverzeichnis in ein Word-Dokument einfügen. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode nutzen, können Sie nun ein Inhaltsverzeichnis mit passenden Überschriften und Seitenzahlen für Ihre Dokumente erstellen.

### FAQs zum Einfügen eines Inhaltsverzeichnisses in ein Word-Dokument

#### F: Kann ich das Erscheinungsbild des Inhaltsverzeichnisses anpassen?

 A: Ja, Sie können das Erscheinungsbild des Inhaltsverzeichnisses anpassen, indem Sie die im angegebenen Formatierungsoptionen ändern`InsertTableOfContents` Methode. Mit den Parametern können Sie die Seitenzahlen, Einrückungen und andere Stile steuern.

#### F: Was passiert, wenn ich bestimmte Überschriftenebenen in das Inhaltsverzeichnis aufnehmen möchte?

 A: Sie können die gewünschten Überschriftenebenen angeben, die in das Inhaltsverzeichnis aufgenommen werden sollen, indem Sie den Wert innerhalb anpassen`InsertTableOfContents` Methode. Zum Beispiel mit`"\\o \"1-3\""` umfasst die Überschriftenebenen 1 bis 3.

#### F: Kann ich das Inhaltsverzeichnis automatisch aktualisieren, wenn ich Änderungen am Dokumentinhalt vornehme?

 A: Ja, Sie können das Inhaltsverzeichnis automatisch aktualisieren, indem Sie die aufrufen`UpdateFields` Methode für das Dokument. Dadurch wird sichergestellt, dass alle am Dokumentinhalt vorgenommenen Änderungen, wie z. B. das Hinzufügen oder Entfernen von Überschriften, im Inhaltsverzeichnis widergespiegelt werden.

#### F: Wie kann ich die Überschriftenebenen im Inhaltsverzeichnis unterschiedlich gestalten?

 A: Sie können die Überschriftenebenen unterschiedlich gestalten, indem Sie für jede Überschriftenebene unterschiedliche Absatzstile verwenden. Durch die Zuweisung unterschiedlicher`StyleIdentifier` Werte zum`ParagraphFormat` des`DocumentBuilder`können Sie für jede Überschriftenebene unterschiedliche Stile erstellen.

#### F: Ist es möglich, den Überschriften im Inhaltsverzeichnis zusätzliche Formatierungen hinzuzufügen?

 A: Ja, Sie können den Überschriften im Inhaltsverzeichnis zusätzliche Formatierungen hinzufügen, z. B. Schriftarten, Farben oder andere Eigenschaften. Durch Anpassen der`Font` Eigenschaften der`DocumentBuilder`können Sie benutzerdefinierte Formatierungen auf die Überschriften anwenden.