---
title: Wywołanie zwrotne dzielenia
linktitle: Wywołanie zwrotne dzielenia
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać wywołania zwrotnego dzielenia wyrazów w Aspose.Words dla .NET do obsługi dzielenia wyrazów.
type: docs
weight: 10
url: /pl/net/working-with-hyphenation/hyphenation-callback/
---

W tym samouczku krok po kroku pokażemy, jak korzystać z funkcji wywołania zwrotnego dzielenia wyrazów w Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowane i skonfigurowane Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Zapisz przypomnienie o dzieleniu wyrazów

 Najpierw zarejestrujemy wywołanie zwrotne dzielenia wyrazów, używając niestandardowego`CustomHyphenationCallback` klasa. Dzięki temu będziemy mogli obsługiwać dzielenie wyrazów według naszych własnych zasad:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Upewnij się, że zaimplementowałeś`CustomHyphenationCallback` klasy zgodnie z Twoimi konkretnymi potrzebami.

## Krok 2: Załaduj dokument i zastosuj dzielenie wyrazów

Następnie załaduj dokument z określonego katalogu i podziel słowa za pomocą Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Krok 3: Obsługa błędów brakujących słowników

przypadku braku słownika dzielenia wyrazów przechwycimy odpowiedni wyjątek i wyświetlimy komunikat o błędzie:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Krok 4: Oczyść i wyłącz przypomnienie o dzieleniu wyrazów

Na koniec, dla zachowania czystości i wyłączenia przypomnienia o dzieleniu wyrazów, wykonaj następujące kroki:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Spowoduje to oczyszczenie i wyłączenie przypomnienia o dzieleniu wyrazów po zakończeniu przetwarzania.

Więc ! Pomyślnie użyłeś wywołania zwrotnego dzielenia wyrazów w Aspose.Words dla .NET.

### Przykładowy kod źródłowy wywołania zwrotnego dzielenia wyrazów w Aspose.Words dla .NET

```csharp
try
{
	 // Zarejestruj wywołanie zwrotne dzielenia wyrazów.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go tak, aby odpowiadał Twoim konkretnym potrzebom.

### Często zadawane pytania

#### P: Co to jest przypomnienie o sylabizacji w Aspose.Words?

Odp.: Przypomnienie o sylabizacji w Aspose.Words to funkcja, która pozwala dostosować sposób sylabizacji słów w dokumentach. Korzystając z przypomnienia o sylabizacji, możesz określić niestandardowe reguły sylabizacji słów, co może być przydatne w określonych językach lub w określonych scenariuszach, w których domyślna sylabizacja nie daje pożądanych rezultatów.

#### P: Jak ustawić przypomnienie o sylabizacji w Aspose.Words?

 O: Aby zdefiniować wywołanie zwrotne polegające na dzieleniu wyrazów w Aspose.Words, musisz utworzyć klasę, która implementuje`HyphenationCallback` interfejs i zaimplementuj`HandleWord()` metoda. Ta metoda będzie wywoływana dla każdego słowa napotkanego podczas sylabizacji. Możesz zastosować do niego niestandardowe reguły sylabizacji i zwrócić sylabizowane słowo. Następnie możesz powiązać wywołanie zwrotne dzielenia wyrazów za pomocą`Document.HyphenationCallback` własność Twojego dokumentu.

#### P: Jaka jest zaleta używania przypomnienia o sylabizacji w Aspose.Words?

Odp.: Zaletą korzystania z przypomnienia o sylabie w Aspose.Words jest możliwość dostosowania sposobu sylabizacji słów w dokumentach. Daje to większą kontrolę nad sylabizacją, szczególnie w przypadku określonych języków lub scenariuszy, w których domyślna sylabizacja nie daje pożądanych rezultatów. Do każdego słowa możesz zastosować określone reguły, aby uzyskać precyzyjną sylabizację zgodnie ze swoimi potrzebami.

#### P: W jakich typowych sytuacjach pomocne może być użycie przypomnienia o sylabizacji?

Odp.: Użycie wzmacniacza sylabizacji może być przydatne w kilku scenariuszach, takich jak:
- Sylabizacja słów w określonych językach, które mają określone zasady sylabizacji.
- Zastosowanie spersonalizowanych zasad sylabizacji akronimów lub słów technicznych.
- Dostosowanie sylabizacji do preferencji stylistycznych lub standardów typograficznych.

#### P: Jak mogę przetestować niestandardową sylabizację z przypomnieniem o sylabizacji w Aspose.Words?

 O: Aby przetestować niestandardową sylabizację z przypomnieniem o sylabizacji w Aspose.Words, możesz utworzyć dokument testowy zawierający słowa, dla których chcesz zastosować niestandardowe reguły sylabizacji. Następnie możesz ustawić niestandardowe wywołanie zwrotne sylabizacji, zadzwoń pod numer`Document.Range.Replace()` metodę zamiany słów w dokumencie i użyj metody`Hyphenate()` metoda`Hyphenation` class, aby uzyskać sylabizację słów. Następnie możesz sformatować sylabizowane słowa według potrzeb, na przykład dodając łączniki między sylabami.