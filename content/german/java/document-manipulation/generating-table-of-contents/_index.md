---
title: Generieren eines Inhaltsverzeichnisses in Aspose.Words für Java
linktitle: Inhaltsverzeichnis erstellen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für Java ein Inhaltsverzeichnis (TOC) generieren und anpassen. Erstellen Sie mühelos organisierte und professionelle Dokumente.
type: docs
weight: 21
url: /de/java/document-manipulation/generating-table-of-contents/
---

## Einführung in die Generierung von Inhaltsverzeichnissen in Aspose.Words für Java

In diesem Tutorial führen wir Sie durch den Prozess der Erstellung eines Inhaltsverzeichnisses (TOC) mit Aspose.Words für Java. Das Inhaltsverzeichnis ist eine entscheidende Funktion für die Erstellung organisierter Dokumente. Wir besprechen, wie Sie das Erscheinungsbild und Layout des Inhaltsverzeichnisses anpassen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Aspose.Words für Java in Ihrem Java-Projekt installiert und eingerichtet ist.

## Schritt 1: Erstellen Sie ein neues Dokument

Erstellen wir zunächst ein neues Dokument, mit dem wir arbeiten können.

```java
Document doc = new Document();
```

## Schritt 2: Anpassen der Inhaltsverzeichnisse

Um das Erscheinungsbild Ihres Inhaltsverzeichnisses anzupassen, können Sie die damit verbundenen Stile ändern. In diesem Beispiel machen wir die Inhaltsverzeichniseinträge der ersten Ebene fett.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## Schritt 3: Fügen Sie Ihrem Dokument Inhalte hinzu

Sie können Ihre Inhalte zum Dokument hinzufügen. Dieser Inhalt wird zur Generierung des Inhaltsverzeichnisses verwendet.

## Schritt 4: Generieren Sie das Inhaltsverzeichnis

Um das Inhaltsverzeichnis zu generieren, fügen Sie an der gewünschten Stelle in Ihrem Dokument ein Inhaltsverzeichnisfeld ein. Dieses Feld wird automatisch basierend auf den Überschriften und Stilen in Ihrem Dokument ausgefüllt.

```java
// Fügen Sie an der gewünschten Stelle in Ihrem Dokument ein Inhaltsverzeichnisfeld ein.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Schritt 5: Speichern Sie das Dokument

Speichern Sie abschließend das Dokument mit dem Inhaltsverzeichnis.

```java
doc.save("your_output_path_here");
```

## Anpassen von Tabstopps im Inhaltsverzeichnis

Sie können auch die Tabstopps in Ihrem Inhaltsverzeichnis anpassen, um das Layout der Seitenzahlen zu steuern. So können Sie Tabstopps ändern:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Rufen Sie den ersten in diesem Absatz verwendeten Tabulator auf, der die Seitenzahlen ausrichtet.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Entfernen Sie die alte Lasche.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Fügen Sie einen neuen Tab an einer geänderten Position ein (z. B. 50 Einheiten nach links).
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Jetzt haben Sie in Ihrem Dokument ein benutzerdefiniertes Inhaltsverzeichnis mit angepassten Tabstopps für die Ausrichtung der Seitenzahlen.


## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Words für Java, einer leistungsstarken Bibliothek für die Arbeit mit Word-Dokumenten, ein Inhaltsverzeichnis (TOC) erstellen. Ein gut strukturiertes Inhaltsverzeichnis ist für die Organisation und Navigation in langen Dokumenten unerlässlich, und Aspose.Words bietet die Tools zum mühelosen Erstellen und Anpassen von Inhaltsverzeichnissen.

## FAQs

### Wie ändere ich die Formatierung von Inhaltsverzeichniseinträgen?

 Sie können die den Inhaltsverzeichnisebenen zugeordneten Stile mit ändern`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`, wobei X der TOC-Wert ist.

### Wie kann ich meinem Inhaltsverzeichnis weitere Ebenen hinzufügen?

Um mehr Ebenen in Ihr Inhaltsverzeichnis aufzunehmen, können Sie das Feld „Inhaltsverzeichnis“ ändern und die gewünschte Anzahl an Ebenen angeben.

### Kann ich die Tabstopppositionen für bestimmte Inhaltsverzeichniseinträge ändern?

Ja, wie im obigen Codebeispiel gezeigt, können Sie die Tabstopppositionen für bestimmte Inhaltsverzeichniseinträge ändern, indem Sie die Absätze durchlaufen und die Tabstopps entsprechend ändern.