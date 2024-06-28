---
title: Dodawanie treści przy użyciu narzędzia DocumentBuilder w Aspose.Words dla Java
linktitle: Dodawanie treści przy użyciu narzędzia DocumentBuilder
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Tworzenie dokumentów głównych za pomocą Aspose.Words dla języka Java. Przewodnik krok po kroku dotyczący dodawania tekstu, tabel, obrazów i nie tylko. Twórz wspaniałe dokumenty Word bez wysiłku.
type: docs
weight: 26
url: /pl/java/document-manipulation/adding-content-using-documentbuilder/
---

## Wprowadzenie do dodawania treści przy użyciu narzędzia DocumentBuilder w Aspose.Words dla Java

W tym przewodniku krok po kroku odkryjemy, jak używać Aspose.Words for Java DocumentBuilder do dodawania różnych typów treści do dokumentu programu Word. Omówimy wstawianie tekstu, tabel, linii poziomych, pól formularzy, kodu HTML, hiperłączy, spisu treści, obrazów wbudowanych i pływających, akapitów i nie tylko. Zacznijmy!

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że w swoim projekcie masz skonfigurowaną bibliotekę Aspose.Words for Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

## Dodawanie tekstu

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw prosty akapit tekstowy
builder.write("This is a simple text paragraph.");

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie tabel

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Rozpocznij tworzenie stołu
Table table = builder.startTable();

// Wstaw komórki i treść
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Zakończ stół
builder.endTable();

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie linii poziomej

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw linię poziomą
builder.insertHorizontalRule();

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie pól formularza

### Pole formularza wprowadzania tekstu

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pole formularza wprowadzania tekstu
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

### Pole wyboru Pole formularza

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pole formularza pola wyboru
builder.insertCheckBox("CheckBox", true, true, 0);

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

### Pole formularza pola kombi

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Zdefiniuj elementy pola kombi
String[] items = { "Option 1", "Option 2", "Option 3" };

// Wstaw pole formularza pola kombi
builder.insertComboBox("DropDown", items, 0);

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie HTML-a

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw treść HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie hiperłączy

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw hiperłącze
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com”, fałsz);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodanie spisu treści

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw spis treści
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Dodaj treść dokumentu
// ...

// Zaktualizuj spis treści
doc.updateFields();

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie obrazów

### Obraz wbudowany

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw obraz osadzony
builder.insertImage("path/to/your/image.png");

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

### Pływający obraz

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pływający obraz
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Dodawanie akapitów

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ustaw formatowanie akapitu
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Wstaw akapit
builder.writeln("This is a formatted paragraph.");

// Zapisz dokument
doc.save("path/to/your/document.docx");
```

## Krok 10: Przesuwanie kursora

 Możesz kontrolować pozycję kursora w dokumencie, korzystając z różnych metod, np`moveToParagraph`, `moveToCell`i więcej. Oto przykład:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Przesuń kursor do określonego akapitu
builder.moveToParagraph(2, 0);

// Dodaj treść w nowej pozycji kursora
builder.writeln("This is the 3rd paragraph.");
```

Oto niektóre typowe operacje, które można wykonać przy użyciu Aspose.Words dla Java DocumentBuilder. Zapoznaj się z dokumentacją biblioteki, aby uzyskać bardziej zaawansowane funkcje i opcje dostosowywania. Udanego tworzenia dokumentów!


## Wniosek

W tym obszernym przewodniku zbadaliśmy możliwości Aspose.Words dla narzędzia DocumentBuilder Java w zakresie dodawania różnych typów treści do dokumentów programu Word. Omówiliśmy tekst, tabele, linie poziome, pola formularzy, kod HTML, hiperłącza, spis treści, obrazy, akapity i ruch kursora.

## Często zadawane pytania

### P: Co to jest Aspose.Words dla Java?

O: Aspose.Words for Java to biblioteka Java, która umożliwia programistom programowe tworzenie, modyfikowanie i manipulowanie dokumentami Microsoft Word. Zapewnia szeroką gamę funkcji do generowania, formatowania i wstawiania treści dokumentów.

### P: Jak mogę dodać spis treści do mojego dokumentu?

O: Aby dodać spis treści, użyj metody`DocumentBuilder` , aby wstawić pole spisu treści do dokumentu. Pamiętaj o zaktualizowaniu pól w dokumencie po dodaniu treści, aby wypełnić spis treści. Oto przykład:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pole spisu treści
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Dodaj treść dokumentu
// ...

// Zaktualizuj spis treści
doc.updateFields();
```

### P: Jak wstawić obrazy do dokumentu za pomocą Aspose.Words dla Java?

 Odp.: Możesz wstawiać obrazy, zarówno wbudowane, jak i swobodne, za pomocą`DocumentBuilder`. Oto przykłady obu:

#### Obraz wbudowany:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw obraz osadzony
builder.insertImage("path/to/your/image.png");
```

#### Pływający obraz:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pływający obraz
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### P: Czy mogę formatować tekst i akapity podczas dodawania treści?

 Odp.: Tak, możesz formatować tekst i akapity za pomocą`DocumentBuilder`. Możesz ustawić właściwości czcionki, wyrównanie akapitu, wcięcie i inne ustawienia. Oto przykład:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ustaw formatowanie czcionki i akapitu
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Wstaw sformatowany akapit
builder.writeln("This is a formatted paragraph.");
```

### P: Jak mogę przenieść kursor do określonego miejsca w dokumencie?

 Odp.: Możesz kontrolować pozycję kursora za pomocą metod takich jak`moveToParagraph`, `moveToCell`i więcej. Oto przykład:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Przesuń kursor do określonego akapitu
builder.moveToParagraph(2, 0);

// Dodaj treść w nowej pozycji kursora
builder.writeln("This is the 3rd paragraph.");
```

Oto kilka typowych pytań i odpowiedzi, które pomogą Ci rozpocząć pracę z Aspose.Words dla Java DocumentBuilder. Jeśli masz więcej pytań lub potrzebujesz dalszej pomocy, zapoznaj się z sekcją[dokumentacja biblioteki](https://reference.aspose.com/words/java/) lub poproś o pomoc społeczność Aspose.Words i zasoby wsparcia.