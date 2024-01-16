---
title: Dzielenie dokumentów na strony HTML w Aspose.Words dla Java
linktitle: Dzielenie dokumentów na strony HTML
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak dzielić dokumenty na strony HTML za pomocą Aspose.Words dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby uzyskać bezproblemową konwersję dokumentów.
type: docs
weight: 25
url: /pl/java/document-manipulation/splitting-documents-into-html-pages/
---

## Wprowadzenie do dzielenia dokumentów na strony HTML w Aspose.Words dla Java

W tym przewodniku krok po kroku odkryjemy, jak podzielić dokumenty na strony HTML za pomocą Aspose.Words dla Java. Aspose.Words to potężny interfejs API Java do pracy z dokumentami Microsoft Word, zapewniający rozbudowane funkcje manipulacji dokumentami, w tym możliwość konwertowania dokumentów do różnych formatów, w tym HTML.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Words dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

## Krok 1: Zaimportuj niezbędne pakiety

```java
import com.aspose.words.*;
import java.io.*;
import java.util.ArrayList;
```

## Krok 2: Utwórz metodę konwersji Worda na HTML

```java
class WordToHtmlConverter
{
    // Szczegóły implementacji konwersji Word na HTML.
    // ...
}
```

## Krok 3: Wybierz akapity nagłówka na początku tematu

```java
private ArrayList<Paragraph> selectTopicStarts()
{
    NodeCollection paras = mDoc.getChildNodes(NodeType.PARAGRAPH, true);
    ArrayList<Paragraph> topicStartParas = new ArrayList<Paragraph>();
    for (Paragraph para : (Iterable<Paragraph>) paras)
    {
        int style = para.getParagraphFormat().getStyleIdentifier();
        if (style == StyleIdentifier.HEADING_1)
            topicStartParas.add(para);
    }
    return topicStartParas;
}
```

## Krok 4: Wstaw podziały sekcji przed akapitami nagłówkowymi

```java
private void insertSectionBreaks(ArrayList<Paragraph> topicStartParas)
{
    DocumentBuilder builder = new DocumentBuilder(mDoc);
    for (Paragraph para : topicStartParas)
    {
        Section section = para.getParentSection();
        if (para != section.getBody().getFirstParagraph())
        {
            builder.moveTo(para.getFirstChild());
            builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
            section.getBody().getLastParagraph().remove();
        }
    }
}
```

## Krok 5: Podziel dokument na tematy

```java
private ArrayList<Topic> saveHtmlTopics() throws Exception
{
    ArrayList<Topic> topics = new ArrayList<Topic>();
    for (int sectionIdx = 0; sectionIdx < mDoc.getSections().getCount(); sectionIdx++)
    {
        Section section = mDoc.getSections().get(sectionIdx);
        String paraText = section.getBody().getFirstParagraph().getText();
        String fileName = makeTopicFileName(paraText);
        if ("".equals(fileName))
            fileName = "UNTITLED SECTION " + sectionIdx;
        fileName = mDstDir + fileName + ".html";
        String title = makeTopicTitle(paraText);
        if ("".equals(title))
            title = "UNTITLED SECTION " + sectionIdx;
        Topic topic = new Topic(title, fileName);
        topics.add(topic);
        saveHtmlTopic(section, topic);
    }
    return topics;
}
```

## Krok 6: Zapisz każdy temat jako plik HTML

```java
private void saveHtmlTopic(Section section, Topic topic) throws Exception
{
    Document dummyDoc = new Document();
    dummyDoc.removeAllChildren();
    dummyDoc.appendChild(dummyDoc.importNode(section, true, ImportFormatMode.KEEP_SOURCE_FORMATTING));
    dummyDoc.getBuiltInDocumentProperties().setTitle(topic.getTitle());
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    {
        saveOptions.setPrettyFormat(true);
        saveOptions.setAllowNegativeIndent(true);
        saveOptions.setExportHeadersFootersMode(ExportHeadersFootersMode.NONE);
    }
    dummyDoc.save(topic.getFileName(), saveOptions);
}
```

## Krok 7: Wygeneruj spis treści dla tematów

```java
private void saveTableOfContents(ArrayList<Topic> topics) throws Exception
{
    Document tocDoc = new Document(mTocTemplate);
    tocDoc.getMailMerge().setFieldMergingCallback(new HandleTocMergeField());
    tocDoc.getMailMerge().executeWithRegions(new TocMailMergeDataSource(topics));
    tocDoc.save(mDstDir + "contents.html");
}
```

Teraz, gdy opisaliśmy kroki, możesz zaimplementować każdy krok w swoim projekcie Java, aby podzielić dokumenty na strony HTML za pomocą Aspose.Words for Java. Ten proces umożliwi Ci utworzenie uporządkowanej reprezentacji HTML Twoich dokumentów, dzięki czemu będą one bardziej dostępne i przyjazne dla użytkownika.

## Wniosek

W tym obszernym przewodniku omówiliśmy proces dzielenia dokumentów na strony HTML za pomocą Aspose.Words dla Java. Wykonując opisane czynności, możesz skutecznie konwertować dokumenty programu Word do formatu HTML, dzięki czemu Twoje treści będą bardziej dostępne w Internecie.

## Często zadawane pytania

### Jak zainstalować Aspose.Words dla Java?

 Aby zainstalować Aspose.Words dla Java, możesz pobrać bibliotekę z[Tutaj](https://releases.aspose.com/words/java/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

### Czy mogę dostosować dane wyjściowe HTML?

 Tak, możesz dostosować wyjście HTML, dostosowując opcje zapisywania w pliku`HtmlSaveOptions` klasa. Dzięki temu możesz kontrolować formatowanie i wygląd generowanych plików HTML.

### Jakie wersje programu Microsoft Word są obsługiwane przez Aspose.Words dla Java?

Aspose.Words for Java obsługuje szeroką gamę formatów dokumentów Microsoft Word, w tym DOC, DOCX, RTF i inne. Jest kompatybilny z różnymi wersjami Microsoft Word.

### Jak mogę obsługiwać obrazy w przekonwertowanym formacie HTML?

Aspose.Words for Java może obsługiwać obrazy w przekonwertowanym formacie HTML, zapisując je jako osobne pliki w tym samym folderze, co plik HTML. Zapewnia to prawidłowe wyświetlanie obrazów w wynikach HTML.

### Czy dostępna jest wersja próbna Aspose.Words dla Java?

Tak, możesz poprosić o bezpłatną wersję próbną Aspose.Words dla Java ze strony internetowej Aspose, aby ocenić jej funkcje i możliwości przed zakupem licencji.