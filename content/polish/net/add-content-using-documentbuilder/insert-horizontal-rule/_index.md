---
title: Wstaw linię poziomą w dokumencie programu Word
linktitle: Wstaw linię poziomą w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać poziome linie w dokumentach programu Word za pomocą Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
tym kompleksowym przykładzie dowiesz się, jak wstawić poziomą linię do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł dodawać do swoich dokumentów poziome linie w celu wizualnej separacji i organizacji.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument i narzędzie DocumentBuider
Aby rozpocząć, utwórz nowy dokument za pomocą klasy Document i zainicjuj obiekt DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw linię poziomą
Następnie za pomocą metody Writeln klasy DocumentBuilder dodaj tekst opisowy, a następnie wstaw linię poziomą:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Krok 3: Zapisz dokument
Po wstawieniu linii poziomej należy zapisać dokument do pliku przy pomocy metody Save klasy Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Przykładowy kod źródłowy dla wstawiania linii poziomej przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do wstawiania linii poziomej przy użyciu Aspose.Words dla .NET:
Linie poziome są przydatne w różnych scenariuszach, takich jak dzielenie sekcji, tworzenie przerw wizualnych lub wyróżnianie ważnych informacji.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Pamiętaj, aby dostosować kod do swoich konkretnych wymagań i w razie potrzeby wzbogacić go o dodatkowe funkcjonalności.

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak wstawić linię poziomą do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz wizualnie oddzielać i organizować dokumenty za pomocą linii poziomych.

### Często zadawane pytania dotyczące wstawiania linii poziomej w dokumencie programu Word

#### P: Czy mogę dostosować wygląd linii poziomej?

Odp.: Tak, absolutnie! Aspose.Words dla .NET udostępnia różne właściwości umożliwiające dostosowanie wyglądu linii poziomej. Możesz dostosować jego szerokość, wysokość, wyrównanie, kolor i cieniowanie, aby dopasować je do estetyki dokumentu.

#### P: Czy mogę dodać wiele reguł poziomych w jednym dokumencie?

Odp.: Oczywiście! Możesz wstawić dowolną liczbę linii poziomych w dokumencie programu Word za pomocą Aspose.Words dla .NET. Po prostu powtórz proces wstawiania, aby dodać wiele przerw wizualnych lub podziałów sekcji.

#### P: Czy linie poziome są kompatybilne z innymi formatami plików, takimi jak PDF?

O: Tak, linie poziome wstawione za pomocą Aspose.Words dla .NET są kompatybilne z różnymi formatami plików, w tym DOCX i PDF. Oznacza to, że możesz eksportować dokumenty w różnych formatach, zachowując zasady horyzontalne.

#### P: Czy mogę programowo wstawić linię poziomą w określonych miejscach dokumentu?

Odp.: Absolutnie! Aspose.Words dla .NET umożliwia programowe umieszczenie linii poziomej w określonych miejscach w dokumencie. Możesz kontrolować jego rozmieszczenie na podstawie zawartości i struktury dokumentu.

#### P: Czy Aspose.Words dla .NET jest odpowiedni zarówno dla aplikacji stacjonarnych, jak i internetowych?

O: Tak, Aspose.Words dla .NET jest wszechstronny i może być używany zarówno w aplikacjach stacjonarnych, jak i internetowych. Niezależnie od tego, czy tworzysz aplikację Windows, czy system internetowy, możesz bez wysiłku zintegrować bibliotekę.