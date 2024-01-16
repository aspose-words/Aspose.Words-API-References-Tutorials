---
title: Indeksowany format 1Bpp
linktitle: Indeksowany format 1Bpp
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak formatować obrazy z dokładnością do 1 bpp indeksowane za pomocą Aspose.Words dla .NET. Kompletny samouczek dotyczący obrazów o małej głębi kolorów.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
W tym samouczku przyjrzymy się kodowi źródłowemu C# udostępnionemu dla funkcji „Format 1Bpp Indexed” w Aspose.Words dla .NET. Ta funkcja umożliwia formatowanie obrazów w dokumencie w formacie PNG z głębią kolorów 1 bit na piksel (1 bpp) i trybem kolorów indeksowanych.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Na tym etapie konfigurujemy opcje tworzenia kopii zapasowych obrazów. Tworzymy nowe`ImageSaveOptions`obiekt określający żądany format zapisu, tutaj „Png” dla formatu PNG. Definiujemy również stronę, która ma zostać uwzględniona w obrazie, tryb kolorów czarno-białych oraz format indeksowanego piksela 1 bpp.

## Krok 4: Tworzenie kopii zapasowych obrazów

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 W tym ostatnim kroku zapisujemy obrazy dokumentów w formacie PNG za pomocą`Save` metodę i przekazanie ścieżki do pliku wyjściowego wraz z określonymi opcjami zapisu.

Teraz możesz uruchomić kod źródłowy, aby sformatować obrazy dokumentów w formacie PNG z indeksowaną głębią kolorów 1 bpp. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithImageSaveOptions.Format1BppIndexed.Png”.

### Przykładowy kod źródłowy dla formatu 1Bpp Indeksowany przy użyciu Aspose.Words dla .NET

```csharp 
 
			 // Ścieżka do katalogu dokumentów
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Wniosek

W tym samouczku zbadaliśmy funkcję formatu indeksowanego 1Bpp w Aspose.Words dla .NET. Dowiedzieliśmy się, jak formatować obrazy w dokumencie w formacie PNG z głębią kolorów 1 bit na piksel (1 bpp) i trybem kolorów indeksowanych.

Ta funkcja jest przydatna, gdy chcesz uzyskać obrazy o małej głębi kolorów i małym rozmiarze pliku. Format indeksowany 1Bpp umożliwia reprezentowanie obrazów przy użyciu indeksowanej palety kolorów, co może być korzystne w niektórych specyficznych zastosowaniach.

Aspose.Words dla .NET oferuje szeroką gamę zaawansowanych funkcji do manipulowania i generowania dokumentów. Format indeksowany 1Bpp jest jednym z wielu potężnych narzędzi, jakie oddaje do Twojej dyspozycji.