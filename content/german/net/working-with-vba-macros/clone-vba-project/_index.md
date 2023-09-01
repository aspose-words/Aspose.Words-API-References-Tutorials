---
title: Klonen Sie ein VBA-Projekt aus einem Word-Dokument
linktitle: Klonen Sie ein VBA-Projekt aus einem Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

### FAQs

#### F: Was ist das Duplizieren eines VBA-Projekts?

A: Beim Duplizieren eines VBA-Projekts wird der gesamte VBA-Code aus einem Word-Quelldokument in ein anderes Dokument kopiert. Dadurch können Sie VBA-Code in verschiedenen Kontexten wiederverwenden oder mit anderen Dokumenten teilen.

#### F: Was sind die Voraussetzungen für das Klonen eines VBA-Projekts aus einem Word-Dokument?

A: Bevor Sie ein VBA-Projekt aus einem Word-Dokument klonen können, müssen Sie über praktische Kenntnisse der Programmiersprache C# verfügen. Sie müssen außerdem die Aspose.Words for .NET-Bibliothek in Ihrem Projekt installieren. Außerdem benötigen Sie ein Word-Dokument mit einem VBA-Projekt, das Sie klonen möchten.

#### F: Wie lege ich das Dokumentverzeichnis im Code fest?
 A: Im bereitgestellten Code müssen Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem entsprechenden Pfad zu dem Verzeichnis, in dem sich Ihr Word-Dokument mit dem VBA-Projekt befindet.

#### F: Wie speichere ich ein Zieldokument mit einem geklonten VBA-Projekt?

A: Um das Zieldokument mit dem geklonten VBA-Projekt zu speichern, können Sie das verwenden`Save` Methode der`Document` Klasse durch Angabe des gewünschten Zielpfads und Dateinamens.

#### F: Kann ich Aspose.Words für .NET verwenden, um andere Aspekte von Word-Dokumenten zu bearbeiten?

A: Ja, Aspose.Words für .NET ist eine leistungsstarke Bibliothek, mit der Sie verschiedene Aspekte von Word-Dokumenten bearbeiten können. Sie können Daten aus Word-Dokumenten erstellen, bearbeiten, konvertieren und extrahieren, einschließlich Inhalt, Formatierung, Bildern, Tabellen, Diagrammen und mehr.