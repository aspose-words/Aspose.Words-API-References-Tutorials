---
title: Dodaj przycięte rogi
linktitle: Dodaj przycięte rogi
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać kształt z przyciętymi rogami do dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/add-corners-snipped/
---

 W tym samouczku wyjaśniono, jak dodać kształt z przyciętymi rogami do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Kształt przyciętych narożników można dostosować i wstawić za pomocą narzędzia`InsertShape` metoda.

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
 Utwórz nową instancję`Document` klasa i A`DocumentBuilder`sprzeciwić się pracy z dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstaw kształt ściętych narożników
 Użyj`InsertShape` metoda`DocumentBuilder` obiekt, aby wstawić kształt z obciętymi narożnikami. Określ typ kształtu (w tym przypadku`ShapeType.TopCornersSnipped`) i podaj żądany rozmiar kształtu.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Krok 4: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithShapes.AddCornersSnipped.docx”.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Przykładowy kod źródłowy narzędzia Dodaj rogi wycięte przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Otóż to! Pomyślnie dodałeś obcięty kształt rogów do swojego dokumentu programu Word przy użyciu Aspose.Words dla .NET.