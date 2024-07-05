---
title: Inhaltsverzeichnis-Tabstopps im Word-Dokument ändern
linktitle: Inhaltsverzeichnis-Tabstopps im Word-Dokument ändern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Registerkarten des Inhaltsverzeichnisses in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, die in einem Inhaltsverzeichnis eines Word-Dokuments verwendeten Registerkarten zu ändern. In dieser Anleitung zeigen wir Ihnen, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET Registerkarten im Inhaltsverzeichnis eines Dokuments ändern können.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Textverarbeitung mit Word-Dokumenten einfach und effizient macht. Sie bietet eine breite Palette an Funktionen zum Erstellen, Bearbeiten und Manipulieren von Word-Dokumenten, einschließlich der Änderung von Inhaltsverzeichnis-Registerkarten.

## Laden des Dokuments mit dem Inhaltsverzeichnis

Der erste Schritt besteht darin, das Word-Dokument mit dem zu ändernden Inhaltsverzeichnis zu laden. Verwenden Sie die Document-Klasse, um das Dokument aus der Quelldatei zu laden. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

In diesem Beispiel laden wir das Dokument „Inhaltsverzeichnis.docx“, das sich im Verzeichnis „Dokumente“ befindet.

## Registerkarten im Inhaltsverzeichnis ändern

Sobald das Dokument geladen ist, gehen wir jeden Absatz des Dokuments durch und prüfen, ob er mit den Ergebnisstilen des Inhaltsverzeichnisses (TOC) formatiert ist. Wenn ja, ändern wir die Tabulatoren, die zum Ausrichten der Seitenzahlen verwendet werden. So geht's:

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

In diesem Beispiel verwenden wir eine Schleife, um jeden Absatz im Dokument zu durchlaufen. Anschließend prüfen wir, ob der Absatz mit den Formatvorlagen für Inhaltsverzeichnisergebnisse (TOC) formatiert ist. Wenn dies der Fall ist, greifen wir auf die erste in diesem Absatz verwendete Registerkarte zu und ändern sie, indem wir die alte Registerkarte entfernen und eine neue Registerkarte mit geänderter Position hinzufügen.

## Geändertes Dokument speichern

Nachdem Sie die erforderlichen Änderungen an den Registerkarten im Inhaltsverzeichnis vorgenommen haben, können Sie das geänderte Dokument mit der Save-Methode der Document-Klasse speichern. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

In diesem Beispiel speichern wir das geänderte Dokument als „WorkingWithTableOfContent.ChangeTocTabStops.docx“.

### Beispiel-Quellcode für die Funktion „Inhaltsverzeichnis-Registerkarten bearbeiten“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
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

// Speichern des geänderten Dokuments
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Abschluss

In diesem Handbuch haben wir erläutert, wie Sie mit Aspose.Words für .NET die Registerkarten im Inhaltsverzeichnis eines Word-Dokuments mithilfe des bereitgestellten C#-Quellcodes ändern können. Indem Sie die angegebenen Schritte befolgen, können Sie die Registerkarten des Inhaltsverzeichnisses in Ihren Word-Dokumenten in Ihrer C#-Anwendung problemlos anpassen. Aspose.Words bietet enorme Flexibilität und Leistung beim Arbeiten mit den Stilen und der Formatierung Ihrer Dokumente, sodass Sie attraktive und professionelle Word-Dokumente erstellen können.

### FAQs zum Ändern von Inhaltsverzeichnis-Tabstopps in Word-Dokumenten

#### F: Was ist der Zweck der Funktion „Inhaltsverzeichnis-Tabstopps im Word-Dokument ändern“ in Aspose.Words für .NET?

A: Mit der Funktion „Tabulatorstopps im Inhaltsverzeichnis in Word-Dokument ändern“ in Aspose.Words für .NET können Sie die im Inhaltsverzeichnis eines Word-Dokuments verwendeten Tabulatorstopps ändern. Sie können damit die Ausrichtung und Positionierung der Seitenzahlen und der entsprechenden Überschriften im Inhaltsverzeichnis anpassen.

#### F: Was ist Aspose.Words für .NET?

A: Aspose.Words für .NET ist eine leistungsstarke Bibliothek für die Textverarbeitung mit Word-Dokumenten in .NET-Anwendungen. Sie bietet umfassende Funktionen zum programmgesteuerten Erstellen, Bearbeiten, Bearbeiten und Konvertieren von Word-Dokumenten mit C# oder anderen .NET-Sprachen.

#### F: Wie lade ich mit Aspose.Words für .NET ein Word-Dokument mit einem Inhaltsverzeichnis?

 A: Um ein Word-Dokument mit einem Inhaltsverzeichnis mit Aspose.Words für .NET zu laden, können Sie den`Document` Klasse und deren Konstruktor. Indem Sie den Dateipfad des Dokuments angeben, können Sie es in eine`Document` Objekt. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Dieser Codeausschnitt lädt das Dokument „Inhaltsverzeichnis.docx“, das sich im angegebenen Verzeichnis befindet.

