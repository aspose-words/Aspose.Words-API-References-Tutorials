---
title: Ładowanie plików tekstowych za pomocą Aspose.Words dla Java
linktitle: Ładowanie plików tekstowych za pomocą
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Odblokuj moc Aspose.Words dla Java. Dowiedz się, jak ładować dokumenty tekstowe, zarządzać listami, obsługiwać spacje i kontrolować kierunek tekstu.
type: docs
weight: 13
url: /pl/java/document-loading-and-saving/loading-text-files/
---

## Wprowadzenie do ładowania plików tekstowych za pomocą Aspose.Words dla Java

W tym przewodniku przyjrzymy się, jak ładować pliki tekstowe przy użyciu Aspose.Words dla Java i manipulować nimi jako dokumentami programu Word. Omówimy różne aspekty, takie jak wykrywanie list, obsługa spacji i kontrolowanie kierunku tekstu.

## Krok 1: Wykrywanie list

Aby załadować dokument tekstowy i wykryć listy, możesz wykonać następujące kroki:

```java
// Utwórz dokument w postaci zwykłego tekstu w postaci ciągu znaków z częściami, które można interpretować jako listy.
// Po załadowaniu pierwsze trzy listy będą zawsze wykrywane przez Aspose.Words,
// i Listy zostaną dla nich utworzone po załadowaniu.
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
//Czwarta lista, ze spacjami pomiędzy numerem listy a zawartością elementu listy,
// zostanie wykryty jako lista tylko wtedy, gdy „DetectNumberingWithWhitespaces” w obiekcie LoadOptions ma wartość true,
// aby uniknąć omyłkowego rozpoznania akapitów rozpoczynających się od liczb jako list.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// Załaduj dokument, stosując LoadOptions jako parametr i sprawdź wynik.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Ten kod demonstruje, jak załadować dokument tekstowy z różnymi formatami list i użyć`DetectNumberingWithWhitespaces` opcja prawidłowego wykrywania list.

## Krok 2: Obsługa opcji spacji

Aby kontrolować spacje początkowe i końcowe podczas ładowania dokumentu tekstowego, możesz użyć następującego kodu:

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

 W tym przykładzie ładujemy dokument tekstowy i przycinamy spacje początkowe i końcowe za pomocą`TxtLeadingSpacesOptions.TRIM` I`TxtTrailingSpacesOptions.TRIM`.

## Krok 3: Kontrolowanie kierunku tekstu

Aby określić kierunek tekstu podczas ładowania dokumentu tekstowego, możesz użyć następującego kodu:

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

Ten kod ustawia kierunek dokumentu na automatyczne wykrywanie (`DocumentDirection.AUTO`i ładuje dokument tekstowy z tekstem hebrajskim. W razie potrzeby możesz dostosować kierunek dokumentu.

## Kompletny kod źródłowy do ładowania plików tekstowych za pomocą Aspose.Words dla Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// Utwórz dokument w postaci zwykłego tekstu w postaci ciągu znaków z częściami, które można interpretować jako listy.
	// Po załadowaniu pierwsze trzy listy będą zawsze wykrywane przez Aspose.Words,
	// i Listy zostaną dla nich utworzone po załadowaniu.
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
	// Czwarta lista, ze spacjami pomiędzy numerem listy a zawartością elementu listy,
	// zostanie wykryty jako lista tylko wtedy, gdy „DetectNumberingWithWhitespaces” w obiekcie LoadOptions ma wartość true,
	// aby uniknąć omyłkowego rozpoznania akapitów rozpoczynających się od liczb jako list.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// Załaduj dokument, stosując LoadOptions jako parametr i sprawdź wynik.
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

## Wniosek

W tym przewodniku omówiliśmy, jak ładować pliki tekstowe za pomocą Aspose.Words dla Java, wykrywać listy, obsługiwać spacje i kontrolować kierunek tekstu. Techniki te umożliwiają efektywne manipulowanie dokumentami tekstowymi w aplikacjach Java.

## Często zadawane pytania

### Co to jest Aspose.Words dla Java?

Aspose.Words for Java to potężna biblioteka do przetwarzania dokumentów, która umożliwia programistom tworzenie, manipulowanie i konwertowanie dokumentów programu Word w aplikacjach Java. Zapewnia szeroką gamę funkcji do pracy z tekstem, tabelami, obrazami i innymi elementami dokumentu.

### Jak mogę rozpocząć pracę z Aspose.Words dla Java?

Aby rozpocząć korzystanie z Aspose.Words dla Java, wykonaj następujące kroki:
1. Pobierz i zainstaluj bibliotekę Aspose.Words dla Java.
2.  Zapoznaj się z dokumentacją pod adresem[Aspose.Words dla odniesienia do API Java](https://reference.aspose.com/words/java/)szczegółowe informacje i przykłady.
3. Zapoznaj się z przykładowym kodem i samouczkami, aby dowiedzieć się, jak efektywnie korzystać z biblioteki.

### Jak załadować dokument tekstowy za pomocą Aspose.Words dla Java?

 Aby załadować dokument tekstowy za pomocą Aspose.Words dla Java, możesz użyć`TxtLoadOptions` klasa i`Document` klasa. Upewnij się, że w razie potrzeby określono odpowiednie opcje obsługi spacji i kierunku tekstu. Szczegółowy przykład znajdziesz w przewodniku krok po kroku w tym artykule.

### Czy mogę przekonwertować załadowany dokument tekstowy na inne formaty?

 Tak, Aspose.Words for Java umożliwia konwersję załadowanego dokumentu tekstowego do różnych formatów, w tym DOCX, PDF i innych. Możesz skorzystać z`Document` klasa do wykonywania konwersji. Sprawdź dokumentację pod kątem konkretnych przykładów konwersji.

### Jak postępować ze spacjami w załadowanych dokumentach tekstowych?

 Możesz kontrolować sposób obsługi spacji początkowych i końcowych w załadowanych dokumentach tekstowych za pomocą`TxtLoadOptions` . Opcje takie jak`TxtLeadingSpacesOptions` I`TxtTrailingSpacesOptions`umożliwiają przycięcie lub zachowanie odstępów w razie potrzeby. Przykład można znaleźć w sekcji „Obsługa opcji przestrzeni” w tym przewodniku.

### Jakie znaczenie ma kierunek tekstu w Aspose.Words dla Java?

Kierunek tekstu jest niezbędny w przypadku dokumentów zawierających mieszane pisma lub języki, takie jak hebrajski czy arabski. Aspose.Words dla Java udostępnia opcje umożliwiające określenie kierunku tekstu, zapewniając prawidłowe renderowanie i formatowanie tekstu w tych językach. W sekcji „Kontrola kierunku tekstu” w tym przewodniku pokazano, jak ustawić kierunek tekstu.

### Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Words dla Java?

 Aby uzyskać dodatkowe zasoby, dokumentację i wsparcie, odwiedź stronę[Aspose.Words dla dokumentacji Java](https://reference.aspose.com/words/java/). Możesz także uczestniczyć w forach społeczności Aspose.Words lub skontaktować się z pomocą techniczną Aspose w celu uzyskania pomocy w przypadku konkretnych problemów lub zapytań.

### Czy Aspose.Words dla Java nadaje się do projektów komercyjnych?

Tak, Aspose.Words dla Java nadaje się zarówno do projektów osobistych, jak i komercyjnych. Oferuje opcje licencjonowania dostosowane do różnych scenariuszy użytkowania. Upewnij się, że zapoznałeś się z warunkami licencji i cenami na stronie internetowej Aspose, aby wybrać odpowiednią licencję dla swojego projektu.