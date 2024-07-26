---
title: Jednostka miary
linktitle: Jednostka miary
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak skonfigurować funkcję jednostki miary w Aspose.Words dla .NET, aby zachować formatowanie dokumentu podczas konwersji ODT.
type: docs
weight: 10
url: /pl/net/programming-with-odtsaveoptions/measure-unit/
---
## Wstęp

Czy kiedykolwiek musiałeś konwertować dokumenty programu Word do różnych formatów, ale potrzebowałeś określonej jednostki miary dla swojego układu? Niezależnie od tego, czy masz do czynienia z calami, centymetrami czy punktami, zapewnienie integralności dokumentu podczas procesu konwersji ma kluczowe znaczenie. W tym samouczku omówimy, jak skonfigurować funkcję jednostki miary w Aspose.Words dla .NET. Ta zaawansowana funkcja zapewnia zachowanie formatowania dokumentu dokładnie tak, jak jest to potrzebne podczas konwersji do formatu ODT (tekst otwartego dokumentu).

## Warunki wstępne

Zanim zagłębisz się w kod, musisz wykonać kilka czynności:

1. Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną najnowszą wersję Aspose.Words dla .NET. Jeśli jeszcze go nie masz, możesz go pobrać ze strony[Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: IDE, takie jak Visual Studio, do pisania i wykonywania kodu C#.
3. Podstawowa znajomość języka C#: Zrozumienie podstaw języka C# pomoże ci postępować zgodnie z samouczkiem.
4. Dokument programu Word: Przygotuj przykładowy dokument programu Word, którego możesz użyć do konwersji.

## Importuj przestrzenie nazw

Zanim zaczniemy kodować, upewnijmy się, że zaimportowaliśmy niezbędne przestrzenie nazw. Dodaj te dyrektywy using na górze pliku kodu:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Skonfiguruj katalog dokumentów

Najpierw musisz zdefiniować ścieżkę do katalogu dokumentów. Tutaj znajduje się dokument programu Word i miejsce, w którym zostanie zapisany przekonwertowany plik.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Zastępować`"YOUR DOCUMENTS DIRECTORY"` z rzeczywistą ścieżką do katalogu. Dzięki temu Twój kod będzie wiedział, gdzie znaleźć dokument programu Word.

## Krok 2: Załaduj dokument Word

 Następnie musisz załadować dokument Word, który chcesz przekonwertować. Odbywa się to za pomocą`Document` klasa z Aspose.Words.

```csharp
// Załaduj dokument programu Word
Document doc = new Document(dataDir + "Document.docx");
```

Upewnij się, że dokument programu Word o nazwie „Document.docx” znajduje się w określonym katalogu.

## Krok 3: Skonfiguruj jednostkę miary

 Teraz skonfigurujmy jednostkę miary dla konwersji ODT. To tutaj dzieje się magia. Założymy`OdtSaveOptions` używać cali jako jednostki miary.

```csharp
// Konfiguracja opcji tworzenia kopii zapasowych za pomocą funkcji „Jednostka miary”.
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 W tym przykładzie ustawiamy jednostkę miary na cale. Można także wybrać inne jednostki, np`OdtSaveMeasureUnit.Centimeters` Lub`OdtSaveMeasureUnit.Points` w zależności od Twoich wymagań.

## Krok 4: Konwertuj dokument na ODT

 Na koniec przekonwertujemy dokument Word na format ODT, korzystając ze skonfigurowanego`OdtSaveOptions`.

```csharp
// Konwertuj dokument na ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Ta linia kodu zapisuje przekonwertowany dokument w określonym katalogu z zastosowaną nową jednostką miary.

## Wniosek

masz to! Wykonując poniższe kroki, możesz łatwo skonfigurować funkcję jednostki miary w Aspose.Words dla .NET, aby mieć pewność, że układ dokumentu zostanie zachowany podczas konwersji. Niezależnie od tego, czy pracujesz z calami, centymetrami czy punktami, ten samouczek pokaże Ci, jak z łatwością przejąć kontrolę nad formatowaniem dokumentu.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do programowej pracy z dokumentami programu Word. Umożliwia programistom tworzenie, modyfikowanie, konwertowanie i przetwarzanie dokumentów programu Word bez konieczności używania programu Microsoft Word.

### Czy mogę używać innych jednostek miary oprócz cali?
 Tak, Aspose.Words dla .NET obsługuje inne jednostki miary, takie jak centymetry i punkty. Można określić żądaną jednostkę za pomocą`OdtSaveMeasureUnit` wyliczenie.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Words dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Words dla .NET ze strony[Tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć dokumentację Aspose.Words dla .NET?
 Możesz uzyskać dostęp do obszernej dokumentacji Aspose.Words dla .NET pod adresem[ten link](https://reference.aspose.com/words/net/).

### Jak mogę uzyskać wsparcie dla Aspose.Words dla .NET?
 Aby uzyskać pomoc, możesz odwiedzić forum Aspose.Words pod adresem[ten link](https://forum.aspose.com/c/words/8).
