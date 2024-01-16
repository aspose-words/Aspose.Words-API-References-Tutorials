---
title: Zaktualizuj właściwość ostatniego zapisanego czasu
linktitle: Zaktualizuj właściwość ostatniego zapisanego czasu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak automatycznie aktualizować właściwość Ostatni zapisany czas podczas zapisywania dokumentu za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
W tym samouczku przyjrzymy się dostarczonemu kodowi źródłowemu C#, aby zaktualizować właściwość czasu ostatniego zapisu podczas zapisywania dokumentu przy użyciu Aspose.Words dla .NET. Ta funkcja umożliwia automatyczną aktualizację właściwości czasu ostatniego zapisu wygenerowanego dokumentu.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 W tym kroku konfigurujemy opcje zapisywania OOXML za pomocą pliku`OoxmlSaveOptions` klasa. Umożliwiamy automatyczną aktualizację właściwości ostatniego zapisu czasu poprzez ustawienie`UpdateLastSavedTimeProperty` Do`true`.

## Krok 4: Zapisz dokument ze zaktualizowaną właściwością

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 W ostatnim kroku zapisujemy dokument za pomocą pliku`Save` metodę i przekazanie ścieżki do pliku wyjściowego za pomocą`.docx` rozszerzenie wraz z określonymi opcjami zapisywania.

Teraz możesz uruchomić kod źródłowy, aby automatycznie zaktualizować właściwość czasu ostatniego zapisu podczas zapisywania dokumentu. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx”.

### Przykładowy kod źródłowy dla właściwości Aktualizuj ostatni zapisany czas przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcję automatycznego aktualizowania właściwości czasu ostatniego zapisu podczas zapisywania dokumentu przy użyciu Aspose.Words dla .NET. Włączając tę funkcję z opcjami zapisywania OOXML, możesz mieć pewność, że właściwość czasu ostatniego zapisu zostanie automatycznie zaktualizowana w wygenerowanym dokumencie.

Aktualizacja właściwości czasu ostatniego zapisu może być przydatna do śledzenia zmian i wersji dokumentu. Śledzi także, kiedy dokument został ostatnio zapisany, co może być przydatne w różnych scenariuszach.

Aspose.Words dla .NET ułatwia automatyczną aktualizację właściwości Czas ostatniej kopii zapasowej, zapewniając elastyczne i wydajne opcje tworzenia kopii zapasowych. Możesz zintegrować tę funkcję ze swoimi projektami, aby mieć pewność, że wygenerowane dokumenty zawierają dokładne informacje o kopii zapasowej.