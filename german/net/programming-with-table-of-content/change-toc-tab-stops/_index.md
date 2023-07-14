---
title: Ändern Sie die Tabstopps im Inhaltsverzeichnis im Word-Dokument
linktitle: Ändern Sie die Tabstopps im Inhaltsverzeichnis im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Registerkarten des Inhaltsverzeichnisses in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, die in einem Inhaltsverzeichnis eines Word-Dokuments verwendeten Tabs zu ändern. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um Tabulatoren im Inhaltsverzeichnis eines Dokuments zu ändern.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Textverarbeitung mit Word-Dokumenten einfach und effizient macht. Es bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten, einschließlich der Änderung von Inhaltsverzeichnis-Registerkarten.

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

### FAQs zum Ändern von Tabstopps im Inhaltsverzeichnis in Word-Dokumenten

#### F: Was ist der Zweck der Funktion „Inhaltsverzeichnis-Tabstopps in Word-Dokument ändern“ in Aspose.Words für .NET?

A: Mit der Funktion „Inhaltsverzeichnis-Tabstopps in Word-Dokument ändern“ in Aspose.Words für .NET können Sie die Tabstopps ändern, die im Inhaltsverzeichnis eines Word-Dokuments verwendet werden. Damit können Sie die Ausrichtung und Positionierung der Seitenzahlen und der entsprechenden Überschriften im Inhaltsverzeichnis anpassen.

#### F: Was ist Aspose.Words für .NET?

A: Aspose.Words für .NET ist eine leistungsstarke Bibliothek, die für die Textverarbeitung mit Word-Dokumenten in .NET-Anwendungen entwickelt wurde. Es bietet umfassende Funktionen zum programmgesteuerten Erstellen, Bearbeiten, Bearbeiten und Konvertieren von Word-Dokumenten mit C# oder anderen .NET-Sprachen.

#### F: Wie lade ich mit Aspose.Words für .NET ein Word-Dokument mit einem Inhaltsverzeichnis?

 A: Um ein Word-Dokument mit einem Inhaltsverzeichnis mit Aspose.Words für .NET zu laden, können Sie das verwenden`Document` Klasse und ihr Konstruktor. Durch Angabe des Dateipfads des Dokuments können Sie es in eine laden`Document` Objekt. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Dieses Code-Snippet lädt das Dokument „Inhaltsverzeichnis.docx“, das sich im angegebenen Verzeichnis befindet.

#### F: Wie kann ich mit Aspose.Words für .NET die im Inhaltsverzeichnis verwendeten Tabs ändern?

 A: Sobald das Dokument geladen ist, können Sie jeden Absatz des Dokuments durchlaufen und mithilfe der Ergebnisstile des Inhaltsverzeichnisses (TOC) prüfen, ob er formatiert ist. Wenn ein Absatz im Inhaltsverzeichnisstil formatiert ist, können Sie die Tabulatoren ändern, die zum Ausrichten der Seitenzahlen verwendet werden. In Aspose.Words für .NET können Sie auf Folgendes zugreifen`ParagraphFormat` Eigenschaft jedes Absatzes, um die Tabstopps abzurufen und zu ändern. Hier ist ein Beispiel:

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

In diesem Code durchläuft die Schleife jeden Absatz im Dokument. Wenn ein Absatz einen Inhaltsverzeichnisstil hat, greift es auf den ersten in diesem Absatz verwendeten Tabstopp zu, entfernt ihn und fügt einen neuen Tabstopp mit einer geänderten Position hinzu.

#### F: Kann ich mit Aspose.Words für .NET die Tabulatoren für mehrere Ebenen im Inhaltsverzeichnis ändern?

A: Ja, Sie können die Tabulatoren für mehrere Ebenen im Inhaltsverzeichnis mit Aspose.Words für .NET ändern. Indem Sie jeden Absatz durchlaufen und den Inhaltsverzeichnisstil überprüfen, können Sie die Tabulatoren für jede Ebene einzeln ändern. Sie können auf die gewünschte Ebene des Inhaltsverzeichnisses zugreifen und die Tabstopps entsprechend anpassen.

#### F: Wie speichere ich das geänderte Dokument, nachdem ich die Tabulatoren im Inhaltsverzeichnis mit Aspose.Words für .NET geändert habe?

 A: Nachdem Sie die erforderlichen Änderungen an den Registerkarten im Inhaltsverzeichnis vorgenommen haben, können Sie das geänderte Dokument mit speichern`Save` Methode der`Document` Klasse. Geben Sie den gewünschten Dateipfad und Namen für das Ausgabedokument als Parameter an`Save` Methode. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Dieser Code speichert das geänderte Dokument als „WorkingWithTableOfContent.ChangeTocTabStops.docx“.

#### F: Kann ich andere Aspekte des Inhaltsverzeichnisses mit Aspose.Words für .NET anpassen?

A: Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Inhaltsverzeichnisses anpassen. Neben dem Ändern der Tabulatoren können Sie auch Schriftarten, Größe, Ausrichtung und andere Formatierungseigenschaften der Inhaltsverzeichniseinträge und Seitenzahlen ändern. Darüber hinaus können Sie die Einrückung, den Abstand und die Formatierung der entsprechenden Überschriften anpassen.

#### Q:. Kann ich mit Aspose.Words für .NET die Tabulatorausrichtung und die Führungszeichen für das Inhaltsverzeichnis ändern?

A: Ja, Sie können die Tabulatorausrichtung und die Führungszeichen für das Inhaltsverzeichnis mit Aspose.Words für .NET ändern. Indem Sie auf die Tabstopps zugreifen und deren Ausrichtung und Führungseigenschaften anpassen, können Sie die Ausrichtung und das visuelle Erscheinungsbild der Seitenzahlen und entsprechenden Überschriften im Inhaltsverzeichnis steuern.

#### F: Unterstützt Aspose.Words für .NET das Ändern anderer Stile und Formatierungen in Word-Dokumenten?

A: Ja, Aspose.Words für .NET bietet umfassende Unterstützung für die Änderung verschiedener Stile und Formatierungen in Word-Dokumenten. Sie können damit Stile für verschiedene Elemente wie Absätze, Überschriften, Tabellen, Listen und mehr ändern. Sie können Schriftarten, Farben, Ausrichtung, Einrückung, Abstände und andere Formatierungsaspekte entsprechend Ihren Anforderungen ändern.

#### F: Kann ich die Tabulatoren im Inhaltsverzeichnis eines vorhandenen Word-Dokuments mit Aspose.Words für .NET ändern?

A: Ja, Sie können die Tabulatoren im Inhaltsverzeichnis eines vorhandenen Word-Dokuments mit Aspose.Words für .NET ändern. Indem Sie das Dokument laden, die Absätze durchlaufen und die erforderlichen Änderungen an den Tabstopps vornehmen, können Sie die Tabulatoren im Inhaltsverzeichnis aktualisieren. Speichern Sie abschließend das Dokument, um die Änderungen zu übernehmen.