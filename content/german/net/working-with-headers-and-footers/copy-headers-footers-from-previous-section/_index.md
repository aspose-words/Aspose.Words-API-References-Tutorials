---
title: Kopieren Sie Kopf- und Fußzeilen aus dem vorherigen Abschnitt
linktitle: Kopieren Sie Kopf- und Fußzeilen aus dem vorherigen Abschnitt
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen aus dem vorherigen Abschnitt in Word-Dokumente kopieren.
type: docs
weight: 10
url: /de/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Kopf- und Fußzeilen aus dem vorherigen Abschnitt in ein Word-Dokument kopieren. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und eingerichtet ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie[Aspose.Releases]https://releases.aspose.com/words/net/.

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

### FAQs

#### F: Wie kann ich die Kopf- und Fußzeilen aus dem vorherigen Abschnitt in Aspose.Words kopieren?

 A: Um Kopf- und Fußzeilen aus dem vorherigen Abschnitt in Aspose.Words zu kopieren, können Sie die verwenden`CopyHeadersFootersFromPreviousSection()` Methode auf die aktuelle`Section`Objekt. Dadurch werden die Kopf- und Fußzeilen aus dem vorherigen Abschnitt in den aktuellen Abschnitt kopiert.

#### F: Ist es möglich, nur die Kopf- oder Fußzeile aus dem vorherigen Abschnitt in Aspose.Words zu kopieren?

 A: Ja, es ist möglich, nur die Kopf- oder Fußzeile aus dem vorherigen Abschnitt in Aspose.Words zu kopieren. Hierfür können Sie die verwenden`CopyHeaderFromPreviousSection()` Und`CopyFooterFromPreviousSection()` Methoden auf dem aktuellen`Section` -Objekt, um gezielt die Kopf- oder Fußzeile vom vorherigen Abschnitt in den aktuellen Abschnitt zu kopieren.

#### F: Ersetzt das Kopieren von Kopf- und Fußzeilen aus dem vorherigen Abschnitt vorhandene Kopf- und Fußzeilen im aktuellen Abschnitt?

A: Ja, durch das Kopieren von Kopf- und Fußzeilen aus dem vorherigen Abschnitt werden vorhandene Kopf- und Fußzeilen im aktuellen Abschnitt ersetzt. Wenn Sie die vorhandenen Kopf- und Fußzeilen beibehalten und zu den kopierten Kopf- und Fußzeilen hinzufügen möchten, müssen Sie einen zusätzlichen Vorgang zum Zusammenführen der Inhalte ausführen.

#### F: Wie kann ich in Aspose.Words überprüfen, ob ein Abschnitt eine Kopf- oder Fußzeile aus dem vorherigen Abschnitt enthält?

A: Um zu überprüfen, ob ein Abschnitt eine Kopf- oder Fußzeile aus dem vorherigen Abschnitt in Aspose.Words enthält, können Sie die verwenden`HasHeader` Und`HasFooter` Eigenschaften auf der`Section` Objekt, um festzustellen, ob die Kopfzeile, Kopfzeile oder Fußzeile vorhanden ist. Wenn`HasHeader` oder`HasFooter` kehrt zurück`false`, bedeutet dies, dass in diesem Abschnitt keine Kopf- oder Fußzeile aus dem vorherigen Abschnitt vorhanden ist.