---
title: Wyodrębnianie treści z dokumentów w Aspose.Words dla Java
linktitle: Wyodrębnianie treści z dokumentów
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak z łatwością wyodrębniać zawartość z dokumentów za pomocą Aspose.Words dla Java. Nasz przewodnik krok po kroku i próbki kodu upraszczają ten proces.
type: docs
weight: 13
url: /pl/java/document-manipulation/extracting-content-from-documents/
---

## Wprowadzenie do wyodrębniania treści z dokumentów w Aspose.Words dla Java

świecie przetwarzania dokumentów wyodrębnianie treści z dokumentów jest powszechnym wymogiem. Niezależnie od tego, czy chcesz wyodrębnić tekst, tabele, obrazy, czy określone elementy dokumentu, Aspose.Words dla Java zapewnia potężne narzędzia, dzięki którym to zadanie stanie się proste. W tym obszernym przewodniku przeprowadzimy Cię przez proces wyodrębniania treści z dokumentów za pomocą Aspose.Words dla Java. 

## Warunki wstępne

Zanim zagłębimy się w proces ekstrakcji, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Aspose.Words for Java: Powinieneś mieć zainstalowany i skonfigurowany Aspose.Words for Java w swoim środowisku programistycznym Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

2. Dokument, z którego można wyodrębnić treść: W tym przewodniku użyjemy przykładowego dokumentu o nazwie „Wyodrębnij treść.docx”. Upewnij się, że masz podobny dokument gotowy do wyodrębnienia.

## Wyodrębnianie treści pomiędzy węzłami na poziomie bloku

```java
// Przykładowy kod Java do wyodrębniania treści między węzłami na poziomie bloków
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getLastSection().getChild(NodeType.PARAGRAPH, 2, true);
Table endTable = (Table) doc.getLastSection().getChild(NodeType.TABLE, 0, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endTable, true);
Collections.reverse(extractedNodes);
while (extractedNodes.size() > 0) {
    endTable.getParentNode().insertAfter((Node) extractedNodes.get(0), endTable);
    extractedNodes.remove(0);
}
doc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBlockLevelNodes.docx");
```

## Wyodrębnianie treści pomiędzy zakładkami

```java
//Przykładowy kod Java do wyodrębniania zawartości pomiędzy zakładkami
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("Bookmark1");
BookmarkStart bookmarkStart = bookmark.getBookmarkStart();
BookmarkEnd bookmarkEnd = bookmark.getBookmarkEnd();
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.IncludingBookmark.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.WithoutBookmark.docx");
```

## Wyodrębnianie treści pomiędzy zakresami komentarzy

```java
// Przykład kodu Java do wyodrębniania treści pomiędzy zakresami komentarzy
Document doc = new Document("Your Directory Path" + "Extract content.docx");
CommentRangeStart commentStart = (CommentRangeStart) doc.getChild(NodeType.COMMENT_RANGE_START, 0, true);
CommentRangeEnd commentEnd = (CommentRangeEnd) doc.getChild(NodeType.COMMENT_RANGE_END, 0, true);
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.IncludingComment.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.WithoutComment.docx");
```

## Wyodrębnianie treści pomiędzy akapitami

```java
// Przykładowy kod Java do wyodrębniania treści pomiędzy akapitami
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## Wyodrębnianie treści pomiędzy stylami akapitów

```java
// Przykładowy kod Java do wyodrębniania treści pomiędzy stylami akapitów
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## Wyodrębnianie zawartości pomiędzy uruchomieniami

```java
// Przykładowy kod Java do wyodrębniania zawartości między uruchomieniami
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString(SaveFormat.TEXT));
```

## Wyodrębnianie treści za pomocą DocumentVisitor

```java
// Przykładowy kod Java do wyodrębniania treści za pomocą DocumentVisitor
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## Wyodrębnianie treści za pomocą pola

```java
// Przykład kodu Java do wyodrębniania treści za pomocą pola
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## Wyodrębnianie spisu treści

```java
// Przykładowy kod Java do wyodrębniania spisu treści
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
for (Field field : doc.getRange().getFields()) {
    if (field.getType() == FieldType.FIELD_HYPERLINK) {
        FieldHyperlink hyperlink = (FieldHyperlink) field;
        if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
            Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(tocItem.toString(SaveFormat.TEXT).trim());
            System.out.println("------------------");
            Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
            Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(pointer.toString(SaveFormat.TEXT));
        }
    }
}
```

