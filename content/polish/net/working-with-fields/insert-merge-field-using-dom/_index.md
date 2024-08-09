---
title: Wstaw pole scalania za pomocą DOM
linktitle: Wstaw pole scalania za pomocą DOM
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać i konfigurować pola scalania w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając z tego wszechstronnego samouczka krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-merge-field-using-dom/
---
## Wstęp

Jeśli pracujesz z przetwarzaniem dokumentów w .NET, prawdopodobnie natknąłeś się na Aspose.Words. Ta potężna biblioteka oferuje szeroką gamę funkcji do programowego manipulowania dokumentami programu Word. W tym samouczku skupimy się na jednej konkretnej funkcji: wstawieniu pola scalania przy użyciu modelu obiektowego dokumentu (DOM) w Aspose.Words dla .NET. Ten przewodnik przeprowadzi Cię przez każdy krok, od skonfigurowania środowiska po wstawienie i aktualizację pola scalania w dokumencie programu Word.

## Warunki wstępne

Zanim zagłębisz się w kod, upewnij się, że masz wszystko, czego potrzebujesz, wraz z tym samouczkiem.

1. Podstawowa znajomość języka C#: Powinieneś czuć się komfortowo w programowaniu w języku C#.
2. Zainstalowany program Visual Studio: Upewnij się, że na komputerze jest zainstalowany program Visual Studio lub inne środowisko C# IDE.
3.  Aspose.Words dla .NET: Pobierz i zainstaluj najnowszą wersję Aspose.Words dla .NET ze strony[Wydania](https://releases.aspose.com/words/net/).
4.  Ważna licencja: Jeśli nie masz licencji, możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) do oceny.

## Krok 1: Skonfiguruj swój projekt

Na początek skonfigurujmy nowy projekt w Visual Studio.

1. Otwórz Visual Studio.
2. Utwórz nowy projekt: Przejdź do Plik > Nowy > Projekt. Wybierz aplikację konsolową C#.
3. Nazwij swój projekt: nadaj swojemu projektowi znaczącą nazwę i kliknij Utwórz.

## Krok 2: Zainstaluj Aspose.Words

Aby używać Aspose.Words, musisz dodać go do swojego projektu. Można to zrobić za pomocą Menedżera pakietów NuGet.

1. Otwórz Menedżera pakietów NuGet: kliknij projekt prawym przyciskiem myszy w Eksploratorze rozwiązań, a następnie wybierz opcję Zarządzaj pakietami NuGet.
2. Wyszukaj Aspose.Words: w Menedżerze pakietów NuGet wyszukaj „Aspose.Words”.
3. Zainstaluj pakiet: Kliknij Zainstaluj, aby dodać Aspose.Words do swojego projektu.

## Krok 3: Importuj przestrzenie nazw

Aby rozpocząć korzystanie z Aspose.Words, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Oto jak możesz to zrobić:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Krok 4: Zainicjuj swój dokument

Teraz, gdy wszystko jest skonfigurowane, utwórzmy nowy dokument Word i zainicjuj DocumentBuilder.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i narzędzie DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 5: Przesuń kursor do określonego akapitu

Następnie musimy przesunąć kursor do konkretnego akapitu w dokumencie, w którym chcemy wstawić pole scalania.

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## Krok 6: Wstaw pole scalania

 Wstawianie pola scalającego jest proste. Będziemy korzystać z`InsertField` metoda`DocumentBuilder` klasa.

```csharp
// Wstaw pole scalania pól.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Krok 7: Skonfiguruj pole scalania

Po wstawieniu pola scalania możesz ustawić różne właściwości, aby skonfigurować je zgodnie ze swoimi potrzebami.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Krok 8: Zaktualizuj i zapisz dokument

Na koniec zaktualizuj pole, aby upewnić się, że wszystkie ustawienia zostały zastosowane, i zapisz dokument.

```csharp
// Zaktualizuj pole.
field.Update();

// Zapisz dokument.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Wniosek

Wykonując poniższe kroki, możesz łatwo wstawiać i konfigurować pola scalania w dokumencie programu Word przy użyciu Aspose.Words dla .NET. W tym samouczku omówiono podstawowe kroki od skonfigurowania środowiska do zapisania ostatecznego dokumentu. Dzięki Aspose.Words możesz zautomatyzować złożone zadania przetwarzania dokumentów, dzięki czemu Twoje aplikacje .NET będą potężniejsze i wydajniejsze.

## Często zadawane pytania

###  Co to jest pole scalania?
Pole scalania to element zastępczy w dokumencie, który można dynamicznie zastępować danymi ze źródła danych, takiego jak baza danych lub plik CSV.

###  Czy mogę używać Aspose.Words za darmo?
 Aspose.Words oferuje bezpłatną wersję próbną, którą możesz pobrać[Tutaj](https://releases.aspose.com/). W przypadku długotrwałego użytkowania konieczne będzie wykupienie licencji.

###  Jak uzyskać tymczasową licencję na Aspose.Words?
 Licencję tymczasową można uzyskać ze strony internetowej Aspose[Tutaj](https://purchase.aspose.com/temporary-license/).

### Jakie wersje .NET są obsługiwane przez Aspose.Words?
Aspose.Words obsługuje wiele wersji .NET, w tym .NET Framework, .NET Core i .NET Standard.

###  Gdzie mogę znaleźć dokumentację API dla Aspose.Words?
 Dostępna jest dokumentacja API[Tutaj](https://reference.aspose.com/words/net/).