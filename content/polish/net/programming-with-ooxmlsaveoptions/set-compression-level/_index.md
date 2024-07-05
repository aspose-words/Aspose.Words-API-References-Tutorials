---
title: Ustaw poziom kompresji
linktitle: Ustaw poziom kompresji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić poziom kompresji podczas zapisywania dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
W tym samouczku przyjrzymy się dostarczonemu kodowi źródłowemu C#, aby ustawić poziom kompresji podczas zapisywania dokumentu przy użyciu Aspose.Words dla .NET. Ta funkcja pozwala kontrolować poziom kompresji generowanego dokumentu.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne za pomocą Aspose.Words dla .NET. Upewnij się, że dodałeś niezbędne odniesienia i zaimportowałeś odpowiednie przestrzenie nazw.

## Krok 2: Załaduj dokument

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 W tym kroku ładujemy dokument za pomocą`Document` metodę i przekazanie ścieżki do pliku DOCX do załadowania.

## Krok 3: Konfiguracja opcji tworzenia kopii zapasowych OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 W tym kroku konfigurujemy opcje zapisywania OOXML za pomocą pliku`OoxmlSaveOptions` klasa. Ustawiamy poziom kompresji na`SuperFast` aby uzyskać szybszą kompresję.

## Krok 4: Zapisz dokument z określonym poziomem kompresji

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 W ostatnim kroku zapisujemy dokument za pomocą pliku`Save` metodę i przekazanie ścieżki do pliku wyjściowego za pomocą`.docx` rozszerzenie wraz z określonymi opcjami zapisywania.

Teraz możesz uruchomić kod źródłowy, aby ustawić poziom kompresji podczas zapisywania dokumentu. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx”.

### Przykładowy kod źródłowy dla Ustaw poziom kompresji przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcjonalność ustawiania poziomu kompresji podczas zapisywania dokumentu przy użyciu Aspose.Words dla .NET. Określając odpowiedni poziom kompresji, możesz zoptymalizować rozmiar dokumentu i szybkość generowania.

 The`OoxmlSaveOptions` class zapewnia elastyczność kontrolowania poziomu kompresji poprzez ustawienie`CompressionLevel` właściwość do odpowiedniej wartości, np`SuperFast`. Pozwala to uzyskać właściwą równowagę pomiędzy rozmiarem pliku i szybkością tworzenia kopii zapasowych, w zależności od konkretnych potrzeb.

Korzystanie z kompresji może być korzystne, gdy trzeba zmniejszyć rozmiar generowanych plików, zwłaszcza w przypadku dużych dokumentów. Może to ułatwić przechowywanie, udostępnianie i przesyłanie dokumentów.

Aspose.Words dla .NET oferuje szereg zaawansowanych opcji i funkcji do manipulacji dokumentami. Korzystając z odpowiednich opcji tworzenia kopii zapasowych, możesz dostosować proces generowania dokumentów i zoptymalizować wydajność swojej aplikacji.

Zachęcamy do poznania większej liczby funkcji Aspose.Words dla .NET, aby usprawnić przepływ pracy podczas generowania dokumentów.