#### F: Wie kann ich mit Aspose.Words für .NET die im Inhaltsverzeichnis verwendeten Registerkarten ändern?

 A: Sobald das Dokument geladen ist, können Sie jeden Absatz des Dokuments durchlaufen und prüfen, ob er mit den Ergebnisstilen des Inhaltsverzeichnisses (TOC) formatiert ist. Wenn ein Absatz als TOC-Stil formatiert ist, können Sie die Tabulatoren ändern, die zum Ausrichten der Seitenzahlen verwendet werden. In Aspose.Words für .NET können Sie auf die`ParagraphFormat` Eigenschaft jedes Absatzes, um die Tabulatorstopps abzurufen und zu ändern. Hier ist ein Beispiel:

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

In diesem Code durchläuft die Schleife jeden Absatz im Dokument. Wenn ein Absatz einen TOC-Stil hat, greift sie auf den ersten in diesem Absatz verwendeten Tabulator zu, entfernt ihn und fügt einen neuen Tabulator mit geänderter Position hinzu.

#### F: Kann ich mit Aspose.Words für .NET die Registerkarten für mehrere Ebenen im Inhaltsverzeichnis ändern?

A: Ja, Sie können die Tabulatoren für mehrere Ebenen im Inhaltsverzeichnis mit Aspose.Words für .NET ändern. Indem Sie jeden Absatz durchgehen und den Inhaltsverzeichnisstil überprüfen, können Sie die Tabulatoren für jede Ebene einzeln ändern. Sie können auf die gewünschte Ebene des Inhaltsverzeichnisses zugreifen und die Tabulatoren entsprechend anpassen.

#### F: Wie speichere ich das geänderte Dokument, nachdem ich mit Aspose.Words für .NET die Registerkarten im Inhaltsverzeichnis geändert habe?

 A: Nachdem Sie die erforderlichen Änderungen an den Registerkarten im Inhaltsverzeichnis vorgenommen haben, können Sie das geänderte Dokument mit dem`Save` Methode der`Document` Klasse. Geben Sie den gewünschten Dateipfad und Namen für das Ausgabedokument als Parameter an die`Save` Methode. Hier ist ein Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Dieser Code speichert das geänderte Dokument als „WorkingWithTableOfContent.ChangeTocTabStops.docx“.

#### F: Kann ich mit Aspose.Words für .NET andere Aspekte des Inhaltsverzeichnisses anpassen?

A: Ja, mit Aspose.Words für .NET können Sie verschiedene Aspekte des Inhaltsverzeichnisses anpassen. Neben dem Ändern der Registerkarten können Sie die Schriftart, -größe, -ausrichtung und andere Formatierungseigenschaften der Inhaltsverzeichniseinträge und Seitenzahlen ändern. Darüber hinaus können Sie die Einrückung, den Abstand und die Formatierung der entsprechenden Überschriften anpassen.

#### F: Kann ich mit Aspose.Words für .NET die Tabulatorausrichtung und Füllzeichen für das Inhaltsverzeichnis ändern?

A: Ja, Sie können die Tabulatorausrichtung und die Füllzeichen für das Inhaltsverzeichnis mit Aspose.Words für .NET ändern. Indem Sie auf die Tabulatoren zugreifen und deren Ausrichtung und Füllzeicheneigenschaften anpassen, können Sie die Ausrichtung und das Erscheinungsbild der Seitenzahlen und der entsprechenden Überschriften im Inhaltsverzeichnis steuern.

#### F: Unterstützt Aspose.Words für .NET das Ändern anderer Stile und Formatierungen in Word-Dokumenten?

A: Ja, Aspose.Words für .NET bietet umfassende Unterstützung zum Ändern verschiedener Stile und Formatierungen in Word-Dokumenten. Sie können Stile für verschiedene Elemente wie Absätze, Überschriften, Tabellen, Listen und mehr ändern. Sie können Schriftarten, Farben, Ausrichtung, Einrückung, Abstand und andere Formatierungsaspekte entsprechend Ihren Anforderungen ändern.

#### F: Kann ich mit Aspose.Words für .NET die Registerkarten im Inhaltsverzeichnis eines vorhandenen Word-Dokuments ändern?

A: Ja, Sie können die Tabulatoren im Inhaltsverzeichnis in einem vorhandenen Word-Dokument mit Aspose.Words für .NET ändern. Indem Sie das Dokument laden, die Absätze durchlaufen und die erforderlichen Änderungen an den Tabulatoren vornehmen, können Sie die Tabulatoren im Inhaltsverzeichnis aktualisieren. Speichern Sie abschließend das Dokument, um die Änderungen anzuwenden.