---
title: Revisionen in Sprechblasen anzeigen
linktitle: Revisionen in Sprechblasen anzeigen
second_title: Aspose.Words für .NET API-Referenz
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



