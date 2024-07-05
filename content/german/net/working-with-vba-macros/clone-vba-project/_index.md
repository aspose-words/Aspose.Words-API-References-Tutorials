---
title: VBA-Projekt aus einem Word-Dokument klonen
linktitle: VBA-Projekt aus einem Word-Dokument klonen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in diesem Tutorial, wie Sie mit Aspose.Words für .NET ein VBA-Projekt aus einem Word-Dokument klonen.
type: docs
weight: 10
url: /de/net/working-with-vba-macros/clone-vba-project/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein VBA-Projekt mit Makros aus einem Word-Dokument klonen. Durch das Klonen eines VBA-Projekts können Sie den gesamten VBA-Code von einem Quelldokument in ein anderes Dokument kopieren. Wir führen Sie Schritt für Schritt durch, damit Sie den Code in Ihrem .NET-Projekt verstehen und implementieren können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit einem VBA-Projekt, das Sie klonen möchten

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments setzen. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Quelldokument laden
Als Nächstes laden wir das Quell-Word-Dokument, das das VBA-Projekt enthält, das wir klonen möchten.

```csharp
// Laden des Quelldokuments
Document doc = new Document(dataDir + "VBA project.docm");
```

## Schritt 3: Erstellen Sie ein neues Dokument mit dem geklonten VBA-Projekt
Wir erstellen ein neues Dokument mit einem leeren VBA-Projekt und klonen das VBA-Projekt aus dem Quelldokument.

```csharp
// Erstellen Sie ein neues Dokument mit einem leeren VBA-Projekt
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Schritt 4: Zieldokument speichern
Abschließend speichern wir das Zieldokument zusammen mit dem geklonten VBA-Projekt in einer Datei.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Beispiel-Quellcode zum Klonen eines VBA-Projekts mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET ein VBA-Projekt aus einem Word-Dokument mit Makros klont. Durch das Klonen von VBA-Projekten können Sie den gesamten VBA-Code von einem Quelldokument in ein anderes Dokument kopieren. Nutzen Sie diese Funktion, um Ihre Makros in verschiedenen Dokumenten zu organisieren und zu verwalten.

### Häufig gestellte Fragen

#### F: Was ist das Duplizieren eines VBA-Projekts?

A: Beim Duplizieren eines VBA-Projekts wird der gesamte VBA-Code aus einem Word-Quelldokument in ein anderes Dokument kopiert. Auf diese Weise können Sie VBA-Code in verschiedenen Kontexten wiederverwenden oder mit anderen Dokumenten teilen.

#### F: Was sind die Voraussetzungen für das Klonen eines VBA-Projekts aus einem Word-Dokument?

A: Bevor Sie ein VBA-Projekt aus einem Word-Dokument klonen können, müssen Sie über Kenntnisse der Programmiersprache C# verfügen. Sie müssen außerdem die Bibliothek Aspose.Words für .NET in Ihrem Projekt installieren. Außerdem benötigen Sie ein Word-Dokument, das ein VBA-Projekt enthält, das Sie klonen möchten.

#### F: Wie lege ich das Dokumentverzeichnis im Code fest?
 A: Im bereitgestellten Code müssen Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den entsprechenden Pfad zu dem Verzeichnis, in dem sich Ihr Word-Dokument mit dem VBA-Projekt befindet.

#### F: Wie speichere ich ein Zieldokument mit einem geklonten VBA-Projekt?

A: Um das Zieldokument mit dem geklonten VBA-Projekt zu speichern, können Sie den`Save` Methode der`Document` Klasse, indem Sie den gewünschten Zielpfad und Dateinamen angeben.

#### F: Kann ich Aspose.Words für .NET verwenden, um andere Aspekte von Word-Dokumenten zu bearbeiten?

A: Ja, Aspose.Words für .NET ist eine leistungsstarke Bibliothek, mit der Sie verschiedene Aspekte von Word-Dokumenten bearbeiten können. Sie können Daten aus Word-Dokumenten erstellen, bearbeiten, konvertieren und extrahieren, einschließlich Inhalt, Formatierung, Bilder, Tabellen, Diagramme und mehr.