---
title: Wykryj inteligentny kształt grafiki
linktitle: Wykryj inteligentny kształt grafiki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wykrywać kształty Smart Art w dokumencie programu Word za pomocą Aspose.Words dla .NET, identyfikując reprezentacje graficzne.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/detect-smart-art-shape/
---

W tym samouczku wyjaśniono, jak wykrywać kształty Smart Art w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Kształty Smart Art to graficzne reprezentacje używane do wizualnego przedstawiania informacji i pomysłów.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Zacznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument
 Załaduj dokument Word za pomocą`Document` konstruktor, przekazując ścieżkę do dokumentu jako parametr.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Krok 3: Wykryj inteligentne kształty artystyczne
 Iteruj przez węzły podrzędne typu`Shape` w dokumencie za pomocą`GetChildNodes`metoda. Sprawdź, czy każdy kształt ma inteligentną grafikę, używając`HasSmart Art` nieruchomość.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Krok 4: Wyprowadź wynik
Wydrukuj liczbę kształtów z grafiką Smart Art wykrytą w dokumencie.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Przykładowy kod źródłowy funkcji Detect Smart Art Shape przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Otóż to! Pomyślnie wykryłeś kształty Smart Art w dokumencie programu Word przy użyciu Aspose.Words dla .NET.