---
title: Pobierz zakres stron JPEG
linktitle: Pobierz zakres stron JPEG
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak uzyskać szereg stron JPEG za pomocą Aspose.Words dla .NET. Kompletny samouczek dotyczący wyodrębniania niestandardowych obrazów.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

W tym samouczku przyjrzymy się kodowi źródłowemu C# udostępnionemu dla funkcji „Uzyskaj zakres stron JPEG” w Aspose.Words dla .NET. Ta funkcja umożliwia konwersję określonego zakresu stron dokumentu na obrazy w formacie JPEG.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne za pomocą Aspose.Words dla .NET. Upewnij się, że dodałeś niezbędne odniesienia i zaimportowałeś odpowiednie przestrzenie nazw.

## Krok 2: Załaduj dokument

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 W tym kroku ładujemy dokument za pomocą`Document` metodę i przekazanie ścieżki do pliku DOCX do załadowania.

## Krok 3: Skonfiguruj opcje tworzenia kopii zapasowych obrazu

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Na tym etapie konfigurujemy opcje tworzenia kopii zapasowych obrazów. Tworzymy nowe`ImageSaveOptions` obiekt określający żądany format zapisu, tutaj „Jpeg” dla formatu JPEG. Ustalamy także zakres stron do konwersji za pomocą`PageSet`obiekt. Na koniec dostosowujemy jasność i kontrast obrazu za pomocą`ImageBrightness`I`ImageContrast` właściwości, odpowiednio. Zmieniamy także rozdzielczość poziomą za pomocą`HorizontalResolution` nieruchomość.

## Krok 4: Tworzenie kopii zapasowych obrazów

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 W tym ostatnim kroku zapisujemy obrazy określonego zakresu stron w formacie JPEG za pomocą`Save` metodę i przekazanie ścieżki do pliku wyjściowego wraz z określonymi opcjami zapisu.

Teraz możesz uruchomić kod źródłowy, aby przekonwertować określony zakres stron w dokumencie na obrazy JPEG. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithImageSaveOptions.GetJpegPageRange.jpeg”.

### Przykładowy kod źródłowy dla Get JPEG Page Range przy użyciu Aspose.Words dla .NET

```csharp 
 // Ścieżka do katalogu dokumentów
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Ustaw „PageSet” na „0”, aby przekonwertować tylko pierwszą stronę dokumentu.
options.PageSet = new PageSet(0);

// Zmień jasność i kontrast obrazu.
// Obydwa są w skali 0-1 i domyślnie wynoszą 0,5.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Zmień rozdzielczość poziomą.
// Domyślna wartość tych właściwości to 96,0 dla rozdzielczości 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcjonalność pobierania zakresu stron JPEG za pomocą Aspose.Words dla .NET. Dowiedzieliśmy się, jak konwertować określony zakres stron dokumentu na obrazy w formacie JPEG, dostosowując jednocześnie opcje zapisywania.

Ta funkcja jest przydatna, gdy chcesz wyodrębnić określone strony z dokumentu i zapisać je jako obrazy JPEG. Możesz także dostosować jasność, kontrast i rozdzielczość poziomą obrazów, aby uzyskać spersonalizowane rezultaty.

Aspose.Words dla .NET oferuje szeroką gamę zaawansowanych funkcji do manipulowania i generowania dokumentów. Uzyskanie zakresu stron w formacie JPEG jest jednym z wielu potężnych narzędzi, jakie udostępnia.

Możesz zintegrować tę funkcję ze swoimi projektami Aspose.Words for .NET, aby uzyskać wysokiej jakości obrazy JPEG ze swoich dokumentów.