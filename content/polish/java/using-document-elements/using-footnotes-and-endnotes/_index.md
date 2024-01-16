---
title: Korzystanie z przypisów dolnych i końcowych w Aspose.Words dla Java
linktitle: Korzystanie z przypisów dolnych i końcowych
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Naucz się efektywnie korzystać z przypisów dolnych i końcowych w Aspose.Words dla Java. Popraw swoje umiejętności formatowania dokumentów już dziś!
type: docs
weight: 13
url: /pl/java/using-document-elements/using-footnotes-and-endnotes/
---

W tym samouczku przeprowadzimy Cię przez proces używania przypisów dolnych i końcowych w Aspose.Words dla Java. Przypisy dolne i końcowe to istotne elementy formatowania dokumentu, często używane w przypadku cytatów, odniesień i dodatkowych informacji. Aspose.Words dla Java zapewnia solidną funkcjonalność umożliwiającą bezproblemową pracę z przypisami dolnymi i końcowymi.

## 1. Wprowadzenie do przypisów dolnych i końcowych

Przypisy dolne i końcowe to adnotacje dostarczające dodatkowych informacji lub cytatów w dokumencie. Przypisy dolne pojawiają się na dole strony, natomiast przypisy końcowe są gromadzone na końcu sekcji lub dokumentu. Są powszechnie stosowane w artykułach akademickich, raportach i dokumentach prawnych w celu odniesienia się do źródeł lub wyjaśnienia treści.

## 2. Konfigurowanie środowiska

Zanim zaczniemy pracować z przypisami dolnymi i końcowymi, musisz skonfigurować środowisko programistyczne. Upewnij się, że masz zainstalowany i skonfigurowany interfejs API Aspose.Words for Java w swoim projekcie.

## 3. Dodawanie przypisów do dokumentu

Aby dodać przypisy do dokumentu, wykonaj następujące kroki:
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

public void getFootnoteOptions(){
    Document doc = new Document(dataDir + "Document.docx");
    
    // Określ liczbę kolumn, według których sformatowany jest obszar przypisów.
    doc.getFootnoteOptions().setColumns(3);
    doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
}
```

## 4. Modyfikowanie opcji przypisów

Możesz modyfikować opcje przypisów, aby dostosować ich wygląd i zachowanie. Oto jak:
```java
@Test
public void setFootnoteAndEndNotePosition() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    
    doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
    doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
}
```

## 5. Dodawanie przypisów końcowych do dokumentu

Dodawanie przypisów końcowych do dokumentu jest proste. Oto przykład:
```java
@Test
public void setEndnoteOptions() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    DocumentBuilder builder = new DocumentBuilder(doc);
    
    builder.write("Some text");
    builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
    
    EndnoteOptions option = doc.getEndnoteOptions();
    option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
    option.setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
}
```

## 6. Dostosowywanie ustawień przypisu końcowego

Możesz dodatkowo dostosować ustawienia przypisu końcowego, aby spełnić wymagania dokumentu.

## Kompletny kod źródłowy
```java
	string dataDir = "Your Document Directory";
	string outPath = "Your Output Directory";
	public void getFootnoteOptions(){
        Document doc = new Document(dataDir + "Document.docx");
        // Określ liczbę kolumn, według których sformatowany jest obszar przypisów.
        doc.getFootnoteOptions().setColumns(3);
        doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
    }
    @Test
    public void setFootnoteAndEndNotePosition() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
        doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
    }
    @Test
    public void setEndnoteOptions() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Some text");
        builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
        EndnoteOptions option = doc.getEndnoteOptions();
        option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
        option.setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
	}
```

## 7. Wnioski

W tym samouczku omówiliśmy, jak pracować z przypisami dolnymi i końcowymi w Aspose.Words dla Java. Funkcje te są nieocenione przy tworzeniu dokumentów o dobrze zorganizowanej strukturze z odpowiednimi cytatami i odniesieniami.

Teraz, gdy już nauczyłeś się korzystać z przypisów dolnych i końcowych, możesz ulepszyć formatowanie dokumentu i uczynić jego treść bardziej profesjonalną.

### Często Zadawane Pytania

### 1. Jaka jest różnica między przypisami dolnymi a przypisami końcowymi?
Przypisy dolne pojawiają się na dole strony, natomiast przypisy końcowe są gromadzone na końcu sekcji lub dokumentu.

### 2. Jak mogę zmienić położenie przypisów dolnych i końcowych?
 Możesz skorzystać z`setPosition` metoda zmiany położenia przypisów dolnych i końcowych.

### 3. Czy mogę dostosować formatowanie przypisów dolnych i końcowych?
Tak, możesz dostosować formatowanie przypisów dolnych i końcowych za pomocą Aspose.Words dla Java.

### 4. Czy przypisy dolne i końcowe są ważne w formatowaniu dokumentu?
Tak, przypisy dolne i końcowe są niezbędne do umieszczania odniesień i dodatkowych informacji w dokumentach.

Zachęcamy do poznania większej liczby funkcji Aspose.Words dla Java i zwiększenia możliwości tworzenia dokumentów. Miłego kodowania!