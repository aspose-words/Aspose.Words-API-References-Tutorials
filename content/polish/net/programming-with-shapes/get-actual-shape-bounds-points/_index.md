---
title: Zdobądź rzeczywiste punkty granic kształtu
linktitle: Zdobądź rzeczywiste punkty granic kształtu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak pobrać rzeczywiste granice kształtu w punktach (jednostka miary) w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/get-actual-shape-bounds-points/
---

W tym samouczku wyjaśniono, jak pobrać rzeczywiste granice kształtu w punktach (jednostka miary) w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Granice reprezentują rozmiar i położenie kształtu w dokumencie.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Utwórz nowy dokument i narzędzie DocumentBuider
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` sprzeciwić się pracy z dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw kształt obrazu
 Użyj`InsertImage` metoda`DocumentBuilder` obiekt, aby wstawić kształt obrazu do dokumentu. Podaj ścieżkę do pliku obrazu jako parametr.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Krok 3: Pobierz rzeczywiste punkty granic kształtu
 Uzyskaj dostęp do kształtu`ShapeRenderer` używając`GetShapeRenderer` metoda. Następnie pobierz rzeczywiste granice kształtu w punktach za pomocą`BoundsInPoints` nieruchomość.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Przykładowy kod źródłowy funkcji Uzyskaj punkty granic rzeczywistego kształtu przy użyciu Aspose.Words dla .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Otóż to! Pomyślnie pobrałeś rzeczywiste granice kształtu w punktach w dokumencie programu Word przy użyciu Aspose.Words dla .NET.