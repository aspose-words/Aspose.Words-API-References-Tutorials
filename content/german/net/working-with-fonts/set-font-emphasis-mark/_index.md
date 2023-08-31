---
title: Legen Sie die Markierung für die Schriftbetonung fest
linktitle: Legen Sie die Markierung für die Schriftbetonung fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET den Schriftbetonungsstil in einem Word-Dokument festlegen.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-emphasis-mark/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET den Schriftbetonungsstil in einem Word-Dokument festlegen. Mit der Schrifthervorhebung werden bestimmte Wörter oder Phrasen im Text hervorgehoben.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Legen Sie zunächst den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments fest. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Erstellen Sie das Dokument und passen Sie es an
 Erstellen Sie eine Instanz von`Document` Klasse und eine zugehörige`DocumentBuilder` um den Dokumentinhalt zu erstellen. Benutzen Sie die`Font.EmphasisMark` Eigenschaft, auf die der Schrifthervorhebungsstil festgelegt werden soll`EmphasisMark.UnderSolidCircle` . Dann nutzen Sie die`Write` Und`Writeln` Methoden der`DocumentBuilder` um Text mit der angegebenen Schriftarthervorhebung hinzuzufügen.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Schritt 3: Speichern Sie das Dokument
 Speichern Sie das Dokument mit`Save` Methode der`Document` mit dem entsprechenden Pfad und Dateinamen.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Beispielquellcode für Set Font Emphasis Mark mit Aspose.Words für .NET 

```csharp
//Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Words für .NET den Schriftbetonungsstil in einem Word-Dokument festlegen. Experimentieren Sie mit verschiedenen Hervorhebungsstilen und nutzen Sie diese Funktion, um Wörter oder Phrasen in Ihren Dokumenten hervorzuheben.

### FAQs

#### F: Wie kann ich mit Aspose.Words einer bestimmten Schriftart in einem Word-Dokument Akzentzeichen hinzufügen?

A: Um mit Aspose.Words Akzentzeichen zu einer bestimmten Schriftart in einem Word-Dokument hinzuzufügen, können Sie die API verwenden, um zur gewünschten Schriftart zu navigieren und die entsprechenden Akzentzeichen anzuwenden. Dadurch werden dem Text Akzentzeichen mit der ausgewählten Schriftart hinzugefügt.

#### F: Ist es möglich, den Stil von Akzentzeichen in einem Word-Dokument mit Aspose.Words zu ändern?

A: Ja, mit Aspose.Words können Sie den Stil von Akzentzeichen in einem Word-Dokument ändern. Mit der API können Sie Stileigenschaften wie Farbe, Größe, Linientyp usw. anpassen, um das Erscheinungsbild von Akzentzeichen anzupassen.

#### F: Wie kann ich mit Aspose.Words alle Akzentzeichen aus einem Word-Dokument entfernen?

A: Um alle Akzentzeichen aus einem Word-Dokument mit Aspose.Words zu entfernen, können Sie die API verwenden, um das Dokument zu durchsuchen, vorhandene Akzentzeichen zu erkennen und sie mit den entsprechenden Methoden zu entfernen. Dadurch werden alle Hervorhebungszeichen aus dem Dokument entfernt.

#### F: Kann ich einem bestimmten Textteil in einem Word-Dokument Akzentzeichen hinzufügen?

A: Ja, Sie können mit Aspose.Words einem bestimmten Textteil in einem Word-Dokument Akzentzeichen hinzufügen. Mithilfe der API können Sie den gewünschten Textbereich auswählen und diesem Teil des Textes entsprechende Hervorhebungszeichen hinzufügen.

#### F: Können die Akzentzeichen an meine Bedürfnisse angepasst werden?

A: Ja, Akzentzeichen können mit Aspose.Words an Ihre Bedürfnisse angepasst werden. Sie können die Stileigenschaften von Akzentzeichen wie Farbe, Größe, Linientyp usw. an Ihre Formatierungsvorlieben anpassen.