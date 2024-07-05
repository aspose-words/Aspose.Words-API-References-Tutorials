---
title: Abschnitt „Kopieren“
linktitle: Abschnitt „Kopieren“
second_title: Aspose.Words Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET einen Abschnitt aus einem Word-Dokument in ein anderes Dokument kopieren.
type: docs
weight: 10
url: /de/net/working-with-section/copy-section/
---

In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET einen Abschnitt aus einem Word-Dokument in ein anderes Dokument kopieren. Durch das Kopieren eines Abschnitts können Sie einen bestimmten Abschnitt aus einem Quelldokument in ein Zieldokument übertragen. Wir führen Sie Schritt für Schritt durch, damit Sie den Code verstehen und in Ihrem .NET-Projekt implementieren können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Quelldokument, das den zu kopierenden Abschnitt enthält
- Ein leeres Zieldokument, in das Sie den Abschnitt kopieren möchten

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad festlegen, in dem sich Ihre Dokumente befinden. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Quell- und Zieldokumente laden
 Als nächstes laden wir das Quelldokument in eine Instanz des`Document` Klasse namens`srcDoc` . Wir erstellen außerdem eine leere Instanz des`Document` Klasse namens`dstDoc` für das Zieldokument.

```csharp
// Laden des Quelldokuments
Document srcDoc = new Document(dataDir + "Document.docx");

// Erstellen Sie ein leeres Zieldokument
Document dstDoc = new Document();
```

## Schritt 3: Kopieren Sie den Abschnitt in das Zieldokument
 Um den Abschnitt aus dem Quelldokument in das Zieldokument zu kopieren, verwenden wir den`ImportNode`Methode, um den Quellabschnitt zu importieren und ihn dem Zieldokument hinzuzufügen.

```csharp
// Abschnitt „Quelle abrufen“
Section sourceSection = srcDoc.Sections[0];

// Kopieren Sie den Abschnitt in das Zieldokument
Section newSection = (Section)dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
```

## Schritt 4: Zieldokument speichern
Abschließend speichern wir das Zieldokument mit dem kopierten Abschnitt in einer Datei.

```csharp
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");
```

### Beispielquellcode für Copy Section mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document.docx");
Document dstDoc = new Document();
Section sourceSection = srcDoc.Sections[0];
Section newSection = (Section) dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET einen Abschnitt aus einem Word-Dokument in ein anderes Dokument kopiert. Durch das Kopieren von Abschnitten können Sie bestimmte Abschnitte problemlos von einem Quelldokument in ein Zieldokument übertragen. Verwenden Sie diese Methode, um Abschnitte Ihrer Dokumente effizient zu organisieren und zu bearbeiten.

### Häufig gestellte Fragen

#### F: Was sind die Voraussetzungen für das Kopieren eines Abschnitts aus einem Word-Dokument in ein anderes Dokument mit Aspose.Words für .NET?

A: Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Gegenstände verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words for .NET-Bibliothek
- Ein Quelldokument, das den zu kopierenden Abschnitt enthält
- Ein leeres Zieldokument, in das Sie den Abschnitt kopieren möchten

#### F: Wie lege ich das Dokumentverzeichnis in Aspose.Words für .NET fest?

 A: Um den Pfad zum Verzeichnis mit Ihren Dokumenten festzulegen, müssen Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad. So geht's:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### F: Wie lade ich Quell- und Zieldokumente in Aspose.Words für .NET?

A: Um das Quelldokument in eine Instanz des`Document` Klasse namens`srcDoc` und erstellen Sie eine leere Instanz des`Document` Klasse namens`dstDoc` Für das Zieldokument können Sie den folgenden Code verwenden:

```csharp
// Laden des Quelldokuments
Document srcDoc = new Document(dataDir + "Document.docx");

// Erstellen Sie ein leeres Zieldokument
Document dstDoc = new Document();
```

#### F: Wie kopiere ich in Aspose.Words für .NET einen Abschnitt vom Quelldokument in das Zieldokument?

A: Um den Abschnitt aus dem Quelldokument in das Zieldokument zu kopieren, können Sie den folgenden Code verwenden:

```csharp
// Abschnitt „Quelle abrufen“
Section sourceSection = srcDoc.Sections[0];

// Kopieren Sie den Abschnitt in das Zieldokument
Section newSection = (Section)dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
```

#### F: Wie speichere ich ein Zieldokument mit kopiertem Abschnitt in Aspose.Words für .NET?

A: Schließlich können Sie das Zieldokument, das den kopierten Abschnitt enthält, mit dem folgenden Code in einer Datei speichern:

```csharp
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");
```