---
title: Wstaw pole TOA bez narzędzia do tworzenia dokumentów
linktitle: Wstaw pole TOA bez narzędzia do tworzenia dokumentów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pole TOA bez użycia narzędzia do tworzenia dokumentów w Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby skutecznie zarządzać cytatami prawnymi.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-toafield-without-document-builder/
---
## Wstęp

Tworzenie pola tabeli źródeł (TOA) w dokumencie programu Word może przypominać układanie złożonej układanki. Jednak przy pomocy Aspose.Words dla .NET proces staje się płynny i prosty. W tym artykule przeprowadzimy Cię przez kolejne etapy wstawiania pola TOA bez korzystania z narzędzia do tworzenia dokumentów, co ułatwi Ci zarządzanie cytatami i odniesieniami prawnymi w dokumentach programu Word.

## Warunki wstępne

Zanim zagłębisz się w samouczek, omówmy najważniejsze rzeczy, których będziesz potrzebować:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną najnowszą wersję. Można go pobrać z[Strona Aspose](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: IDE zgodne z platformą .NET, takie jak Visual Studio.
- Podstawowa znajomość języka C#: Pomocne będzie zrozumienie podstawowej składni i pojęć języka C#.
- Przykładowy dokument programu Word: Utwórz lub przygotuj przykładowy dokument, w którym chcesz wstawić pole TOA.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw z biblioteki Aspose.Words. Taka konfiguracja zapewnia dostęp do wszystkich klas i metod wymaganych do manipulowania dokumentami.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Podzielmy proces na proste, łatwe do wykonania kroki. Przeprowadzimy Cię przez każdy etap, wyjaśniając, co robi każdy fragment kodu i jak przyczynia się do tworzenia pola TOA.

## Krok 1: Zainicjuj dokument

 Najpierw musisz utworzyć instancję`Document` klasa. Ten obiekt reprezentuje dokument programu Word, nad którym pracujesz.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Ten kod inicjuje nowy dokument programu Word. Możesz o tym pomyśleć jako o utworzeniu pustego płótna, do którego dodasz swoją treść.

## Krok 2: Utwórz i skonfiguruj pole TA

Następnie dodamy pole TA (tabela źródeł). To pole zaznacza wpisy, które pojawią się w TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Chcemy wstawić pola TA i TOA w następujący sposób:
// { TA \c 1 \l "Wartość 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Oto zestawienie:
- Akapit para = nowy akapit (doc);: Tworzy nowy akapit w dokumencie.
-  FieldTA poleTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Dodaje pole TA do akapitu. The`FieldType.FieldTOAEntry` określa, że jest to pole wejściowe TOA.
- FieldTA.EntryCategory = "1";: Ustawia kategorię wpisu. Jest to przydatne do kategoryzowania różnych typów wpisów.
- FieldTA.LongCitation = "Wartość 0";: Określa długi tekst cytatu. To jest tekst, który pojawi się w TOA.
- doc.FirstSection.Body.AppendChild(para);: Dołącza akapit z polem TA do treści dokumentu.

## Krok 3: Dodaj pole TOA

Teraz wstawimy rzeczywiste pole TOA, które kompiluje wszystkie wpisy TA w tabeli.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

W tym kroku:
- FieldToa FieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Dodaje pole TOA do akapitu.
- FieldToa.EntryCategory = "1";: Filtruje wpisy tak, aby zawierały tylko te oznaczone kategorią "1".

## Krok 4: Zaktualizuj pole TOA

Po wstawieniu pola TOA należy je zaktualizować, aby odzwierciedlało najnowsze wpisy.

```csharp
fieldToa.Update();
```

Polecenie to odświeża pole TOA, zapewniając prawidłowe wyświetlenie wszystkich zaznaczonych wpisów w tabeli.

## Krok 5: Zapisz dokument

Na koniec zapisz dokument z nowo dodanym polem TOA.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Ta linia kodu zapisuje dokument w określonym katalogu. Pamiętaj o wymianie`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której chcesz zapisać plik.

## Wniosek

I masz to! Pomyślnie dodałeś pole TOA do dokumentu Word bez użycia narzędzia do tworzenia dokumentów. Wykonując poniższe kroki, możesz efektywnie zarządzać cytatami i tworzyć kompleksowe tabele autorytetów w swoich dokumentach prawnych. Aspose.Words dla .NET sprawia, że proces ten przebiega płynnie i wydajnie, zapewniając narzędzia do łatwej obsługi złożonych zadań związanych z dokumentami.

## Często zadawane pytania

### Czy mogę dodać wiele pól TA z różnymi kategoriami?
 Tak, możesz dodać wiele pól TA z różnymi kategoriami, ustawiając`EntryCategory`odpowiednio własność.

### Jak mogę dostosować wygląd TOA?
Możesz dostosować wygląd TOA, modyfikując właściwości pola TOA, takie jak formatowanie wpisów i etykiety kategorii.

### Czy możliwa jest automatyczna aktualizacja pola TOA?
 Chociaż możesz ręcznie zaktualizować pole TOA za pomocą`Update` metoda Aspose.Words nie obsługuje obecnie automatycznych aktualizacji zmian w dokumentach.

### Czy mogę programowo dodać pola TA w określonych częściach dokumentu?
Tak, możesz dodać pola TA w określonych miejscach, wstawiając je w odpowiednich akapitach lub sekcjach.

### Jak obsługiwać wiele pól TOA w jednym dokumencie?
 Możesz zarządzać wieloma polami TOA, przypisując różne`EntryCategory` wartości i zapewnienie, że każde pole TOA filtruje wpisy na podstawie swojej kategorii.