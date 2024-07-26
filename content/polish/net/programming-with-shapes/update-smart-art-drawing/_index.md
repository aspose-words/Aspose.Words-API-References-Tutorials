---
title: Zaktualizuj inteligentny rysunek artystyczny
linktitle: Zaktualizuj inteligentny rysunek artystyczny
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zaktualizować rysunek Smart Art w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/update-smart-art-drawing/
---

W tym samouczku wyjaśniono, jak zaktualizować rysunek Smart Art w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeglądając kształty w dokumencie i sprawdzając, czy mają one grafikę Smart Art, możesz zaktualizować rysunek Smart Art, aby odzwierciedlić wszelkie zmiany wprowadzone w jego danych.

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
 Załaduj dokument programu Word zawierający rysunek Smart Art za pomocą`Document` konstruktor klasy.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Krok 3: Zaktualizuj inteligentny rysunek artystyczny
 Iteruj po kształtach w dokumencie, używając metody`GetChildNodes` metoda z`NodeType.Shape` parametr. Sprawdź, czy każdy kształt ma inteligentną grafikę, używając`HasSmartArt`właściwość i jeśli to prawda, wywołaj metodę`UpdateSmartArtDrawing` metoda aktualizacji rysunku Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Przykładowy kod źródłowy aktualizacji inteligentnego rysunku artystycznego przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Otóż to! Pomyślnie zaktualizowałeś rysunek Smart Art w dokumencie programu Word przy użyciu Aspose.Words dla .NET.