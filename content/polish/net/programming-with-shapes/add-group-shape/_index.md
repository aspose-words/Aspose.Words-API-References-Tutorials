---
title: Dodaj kształt grupy
linktitle: Dodaj kształt grupy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać kształt grupy składający się z wielu kształtów do dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/add-group-shape/
---

tym samouczku wyjaśniono, jak dodać kształt grupy zawierający wiele kształtów do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Kształty grupowe umożliwiają łączenie wielu kształtów i manipulowanie nimi w ramach jednego elementu.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym chcesz zapisać dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz nowy dokument i GroupShape
 Utwórz nową instancję`Document` klasa i`GroupShape` sprzeciwić się pracy z dokumentem.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Krok 3: Utwórz i dodaj kształty do GroupShape
 Twórz indywidualne kształty, np`accentBorderShape`I`actionButtonShape` używając`Shape` klasa. Dostosuj ich właściwości według potrzeb. Dołącz te kształty do`groupShape` obiekt.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Krok 4: Ustaw wymiary dla GroupShape
 Ustaw szerokość, wysokość i rozmiar współrzędnych dla`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Krok 5: Wstaw GroupShape do dokumentu
 Stwórz`DocumentBuilder` obiekt i wstaw`groupShape` do dokumentu za pomocą`InsertNode` metoda.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Krok 6: Zapisz dokument
 Zapisz dokument w określonym katalogu za pomocą`Save` metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithShapes.AddGroupShape.docx”.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Przykładowy kod źródłowy dla Dodaj kształt grupy przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Otóż to! Pomyślnie dodałeś kształt grupy zawierający wiele kształtów do dokumentu programu Word za pomocą Aspose.W