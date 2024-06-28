---
title: Dziel wyrazy w językach
linktitle: Dziel wyrazy w językach
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dzielić wyrazy w różnych językach w dokumentach programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-hyphenation/hyphenate-words-of-languages/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak dzielić wyrazy w różnych językach w dokumentach programu Word za pomocą Aspose.Words dla .NET. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

Aby rozpocząć, upewnij się, że masz zainstalowane i skonfigurowane Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z oficjalnej strony.

## Krok 1: Inicjowanie obiektu dokumentu

 Najpierw zainicjuj`Document` obiekt, podając ścieżkę do dokumentu źródłowego zawierającego tekst w różnych językach:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Krok 2: Zapisywanie słowników dzielenia wyrazów

Następnie zapisz słowniki dzielenia wyrazów dla różnych języków, które chcesz przetworzyć. W tym przykładzie rejestrujemy słowniki dla amerykańskiego angielskiego i szwajcarskiego niemieckiego:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Upewnij się, że masz odpowiednie pliki słownika w swoim katalogu danych.

## Krok 3: Przetwarzanie słów przez dzielenie wyrazów

Teraz możesz używać funkcji dzielenia wyrazów do przetwarzania słów w różnych językach. Możesz użyć różnych metod`Document` Lub`DocumentBuilder` w zależności od Twoich konkretnych potrzeb.

```csharp
// Przykład: użycie metody Hyphenate narzędzia DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Krok 4: Zapisz dokument

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Więc ! Pomyślnie przetworzyłeś słowa, dzieląc je w różnych językach w dokumencie programu Word za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy do dzielenia wyrazów przy użyciu Aspose.Words dla .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go tak, aby odpowiadał Twoim konkretnym potrzebom.

### Często zadawane pytania

#### P: Jak mogę sylabizować słowo w określonym języku za pomocą Aspose.Words?

 Odp.: Aby sylabizować słowo w określonym języku za pomocą Aspose.Words, możesz użyć`Hyphenation` klasa i`Hyphenate()` metoda. Utwórz instancję`Hyphenation` class określając żądany język, a następnie wywołaj metodę`Hyphenate()` metoda przekazująca słowo do sylabizacji jako argument. W ten sposób otrzymasz sylaby słowa w określonym języku.

#### P: Jakich kodów językowych powinienem użyć, aby określić język sylabizacji w Aspose.Words?

O: Aby określić język sylabizacji w Aspose.Words, musisz użyć odpowiednich kodów językowych. Na przykład możesz użyć „en” dla języka angielskiego, „fr” dla języka francuskiego, „es” dla języka hiszpańskiego, „de” dla języka niemieckiego itp. Pełną listę obsługiwanych kodów języków znajdziesz w dokumentacji Aspose.Words.

#### P: Czy sylabizacja działa we wszystkich językach w Aspose.Words?

O: Sylabizacja w Aspose.Words zależy od reguł sylabizacji specyficznych dla języka. Chociaż Aspose.Words obsługuje szeroką gamę języków, niektóre języki mogą nie być obsługiwane lub sylabizacja może być dla nich niedostępna. Sprawdź dokumentację Aspose.Words, aby dowiedzieć się, które języki są obsługiwane w przypadku sylabizacji.