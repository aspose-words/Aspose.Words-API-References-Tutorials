---
title: Kierunek tekstu dokumentu
linktitle: Kierunek tekstu dokumentu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić kierunek tekstu dokumentu w programie Word przy użyciu Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku. Idealny do obsługi języków pisanych od prawej do lewej.
type: docs
weight: 10
url: /pl/net/programming-with-txtloadoptions/document-text-direction/
---
## Wstęp

Podczas pracy z dokumentami programu Word, szczególnie tymi zawierającymi wiele języków lub mającymi specjalne potrzeby formatowania, ustawienie kierunku tekstu może mieć kluczowe znaczenie. Na przykład w przypadku języków pisanych od prawej do lewej, takich jak hebrajski lub arabski, może zaistnieć potrzeba odpowiedniego dostosowania kierunku tekstu. W tym przewodniku omówimy, jak ustawić kierunek tekstu w dokumencie za pomocą Aspose.Words dla .NET. 

## Warunki wstępne

Zanim zagłębimy się w kod, upewnij się, że masz następujące elementy:

-  Biblioteka Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words dla .NET. Można go pobrać z[Strona Aspose](https://releases.aspose.com/words/net/).
- Visual Studio: środowisko programistyczne do pisania i wykonywania kodu C#.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# będzie korzystna przy pisaniu kodu.

## Importuj przestrzenie nazw

Na początek musisz zaimportować przestrzenie nazw niezbędne do pracy z Aspose.Words w swoim projekcie. Oto jak możesz to zrobić:

```csharp
using Aspose.Words;
using Aspose.Words.Loading;
```

Te przestrzenie nazw zapewniają dostęp do klas i metod potrzebnych do manipulowania dokumentami programu Word.

## Krok 1: Zdefiniuj ścieżkę do katalogu dokumentów

Najpierw ustaw ścieżkę do miejsca, w którym znajduje się dokument. Ma to kluczowe znaczenie dla prawidłowego ładowania i zapisywania plików.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której przechowywany jest dokument.

## Krok 2: Utwórz TxtLoadOptions z ustawieniem kierunku dokumentu

 Następnie musisz utworzyć instancję`TxtLoadOptions` i ustaw`DocumentDirection` nieruchomość. Mówi to Aspose.Words, jak postępować z kierunkiem tekstu w dokumencie.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };
```

 W tym przykładzie używamy`DocumentDirection.Auto` aby Aspose.Words automatycznie określił kierunek na podstawie treści.

## Krok 3: Załaduj dokument

 Teraz załaduj dokument za pomocą`Document` klasa i wcześniej zdefiniowana`loadOptions`.

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Tutaj,`"Hebrew text.txt"` to nazwa twojego pliku tekstowego. Upewnij się, że ten plik istnieje w określonym katalogu.

## Krok 4: Uzyskaj dostęp i sprawdź dwukierunkowe formatowanie akapitu

Aby potwierdzić, że kierunek tekstu jest ustawiony prawidłowo, przejdź do pierwszego akapitu dokumentu i sprawdź jego dwukierunkowe formatowanie.

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

Ten krok jest przydatny do debugowania i sprawdzania, czy kierunek tekstu w dokumencie został zastosowany zgodnie z oczekiwaniami.

## Krok 5: Zapisz dokument z nowymi ustawieniami

Na koniec zapisz dokument, aby zastosować i zachować zmiany.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Tutaj,`"WorkingWithTxtLoadOptions.DocumentTextDirection.docx"` to nazwa pliku wyjściowego. Pamiętaj, aby wybrać nazwę odzwierciedlającą wprowadzone zmiany.

## Wniosek

Ustawianie kierunku tekstu w dokumentach programu Word jest prostym procesem dzięki Aspose.Words dla .NET. Wykonując poniższe kroki, możesz łatwo skonfigurować sposób, w jaki dokument obsługuje tekst pisany od prawej do lewej lub od lewej do prawej. Niezależnie od tego, czy pracujesz z dokumentami wielojęzycznymi, czy też potrzebujesz sformatować kierunek tekstu dla określonych języków, Aspose.Words zapewnia solidne rozwiązanie spełniające Twoje potrzeby.

## Często zadawane pytania

###  Co to jest`DocumentDirection` property used for?

 The`DocumentDirection` nieruchomość w`TxtLoadOptions` określa kierunek tekstu w dokumencie. Można to ustawić`DocumentDirection.Auto`, `DocumentDirection.LeftToRight` , Lub`DocumentDirection.RightToLeft`.

### Czy mogę ustawić kierunek tekstu dla określonych akapitów zamiast dla całego dokumentu?

 Tak, możesz ustawić kierunek tekstu dla określonych akapitów za pomocą`ParagraphFormat.Bidi` własność, ale`TxtLoadOptions.DocumentDirection` Właściwość ustawia domyślny kierunek dla całego dokumentu.

###  Jakie formaty plików są obsługiwane przy ładowaniu`TxtLoadOptions`?

`TxtLoadOptions` służy głównie do ładowania plików tekstowych (.txt). W przypadku innych formatów plików użyj różnych klas, takich jak`DocLoadOptions` Lub`DocxLoadOptions`.

### Jak obsługiwać dokumenty zawierające mieszane wskazówki tekstowe?

 W przypadku dokumentów zawierających mieszane kierunki tekstu może zaistnieć potrzeba obsługi formatowania według akapitu. Skorzystaj z`ParagraphFormat.Bidi` właściwość, aby dostosować kierunek każdego akapitu według potrzeb.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Words dla .NET?

 Więcej szczegółów znajdziesz w[Aspose.Words dla dokumentacji .NET](https://reference.aspose.com/words/net/) . Możesz także eksplorować dodatkowe zasoby, takie jak[Pobierz link](https://releases.aspose.com/words/net/), [Kupić](https://purchase.aspose.com/buy), [Bezpłatny okres próbny](https://releases.aspose.com/), [Licencja tymczasowa](https://purchase.aspose.com/temporary-license/) , I[Wsparcie](https://forum.aspose.com/c/words/8).