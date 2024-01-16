---
title: Ucieczka z URI w dokumencie PDF
linktitle: Ucieczka z URI w dokumencie PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku Jak uciec od URI w dokumencie PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/escape-uri/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący sposobu ucieczki identyfikatora URI w dokumencie PDF za pomocą Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz mógł zrozumieć, jak wstawiać hiperłącza ze zmienionym Uri w dokumencie.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz dokument i narzędzie DocumentBuilder

 Następnie musimy utworzyć nowy`Document` obiekt i a`DocumentBuilder` obiekt do zbudowania dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw hiperłącza ze zmienionym Uri

 Użyj`InsertHyperlink` metoda`DocumentBuilder` obiekt, aby wstawić hiperłącza do dokumentu. Uri należy uciec za pomocą`Uri.EscapeUriString` funkcję pozwalającą uniknąć błędów formatowania.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test”), fałsz);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test”),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test”), fałsz);
```

## Krok 4: Zapisz dokument jako plik PDF

 Wreszcie możemy zapisać dokument jako plik PDF za pomocą`Save` metoda`Document` obiekt. Określ nazwę pliku wyjściowego.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

To wszystko ! Pomyślnie wstawiłeś hiperłącza ze zmienionymi identyfikatorami Uri do dokumentu przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy ucieczki Uri za pomocą Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", fałsz);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", fałsz);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Wniosek

W tym samouczku omówiliśmy, jak uciec od identyfikatorów URI w dokumencie PDF za pomocą Aspose.Words dla .NET. Uciekając od identyfikatorów URI, można uniknąć błędów formatowania i zapewnić poprawną interpretację i wyświetlanie hiperłączy w dokumencie PDF. Postępuj zgodnie z instrukcjami, aby wstawić hiperłącza ze zmienionymi identyfikatorami URI do dokumentu PDF. Koniecznie ucieknij.

### Często Zadawane Pytania

#### P: Jaki jest identyfikator URI ucieczki w dokumencie PDF i dlaczego jest on ważny?
Odp.: URI ucieczki w dokumencie PDF odnosi się do metody konwertowania znaków specjalnych w adresie URL na sekwencje ucieczki w celu uniknięcia błędów formatu. Jest to ważne, ponieważ znaki specjalne w adresie URL mogą zakłócać jego strukturę i prowadzić do błędnej interpretacji lub nieprawidłowego renderowania. Uciekając od znaków specjalnych, gwarantujemy, że adres URL zostanie poprawnie zinterpretowany i wyświetlony w dokumencie PDF.

#### P: Jak mogę użyć Aspose.Words dla .NET do ucieczki przed identyfikatorami URI w dokumencie PDF?
O: Aby uciec od identyfikatorów URI w dokumencie PDF przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` obiekt do zbudowania dokumentu.

 Użyj`InsertHyperlink` metoda`DocumentBuilder` obiekt, aby wstawić hiperłącza do dokumentu. Pamiętaj, aby uciec od identyfikatora URI za pomocą`Uri.EscapeUriString` funkcję pozwalającą uniknąć błędów formatowania.

 Użyj`Save` metoda`Document` obiekt, aby zapisać dokument w formacie PDF, podając nazwę pliku wyjściowego.

#### P: Jakie są zalety zmiany identyfikatorów URI w dokumencie PDF?
O: Korzyści z ucieczki identyfikatora URI w dokumencie PDF są następujące:

Zapobieganie błędom formatu: ucieczka URI pomaga zapobiegać błędom formatu spowodowanym znakami specjalnymi w adresie URL, zapewniając, że adres URL zostanie poprawnie zinterpretowany i wyświetlony w dokumencie PDF.

Zgodność z czytnikami plików PDF: URI ze zmianą znaczenia są na ogół dobrze obsługiwane przez czytniki plików PDF, zapewniając lepszą kompatybilność i spójne doświadczenie użytkownika.

#### P: Jakie znaki specjalne należy zmieniać w identyfikatorze URI?
 Odp.: Znaki specjalne, które należy zmienić w identyfikatorze URI, to: spacja, <, >, ", #,%, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.