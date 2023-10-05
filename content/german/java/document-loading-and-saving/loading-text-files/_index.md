---
title: Laden von Textdateien mit Aspose.Words für Java
linktitle: Laden von Textdateien mit
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Nutzen Sie die Leistungsfähigkeit von Aspose.Words für Java. Erfahren Sie, wie Sie Textdokumente laden, Listen verwalten, mit Leerzeichen umgehen und die Textrichtung steuern.
type: docs
weight: 13
url: /de/java/document-loading-and-saving/loading-text-files/
---

## Einführung in das Laden von Textdateien mit Aspose.Words für Java

In dieser Anleitung erfahren Sie, wie Sie Textdateien mit Aspose.Words für Java laden und als Word-Dokumente bearbeiten. Wir behandeln verschiedene Aspekte wie das Erkennen von Listen, den Umgang mit Leerzeichen und das Steuern der Textrichtung.

## Schritt 1: Listen erkennen

Um ein Textdokument zu laden und Listen zu erkennen, können Sie die folgenden Schritte ausführen:

```java
// Erstellen Sie ein Klartextdokument in Form einer Zeichenfolge mit Teilen, die als Listen interpretiert werden können.
// Beim Laden werden die ersten drei Listen immer von Aspose.Words erkannt.
// Für sie werden nach dem Laden Listenobjekte erstellt.
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
//Die vierte Liste mit Leerzeichen zwischen der Listennummer und dem Inhalt des Listenelements,
// wird nur dann als Liste erkannt, wenn „DetectNumberingWithWhitespaces“ in einem LoadOptions-Objekt auf true gesetzt ist,
// um zu vermeiden, dass Absätze, die mit Zahlen beginnen, fälschlicherweise als Listen erkannt werden.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// Laden Sie das Dokument, während Sie LoadOptions als Parameter anwenden, und überprüfen Sie das Ergebnis.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Dieser Code zeigt, wie man ein Textdokument mit verschiedenen Listenformaten lädt und verwendet`DetectNumberingWithWhitespaces` Option zur korrekten Erkennung von Listen.

## Schritt 2: Umgang mit Leerzeichenoptionen

Um führende und nachfolgende Leerzeichen beim Laden eines Textdokuments zu steuern, können Sie den folgenden Code verwenden:

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

 In diesem Beispiel laden wir ein Textdokument und schneiden führende und nachfolgende Leerzeichen mit ab`TxtLeadingSpacesOptions.TRIM` Und`TxtTrailingSpacesOptions.TRIM`.

## Schritt 3: Textrichtung steuern

Um beim Laden eines Textdokuments die Textrichtung anzugeben, können Sie den folgenden Code verwenden:

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

Dieser Code setzt die Dokumentrichtung auf automatische Erkennung (`DocumentDirection.AUTO`und lädt ein Textdokument mit hebräischem Text. Sie können die Dokumentrichtung nach Bedarf anpassen.

## Vollständiger Quellcode zum Laden von Textdateien mit Aspose.Words für Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// Erstellen Sie ein Klartextdokument in Form einer Zeichenfolge mit Teilen, die als Listen interpretiert werden können.
	// Beim Laden werden die ersten drei Listen immer von Aspose.Words erkannt.
	// Für sie werden nach dem Laden Listenobjekte erstellt.
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// Die vierte Liste mit Leerzeichen zwischen der Listennummer und dem Inhalt des Listenelements,
	// wird nur dann als Liste erkannt, wenn „DetectNumberingWithWhitespaces“ in einem LoadOptions-Objekt auf true gesetzt ist,
	// um zu vermeiden, dass Absätze, die mit Zahlen beginnen, fälschlicherweise als Listen erkannt werden.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// Laden Sie das Dokument, während Sie LoadOptions als Parameter anwenden, und überprüfen Sie das Ergebnis.
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## Abschluss

In diesem Handbuch haben wir untersucht, wie Sie Textdateien mit Aspose.Words für Java laden, Listen erkennen, Leerzeichen verarbeiten und die Textrichtung steuern. Mit diesen Techniken können Sie Textdokumente in Ihren Java-Anwendungen effektiv bearbeiten.

## FAQs

### Was ist Aspose.Words für Java?

Aspose.Words für Java ist eine leistungsstarke Dokumentverarbeitungsbibliothek, die es Entwicklern ermöglicht, Word-Dokumente programmgesteuert in Java-Anwendungen zu erstellen, zu bearbeiten und zu konvertieren. Es bietet zahlreiche Funktionen für die Arbeit mit Text, Tabellen, Bildern und anderen Dokumentelementen.

### Wie kann ich mit Aspose.Words für Java beginnen?

Um mit Aspose.Words für Java zu beginnen, befolgen Sie diese Schritte:
1. Laden Sie die Aspose.Words für Java-Bibliothek herunter und installieren Sie sie.
2.  Weitere Informationen finden Sie in der Dokumentation unter[Aspose.Words für Java API-Referenz](https://reference.aspose.com/words/java/)Ausführliche Informationen und Beispiele finden Sie hier.
3. Erkunden Sie den Beispielcode und die Tutorials, um zu erfahren, wie Sie die Bibliothek effektiv nutzen können.

### Wie lade ich ein Textdokument mit Aspose.Words für Java?

 Um ein Textdokument mit Aspose.Words für Java zu laden, können Sie Folgendes verwenden`TxtLoadOptions` Klasse und die`Document` Klasse. Stellen Sie sicher, dass Sie bei Bedarf die entsprechenden Optionen für den Umgang mit Leerzeichen und die Textrichtung angeben. Ein detailliertes Beispiel finden Sie in der Schritt-für-Schritt-Anleitung in diesem Artikel.

### Kann ich ein geladenes Textdokument in andere Formate konvertieren?

 Ja, mit Aspose.Words für Java können Sie ein geladenes Textdokument in verschiedene Formate konvertieren, darunter DOCX, PDF und mehr. Du kannst den ... benutzen`Document` Klasse, um Konvertierungen durchzuführen. Konvertierungsbeispiele finden Sie in der Dokumentation.

### Wie gehe ich mit Leerzeichen in geladenen Textdokumenten um?

 Mit können Sie steuern, wie führende und nachfolgende Leerzeichen in geladenen Textdokumenten behandelt werden`TxtLoadOptions` . Optionen wie`TxtLeadingSpacesOptions` Und`TxtTrailingSpacesOptions`ermöglichen es Ihnen, Räume nach Bedarf zu kürzen oder zu erhalten. Ein Beispiel finden Sie im Abschnitt „Optionen zum Umgang mit Leerzeichen“ in diesem Handbuch.

### Welche Bedeutung hat die Textrichtung in Aspose.Words für Java?

Die Textrichtung ist für Dokumente mit gemischten Schriftarten oder Sprachen, wie z. B. Hebräisch oder Arabisch, von entscheidender Bedeutung. Aspose.Words für Java bietet Optionen zum Festlegen der Textrichtung und gewährleistet so die ordnungsgemäße Darstellung und Formatierung von Text in diesen Sprachen. Der Abschnitt „Steuern der Textrichtung“ in diesem Handbuch zeigt, wie Sie die Textrichtung festlegen.

### Wo finde ich weitere Ressourcen und Unterstützung für Aspose.Words für Java?

 Weitere Ressourcen, Dokumentation und Support finden Sie unter[Aspose.Words für Java-Dokumentation](https://reference.aspose.com/words/java/). Sie können auch an den Aspose.Words-Community-Foren teilnehmen oder sich an den Aspose-Support wenden, um Hilfe bei bestimmten Problemen oder Anfragen zu erhalten.

### Ist Aspose.Words für Java für kommerzielle Projekte geeignet?

Ja, Aspose.Words für Java eignet sich sowohl für persönliche als auch für kommerzielle Projekte. Es bietet Lizenzoptionen für verschiedene Nutzungsszenarien. Lesen Sie unbedingt die Lizenzbedingungen und Preise auf der Aspose-Website, um die geeignete Lizenz für Ihr Projekt auszuwählen.