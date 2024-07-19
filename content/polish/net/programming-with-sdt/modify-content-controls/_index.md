---
title: Zmodyfikuj kontrolę zawartości
linktitle: Zmodyfikuj kontrolę zawartości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak modyfikować tekst, listy rozwijane i obrazy w ramach kontrolek zawartości w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/modify-content-controls/
---

tym samouczku wyjaśniono, jak modyfikować różne typy kontrolek treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Możesz zaktualizować tekst, wybraną wartość z listy rozwijanej lub zastąpić obraz w ramach kontrolek zawartości.

## Warunki wstępne
Aby skorzystać z tego samouczka, musisz mieć następujące elementy:

- Zainstalowana biblioteka Aspose.Words dla .NET.
- Podstawowa znajomość języka C# i przetwarzania tekstów w dokumentach Word.

## Krok 1: Skonfiguruj katalog dokumentów
 Rozpocznij od ustawienia ścieżki do katalogu dokumentów. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu, w którym znajduje się dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument i wykonaj iterację po kontrolkach zawartości
 Załaduj dokument Word za pomocą`Document` konstruktor, przekazując ścieżkę do dokumentu jako parametr. Wykonaj iterację po wszystkich znacznikach dokumentu strukturalnego w dokumencie, używając a`foreach` pętla.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Wykonuj działania w oparciu o typ kontroli treści
}
```

## Krok 3: Zmodyfikuj kontrolę zawartości zwykłego tekstu
 Dla kontroli zawartości typu`SdtType.PlainText`, usuń wszystkie istniejące elementy podrzędne, utwórz nowy akapit i dodaj ciąg z żądanym tekstem.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Krok 4: Zmodyfikuj kontrolę zawartości listy rozwijanej
 Dla kontroli zawartości typu`SdtType.DropDownList` , zaktualizuj wybraną wartość, ustawiając ją na określoną`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Krok 5: Zmodyfikuj kontrolę zawartości obrazu
 Dla kontroli zawartości typu`SdtType.Picture`, pobierz kształt w kontrolce zawartości i zastąp jego obraz nowym.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Krok 6: Zapisz zmodyfikowany dokument
 Zapisz zmodyfikowany dokument w określonym katalogu za pomocą`Save`metoda. Podaj żądaną nazwę pliku z odpowiednim rozszerzeniem. W tym przykładzie zapisujemy dokument jako „WorkingWithSdt.ModifyContentControls.docx”.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Przykładowy kod źródłowy modyfikacji kontroli zawartości przy użyciu Aspose.Words dla .NET 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Otóż to! Pomyślnie zmodyfikowałeś różne typy kontroli treści w dokumencie programu Word przy użyciu Aspose.Words dla .NET.