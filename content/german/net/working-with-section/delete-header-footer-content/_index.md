---
title: Kopf-/Fußzeileninhalt löschen
linktitle: Kopf-/Fußzeileninhalt löschen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeileninhalte aus einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/working-with-section/delete-header-footer-content/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET Kopf- und Fußzeileninhalte aus einem Word-Dokument entfernen. Das Entfernen von Inhalten aus Kopf- und Fußzeilen kann nützlich sein, wenn Sie diese Elemente in Ihrem Dokument zurücksetzen oder entfernen möchten. Wir führen Sie Schritt für Schritt durch den Code, damit Sie ihn in Ihrem .NET-Projekt verstehen und implementieren können.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit Kopf- und Fußzeilen, die Sie entfernen möchten

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments setzen. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und gehen Sie zum Abschnitt
 Als nächstes laden wir das Word-Dokument in eine Instanz des`Document` Klasse. Wir greifen mit Index 0 auf den ersten Abschnitt des Dokuments zu.

```csharp
// Laden Sie das Dokument
Document doc = new Document(dataDir + "Document.docx");

// Greifen Sie auf den Abschnitt zu
Section section = doc.Sections[0];
```

## Schritt 3: Kopf- und Fußzeileninhalte löschen
 Um den Inhalt der Kopf- und Fußzeile aus dem Abschnitt zu entfernen, verwenden wir die`ClearHeadersFooters` Methode.

```csharp
section.ClearHeadersFooters();
```

### Beispielquellcode zum Löschen von Kopf- und Fußzeileninhalten mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET Kopf- und Fußzeileninhalte aus einem Word-Dokument entfernt. Durch das Entfernen von Inhalten aus Kopf- und Fußzeilen können Sie diese spezifischen Elemente aus Ihrem Dokument zurücksetzen oder entfernen. Sie können diese Funktion gerne Ihren spezifischen Anforderungen entsprechend anpassen und verwenden.

### FAQs zum Löschen von Kopf- und Fußzeileninhalten

#### F: Wie lege ich das Dokumentverzeichnis in Aspose.Words für .NET fest?

 A: Um den Pfad zum Verzeichnis mit Ihren Dokumenten festzulegen, müssen Sie ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad. So geht's:

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### F: Wie lade ich ein Dokument und greife auf den Abschnitt in Aspose.Words für .NET zu?

 A: Um das Word-Dokument in eine Instanz des`Document` Klasse namens`doc` und mit dem Index 0 auf den ersten Abschnitt des Dokuments zugreifen möchten, können Sie den folgenden Code verwenden:

```csharp
// Laden Sie das Dokument
Document doc = new Document(dataDir + "Document.docx");

// Greifen Sie auf den Abschnitt zu
Section section = doc.Sections[0];
```

#### F: Wie entferne ich Kopf- und Fußzeileninhalte in Aspose.Words für .NET?

 A: Um den Inhalt der Kopf- und Fußzeile aus dem Abschnitt zu entfernen, können Sie das`ClearHeadersFooters` Methode:

```csharp
section.ClearHeadersFooters();
```

#### F: Wie speichere ich das geänderte Dokument in Aspose.Words für .NET?

A: Nachdem Sie den Kopf- und Fußzeileninhalt gelöscht haben, können Sie das geänderte Dokument mit dem folgenden Code in einer Datei speichern:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```