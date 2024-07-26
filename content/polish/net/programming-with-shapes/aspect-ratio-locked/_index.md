---
title: Proporcje obrazu zablokowane
linktitle: Proporcje obrazu zablokowane
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zablokować lub odblokować proporcje kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/aspect-ratio-locked/
---

W tym samouczku wyjaśniono, jak zablokować lub odblokować proporcje kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Blokując proporcje, możesz zachować oryginalne proporcje kształtu podczas zmiany jego rozmiaru.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i narzędzie DocumentBuider
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder` sprzeciwić się pracy z dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw kształt obrazu
 Użyj`InsertImage` metoda`DocumentBuilder` obiekt, aby wstawić kształt obrazu do dokumentu. Podaj ścieżkę do pliku obrazu jako parametr.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Krok 4: Zablokuj lub odblokuj współczynnik proporcji
 Ustaw`AspectRatioLocked` właściwość kształtu do`true` Lub`false` aby odpowiednio zablokować lub odblokować współczynnik proporcji.

```csharp
shape.AspectRatioLocked = false; // Odblokuj proporcje
```

## Krok 5: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithShapes.AspectRatioLocked.docx”.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Przykładowy kod źródłowy dla współczynnika proporcji zablokowanego przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Otóż to! Pomyślnie zablokowałeś lub odblokowałeś proporcje kształtu w dokumencie programu Word przy użyciu Aspose.Words dla .NET.