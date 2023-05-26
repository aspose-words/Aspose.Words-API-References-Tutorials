---
title: Vba-Projekt klonen
linktitle: Vba-Projekt klonen
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET ein VBA-Projekt aus einem Word-Dokument klonen.
type: docs
weight: 10
url: /de/net/working-with-vba-macros/clone-vba-project/
---

In diesem Tutorial erklären wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein VBA-Projekt aus einem Word-Dokument mit Makros klonen. Durch das Klonen eines VBA-Projekts können Sie den gesamten VBA-Code von einem Quelldokument in ein anderes kopieren. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument, das ein VBA-Projekt enthält, das Sie klonen möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Quelldokument laden
Als Nächstes laden wir das Word-Quelldokument, das das VBA-Projekt enthält, das wir klonen möchten.

```csharp
// Laden Sie das Quelldokument
Document doc = new Document(dataDir + "VBA project.docm");
```

## Schritt 3: Erstellen Sie ein neues Dokument mit dem geklonten VBA-Projekt
Wir erstellen ein neues Dokument mit einem leeren VBA-Projekt und klonen das VBA-Projekt aus dem Quelldokument.

```csharp
// Erstellen Sie ein neues Dokument mit einem leeren VBA-Projekt
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Schritt 4: Speichern Sie das Zieldokument
Abschließend speichern wir das Zieldokument zusammen mit dem geklonten VBA-Projekt in einer Datei.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Beispielquellcode für das Klonen eines VBA-Projekts mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET ein VBA-Projekt aus einem Word-Dokument mit Makros klont. Durch das Klonen von VBA-Projekten können Sie den gesamten VBA-Code von einem Quelldokument in ein anderes kopieren. Nutzen Sie diese Funktion gerne zum Organisieren und Verwalten Ihrer Makros in verschiedenen Dokumenten.
