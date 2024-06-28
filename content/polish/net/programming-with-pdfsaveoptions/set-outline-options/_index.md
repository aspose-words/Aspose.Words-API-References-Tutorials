---
title: Ustaw opcje konspektu w dokumencie PDF
linktitle: Ustaw opcje konspektu w dokumencie PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący ustawiania opcji konspektu w dokumencie PDF za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/set-outline-options/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z funkcji ustawiania opcji konspektu w celu określenia rozmiaru metapliku w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz w stanie zrozumieć, jak ustawić opcje konspektu w dokumencie i wygenerować plik PDF z odpowiednimi opcjami konspektu.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Prześlij dokument

Następnie musimy załadować dokument, który chcemy przetworzyć. W tym przykładzie zakładamy, że dokument nazywa się „Rendering.docx” i znajduje się w określonym katalogu dokumentów.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania jako PDF za pomocą opcji planu

Aby ustawić opcje konspektu w wygenerowanym pliku PDF, musimy skonfigurować plik`PdfSaveOptions` obiekt. Możemy ustawić liczbę poziomów konspektu nagłówka (`HeadingsOutlineLevels`) i liczbę rozwiniętych poziomów konspektu (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Krok 4: Zapisz dokument jako plik PDF z opcjami konspektu

Wreszcie możemy zapisać dokument w formacie PDF, korzystając z wcześniej skonfigurowanych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

To wszystko ! Pomyślnie ustawiłeś opcje konspektu w dokumencie i wygenerowałeś plik PDF z odpowiednimi opcjami konspektu za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy do ustawiania opcji planu na rozmiar metapliku za pomocą Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Wniosek

W tym samouczku wyjaśniliśmy, jak ustawić opcje konspektu w dokumencie PDF za pomocą Aspose.Words dla .NET. Korzystając z opisanych kroków, możesz łatwo określić poziomy nagłówków i konspektu w swoim dokumencie oraz wygenerować plik PDF z odpowiednimi opcjami konspektu. Korzystaj z opcji konspektu, aby ulepszyć strukturę i nawigację w dokumentach PDF za pomocą Aspose.Words dla .NET.

### Często Zadawane Pytania

#### P: Jaka jest opcja konspektu w dokumencie PDF?
Odp.: Opcja konspektu w dokumencie PDF odnosi się do hierarchicznej struktury zawartości dokumentu. Umożliwia utworzenie interaktywnego spisu treści i ułatwia nawigację po dokumencie. Opcje konspektu określają poziom tytułu i podtytułu, który ma zostać uwzględniony w konspekcie oraz poziom szczegółowości wyświetlanej w wygenerowanym konspekcie.

#### P: Jak mogę ustawić opcje konspektu w dokumencie PDF przy użyciu Aspose.Words dla .NET?
O: Aby ustawić opcje konspektu w dokumencie PDF za pomocą Aspose.Words dla .NET, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu, w którym znajdują się Twoje dokumenty, zastępując`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument, który chcesz przekonwertować do formatu PDF za pomocą`Document` class i określ ścieżkę do dokumentu w określonym katalogu dokumentów.

 Skonfiguruj opcje zapisywania jako PDF, tworząc instancję pliku`PdfSaveOptions` klasy i używając`OutlineOptions` właściwość, aby ustawić opcje konturu. Możesz określić liczbę poziomów nagłówków, które mają zostać uwzględnione w konspekcie, za pomocą opcji`HeadingsOutlineLevels` właściwość i liczbę rozwiniętych poziomów konspektu za pomocą`ExpandedOutlineLevels` nieruchomość.

 Zapisz dokument w formacie PDF za pomocą`Save` metoda`Document` class określając ścieżkę i opcje zapisu.

#### P: Do czego służy opcja planu w dokumencie PDF?
Odp.: Opcja konspektu w dokumencie PDF umożliwia utworzenie hierarchicznej struktury treści, co ułatwia poruszanie się po dokumencie i dostęp do różnych jego sekcji. Dzięki temu użytkownicy mogą szybko przeskakiwać do określonych części dokumentu, klikając wpisy w spisie treści lub konspekcie. Opcja konspektu poprawia również wygodę czytania, zapewniając przegląd ogólnej struktury dokumentu.
