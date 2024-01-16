---
title: Wywołanie zwrotne zapisywania strony
linktitle: Wywołanie zwrotne zapisywania strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dostosować zapisywanie stron dokumentów do obrazów za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-imagesaveoptions/page-saving-callback/
---

W tym samouczku przyjrzymy się kodowi źródłowemu C# udostępnionemu do korzystania z wywołania zwrotnego zapisywania strony z opcjami zapisywania obrazu Aspose.Words dla .NET. Ta funkcja umożliwia wykonywanie niestandardowych działań podczas zapisywania każdej strony dokumentu jako obrazu.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 W tym kroku konfigurujemy opcje zapisywania obrazu, tworząc nowy`ImageSaveOptions` obiekt. Określamy żądany format kopii zapasowej, tutaj „Png” dla formatu PNG. Używamy`PageSet` aby określić zakres stron do zapisania, tutaj od pierwszej do ostatniej strony dokumentu (`doc.PageCount - 1`). Ustawiamy również`PageSavingCallback` do instancji`HandlePageSavingCallback`, która jest niestandardową klasą do obsługi wywołania zwrotnego zapisywania strony.

## Krok 4: Implementacja wywołania zwrotnego Zapisz stronę

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Zaimplementuj tutaj swoje niestandardowe działania
         // Dostęp do informacji o stronie można uzyskać poprzez właściwość „args.PageIndex”.
         // Możesz także zmienić opcje zapisywania dla każdej strony indywidualnie
     }
}
```

 Na tym etapie wdrażamy`HandlePageSavingCallback` klasa, która implementuje`IPageSavingCallback` interfejs. Możesz dostosować tę klasę, dodając określone działania w pliku`PageSaving` metoda. Dostęp do informacji o stronie można uzyskać poprzez`args.PageIndex` własność`PageSavingArgs` obiekt przekazany jako argument.

## Krok 5: Zapisywanie stron jako obrazów

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 W tym ostatnim kroku zapisujemy każdą stronę dokumentu jako obraz za pomocą`Save` metodę i przekazanie ścieżki do pliku wyjściowego za pomocą`.png` rozszerzenie wraz z określonymi opcjami zapisywania.

Teraz możesz uruchomić kod źródłowy, aby wykonać niestandardowe działania podczas zapisywania każdej strony dokumentu jako obrazu. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithImageSaveOptions.PageSavingCallback.png”.

### Przykładowy kod źródłowy wywołania zwrotnego zapisywania strony przy użyciu Aspose.Words dla .NET


```csharp 
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Wniosek

W tym samouczku omówiliśmy funkcję wywołania zwrotnego zapisywania strony z opcjami zapisywania obrazów Aspose.Words dla .NET. Dowiedzieliśmy się, jak wykonywać niestandardowe działania podczas zapisywania każdej strony dokumentu jako obrazu.

Ta funkcja jest przydatna, gdy chcesz wykonać określone operacje na każdej stronie podczas konwersji na obrazy. Możesz uzyskać dostęp do informacji o stronie i użyć ich do dostosowania opcji tworzenia kopii zapasowych lub wykonania innego przetwarzania specyficznego dla strony.

Aspose.Words dla .NET oferuje szeroką gamę zaawansowanych funkcji do manipulowania i generowania dokumentów. Przypomnienie o zapisaniu strony to jedno z wielu potężnych narzędzi, które pozwala dostosować proces zapisywania stron w obrazach.