---
title: Ändern Sie VBA-Makros
linktitle: Ändern Sie VBA-Makros
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie VBA-Makros eines Word-Dokuments mit Aspose.Words für .NET bearbeiten.
type: docs
weight: 10
url: /de/net/working-with-vba-macros/modify-vba-macros/
---
In diesem Tutorial erklären wir, wie Sie VBA-Makros eines Word-Dokuments mithilfe der Aspose.Words-Bibliothek für .NET ändern. Durch das Bearbeiten von VBA-Makros können Sie vorhandenen VBA-Code in Ihrem Word-Dokument aktualisieren. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit VBA-Makros, die Sie ändern möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument mit den VBA-Makros
Als nächstes laden wir das Word-Dokument mit den VBA-Makros, die wir ändern möchten.

```csharp
// Laden Sie das Dokument mit den VBA-Makros
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Schritt 3: Ändern Sie den Makro-Quellcode
 Wir werden nun den Quellcode des ersten Makros des VBA-Projekts ändern. Ersetze das`newSourceCode` Variable mit dem neuen Quellcode, den Sie verwenden möchten.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Schritt 4: Speichern Sie das geänderte Dokument
Abschließend speichern wir das geänderte Dokument mit den aktualisierten VBA-Makros in einer Datei.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Beispielquellcode zum Ändern von VBA-Makros mit Aspose.Words für .NET
 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man VBA-Makros in einem Word-Dokument mit Aspose.Words für .NET bearbeitet. Durch das Bearbeiten von VBA-Makros können Sie vorhandenen VBA-Code in Ihrem Dokument aktualisieren, um Änderungen oder Verbesserungen vorzunehmen. Nutzen Sie diese Funktion gerne, um Ihre Word-Dokumente weiter anzupassen und zu automatisieren.