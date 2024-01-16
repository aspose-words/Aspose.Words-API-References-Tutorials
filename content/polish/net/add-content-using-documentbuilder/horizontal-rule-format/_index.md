---
title: Format linii poziomej w dokumencie programu Word
linktitle: Format linii poziomej w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak formatować linie poziome w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/horizontal-rule-format/
---
tym kompleksowym przykładzie dowiesz się, jak sformatować linię poziomą w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł dostosować wyrównanie, szerokość, wysokość, kolor i inne właściwości linii poziomej.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz narzędzie DocumentBuilder i wstaw linię poziomą
Na początek utwórz obiekt DocumentBuilder i użyj metody InsertHorizontalRule, aby wstawić linię poziomą:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Krok 2: Uzyskaj dostęp do formatu linii poziomej
Następnie uzyskaj dostęp do właściwości HorizontalRuleFormat obiektu Shape, aby pobrać opcje formatowania:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Krok 3: Dostosuj opcje formatowania
Teraz możesz dostosować różne opcje formatowania linii poziomej. Można na przykład dostosować wyrównanie, szerokość, wysokość, kolor i cieniowanie:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Krok 4: Zapisz dokument
Po sformatowaniu linii poziomej zapisz dokument do pliku korzystając z metody Save obiektu Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Przykładowy kod źródłowy dla formatu reguły poziomej przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do formatowania linii poziomej przy użyciu Aspose.Words dla .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Pamiętaj, aby dostosować kod do swoich konkretnych wymagań i w razie potrzeby wzbogacić go o dodatkowe funkcjonalności.

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się formatować linię poziomą w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz dostosować wygląd linii poziomych, aby poprawić układ wizualny dokumentu.

Eksperymentuj z różnymi opcjami formatowania, aby uzyskać pożądany styl i efekt linii poziomych.

### Często zadawane pytania dotyczące formatu linii poziomej w dokumencie programu Word

#### P: Czy mogę zastosować różne kolory do linii poziomej?

Odp.: Absolutnie! Dzięki Aspose.Words dla .NET możesz łatwo dostosować kolor linii poziomej, ustawiając właściwość Color na żądaną wartość koloru. Dzięki temu możesz dopasować linię poziomą do ogólnego projektu dokumentu.

#### P: Czy można dostosować szerokość i wysokość linii poziomej?

O: Tak, masz pełną kontrolę nad szerokością i wysokością linii poziomej. Modyfikując właściwości SzerokośćPercent i Wysokość, można uzyskać żądane wymiary linii poziomej.

#### P: Czy mogę zmienić wyrównanie linii poziomej w dokumencie?

Odp.: Oczywiście! Aspose.Words dla .NET umożliwia określenie wyrównania linii poziomej przy użyciu właściwości Alignment. Możesz wybierać spośród różnych opcji, takich jak Środek, Lewo, Prawo i Wyrównanie.

#### P: Czy mogę zastosować cieniowanie lub kolor tła do linii poziomej?

Odp.: Tak, możesz dodać cieniowanie lub kolor tła do linii poziomej. Domyślnie właściwość NoShade jest ustawiona na true, ale można ustawić ją na false i zdefiniować cieniowanie przy użyciu odpowiednich metod.

#### P: Czy mogę wstawić wiele linii poziomych w jednym dokumencie?

Odp.: Absolutnie! Możesz wstawić wiele poziomych linii w dokumencie programu Word za pomocą Aspose.Words dla .NET. W razie potrzeby po prostu powtórz kroki z samouczka, aby dodać dowolną liczbę linii poziomych.