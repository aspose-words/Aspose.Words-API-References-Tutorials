---
title: Obraz
linktitle: Obraz
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić i dostosować obraz za pomocą Aspose.Words dla .NET Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/image/
---

tym przykładzie wyjaśnimy, jak używać funkcji obrazu w Aspose.Words dla .NET. Obrazy umożliwiają wstawianie ilustracji i grafik do dokumentu.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Wstawianie obrazu

 Możemy wstawić obraz za pomocą`Shape` class i określenie typu obrazu, tutaj`ShapeType.Image` . Ustawiamy także typ zawijania obrazu`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Krok 3: Dostosowywanie obrazu

 Dostosowujemy obraz, podając na przykład jego pełną ścieżkę`"/attachment/1456/pic001.png"`i dodanie tytułu do obrazu.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Przykładowy kod źródłowy obrazów z Aspose.Words dla .NET

```csharp
// Użyj narzędzia do tworzenia dokumentów, aby dodać treść do dokumentu.
DocumentBuilder builder = new DocumentBuilder();

// Umieść obraz.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Gratulacje! Nauczyłeś się teraz, jak korzystać z funkcji obrazów w Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak mogę wstawić obraz z pliku lokalnego do Aspose.Words?

 O: Aby wstawić obraz z pliku lokalnego do Aspose.Words, możesz użyć metody`Shape` klasa i`InsertImage` metoda.

#### P: Czy mogę wstawić obraz z adresu URL w Aspose.Words?

 O: Tak, możesz wstawić obraz z adresu URL w Aspose.Words. Możesz użyć tego samego`InsertImage`metodę i określ adres URL obrazu zamiast ścieżki pliku lokalnego.

#### P: Jak mogę zmienić rozmiar obrazu w Aspose.Words?

 O: Aby zmienić rozmiar obrazu w Aspose.Words, możesz użyć opcji`Width` I`Height` właściwości`Shape` obiekt.

#### P: Czy mogę zastosować filtry do obrazów w Aspose.Words?

 O: Tak, możesz zastosować filtry do obrazów w Aspose.Words. Na przykład możesz zastosować filtr rozmycia do obrazu, korzystając z opcji`ApplyGaussianBlur` metoda`Shape` obiekt.

#### P: Jak mogę zastąpić jeden obraz innym w Aspose.Words?

 O: Aby zastąpić jeden obraz innym w Aspose.Words, możesz użyć metody`Replace` metoda`Shape` klasa. Ta metoda przyjmuje jako parametr`Shape` obiekt obrazu, który ma zostać zastąpiony oraz`Shape` obiekt nowego obrazu.