---
title: Löschen Sie den Inhalt der Kopf- und Fußzeile
linktitle: Löschen Sie den Inhalt der Kopf- und Fußzeile
second_title: Aspose.Words für .NET API-Referenz
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeileninhalte aus einem Word-Dokument entfernen.
type: docs
weight: 10
url: /de/net/working-with-section/delete-header-footer-content/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie Kopf- und Fußzeileninhalte mithilfe der Aspose.Words-Bibliothek für .NET aus einem Word-Dokument entfernen. Das Entfernen von Inhalten aus Kopf- und Fußzeilen kann nützlich sein, wenn Sie diese Elemente zurücksetzen oder aus Ihrem Dokument entfernen möchten. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit Kopf- und Fußzeilen, die Sie entfernen möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und gehen Sie zum Abschnitt
 Als nächstes laden wir das Word-Dokument in eine Instanz von`Document` Klasse. Wir greifen über den Index 0 auf den ersten Abschnitt des Dokuments zu.

```csharp
//Laden Sie das Dokument
Document doc = new Document(dataDir + "Document.docx");

// Greifen Sie auf den Abschnitt zu
Section section = doc.Sections[0];
```

## Schritt 3: Kopf- und Fußzeileninhalt löschen
 Um den Inhalt der Kopf- und Fußzeile aus dem Abschnitt zu entfernen, verwenden wir die`ClearHeadersFooters` Methode.

```csharp
section.ClearHeadersFooters();
```

### Beispielquellcode zum Löschen von Kopf- und Fußzeileninhalten mit Aspose.Words für .NET 

```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET Kopf- und Fußzeileninhalte aus einem Word-Dokument entfernt. Durch das Entfernen von Inhalten aus Kopf- und Fußzeilen können Sie diese spezifischen Elemente zurücksetzen oder aus Ihrem Dokument entfernen. Sie können diese Funktion gerne an Ihre spezifischen Bedürfnisse anpassen und nutzen.
