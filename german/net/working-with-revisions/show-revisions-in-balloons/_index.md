---
title: Revisionen in Sprechblasen anzeigen
linktitle: Revisionen in Sprechblasen anzeigen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Zeigen Sie Revisionen in Sprechblasen mit Aspose.Words für .NET an.
type: docs
weight: 10
url: /de/net/working-with-revisions/show-revisions-in-balloons/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Revisionen in Sprechblasen in einem Word-Dokument anzeigen. Wir stellen Ihnen den vollständigen Quellcode zur Verfügung und zeigen Ihnen, wie Sie die Markdown-Ausgabe formatieren.

## Schritt 1: Laden des Dokuments

Der erste Schritt besteht darin, das Dokument mit den Überarbeitungen hochzuladen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Schritt 2: Konfigurieren Sie die Optionen zum Anzeigen von Rezensionen

Wir werden die Anzeigeoptionen konfigurieren, um Revisionen in Sprechblasen sichtbar zu machen.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Schritt 3: Speichern Sie das Dokument im PDF-Format

Abschließend speichern wir das Dokument als PDF, wobei die Revisionen in Sprechblasen angezeigt werden.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown-Ausgabeformate

Die Ausgabe kann zur Verbesserung der Lesbarkeit im Markdown formatiert werden. Zum Beispiel :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Beispielquellcode für „Revisionen in Sprechblasen anzeigen“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode zum Anzeigen von Revisionen in Sprechblasen in einem Dokument mit Aspose.Words für .NET:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Rendert, fügt Revisionen inline ein, löscht und formatiert Revisionen in Sprechblasen.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Rendert Revisionsbalken auf der rechten Seite einer Seite.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für .NET Revisionen in Sprechblasen in einem Word-Dokument anzeigt. Durch die Verwendung der entsprechenden Anzeigeoptionen konnten wir die Revisionen in Blasen mit Revisionsbalken auf der rechten Seite sichtbar machen. Aspose.Words für .NET bietet viele leistungsstarke Funktionen zum Bearbeiten von Word-Dokumenten, einschließlich Revisionsverwaltung. Jetzt können Sie dieses Wissen nutzen, um mit Aspose.Words für .NET Revisionen in Sprechblasen in Ihren eigenen Word-Dokumenten anzuzeigen.


### FAQs

#### F: Wie lade ich ein Dokument in Aspose.Words für .NET hoch?

 A: Benutzen Sie die`Document` Klasse von Aspose.Words für .NET zum Laden eines Dokuments aus einer Datei. Sie können den vollständigen Dokumentpfad angeben.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Wie werden Revisionen in Sprechblasen mit Aspose.Words für .NET angezeigt?

 A: Benutzen Sie die`ShowInBalloons` Eigentum der`RevisionOptions` Objekt zum Konfigurieren der Anzeige von Revisionen in Sprechblasen. Sie können diese Eigenschaft aktivieren`ShowInBalloons.FormatAndDelete` um Revisionen in Sprechblasen mit Lösch- und Formatierungsrevisionen anzuzeigen.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### F: Wie speichere ich ein Dokument im PDF-Format mit Aspose.Words für .NET?

 A: Benutzen Sie die`Save` Methode der`Document` Objekt, um das Dokument im PDF-Format zu speichern. Sie müssen den vollständigen Zielpfad mit der Erweiterung „.pdf“ angeben.

```csharp
doc.Save("path/to/destination/document.pdf");
```