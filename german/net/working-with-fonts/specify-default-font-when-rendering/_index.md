---
title: Geben Sie beim Rendern die Standardschriftart an
linktitle: Geben Sie beim Rendern die Standardschriftart an
second_title: Aspose.Words für .NET API-Referenz
description: Schritt-für-Schritt-Anleitung zum Festlegen der Standardschriftart beim Rendern eines Dokuments mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/specify-default-font-when-rendering/
---

In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess zum Festlegen der Standardschriftart beim Rendern eines Dokuments mit Aspose.Words für .NET. Wir erklären Ihnen den gebündelten C#-Quellcode und stellen Ihnen eine umfassende Anleitung zur Verfügung, die Ihnen hilft, diese Funktion zu verstehen und in Ihren eigenen Projekten zu implementieren. Am Ende dieses Tutorials wissen Sie, wie Sie eine Standardschriftart angeben, die beim Rendern Ihrer Dokumente mit Aspose.Words für .NET verwendet werden soll.

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
Zuerst müssen Sie den Pfad zu Ihrem Dokumentenverzeichnis festlegen. Dies ist der Ort, an dem Sie Ihr bearbeitetes gerendertes Dokument speichern möchten. Ersetzen Sie „IHR DOKUMENTENVERZEICHNIS“ durch den entsprechenden Pfad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das zu rendernde Dokument
 Als Nächstes müssen Sie das zu rendernde Dokument mit laden`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Schritt 3: Standardschriftart festlegen
 Jetzt können Sie die beim Rendern zu verwendende Standardschriftart angeben, indem Sie eine Instanz davon erstellen`FontSettings` Klasse und Einstellung der`DefaultFontName` Eigentum der`DefaultFontSubstitution` Einspruch gegen die`DefaultFontSubstitution` Objekt`SubstitutionSettings` von`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Schritt 4: Speichern Sie das gerenderte Dokument
 Schließlich können Sie das gerenderte Dokument mithilfe von in einer Datei speichern`Save()` Methode der`Document` Klasse. Stellen Sie sicher, dass Sie den richtigen Pfad und Dateinamen angeben.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Beispielquellcode für „Standardschriftart beim Rendern angeben“ mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Wenn die hier definierte Standardschriftart beim Rendern nicht gefunden werden kann, dann
	// Stattdessen wird die nächstgelegene Schriftart auf dem Gerät verwendet.
	fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man beim Rendern eines Dokuments mit Aspose.Words für .NET die Standardschriftart angibt. Wenn Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie ganz einfach eine Standardschriftart festlegen, die beim Rendern Ihrer Dokumente verwendet werden soll. Aspose.Words bietet eine leistungsstarke und flexible API für die Arbeit mit Schriftarten in Ihren Dokumenten. Mit diesem Wissen können Sie die Darstellung Ihrer Dokumente steuern und an Ihre spezifischen Anforderungen anpassen.