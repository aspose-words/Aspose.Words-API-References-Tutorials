---
title: Überprüfen Sie den DrawingML-Texteffekt
linktitle: Überprüfen Sie den DrawingML-Texteffekt
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie DrawingML-Texteffekte in einem Word-Dokument mit Aspose.Words für .NET überprüfen.
type: docs
weight: 10
url: /de/net/working-with-fonts/check-drawingml-text-effect/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie DrawingML-Texteffekte in einem Word-Dokument mithilfe der Aspose.Words-Bibliothek für .NET überprüfen. Durch die Überprüfung von DrawingML-Texteffekten können Sie feststellen, ob ein bestimmter Effekt auf einen Teil des Textes angewendet wird. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument, das DrawingML-Texteffekte enthält

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und überprüfen Sie die Texteffekte
Als Nächstes laden wir das Word-Dokument und greifen auf die Sammlung von Abläufen (Zeichenfolgen) im ersten Absatz des Hauptteils des Dokuments zu. Als Nächstes prüfen wir, ob bestimmte DrawingML-Texteffekte auf die Schriftart des ersten Durchlaufs angewendet werden.

```csharp
//Laden Sie das Dokument
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Überprüfen Sie die Texteffekte von DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Beispielquellcode für Check DMLText Effect mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Bei einem Lauf können mehrere DML-Texteffekte angewendet werden.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man DrawingML-Texteffekte in einem Word-Dokument mit Aspose.Words für .NET überprüft. Durch die Überprüfung von DrawingML-Texteffekten können Sie Textteile identifizieren, auf die bestimmte Effekte angewendet werden. Nutzen Sie diese Funktion gerne zum Bearbeiten und Analysieren von Texteffekten in Ihren Word-Dokumenten.
