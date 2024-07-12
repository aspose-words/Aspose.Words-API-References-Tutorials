---
title: Zachowaj starsze znaki kontrolne
linktitle: Zachowaj starsze znaki kontrolne
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zachować starsze znaki kontrolne podczas zapisywania dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

W tym samouczku przyjrzymy się dostarczonemu kodowi źródłowemu C#, aby zachować starsze znaki sterujące podczas zapisywania dokumentu przy użyciu Aspose.Words dla .NET. Ta funkcja pozwala zachować specjalne znaki sterujące podczas konwertowania lub zapisywania dokumentu.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne za pomocą Aspose.Words dla .NET. Upewnij się, że dodałeś niezbędne odniesienia i zaimportowałeś odpowiednie przestrzenie nazw.

## Krok 2: Załaduj dokument

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 W tym kroku ładujemy dokument za pomocą`Document` metodę i przekazanie ścieżki do pliku zawierającego odziedziczone znaki sterujące.

## Krok 3: Konfiguracja opcji tworzenia kopii zapasowych OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 W tym kroku konfigurujemy opcje zapisywania OOXML, tworząc nowy plik`OoxmlSaveOptions` obiekt. Określamy żądany format zapisu (tutaj`FlatOpc` ) i włącz`KeepLegacyControlChars` opcja zachowania starszych znaków kontrolnych.

## Krok 4: Zapisywanie dokumentu ze starszymi znakami kontrolnymi

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 W ostatnim kroku zapisujemy dokument za pomocą pliku`Save` metodę i przekazanie ścieżki do pliku wyjściowego za pomocą`.docx` rozszerzenie wraz z określonymi opcjami zapisywania.

Teraz możesz uruchomić kod źródłowy, aby zachować starsze znaki kontrolne podczas zapisywania dokumentu. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx”.

### Przykładowy kod źródłowy dla znaków kontrolnych Keep Legacy przy użyciu Aspose.Words dla .NET 
```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcjonalność zachowywania starszych znaków kontrolnych podczas zapisywania dokumentu przy użyciu Aspose.Words dla .NET. Nauczyliśmy się, jak zachować te znaki specjalne, które mogą być ważne dla prawidłowego formatowania lub wyświetlania dokumentu.

 Zachowywanie starszych znaków kontrolnych jest szczególnie przydatne podczas przetwarzania tekstu w dokumentach korzystających ze starszych lub specyficznych funkcji, takich jak specjalne znaki sterujące. Włączając opcję`KeepLegacyControlChars` opcję podczas zapisywania dokumentu, masz pewność, że znaki te zostaną zachowane.

Aspose.Words dla .NET oferuje szereg elastycznych i wydajnych opcji tworzenia kopii zapasowych, aby spełnić Twoje potrzeby w zakresie manipulacji dokumentami. Korzystając z odpowiednich opcji, możesz dostosować proces tworzenia kopii zapasowych tak, aby zachować specyfikę Twoich dokumentów.

Możesz włączyć tę funkcjonalność do swoich projektów Aspose.Words for .NET, aby zapewnić integralność i zachowanie starszych znaków kontrolnych w swoich dokumentach.