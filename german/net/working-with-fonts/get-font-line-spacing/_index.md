---
title: Holen Sie sich den Schriftzeilenabstand
linktitle: Holen Sie sich den Schriftzeilenabstand
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET den Schriftzeilenabstand in einem Word-Dokument ermitteln.
type: docs
weight: 10
url: /de/net/working-with-fonts/get-font-line-spacing/
---
In diesem Tutorial erklären wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET den Zeilenabstand der Schriftarten in einem Word-Dokument ermitteln. Der Zeilenabstand der Schriftart definiert den vertikalen Abstand zwischen Textzeilen. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Erstellen Sie ein neues Dokument und einen Dokumentengenerator
 Zuerst erstellen wir ein neues Dokument, indem wir es instanziieren`Document` Klasse und einen Dokumentenersteller durch Instanziieren der`DocumentBuilder` Klasse.

```csharp
// Erstellen Sie ein neues Dokument
Document doc = new Document();

//Erstellen Sie einen Dokumentengenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Konfigurieren Sie die Schriftart
 Als nächstes konfigurieren wir die Schriftart, indem wir die festlegen`Name` Eigenschaft des Dokumentgenerators.

```csharp
// Konfigurieren Sie die Schriftart
builder.Font.Name = "Calibri";
```

## Schritt 3: Fügen Sie dem Dokument Text hinzu
Wir werden nun den Dokumentgenerator verwenden, um dem Dokument formatierten Text hinzuzufügen.

```csharp
// Fügen Sie dem Dokument Text hinzu
builder. Writen("qText");
```

## Schritt 4: Ermitteln Sie den Zeilenabstand der Schriftarten
 Jetzt greifen wir auf die zu`Font` Objekt des ersten Absatzes des Dokuments und rufen Sie den Wert ab`LineSpacing` Eigentum.

```csharp
// Ermitteln Sie den Zeilenabstand der Schriftart
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Beispielquellcode für „Get Font Line Spacing“ mit Aspose.Words für .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET den Schriftzeilenabstand in einem Word-Dokument ermittelt. Der Zeilenabstand der Schriftart ist wichtig, um den vertikalen Abstand zwischen Textzeilen zu steuern. Nutzen Sie diese Funktion gerne, um das Erscheinungsbild Ihres Textes in Ihren Dokumenten anzupassen.

### FAQs

#### F: Wie kann ich den Zeilenabstand eines bestimmten Texts in einem Word-Dokument ändern?

A: Mit Aspose.Words können Sie den Zeilenabstand von bestimmtem Text in einem Word-Dokument ganz einfach ändern. Verwenden Sie die API, um den gewünschten Text auszuwählen und den Abstand zwischen den Zeilen anzupassen, indem Sie den entsprechenden Wert angeben.

#### F: Ist es möglich, in einem Word-Dokument einen genauen Zeilenabstand festzulegen?

A: Ja, mit Aspose.Words können Sie in einem Word-Dokument genaue Abstände zwischen Zeilen festlegen. Mithilfe der API können Sie einen genauen Wert für den Zeilenabstand angeben.

#### F: Wie kann ich den Zeilenabstand für das gesamte Word-Dokument anpassen?

A: Mit Aspose.Words können Sie den Zeilenabstand für das gesamte Word-Dokument ganz einfach anpassen. Verwenden Sie die von der API bereitgestellten Methoden, um den gewünschten Zeilenabstand für das gesamte Dokument festzulegen.

#### F: Unterstützt Aspose.Words mehrere Zeilenabstände?

A: Ja, Aspose.Words unterstützt mehrere Zeilenabstände in Word-Dokumenten. Sie können für die Zeilen Ihres Textes mehrere Abstände festlegen, z. B. das 1,5-fache oder das 2-fache des normalen Abstands.

#### F: Wie kann ich Probleme mit Zeilenüberlappungen beim Anpassen des Zeilenabstands vermeiden?

A: Um Probleme mit Zeilenüberlappungen beim Anpassen des Zeilenabstands zu vermeiden, achten Sie darauf, geeignete Abstandswerte zu wählen. Testen Sie außerdem die endgültige Darstellung Ihres Dokuments, um sicherzustellen, dass der Text lesbar und gut formatiert bleibt.