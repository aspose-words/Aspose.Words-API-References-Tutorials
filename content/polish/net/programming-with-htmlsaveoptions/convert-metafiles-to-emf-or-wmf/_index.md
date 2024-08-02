---
title: Konwertuj metapliki na format EMF lub WMF
linktitle: Konwertuj metapliki na format EMF lub WMF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konwersji metaplików do formatów EMF lub WMF podczas konwersji dokumentu do formatu HTML za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## Wstęp

Witamy w kolejnym głębokim zanurzeniu się w świat Aspose.Words dla .NET. Dzisiaj zajmiemy się ciekawą sztuczką: konwersją obrazów SVG do formatów EMF lub WMF w dokumentach Word. Może to brzmieć nieco technicznie, ale nie martw się. Pod koniec tego samouczka będziesz w tym profesjonalistą. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz pracę z Aspose.Words dla .NET, ten przewodnik krok po kroku przeprowadzi Cię przez wszystko, co musisz wiedzieć.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnijmy się, że mamy wszystko skonfigurowane. Oto, czego potrzebujesz:

1.  Aspose.Words dla biblioteki .NET: Upewnij się, że masz najnowszą wersję. Jeśli go nie masz, możesz go pobrać ze strony[Tutaj](https://releases.aspose.com/words/net/).
2. .NET Framework: Upewnij się, że na komputerze jest zainstalowana platforma .NET Framework.
3. Środowisko programistyczne: IDE takie jak Visual Studio ułatwi Ci życie.
4. Podstawowa znajomość języka C#: Nie musisz być ekspertem, ale podstawowa znajomość będzie pomocna.

Mam wszystko? Świetnie! Zacznijmy.

## Importuj przestrzenie nazw

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw. Jest to kluczowe, ponieważ mówi naszemu programowi, gdzie znaleźć klasy i metody, których będziemy używać.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Te przestrzenie nazw obejmują wszystko, od podstawowych funkcji systemowych po konkretną funkcjonalność Aspose.Words, której potrzebujemy w tym samouczku.

## Krok 1: Skonfiguruj katalog dokumentów

Zacznijmy od zdefiniowania ścieżki do katalogu Twoich dokumentów. Tutaj zostanie zapisany dokument programu Word po konwersji metaplików.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której chcesz zapisać dokument.

## Krok 2: Utwórz ciąg HTML za pomocą SVG

Następnie potrzebujemy ciągu HTML zawierającego obraz SVG, który chcemy przekonwertować. Oto prosty przykład:

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' szerokość='500' wysokość='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

Ten fragment kodu HTML zawiera podstawowy plik SVG z napisem „Witaj, świecie!”.

## Krok 3: Załaduj HTML za pomocą opcji ConvertSvgToEmf

 Teraz używamy`HtmlLoadOptions` aby określić, jak chcemy obsługiwać obrazy SVG w kodzie HTML. Ustawienie`ConvertSvgToEmf` Do`true` zapewnia konwersję obrazów SVG do formatu EMF.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

 Ten fragment kodu tworzy nowy plik`Document` obiekt, ładując do niego ciąg HTML z określonymi opcjami ładowania.

## Krok 4: Ustaw opcję HtmlSaveOptions dla formatu metapliku

 Aby zapisać dokument w poprawnym formacie metapliku, używamy`HtmlSaveOptions` . Tutaj ustawiamy`MetafileFormat` Do`HtmlMetafileFormat.Png` , ale możesz to zmienić na`Emf` Lub`Wmf` w zależności od potrzeb.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## Krok 5: Zapisz dokument

Na koniec zapisujemy dokument, korzystając z określonych opcji zapisywania.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

Spowoduje to zapisanie dokumentu w określonym katalogu z formatem metapliku przekonwertowanym zgodnie z definicją.

## Wniosek

masz to! Wykonując poniższe kroki, pomyślnie przekonwertowałeś obrazy SVG do formatów EMF lub WMF w dokumentach Word przy użyciu Aspose.Words dla .NET. Ta metoda jest przydatna, jeśli chodzi o zapewnienie zgodności i utrzymanie integralności wizualnej dokumentów na różnych platformach. Miłego kodowania!

## Często zadawane pytania

### Czy przy użyciu tej metody mogę konwertować inne formaty obrazów?
Tak, możesz konwertować różne formaty obrazów, odpowiednio dostosowując opcje ładowania i zapisywania.

### Czy konieczne jest użycie określonej wersji .NET Framework?
Aspose.Words dla .NET obsługuje wiele wersji .NET Framework, ale zawsze dobrze jest używać najnowszej wersji, aby uzyskać najlepszą kompatybilność i funkcje.

### Jaka jest zaleta konwersji SVG na EMF lub WMF?
Konwersja SVG na EMF lub WMF zapewnia zachowanie i prawidłowe renderowanie grafiki wektorowej w środowiskach, które mogą nie w pełni obsługiwać SVG.

### Czy mogę zautomatyzować ten proces dla wielu dokumentów?
Absolutnie! Możesz przeglądać wiele plików HTML, stosując ten sam proces w celu zautomatyzowania konwersji w przypadku przetwarzania wsadowego.

### Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Words dla .NET?
 Można znaleźć obszerną dokumentację[Tutaj](https://reference.aspose.com/words/net/) i uzyskaj wsparcie od społeczności Aspose[Tutaj](https://forum.aspose.com/c/words/8).