## Wyodrębnianie tylko tekstu

```java
// Przykładowy kod Java do wyodrębniania samego tekstu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
```

## Wyodrębnianie treści na podstawie stylów

```java
// Przykładowy kod Java do wyodrębniania treści na podstawie stylów
Document doc = new Document("Your Directory Path" + "Styles.docx");
final String PARA_STYLE = "Heading 1";
final String RUN_STYLE = "Intense Emphasis";
ArrayList<Paragraph> paragraphs = paragraphsByStyleName(doc, PARA_STYLE);
System.out.println("Paragraphs with \"{paraStyle}\" styles ({paragraphs.Count}):");
for (Paragraph paragraph : paragraphs)
    System.out.println(paragraph.toString(SaveFormat.TEXT));
ArrayList<Run> runs = runsByStyleName(doc, RUN_STYLE);
System.out.println("\nRuns with \"{runStyle}\" styles ({runs.Count}):");
for (Run run : runs)
    System.out.println(run.getRange().getText());
}

public ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}

public ArrayList<Run> runsByStyleName(Document doc, String styleName) {
    ArrayList<Run> runsWithStyle = new ArrayList<Run>();
    NodeCollection runs = doc.getChildNodes(NodeType.RUN, true);
    for (Run run : (Iterable<Run>) runs) {
        if (run.getFont().getStyle().getName().equals(styleName))
            runsWithStyle.add(run);
    }
    return runsWithStyle;
}
```

## Wyodrębnianie i drukowanie tekstu

```java
// Przykładowy kod Java do wyodrębniania i drukowania tekstu
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## Wyodrębnianie obrazów do plików

```java
// Przykładowy kod Java do wyodrębniania obrazów do plików
Document doc = new Document("Your Directory Path" + "Images.docx");
NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;
for (Shape shape : (Iterable<Shape>) shapes) {
    if (shape.hasImage()) {
        String imageFileName = MessageFormat.format("Image.ExportImages.{0}_{1}",
                imageIndex, FileFormatUtil.imageTypeToExtension(shape.getImageData().getImageType()));
        shape.getImageData().save("Your Directory Path" + imageFileName);
        imageIndex++;
    }
}
```

## Wniosek

Gratulacje! Nauczyłeś się, jak wyodrębniać treść z dokumentów za pomocą Aspose.Words dla Java. W tym przewodniku omówiono różne techniki wyodrębniania, w tym zawartość między węzłami na poziomie bloków, zakładkami, zakresami komentarzy, akapitami i nie tylko. Teraz możesz efektywnie zarządzać ekstrakcją treści dokumentów w aplikacjach Java.

## Często zadawane pytania

### Jak wyodrębnić treść z określonych sekcji dokumentu?

Aby wyodrębnić treść z określonych sekcji dokumentu, możesz zidentyfikować punkty początkowe i końcowe sekcji i użyć odpowiednich metod Aspose.Words for Java w celu wyodrębnienia treści pomiędzy nimi.

### Czy mogę wyodrębnić treść z dokumentów chronionych hasłem?

Tak, Aspose.Words for Java zapewnia funkcję wyodrębniania treści z dokumentów chronionych hasłem. Hasło możesz podać podczas otwierania dokumentu za pomocą`Document` konstruktor klasy.

### Jak wyodrębnić treść i zapisać ją w różnych formatach, takich jak zwykły tekst lub HTML?

 Możesz wyodrębnić treść z dokumentu i zapisać ją w różnych formatach, używając Aspose.Words dla Java. Po wyodrębnieniu zawartości możesz użyć pliku`Document` klasy, aby zapisać je w formatach takich jak zwykły tekst, HTML lub inne.

### Czy istnieje sposób na wyodrębnienie treści z określonych elementów dokumentu, takich jak tabele lub obrazy?

Tak, możesz wyodrębnić treść z określonych elementów dokumentu, takich jak tabele lub obrazy, używając Aspose.Words for Java. Zidentyfikuj elementy, które chcesz wyodrębnić, a następnie użyj odpowiednich metod, aby wyodrębnić ich zawartość.

### Jak mogę zautomatyzować proces wyodrębniania treści w mojej aplikacji Java?

Aby zautomatyzować proces wyodrębniania treści w aplikacji Java, możesz utworzyć niestandardowy kod w oparciu o techniki opisane w tym przewodniku. Możesz także zaimplementować logikę, aby przeglądać wiele dokumentów i wyodrębniać zawartość w razie potrzeby.