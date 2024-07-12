---
title: Bidi-Markierungen in Word-Dokument einfügen
linktitle: Bidi-Markierungen in Word-Dokument einfügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Bidi-Markierungen zu einem Word-Dokument hinzufügen und professionelle mehrsprachige Dokumente erstellen.
type: docs
weight: 10
url: /de/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, einem Dokument Bidi-Markierungen (bidirektional) hinzuzufügen. In dieser Anleitung zeigen wir Ihnen, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET einem Dokument Bidi-Markierungen hinzufügen.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Textverarbeitung mit Word-Dokumenten einfach und effizient macht. Sie bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten, einschließlich des Hinzufügens von Bidi-Markierungen.

## Erstellen des Dokuments und Hinzufügen von Inhalten

Der erste Schritt besteht darin, ein neues Dokument zu erstellen und Inhalt hinzuzufügen. Verwenden Sie die Klasse Document, um eine neue Dokumentinstanz zu erstellen. Verwenden Sie dann die Klasse DocumentBuilder, um dem Dokument Text hinzuzufügen. Hier ist ein Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

In diesem Beispiel erstellen wir ein neues Dokument und verwenden den DocumentBuilder, um Text hinzuzufügen. Wir haben drei Textzeilen hinzugefügt: eine auf Englisch, eine auf Hebräisch und eine auf Arabisch, um das Hinzufügen von Inhalten in verschiedenen Sprachen zu demonstrieren.

## Bidi-Markierungen hinzugefügt

Nachdem der Inhalt hinzugefügt wurde, können wir dem Dokument nun Bidi-Markierungen hinzufügen. Dazu verwenden wir die Klasse TxtSaveOptions und setzen die Eigenschaft AddBidiMarks auf true. So geht's:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

In diesem Beispiel erstellen wir eine Instanz von TxtSaveOptions und setzen die Eigenschaft AddBidiMarks auf true. Als Nächstes verwenden wir die Save-Methode der Document-Klasse, um das Dokument mit Bidi-Markierungen zu speichern.

### Beispiel-Quellcode für die Funktion „Bidi-Markierungen hinzufügen“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und fügen Sie Inhalt hinzu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Bidi-Markierungen hinzufügen
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Abschluss

In diesem Handbuch haben wir erklärt, wie Sie mit Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes Bidi-Markierungen zu einem Word-Dokument hinzufügen. Indem Sie die angegebenen Schritte befolgen, können Sie Ihren Word-Dokumenten in Ihrer C#-Anwendung problemlos Bidi-Markierungen hinzufügen. Aspose.Words bietet enorme Flexibilität und Leistung für die Textverarbeitung mit Textformatierung und Sprachverwaltung, sodass Sie professionell mehrsprachige Dokumente erstellen können.

### Häufig gestellte Fragen

#### F: Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten in einer C#-Anwendung. Sie bietet zahlreiche Funktionen für die Textverarbeitung mit Word-Dokumenten, einschließlich des Hinzufügens von Bidi-Markierungen (bidirektional).

#### F: Welche Funktionen bietet Aspose.Words für .NET?
Aspose.Words für .NET bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten. Einige dieser Funktionen umfassen das Erstellen von Dokumenten, das Hinzufügen von Inhalten, das Formatieren von Text, das Verwalten von Tabellen, das Zusammenführen und Aufteilen von Dokumenten, das Konvertieren von Dokumenten und mehr.

#### F: Wie kann ich mit Aspose.Words für .NET Bidi-Markierungen zu einem Word-Dokument hinzufügen?
Sie können einem Word-Dokument Bidi-Markierungen hinzufügen, indem Sie die folgenden Schritte ausführen:

 Erstellen Sie ein neues Dokument mit dem`Document` Klasse.

 Verwenden Sie die`DocumentBuilder` Klasse, um dem Dokument Inhalt hinzuzufügen.

 Sobald Sie den Inhalt hinzugefügt haben, verwenden Sie die`TxtSaveOptions` Klasse und legen Sie die`AddBidiMarks`Eigentum an`true`.

 Speichern Sie das Dokument mit Bidi-Markierungen mit dem`Save` Methode der`Document` Klasse.

#### F: Unterstützt Aspose.Words mehrere Sprachen zum Hinzufügen von Bidi-Markierungen?
Ja, Aspose.Words unterstützt mehrere Sprachen zum Hinzufügen von Bidi-Markierungen. Mit Aspose.Words für .NET können Sie Texten in verschiedenen Sprachen, wie Englisch, Hebräisch und Arabisch, Bidi-Markierungen hinzufügen.

#### F: Gibt es zusätzliche Optionen zum Speichern des Dokuments mit Bidi-Markierungen?
 Ja, Sie können beim Speichern des Dokuments mit Bidi-Markierungen andere Optionen angeben, indem Sie`TxtSaveOptions` Klasse. Sie können beispielsweise das Dokumentspeicherformat, Kodierungsoptionen usw. festlegen.