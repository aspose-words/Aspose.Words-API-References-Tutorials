---
title: Schriftartformatierung
linktitle: Schriftartformatierung
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie die Schriftart in einem Word-Dokument mit Aspose.Words für .NET formatieren.
type: docs
weight: 10
url: /de/net/working-with-fonts/font-formatting/
---

In diesem Tutorial führen wir Sie durch die Schriftartformatierung in einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET. Mit der Schriftformatierung können Sie das Erscheinungsbild von Text anpassen, einschließlich Größe, Fettdruck, Farbe, Schriftart, Unterstreichung und mehr. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen Sie ein neues Dokument und einen Dokumentengenerator
 Als nächstes erstellen wir ein neues Dokument, indem wir es instanziieren`Document` Klasse und einen Dokumentenersteller durch Instanziieren der`DocumentBuilder` Klasse.

```csharp
// Erstellen Sie ein neues Dokument
Document doc = new Document();

// Erstellen Sie einen Dokumentengenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Konfigurieren Sie die Schriftartformatierung
 Jetzt greifen wir auf die zu`Font` Objekt des Dokumentgenerators und konfigurieren Sie die Schriftartformatierungseigenschaften wie Größe, Fett, Farbe, Schriftart, Unterstreichung usw.

```csharp
// Greifen Sie auf die Schriftart zu
Font font = builder.Font;

// Konfigurieren Sie die Schriftartformatierung
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## Schritt 4: Fügen Sie dem Dokument Text hinzu
Als Nächstes verwenden wir den Document Builder, um dem Dokument formatierten Text hinzuzufügen.

```csharp
// Fügen Sie dem Dokument Text hinzu
builder.Write("Example text.");
```

## Schritt 5: Speichern Sie das Dokument
Abschließend speichern wir das Dokument mit der Schriftartformatierung.

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### Beispielquellcode für die Schriftartformatierung mit Aspose.Words für .NET 
```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET die Schriftartformatierung in einem Word-Dokument vornimmt. Durch die Schriftartformatierung können Sie das Erscheinungsbild von Text in Ihren Dokumenten anpassen. Nutzen Sie diese Funktion gerne, um ansprechende und professionelle Dokumente zu erstellen.