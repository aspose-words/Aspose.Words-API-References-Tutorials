---
title: Zaszyfruj dokument hasłem
linktitle: Zaszyfruj dokument hasłem
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak szyfrować dokumenty hasłem przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Bezpieczeństwo dokumentów jest niezbędne podczas przetwarzania słów z plikami w aplikacji C#. Dzięki bibliotece Aspose.Words dla .NET możesz łatwo chronić swoje dokumenty, szyfrując je hasłem. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces używania kodu źródłowego Aspose.Words for .NET C# do szyfrowania dokumentu przy użyciu opcji zapisywania DocSaveOptions.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to potężna biblioteka do tworzenia, edytowania, konwertowania i ochrony dokumentów programu Word na różnych platformach, w tym .NET. Oferuje wiele funkcji do manipulowania dokumentami, takich jak wstawianie tekstu, zmiana formatowania, dodawanie sekcji i wiele więcej.

## Krok 1: Zdefiniowanie katalogu dokumentów

Pierwszym krokiem jest ustawienie katalogu, w którym chcesz zapisać zaszyfrowany dokument. Należy podać pełną ścieżkę katalogu. Na przykład :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Tworzenie i edycja dokumentu

Następnie możesz utworzyć dokument i dodać do niego treść. Użyj klasy DocumentBuilder udostępnionej przez Aspose.Words, aby zbudować zawartość swojego dokumentu. Na przykład :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

W tym przykładzie tworzymy nowy pusty dokument, a następnie za pomocą narzędzia DocumentBuilder piszemy tekst „Hello World!”.

## Krok 3: Skonfiguruj opcje nagrywania

Teraz skonfigurujmy opcje zapisywania naszego dokumentu. Użyj klasy DocSaveOptions, aby określić ustawienia zapisywania. Na przykład :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

W tym przykładzie tworzymy nowy obiekt DocSaveOptions i ustawiamy właściwość Password na „password”, aby zaszyfrować dokument tym hasłem.

## Krok 4: Włączenie funkcji „Szyfruj dokument hasłem”.

Skonfigurowaliśmy już opcje dla

rejestracja przy użyciu podanego hasła, co automatycznie aktywuje funkcję „Zaszyfruj dokument hasłem”. Dzięki temu dokument zostanie zaszyfrowany hasłem określonym podczas zapisywania.

## Krok 5: Zapisanie dokumentu

Na koniec można zapisać dokument za pomocą metody Save klasy Document. Podaj pełną ścieżkę do pliku i żądaną nazwę pliku. Na przykład :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Pamiętaj, aby zastąpić „dataDir” ścieżką katalogu do dokumentów.

### Przykładowy kod źródłowy opcji zapisywania DocSaveOptions z funkcją „Szyfruj dokument hasłem” przy użyciu Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz i edytuj dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Skonfiguruj opcje zapisywania za pomocą funkcji „Szyfruj dokument hasłem”.
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Zapisz dokument z określonymi opcjami
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Wniosek

W tym przewodniku wyjaśniliśmy, jak używać biblioteki Aspose.Words dla .NET do szyfrowania dokumentu hasłem przy użyciu opcji zapisywania DocSaveOptions. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo zastosować tę funkcjonalność w swojej aplikacji C#. Zaszyfrowanie dokumentu hasłem gwarantuje jego poufność i bezpieczeństwo podczas obsługi.