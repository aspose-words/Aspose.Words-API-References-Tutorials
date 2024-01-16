---
title: Zaszyfruj dokument za pomocą hasła
linktitle: Zaszyfruj dokument za pomocą hasła
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zaszyfrować plik DOCX hasłem przy użyciu Aspose.Words dla .NET. Kompletny samouczek dotyczący bezpieczeństwa dokumentów.
type: docs
weight: 10
url: /pl/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
W tym samouczku przyjrzymy się dostarczonemu kodowi źródłowemu C# w celu zaszyfrowania pliku DOCX hasłem przy użyciu Aspose.Words dla .NET. Ta funkcja pozwala chronić dokument, udostępniając go tylko za pomocą określonego hasła.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 W tym kroku konfigurujemy opcje zapisywania OOXML, tworząc nowy plik`OoxmlSaveOptions` obiekt. Określamy żądane hasło do szyfrowania dokumentu, ustawiając`Password` właściwość na niestandardowe hasło.

## Krok 4: Szyfrowanie dokumentu hasłem

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 W ostatnim kroku zapisujemy dokument za pomocą pliku`Save` metodę i przekazanie ścieżki do pliku wyjściowego za pomocą`.docx` rozszerzenie wraz z określonymi opcjami zapisywania.

Teraz możesz uruchomić kod źródłowy, aby zaszyfrować dokument DOCX hasłem. Wynikowy plik zostanie zapisany w określonym katalogu pod nazwą „WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx”. Pamiętaj, aby chronić swoje hasło, ponieważ będzie ono potrzebne do otwarcia zaszyfrowanego dokumentu.

### Przykładowy kod źródłowy dla Encrypt Docx With Password przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Wniosek

W tym samouczku zbadaliśmy funkcjonalność szyfrowania pliku DOCX hasłem przy użyciu Aspose.Words dla .NET. Dowiedzieliśmy się jak chronić nasze dokumenty udostępniając je jedynie po podanym haśle.

Szyfrowanie dokumentów jest niezbędnym środkiem bezpieczeństwa chroniącym poufne informacje. Dzięki Aspose.Words dla .NET z łatwością możemy dodać tę funkcjonalność do naszych aplikacji.

Postępując zgodnie z podanymi krokami, możesz zintegrować szyfrowanie haseł z projektami Aspose.Words for .NET i zapewnić poufność swoich dokumentów.

Możesz eksperymentować z innymi funkcjami oferowanymi przez Aspose.Words dla .NET, aby wzbogacić swoje aplikacje o zaawansowane funkcje manipulacji dokumentami.
