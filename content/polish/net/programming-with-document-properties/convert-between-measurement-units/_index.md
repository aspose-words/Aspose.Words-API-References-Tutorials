---
title: Konwersja między jednostkami miary
linktitle: Konwersja między jednostkami miary
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący konwersji jednostek miary w dokumencie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-document-properties/convert-between-measurement-units/
---

W tym samouczku przeprowadzimy Cię przez kod źródłowy C#, aby konwertować jednostki miary za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia określenie marginesów, odległości nagłówka i stopki itp. w różnych jednostkach miary.

## Krok 1: Konfiguracja projektu

Aby rozpocząć, utwórz nowy projekt C# w swoim ulubionym środowisku IDE. Upewnij się, że w Twoim projekcie znajduje się odwołanie do biblioteki Aspose.Words for .NET.

## Krok 2: Tworzenie dokumentu i konstruktora

W tym kroku utworzymy nowy dokument i zainicjujemy konstruktor. Użyj następującego kodu:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Skonfiguruj jednostki miary

Teraz przeliczymy wartości marginesów, odległości nagłówka i stopki itp. na różne jednostki miary. Użyj poniższego kodu, aby określić wartości w określonych jednostkach miary:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Ten kod używa`ConvertUtil` klasa Aspose.Words do konwersji określonych wartości na cale (`InchToPoint`). Możesz także skorzystać z innych metod konwersji dostępnych w pliku`ConvertUtil` class do konwersji wartości na inne jednostki miary.

### Przykładowy kod źródłowy konwersji między jednostkami miary przy użyciu Aspose.Words dla .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Nauczyłeś się teraz, jak konwertować jednostki miary podczas określania marginesów, odległości nagłówka i stopki itp. w dokumencie przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz łatwo określić wartości w żądanych jednostkach miary we własnych dokumentach.