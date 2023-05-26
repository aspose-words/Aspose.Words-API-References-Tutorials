---
title: Abschnitt kopieren
linktitle: Abschnitt kopieren
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET einen Abschnitt aus einem Word-Dokument in ein anderes Dokument kopieren.
type: docs
weight: 10
url: /de/net/working-with-section/copy-section/
---

In diesem Tutorial erklären wir, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET einen Abschnitt aus einem Word-Dokument in ein anderes Dokument kopieren. Durch das Kopieren eines Abschnitts können Sie einen bestimmten Abschnitt von einem Quelldokument in ein Zieldokument übertragen. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Quelldokument, das den Abschnitt enthält, den Sie kopieren möchten
- Ein leeres Zieldokument, in das Sie den Abschnitt kopieren möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad festlegen, in dem sich Ihre Dokumente befinden. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Quell- und Zieldokumente laden
 Als Nächstes laden wir das Quelldokument in eine Instanz von`Document` Klasse aufgerufen`srcDoc` . Wir werden auch eine leere Instanz von erstellen`Document` Klasse aufgerufen`dstDoc` für das Zieldokument.

```csharp
// Laden Sie das Quelldokument
Document srcDoc = new Document(dataDir + "Document.docx");

// Erstellen Sie ein leeres Zieldokument
Document dstDoc = new Document();
```

## Schritt 3: Kopieren Sie den Abschnitt in das Zieldokument
Um den Abschnitt vom Quelldokument in das Zieldokument zu kopieren, verwenden wir die`ImportNode` Methode zum Importieren des Quellabschnitts und Hinzufügen zum Zieldokument.

```csharp
// Holen Sie sich den Quellabschnitt
Section sourceSection = srcDoc.Sections[0];

// Kopieren Sie den Abschnitt in das Zieldokument
Section newSection = (Section)dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
```

## Schritt 4: Speichern Sie das Zieldokument
Abschließend speichern wir das Zieldokument mit dem kopierten Abschnitt in einer Datei.

```csharp
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");
```

### Beispielquellcode für Copy Section mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document.docx");
Document dstDoc = new Document();
Section sourceSection = srcDoc.Sections[0];
Section newSection = (Section) dstDoc.ImportNode(sourceSection, true);
dstDoc.Sections.Add(newSection);
dstDoc.Save(dataDir + "WorkingWithSection.CopySection.docx");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET einen Abschnitt aus einem Word-Dokument in ein anderes Dokument kopiert. Durch das Kopieren von Abschnitten können Sie bestimmte Abschnitte einfach von einem Quelldokument in ein Zieldokument übertragen. Fühlen Sie sich frei, diese Methode zu verwenden, um Abschnitte Ihrer Dokumente effizient zu organisieren und zu bearbeiten.