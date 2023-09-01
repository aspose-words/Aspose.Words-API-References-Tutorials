---
title: Fügen Sie Bidi-Marken in ein Word-Dokument ein
linktitle: Fügen Sie Bidi-Marken in ein Word-Dokument ein
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Bidi-Markierungen zu einem Word-Dokument hinzufügen und professionelle mehrsprachige Dokumente erstellen.
type: docs
weight: 10
url: /de/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, einem Dokument Bidi-Markierungen (bidirektional) hinzuzufügen. In diesem Leitfaden führen wir Sie durch die Verwendung des C#-Quellcodes von Aspose.Words für .NET, um einem Dokument Bidi-Markierungen hinzuzufügen.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Textverarbeitung mit Word-Dokumenten einfach und effizient macht. Es bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten, einschließlich des Hinzufügens von Bidi-Marken.

## Erstellen des Dokuments und Hinzufügen von Inhalten

Der erste Schritt besteht darin, ein neues Dokument zu erstellen und ihm Inhalte hinzuzufügen. Verwenden Sie die Document-Klasse, um eine neue Dokumentinstanz zu erstellen. Verwenden Sie dann die DocumentBuilder-Klasse, um dem Dokument Text hinzuzufügen. Hier ist ein Beispiel :

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

Sobald der Inhalt hinzugefügt wurde, können wir dem Dokument nun Bidi-Markierungen hinzufügen. Dazu verwenden wir die Klasse TxtSaveOptions und setzen die Eigenschaft AddBidiMarks auf true. Hier ist wie:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

In diesem Beispiel erstellen wir eine Instanz von TxtSaveOptions und setzen die AddBidiMarks-Eigenschaft auf true. Als Nächstes verwenden wir die Save-Methode der Document-Klasse, um das Dokument mit Bidi-Markierungen zu speichern.

### Beispielquellcode für die Funktion „Bidi-Markierungen hinzufügen“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie das Dokument und fügen Sie Inhalte hinzu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Fügen Sie Bidi-Markierungen hinzu
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie mit Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes Bidi-Markierungen zu einem Word-Dokument hinzufügen. Indem Sie die bereitgestellten Schritte befolgen, können Sie ganz einfach Bidi-Markierungen zu Ihren Word-Dokumenten in Ihrer C#-Anwendung hinzufügen. Aspose.Words bietet enorme Flexibilität und Leistung für die Textverarbeitung mit Textformatierung und Sprachverwaltung, sodass Sie mehrsprachige Dokumente professionell erstellen können.

### Häufig gestellte Fragen

#### F: Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Es bietet viele Funktionen für die Textverarbeitung mit Word-Dokumenten, einschließlich des Hinzufügens von Bidi-Markierungen (bidirektional).

#### F: Welche Funktionen bietet Aspose.Words für .NET?
Aspose.Words für .NET bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten. Zu diesen Funktionen gehören das Erstellen von Dokumenten, das Hinzufügen von Inhalten, das Formatieren von Text, das Verwalten von Tabellen, das Zusammenführen und Teilen von Dokumenten, das Konvertieren von Dokumenten und mehr.

#### F: Wie kann ich mit Aspose.Words für .NET Bidi-Markierungen zu einem Word-Dokument hinzufügen?
Sie können einem Word-Dokument Bidi-Marken hinzufügen, indem Sie die folgenden Schritte ausführen:

 Erstellen Sie ein neues Dokument mit`Document` Klasse.

 Benutzen Sie die`DocumentBuilder` Klasse, um dem Dokument Inhalte hinzuzufügen.

 Sobald Sie den Inhalt hinzugefügt haben, verwenden Sie die`TxtSaveOptions` Klasse und legen Sie die fest`AddBidiMarks` Eigentum zu`true`.

 Speichern Sie das Dokument mit Bidi-Markierungen mithilfe von`Save` Methode der`Document` Klasse.

#### F: Unterstützt Aspose.Words mehrere Sprachen zum Hinzufügen von Bidi-Markierungen?
Ja, Aspose.Words unterstützt mehrere Sprachen zum Hinzufügen von Bidi-Markierungen. Mit Aspose.Words für .NET können Sie Text in verschiedenen Sprachen, beispielsweise Englisch, Hebräisch und Arabisch, Bidi-Markierungen hinzufügen.

#### F: Gibt es zusätzliche Optionen zum Speichern des Dokuments mit Bidi-Markierungen?
 Ja, Sie können beim Speichern des Dokuments mit Bidi-Markierungen andere Optionen angeben`TxtSaveOptions` Klasse. Sie können beispielsweise das Speicherformat des Dokuments, Kodierungsoptionen usw. festlegen.