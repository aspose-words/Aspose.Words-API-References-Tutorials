---
title: Zapisywanie dokumentów jako plików tekstowych w Aspose.Words dla Java
linktitle: Zapisywanie dokumentów jako plików tekstowych
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak zapisywać dokumenty jako pliki tekstowe w Aspose.Words dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku z przykładami kodu Java.
type: docs
weight: 24
url: /pl/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Wprowadzenie do zapisywania dokumentów jako plików tekstowych w Aspose.Words dla Java

W tym samouczku omówimy, jak zapisywać dokumenty jako pliki tekstowe przy użyciu biblioteki Aspose.Words dla Java. Aspose.Words to potężny interfejs API języka Java do pracy z dokumentami programu Word, zapewniający różne opcje zapisywania dokumentów w różnych formatach, w tym w postaci zwykłego tekstu. Omówimy kroki, które należy wykonać, aby to osiągnąć, i po drodze udostępnimy przykładowy kod Java.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Biblioteka Aspose.Words dla Java zintegrowana z Twoim projektem. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).
- Podstawowa znajomość programowania w języku Java.

## Krok 1: Utwórz dokument

Aby zapisać dokument jako plik tekstowy, musimy najpierw utworzyć dokument za pomocą Aspose.Words. Oto prosty fragment kodu Java umożliwiający utworzenie dokumentu z pewną zawartością:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

tym kodzie tworzymy nowy dokument i dodajemy do niego tekst, w tym tekst w różnych językach.

## Krok 2: Zdefiniuj opcje zapisywania tekstu

Następnie musimy zdefiniować opcje zapisywania tekstu, które określają, w jaki sposób dokument powinien zostać zapisany jako plik tekstowy. Możemy skonfigurować różne ustawienia, takie jak dodawanie znaków bidi, wcięcie listy i inne. Spójrzmy na dwa przykłady:

### Przykład 1: Dodawanie znaków BiDi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 W tym przykładzie tworzymy plik`TxtSaveOptions` obiekt i ustaw`AddBidiMarks`własność do`true` aby uwzględnić znaki bidi w wynikach tekstowych.

### Przykład 2: Używanie znaku tabulacji do wcięcia listy

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Tutaj konfigurujemy opcje zapisywania, aby używać znaku tabulacji do wcięcia listy z liczbą 1.

## Krok 3: Zapisz dokument jako tekst

Teraz, gdy zdefiniowaliśmy opcje zapisywania tekstu, możemy zapisać dokument jako plik tekstowy. Poniższy kod demonstruje, jak to zrobić:

```java
doc.save("output.txt", saveOptions);
```

 Zastępować`"output.txt"` z żądaną ścieżką pliku, w którym chcesz zapisać plik tekstowy.

## Kompletny kod źródłowy do zapisywania dokumentów jako plików tekstowych w Aspose.Words dla Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Utwórz listę z trzema poziomami wcięć.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Utwórz listę z trzema poziomami wcięć.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak zapisywać dokumenty jako pliki tekstowe w Aspose.Words dla Java. Omówiliśmy kroki tworzenia dokumentu, definiowania opcji zapisywania tekstu i zapisywania dokumentu w formacie tekstowym. Aspose.Words zapewnia dużą elastyczność w zakresie zapisywania dokumentów, umożliwiając dostosowanie wyników do konkretnych wymagań.

## Często zadawane pytania

### Jak dodać znaki bidi do tekstu wyjściowego?

 Aby dodać znaki bidi do tekstu wyjściowego, ustaw opcję`AddBidiMarks` własność`TxtSaveOptions` Do`true`. Na przykład:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Czy mogę dostosować znak wcięcia listy?

 Tak, możesz dostosować znak wcięcia listy, konfigurując`ListIndentation` własność`TxtSaveOptions`. Na przykład, aby użyć znaku tabulacji do wcięcia listy, możesz wykonać następujące czynności:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Czy Aspose.Words dla Java nadaje się do obsługi tekstu wielojęzycznego?

Tak, Aspose.Words for Java nadaje się do obsługi tekstu wielojęzycznego. Obsługuje różne języki i kodowania znaków, dzięki czemu jest wszechstronnym wyborem do pracy z dokumentami w różnych językach.

### Jak mogę uzyskać dostęp do większej dokumentacji i zasobów Aspose.Words dla Java?

 Obszerną dokumentację i zasoby dotyczące Aspose.Words for Java można znaleźć na stronie z dokumentacją Aspose:[Aspose.Words dla dokumentacji Java](https://reference.aspose.com/words/java/).

### Gdzie mogę pobrać Aspose.Words dla Java?

 Możesz pobrać bibliotekę Aspose.Words for Java ze strony internetowej Aspose:[Pobierz Aspose.Words dla Javy](https://releases.aspose.com/words/java/).