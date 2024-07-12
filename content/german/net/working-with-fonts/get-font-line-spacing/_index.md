---
title: Zeilenabstand für Schriftart abrufen
linktitle: Zeilenabstand für Schriftart abrufen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET den Schriftzeilenabstand in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/working-with-fonts/get-font-line-spacing/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie den Zeilenabstand der Schrift in einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET festlegen. Der Zeilenabstand der Schrift definiert den vertikalen Abstand zwischen Textzeilen. Wir führen Sie Schritt für Schritt durch den Code und helfen Ihnen, ihn in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Neues Dokument und Dokumentgenerator erstellen
 Zunächst erstellen wir ein neues Dokument durch die Instanziierung des`Document` Klasse und einen Dokument-Builder durch Instanziierung der`DocumentBuilder` Klasse.

```csharp
// Neues Dokument erstellen
Document doc = new Document();

//Erstellen Sie einen Dokumentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Konfigurieren Sie die Schriftart
 Als nächstes konfigurieren wir die Schriftart, indem wir die`Name` Eigenschaft des Dokumentgenerators.

```csharp
// Konfigurieren der Schriftart
builder.Font.Name = "Calibri";
```

## Schritt 3: Text zum Dokument hinzufügen
Wir werden jetzt den Dokumentgenerator verwenden, um dem Dokument formatierten Text hinzuzufügen.

```csharp
// Hinzufügen von Text zum Dokument
builder. Writen("qText");
```

## Schritt 4: Zeilenabstand der Schrift ermitteln
 Nun greifen wir auf die`Font` Objekt des ersten Absatzes des Dokuments und ruft den Wert des`LineSpacing` Eigentum.

```csharp
// Den Zeilenabstand der Schriftart ermitteln
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Beispielquellcode zum Abrufen des Zeilenabstands von Schriftarten mit Aspose.Words für .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET den Zeilenabstand der Schrift in einem Word-Dokument erhält. Der Zeilenabstand der Schrift ist wichtig, um den vertikalen Abstand zwischen Textzeilen zu steuern. Sie können diese Funktion gerne verwenden, um das Erscheinungsbild Ihres Textes in Ihren Dokumenten anzupassen.

### Häufig gestellte Fragen

#### F: Wie kann ich den Zeilenabstand eines bestimmten Textes in einem Word-Dokument ändern?

A: Mit Aspose.Words können Sie den Zeilenabstand von bestimmten Texten in einem Word-Dokument ganz einfach ändern. Verwenden Sie die API, um den gewünschten Text auszuwählen und den Zeilenabstand durch Angabe des entsprechenden Werts anzupassen.

#### F: Ist es möglich, in einem Word-Dokument einen exakten Zeilenabstand festzulegen?

A: Ja, Aspose.Words ermöglicht es Ihnen, einen genauen Zeilenabstand in einem Word-Dokument festzulegen. Sie können mithilfe der API einen genauen Wert für den Zeilenabstand angeben.

#### F: Wie kann ich den Zeilenabstand für das gesamte Word-Dokument anpassen?

A: Mit Aspose.Words können Sie den Zeilenabstand für das gesamte Word-Dokument ganz einfach anpassen. Verwenden Sie die von der API bereitgestellten Methoden, um den gewünschten Zeilenabstand für das gesamte Dokument festzulegen.

#### F: Unterstützt Aspose.Words mehrere Zeilenabstände?

A: Ja, Aspose.Words unterstützt mehrere Zeilenabstände in Word-Dokumenten. Sie können für die Zeilen Ihres Textes mehrere Abstände festlegen, z. B. das 1,5-fache oder das 2-fache des normalen Abstands.

#### F: Wie kann ich beim Anpassen des Zeilenabstands Probleme mit Zeilenüberlappungen vermeiden?

A: Um Probleme mit Zeilenüberlappungen beim Anpassen des Zeilenabstands zu vermeiden, achten Sie darauf, geeignete Abstandswerte zu wählen. Testen Sie auch die endgültige Darstellung Ihres Dokuments, um sicherzustellen, dass der Text lesbar und gut formatiert bleibt.