---
title: Kopieren Sie Kopf- und Fußzeilen aus dem vorherigen Abschnitt
linktitle: Kopieren Sie Kopf- und Fußzeilen aus dem vorherigen Abschnitt
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen aus dem vorherigen Abschnitt in Word-Dokumente kopieren.
type: docs
weight: 10
url: /de/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen aus dem vorherigen Abschnitt in ein Word-Dokument kopieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek von der offiziellen Website herunter und installieren Sie sie.

## Schritt 1: Zugriff auf den vorherigen Abschnitt

 Rufen Sie zunächst den vorherigen Abschnitt ab, indem Sie auf zugreifen`PreviousSibling` Eigenschaft des aktuellen Abschnitts:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Schritt 2: Nach vorherigem Abschnitt suchen

Überprüfen Sie als Nächstes, ob ein vorheriger Abschnitt vorhanden ist. Wenn es keinen vorherigen Abschnitt gibt, geben wir einfach Folgendes zurück:

```csharp
if (previousSection == null)
    return;
```

## Schritt 3: Kopf- und Fußzeilen löschen und kopieren

Um die Kopf- und Fußzeilen aus dem vorherigen Abschnitt in den aktuellen Abschnitt zu kopieren, löschen wir die vorhandenen Kopf- und Fußzeilen im aktuellen Abschnitt und durchlaufen dann die Kopf- und Fußzeilen des vorherigen Abschnitts, um geklonte Kopien zum aktuellen Abschnitt hinzuzufügen:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Schritt 4: Speichern des Dokuments

Speichern Sie abschließend das geänderte Dokument:

```csharp
doc.Save("OutputDocument.docx");
```

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich Kopf- und Fußzeilen aus dem vorherigen Abschnitt in den aktuellen Abschnitt in einem Word-Dokument kopiert.

### Beispielquellcode zum Kopieren von Kopf- und Fußzeilen aus dem vorherigen Abschnitt mit Aspose.Words für .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Sie können diesen Code gerne in Ihren eigenen Projekten verwenden und entsprechend Ihren spezifischen Anforderungen modifizieren.