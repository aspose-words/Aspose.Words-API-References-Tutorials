---
title: Beim Rendern die Standardschriftart angeben
linktitle: Beim Rendern die Standardschriftart angeben
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Festlegen der Standardschriftart beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/specify-default-font-when-rendering/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen der Standardschriftart beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären den mitgelieferten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie eine Standardschriftart festlegen, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden soll.

## Schritt 1: Dokumentverzeichnis festlegen
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes, gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das zu rendernde Dokument
 Als nächstes müssen Sie das zu rendernde Dokument laden, indem Sie`Document` Klasse. Achten Sie darauf, den richtigen Dokumentpfad anzugeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Standardschriftart festlegen
 Jetzt können Sie die Standardschriftart für das Rendern festlegen, indem Sie eine Instanz der`FontSettings` Klasse und Festlegen der`DefaultFontName` Eigentum der`DefaultFontSubstitution` Einspruch gegen die`DefaultFontSubstitution` Objekt`SubstitutionSettings` von`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Schritt 4: Speichern des gerenderten Dokuments
 Abschließend können Sie das gerenderte Dokument in einer Datei speichern mit dem`Save()` Methode der`Document` Klasse. Achten Sie darauf, den richtigen Pfad und Dateinamen anzugeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Beispielquellcode für „Standardschriftart beim Rendern angeben“ mit Aspose.Words für .NET 

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Wenn die hier definierte Standardschriftart beim Rendern nicht gefunden werden kann, dann
// Stattdessen wird die ähnlichste Schriftart auf dem Computer verwendet.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man die Standardschriftart beim Rendern eines Dokuments mit Aspose.Words für .NET angibt. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach eine Standardschriftart festlegen, die beim Rendern Ihrer Dokumente verwendet werden soll. Aspose.Words bietet eine leistungsstarke und flexible API für die Textverarbeitung mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie das Rendern Ihrer Dokumente steuern und an Ihre spezifischen Anforderungen anpassen.

### Häufig gestellte Fragen

#### F: Wie kann ich beim Konvertieren in PDF in Aspose.Words eine Standardschriftart angeben?

 A: Um eine Standardschriftart bei der Konvertierung in PDF in Aspose.Words festzulegen, können Sie die`PdfOptions` Klasse und legen Sie die`DefaultFontName`-Eigenschaft auf den Namen der gewünschten Schriftart.

#### F: Was passiert, wenn die Standardschriftart bei der Konvertierung in PDF nicht verfügbar ist?

A: Wenn die angegebene Standardschriftart beim Konvertieren in PDF nicht verfügbar ist, verwendet Aspose.Words eine Ersatzschriftart, um den Text im konvertierten Dokument anzuzeigen. Dies kann zu einem leichten Unterschied im Erscheinungsbild gegenüber der Originalschriftart führen.

#### F: Kann ich eine Standardschriftart für andere Ausgabeformate wie DOCX oder HTML angeben?

A: Ja, Sie können eine Standardschriftart für andere Ausgabeformate wie DOCX oder HTML festlegen, indem Sie die entsprechenden Konvertierungsoptionen verwenden und die entsprechende Eigenschaft für jedes Format festlegen.

#### F: Wie kann ich die in Aspose.Words angegebene Standardschriftart überprüfen?

 A: Um die in Aspose.Words angegebene Standardschriftart zu überprüfen, können Sie den`DefaultFontName` Eigentum der`PdfOptions` Klasse und rufen Sie den Namen der konfigurierten Schriftart ab.

#### F: Ist es möglich, für jeden Abschnitt des Dokuments eine andere Standardschriftart festzulegen?

A: Ja, es ist möglich, für jeden Abschnitt des Dokuments eine andere Standardschriftart festzulegen, indem Sie die für jeden Abschnitt spezifischen Formatierungsoptionen verwenden. Dies würde jedoch eine erweiterte Bearbeitung des Dokuments mithilfe der Aspose.Words-Funktionen erfordern.