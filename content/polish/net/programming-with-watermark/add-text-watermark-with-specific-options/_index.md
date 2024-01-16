---
title: Dodaj tekstowy znak wodny z określonymi opcjami
linktitle: Dodaj tekstowy znak wodny z określonymi opcjami
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać tekstowy znak wodny z określonymi opcjami za pomocą Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

W tym samouczku przeprowadzimy Cię przez proces dodawania tekstowego znaku wodnego z określonymi opcjami za pomocą Aspose.Words dla .NET. Tekstowy znak wodny to tekst nałożony na dokument w celu wskazania, że jest to wersja robocza, poufny itp.

## Krok 1: Korzystanie z generatora dokumentów

Najpierw użyjemy generatora dokumentów, aby dodać treść do naszego dokumentu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument

Załadujemy istniejący dokument, korzystając ze ścieżki dokumentu.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Krok 3: Dodaj tekstowy znak wodny z określonymi opcjami

 Stworzymy instancję`TextWatermarkOptions` class i ustaw żądane opcje tekstowego znaku wodnego.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Krok 4: Zapisz dokument

Wreszcie możemy zapisać dokument z dodanym tekstowym znakiem wodnym.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Przykładowy kod źródłowy dodawania tekstowego znaku wodnego z określonymi opcjami w Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Gratulacje! Nauczyłeś się teraz, jak dodawać tekstowy znak wodny z określonymi opcjami przy użyciu Aspose.Words dla .NET.

