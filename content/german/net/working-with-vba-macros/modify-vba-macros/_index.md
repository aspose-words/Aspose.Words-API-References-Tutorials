---
title: VBA-Makros eines Word-Dokuments ändern
linktitle: VBA-Makros eines Word-Dokuments ändern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in diesem Tutorial, wie Sie VBA-Makros eines Word-Dokuments mit Aspose.Words für .NET bearbeiten.
type: docs
weight: 10
url: /de/net/working-with-vba-macros/modify-vba-macros/
---
In diesem Tutorial erklären wir, wie Sie VBA-Makros eines Word-Dokuments mithilfe der Aspose.Words-Bibliothek für .NET ändern. Durch das Bearbeiten von VBA-Makros können Sie vorhandenen VBA-Code in Ihrem Word-Dokument aktualisieren. Wir führen Sie Schritt für Schritt durch, damit Sie den Code verstehen und in Ihrem .NET-Projekt implementieren können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit VBA-Makros, die Sie ändern möchten

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments setzen. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument mit den VBA-Makros
Als Nächstes laden wir das Word-Dokument mit den VBA-Makros, die wir ändern möchten.

```csharp
// Laden Sie das Dokument mit den VBA-Makros
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Schritt 3: Ändern des Makro-Quellcodes
 Wir werden nun den Quellcode des ersten Makros des VBA-Projekts ändern. Ersetzen Sie das`newSourceCode` Variable mit dem neuen Quellcode, den Sie verwenden möchten.

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

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man VBA-Makros in einem Word-Dokument mit Aspose.Words für .NET bearbeitet. Durch das Bearbeiten von VBA-Makros können Sie vorhandenen VBA-Code in Ihrem Dokument aktualisieren, um Änderungen oder Verbesserungen vorzunehmen. Nutzen Sie diese Funktion, um Ihre Word-Dokumente weiter anzupassen und zu automatisieren.

### Häufig gestellte Fragen

#### F: Was ist ein VBA-Makro in einem Word-Dokument?

A: Ein VBA-Makro in einem Word-Dokument ist ein Code, der ausgeführt werden kann, um bestimmte Aktionen im Dokument auszuführen. Mit VBA-Makros können Sie Aufgaben automatisieren, benutzerdefinierte Funktionen hinzufügen und mit Dokumentinhalten interagieren.

#### F: Was sind die Voraussetzungen für die Bearbeitung von VBA-Makros in einem Word-Dokument?

A: Bevor Sie VBA-Makros in einem Word-Dokument bearbeiten können, müssen Sie über Kenntnisse der Programmiersprache C# verfügen. Sie müssen außerdem die Bibliothek Aspose.Words für .NET in Ihrem Projekt installieren. Außerdem benötigen Sie ein Word-Dokument, das die VBA-Makros enthält, die Sie ändern möchten.

#### F: Wie lege ich das Dokumentverzeichnis im Code fest?

 A: Im bereitgestellten Code müssen Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den entsprechenden Pfad zum Verzeichnis, in dem sich Ihr Word-Dokument mit den VBA-Makros befindet.

#### F: Wie gebe ich den neuen Quellcode des zu ändernden Makros an?

 A: Um den neuen Quellcode des zu ändernden Makros anzugeben, können Sie den`SourceCode` Eigentum des entsprechenden`VbaModule` Objekt, indem Sie ihm eine Zeichenfolge zuweisen, die den neuen VBA-Code enthält.

#### F: Kann ich mehrere VBA-Makros gleichzeitig in einem Word-Dokument bearbeiten?

 A: Ja, Sie können mehrere VBA-Makros in einem Word-Dokument ändern, indem Sie eine Schleife verwenden oder direkt auf die entsprechenden`VbaModule` Objekte im`Modules` Sammlung der`VbaProject` Objekt. Dadurch können Sie mehrere VBA-Makros gleichzeitig in einem einzigen Vorgang aktualisieren.