---
title: Inhaltsverzeichnis-Tabstopps ändern
linktitle: Inhaltsverzeichnis-Tabstopps ändern
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Registerkarten des Inhaltsverzeichnisses in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, die in einem Inhaltsverzeichnis eines Word-Dokuments verwendeten Tabs zu ändern. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um Tabulatoren im Inhaltsverzeichnis eines Dokuments zu ändern.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Arbeit mit Word-Dokumenten einfach und effizient macht. Es bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten, einschließlich der Änderung von Inhaltsverzeichnis-Registerkarten.

## Laden des Dokuments mit dem Inhaltsverzeichnis

Der erste Schritt besteht darin, das Word-Dokument zu laden, das das Inhaltsverzeichnis enthält, das Sie ändern möchten. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

In diesem Beispiel laden wir das Dokument „Inhaltsverzeichnis.docx“, das sich im Dokumentenverzeichnis befindet.

## Tabs im Inhaltsverzeichnis wechseln

Sobald das Dokument geladen ist, gehen wir jeden Absatz des Dokuments durch und prüfen, ob er mit den Ergebnisstilen des Inhaltsverzeichnisses (TOC) formatiert ist. Wenn ja, ändern wir die Tabulatoren, die zum Ausrichten der Seitenzahlen verwendet werden. Hier ist wie:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

In diesem Beispiel verwenden wir eine Schleife, um jeden Absatz im Dokument zu durchlaufen. Anschließend prüfen wir, ob der Absatz mit den TOC-Stilen (Table of Contents Result) formatiert ist. Wenn ja, greifen wir auf den ersten Tab zu, der in diesem Absatz verwendet wird, und ändern ihn, indem wir den alten Tab entfernen und einen neuen Tab mit einer geänderten Position hinzufügen.

## Geändertes Dokument speichern

Nachdem Sie die erforderlichen Änderungen an den Registerkarten im Inhaltsverzeichnis vorgenommen haben, können Sie das geänderte Dokument mit der Save-Methode der Document-Klasse speichern. Hier ist ein Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

In diesem Beispiel speichern wir das geänderte Dokument als „WorkingWithTableOfContent.ChangeTocTabStops.docx“.

### Beispielquellcode für die Funktion „Registerkarten für Inhaltsverzeichnis bearbeiten“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument mit dem Inhaltsverzeichnis
Document doc = new Document(dataDir + "Table of contents.docx");

// Ändern Sie die Registerkarten des Inhaltsverzeichnisses
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Abschluss

In diesem Handbuch haben wir erläutert, wie Sie Aspose.Words für .NET verwenden, um die Tabulatoren im Inhaltsverzeichnis eines Word-Dokuments mithilfe des bereitgestellten C#-Quellcodes zu ändern. Indem Sie die bereitgestellten Schritte befolgen, können Sie die Inhaltsverzeichnisregisterkarten in Ihren Word-Dokumenten in Ihrer C#-Anwendung ganz einfach anpassen. Aspose.Words bietet enorme Flexibilität und Möglichkeiten, mit den Stilen und Formatierungen Ihrer Dokumente zu arbeiten, sodass Sie attraktive und professionelle Word-Dokumente erstellen können.