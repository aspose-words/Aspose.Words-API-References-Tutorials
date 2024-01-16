---
title: Wstaw obraz osadzony w dokumencie programu Word
linktitle: Wstaw obraz osadzony w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać obrazy w tekście w dokumentach programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/add-content-using-documentbuilder/insert-inline-image/
---
W tym kompleksowym samouczku dowiesz się, jak wstawiać obrazy wbudowane do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł dodawać obrazy bezpośrednio do tekstu swoich dokumentów.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument i narzędzie DocumentBuider
Aby rozpocząć, utwórz nowy dokument za pomocą klasy Document i zainicjuj obiekt DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw obraz osadzony
Następnie użyj metody InsertImage klasy DocumentBuilder, aby wstawić obraz osadzony w dokumencie. Podaj ścieżkę pliku obrazu jako parametr:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Krok 3: Zapisz dokument
Po wstawieniu obrazu inline należy zapisać dokument do pliku korzystając z metody Save klasy Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Przykładowy kod źródłowy do wstawiania obrazu wbudowanego przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do wstawiania obrazu wbudowanego przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak wstawiać obrazy wbudowane do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz bezproblemowo dodawać obrazy do tekstu swoich dokumentów.

Obrazy wbudowane są przydatne w różnych scenariuszach, takich jak dodawanie ilustracji, logo lub innych elementów wizualnych bezpośrednio do przepływu dokumentu.

### Często zadawane pytania dotyczące wstawiania obrazu wbudowanego w dokumencie programu Word

#### P: Czy mogę zmienić rozmiar obrazów wbudowanych w dokumencie programu Word?

Odp.: Tak, możesz zmienić rozmiar obrazów wbudowanych za pomocą Aspose.Words dla .NET. Po wstawieniu obrazu można manipulować jego rozmiarem, dostosowując właściwości szerokości i wysokości obiektu Shape reprezentującego obraz.

#### P: Czy można dodać tekst alternatywny do obrazów wbudowanych ze względów dostępności?

Odp.: Tak, możesz dodać tekst alternatywny do obrazów wbudowanych, aby zwiększyć dostępność. Aspose.Words dla .NET obsługuje dodawanie tekstu alternatywnego do obrazów, umożliwiając czytnikom ekranu i innym technologiom wspomagającym opisywanie zawartości obrazu użytkownikom niedowidzącym.

#### P: Czy mogę zastosować formatowanie lub style do obrazów wbudowanych?

Odp.: Absolutnie! Aspose.Words dla .NET zapewnia rozbudowane opcje formatowania obrazów wbudowanych. Do obrazów można zastosować różne style, obramowania, efekty i inne atrybuty formatowania, aby dopasować je do projektu wizualnego dokumentu.

#### P: Czy Aspose.Words dla .NET obsługuje wstawianie obrazów ze strumienia lub tablicy bajtów?

Odp.: Tak, możesz wstawiać obrazy wbudowane ze strumieni lub tablic bajtowych za pomocą Aspose.Words dla .NET. Umożliwia to pracę z obrazami ładowanymi ze źródeł zewnętrznych lub obrazami generowanymi dynamicznie.

#### P: Czy mogę wstawiać obrazy w określonych miejscach w treści tekstowej?

O: Tak, klasa DocumentBuilder w Aspose.Words dla .NET zapewnia precyzyjną kontrolę nad pozycją wstawiania obrazów wbudowanych. Możesz określić dokładną lokalizację w tekście, gdzie powinien zostać wstawiony obraz.