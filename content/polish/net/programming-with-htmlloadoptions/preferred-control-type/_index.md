---
title: Preferowany typ kontroli w dokumencie programu Word
linktitle: Preferowany typ kontroli w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący określania preferowanego typu kontroli w dokumencie Word podczas ładowania dokumentu HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlloadoptions/preferred-control-type/
---
Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z funkcji preferowanego typu kontroli w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz mógł zrozumieć, jak określić preferowany typ kontroli podczas ładowania dokumentu HTML.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj kod HTML

 Aby rozpocząć, musisz zdefiniować kod HTML, który chcesz załadować jako dokument. W tym przykładzie zdefiniowaliśmy`html` zmienna zawierająca kod HTML selektora z opcjami.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Krok 2: Ustaw opcje ładowania HTML

 Następnie tworzymy`HtmlLoadOptions` obiekt i ustaw`PreferredControlType`własność do`HtmlControlType.StructuredDocumentTag`. To mówi Aspose.Words, aby używał StructuredDocumentTags do reprezentowania HTML podczas ładowania.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Krok 3: Załaduj i zapisz dokument

 Używamy`Document` class do załadowania kodu HTML ze strumienia pamięci przy użyciu zdefiniowanych wcześniej opcji ładowania. Następnie zapisujemy dokument w określonym katalogu z rozszerzeniem`.docx`format pliku.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Przykładowy kod źródłowy preferowanego typu kontroli z Aspose.Words dla .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

To wszystko ! Pomyślnie określiłeś preferowany typ kontroli podczas ładowania dokumentu HTML za pomocą Aspose.Words dla .NET.

## Wniosek

 Postępując zgodnie z tym przewodnikiem krok po kroku, nauczyłeś się korzystać z funkcji „Preferowany typ kontroli” w Aspose.Words dla .NET, aby określić żądany typ kontroli podczas ładowania dokumentu HTML. Ustawianie`PreferredControlType`własność do`HtmlControlType.StructuredDocumentTag` pozwala Aspose.Words używać StructuredDocumentTags (SDT) w celu lepszej reprezentacji i przetwarzania treści HTML. Możesz także eksplorować inne typy kontroli, aby dostosować je do swoich konkretnych wymagań. Korzystanie z tej funkcji pomaga zapewnić dokładną i wydajną obsługę dokumentów HTML w aplikacji C# za pomocą Aspose.Words.

### Często zadawane pytania dotyczące preferowanego typu kontroli w dokumencie programu Word

#### P: Jaka jest funkcja „Preferowany typ kontroli” w Aspose.Words dla .NET?

O: Funkcja „Preferowany typ kontroli” umożliwia określenie preferowanego typu kontroli reprezentującej elementy HTML podczas ładowania dokumentu HTML. Pomaga w wyborze odpowiedniego typu kontroli dla lepszej reprezentacji i przetwarzania treści HTML.

#### P: Jak ustawić preferowany typ kontroli podczas ładowania dokumentu HTML?

 O: Aby ustawić preferowany typ kontroli, musisz utworzyć plik`HtmlLoadOptions` obiekt i ustaw go`PreferredControlType` właściwość do pożądanej`HtmlControlType` . W podanym przykładzie`HtmlControlType.StructuredDocumentTag` Jest używane.

#### P: Jakie jest znaczenie używania StructuredDocumentTags (SDT) jako preferowanego typu kontroli?

Odp.: StructuredDocumentTags (SDT) to elementy oparte na języku XML, których można używać do reprezentowania złożonej zawartości i elementów sterujących w dokumencie programu Word. Używanie SDT jako preferowanego typu kontroli może zapewnić lepszą zgodność i reprezentację treści HTML.

#### P: Jak mogę się upewnić, że Aspose.Words użyje preferowanego typu kontroli podczas ładowania dokumentu HTML?

 O: Ustawiając`PreferredControlType`własność do`HtmlControlType.StructuredDocumentTag`jak pokazano w przykładowym kodzie źródłowym, Aspose.Words użyje SDT do reprezentowania elementów HTML podczas ładowania dokumentu.

#### P: Czy mogę używać innych typów kontroli jako preferowanej opcji?

 Odp.: Tak, oprócz`HtmlControlType.StructuredDocumentTag` , Aspose.Words dla .NET obsługuje inne typy kontroli, takie jak`HtmlControlType.ContentControl`I`HtmlControlType.CustomXmlMarkup`.