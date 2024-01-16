---
title: Uzyskaj zakres stron Tiff
linktitle: Uzyskaj zakres stron Tiff
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyodrębnić zakres stron TIFF za pomocą Aspose.Words dla .NET. Kompletny samouczek dotyczący niestandardowych plików TIFF.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

W tym samouczku przyjrzymy się dostarczonemu kodowi źródłowemu C#, aby uzyskać szereg stron TIFF za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia wyodrębnienie określonego zakresu stron z dokumentu i zapisanie ich jako pliku TIFF.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne za pomocą Aspose.Words dla .NET. Upewnij się, że dodałeś niezbędne odniesienia i zaimportowałeś odpowiednie przestrzenie nazw.

## Krok 2: Załaduj dokument

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 W tym kroku ładujemy dokument za pomocą`Document` metodę i przekazanie ścieżki do pliku DOCX do załadowania.

## Krok 3: Zapisanie całego dokumentu w formacie TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

Na tym etapie zapisujemy cały dokument w formacie TIFF przy użyciu pliku`Save` metody i określenie ścieżki do pliku wyjściowego z rozszerzeniem`.tiff`.

## Krok 4: Skonfiguruj opcje tworzenia kopii zapasowych zakresu stron

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Na tym etapie konfigurujemy opcje tworzenia kopii zapasowych dla określonego zakresu stron. Tworzymy nowe`ImageSaveOptions` obiekt określający żądany format zapisu, tutaj „Tiff” dla formatu TIFF. Używamy`PageSet` aby określić zakres stron, które chcemy wyodrębnić, tutaj od strony 0 do strony 1 (włącznie). Ustawiamy także kompresję TIFF na`Ccitt4` i rozdzielczość do 160 dpi.

## Krok 5: Zapisywanie zakresu stron w formacie TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 W tym ostatnim kroku zapisujemy określony zakres stron w formacie TIFF za pomocą`Save` metodę i przekazanie ścieżki do pliku wyjściowego za pomocą`.tiff` rozszerzenie wraz z określonymi opcjami zapisu.

Teraz możesz uruchomić kod źródłowy, aby uzyskać określony zakres stron z dokumentu i zapisać je jako plik TIFF. Powstałe pliki zostaną zapisane w określonym katalogu pod nazwami „WorkingWithImageSaveOptions.MultipageTiff.tiff” dla pełnego dokumentu i „WorkingWithImageSaveOptions.GetTiffPageRange.tiff” dla określonego zakresu stron.

### Przykładowy kod źródłowy Get Tiff Page Range przy użyciu Aspose.Words dla .NET

```csharp 

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcjonalność uzyskiwania szeregu stron TIFF za pomocą Aspose.Words dla .NET. Dowiedzieliśmy się, jak wyodrębnić określony zakres stron z dokumentu i zapisać je jako plik TIFF.

Ta funkcja jest przydatna, gdy chcesz wyodrębnić tylko niektóre strony z dokumentu i zapisać je w standardowym formacie obrazu, takim jak TIFF. Możesz także dostosować opcje kompresji i rozdzielczości, aby uzyskać pliki TIFF najwyższej jakości.

Aspose.Words dla .NET oferuje szeroką gamę zaawansowanych funkcji do manipulowania i generowania dokumentów. Uzyskanie zakresu stron TIFF jest jednym z wielu potężnych narzędzi, jakie udostępnia.

Możesz zintegrować tę funkcjonalność ze swoimi projektami Aspose.Words for .NET, aby wyodrębnić i zapisać określone zakresy stron z dokumentów w formacie TIFF.