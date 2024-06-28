---
title: Zapisywanie dokumentów jako Markdown w Aspose.Words dla Java
linktitle: Zapisywanie dokumentów jako Markdown
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak konwertować dokumenty programu Word do języka Markdown za pomocą Aspose.Words dla języka Java. Ten przewodnik krok po kroku opisuje wyrównywanie tabeli, obsługę obrazów i nie tylko.
type: docs
weight: 18
url: /pl/java/document-loading-and-saving/saving-documents-as-markdown/
---

## Wprowadzenie do zapisywania dokumentów jako Markdown w Aspose.Words dla Java

W tym przewodniku krok po kroku pokażemy, jak zapisywać dokumenty w formacie Markdown przy użyciu Aspose.Words dla Java. Markdown to lekki język znaczników powszechnie używany do formatowania dokumentów tekstowych. Dzięki Aspose.Words dla Java możesz łatwo konwertować dokumenty Word do formatu Markdown. Omówimy różne aspekty zapisywania plików Markdown, w tym wyrównanie zawartości tabeli i obsługę obrazów.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Words dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

## Krok 1: Tworzenie dokumentu Word

Zacznijmy od utworzenia dokumentu Word, który później przekonwertujemy do formatu Markdown. Możesz dostosować ten dokument do swoich wymagań.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw tabelę zawierającą dwie komórki
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// Zapisz dokument jako Markdown
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 W tym przykładzie tworzymy prostą tabelę z dwiema komórkami i ustawiamy wyrównanie akapitów w tych komórkach. Następnie zapisujemy dokument jako Markdown za pomocą`MarkdownSaveOptions`.

## Krok 2: Dostosuj wyrównanie zawartości tabeli

Aspose.Words for Java pozwala dostosować wyrównanie zawartości tabeli podczas zapisywania jako Markdown. Możesz wyrównać zawartość tabeli do lewej, prawej, do środka lub pozwolić, aby została ustalona automatycznie na podstawie pierwszego akapitu w każdej kolumnie tabeli.

Oto jak dostosować wyrównanie zawartości tabeli:

```java
// Ustaw wyrównanie zawartości tabeli do lewej
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// Ustaw wyrównanie zawartości tabeli do prawej
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// Ustaw wyrównanie zawartości tabeli na środek
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//Ustaw wyrównanie zawartości tabeli na automatyczne (określane przez pierwszy akapit)
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 Zmieniając`TableContentAlignment` możesz kontrolować sposób wyrównywania zawartości tabel podczas konwersji do Markdown.

## Krok 3: Obsługa obrazów

 Aby uwzględnić obrazy w dokumencie Markdown, musisz określić folder, w którym znajdują się obrazy. Aspose.Words dla Java pozwala ustawić folder obrazów w`MarkdownSaveOptions`.

Oto jak ustawić folder obrazów i zapisać dokument z obrazami:

```java
// Załaduj dokument zawierający obrazy
Document doc = new Document("document_with_images.docx");

// Ustaw ścieżkę folderu obrazów
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// Zapisz dokument z obrazami
doc.save("document_with_images.md", saveOptions);
```

 Pamiętaj o wymianie`"document_with_images.docx"` ze ścieżką do dokumentu programu Word zawierającego obrazy i`"images_folder/"` z rzeczywistą ścieżką do folderu, w którym przechowywane są obrazy.

## Kompletny kod źródłowy do zapisywania dokumentów jako Markdown w Aspose.Words dla Java

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// Wyrównuje wszystkie akapity wewnątrz tabeli.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// Wyrównanie w tym przypadku zostanie wzięte z pierwszego akapitu w odpowiedniej kolumnie tabeli.
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## Wniosek

tym przewodniku omówiliśmy, jak zapisywać dokumenty w formacie Markdown przy użyciu Aspose.Words dla Java. Omówiliśmy tworzenie dokumentu Word, dostosowywanie wyrównania zawartości tabeli i obsługę obrazów w plikach Markdown. Możesz teraz skutecznie konwertować dokumenty programu Word do formatu Markdown, dzięki czemu będą odpowiednie dla różnych platform wydawniczych i potrzeb związanych z dokumentacją.

## Często zadawane pytania

### Jak zainstalować Aspose.Words dla Java?

 Aspose.Words for Java można zainstalować, dołączając bibliotekę do projektu Java. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/words/java/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

### Czy mogę konwertować złożone dokumenty Word z tabelami i obrazami do Markdown?

Tak, Aspose.Words for Java obsługuje konwersję złożonych dokumentów Word z tabelami, obrazami i różnymi elementami formatowania do Markdown. Możesz dostosować wyniki Markdown do złożoności dokumentu.

### Jak mogę obsługiwać obrazy w plikach Markdown?

 Aby dołączyć obrazy do plików Markdown, ustaw ścieżkę folderu obrazów za pomocą`setImagesFolder`metoda w`MarkdownSaveOptions`. Upewnij się, że pliki obrazów są przechowywane w określonym folderze, a Aspose.Words for Java odpowiednio obsłuży odniesienia do obrazów.

### Czy dostępna jest wersja próbna Aspose.Words dla Java?

Tak, możesz pobrać wersję próbną Aspose.Words dla Java ze strony internetowej Aspose. Wersja próbna umożliwia ocenę możliwości biblioteki przed zakupem licencji.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji?

 Więcej przykładów, dokumentacji i szczegółowych informacji na temat Aspose.Words dla Java można znaleźć na stronie[dokumentacja](https://reference.aspose.com/words/java/).