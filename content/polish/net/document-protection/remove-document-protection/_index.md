---
title: Usuń ochronę dokumentu w dokumencie programu Word
linktitle: Usuń ochronę dokumentu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak usunąć ochronę w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-protection/remove-document-protection/
---
W tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji usuwania ochrony dokumentów w Aspose.Words dla .NET. Ta funkcja umożliwia usunięcie ochrony z dokumentu programu Word w celu udostępnienia go do dalszej edycji. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i dodawanie treści

Zacznij od utworzenia instancji klasy Document i obiektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Dodaj treść do dokumentu

Użyj obiektu DocumentBuilder, aby dodać treść do dokumentu:

```csharp
builder.Writeln("Text added to a document.");
```

## Krok 3: Usuń ochronę dokumentu

Aby wyłączyć ochronę dokumentu, możesz użyć metody Unprotect() obiektu Document. Możesz usunąć ochronę bez hasła lub z poprawnym hasłem. Usuwanie ochrony bez hasła:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Pamiętaj, aby zastąpić „newPassword” poprawnym hasłem dokumentu.

## Krok 4: Zapisz dokument bez ochrony

Na koniec zapisz dokument bez ochrony, korzystając z metody Save() obiektu Document:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać dokument bez ochrony.

### Przykładowy kod źródłowy dla Usuń ochronę dokumentów przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do usuwania ochrony dokumentu za pomocą Aspose.Words dla .NET:

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// Dokumenty mogą zostać usunięte bez ochrony hasłem lub przy użyciu prawidłowego hasła.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Wykonując poniższe kroki, możesz łatwo usunąć ochronę z dokumentu Word za pomocą Aspose.Words dla .NET.

## Wniosek

W tym samouczku omówiliśmy, jak usunąć ochronę dokumentu w dokumencie programu Word za pomocą Aspose.Words dla .NET. Wykonując podane kroki, możesz łatwo wyłączyć ochronę dokumentu i udostępnić go do dalszej edycji. Aspose.Words dla .NET zapewnia potężne API, które pozwala manipulować ustawieniami ochrony dokumentów i dostosowywać poziom bezpieczeństwa dokumentów Word. Usunięcie ochrony dokumentu zapewnia elastyczność modyfikowania zawartości i formatowania dokumentu w razie potrzeby.

### Często zadawane pytania dotyczące usuwania ochrony dokumentów w dokumencie programu Word

#### P: Jaka jest ochrona dokumentów w Aspose.Words dla .NET?

Odp.: Ochrona dokumentów w Aspose.Words dla .NET odnosi się do funkcji, która pozwala zastosować środki bezpieczeństwa do dokumentu programu Word w celu ograniczenia edycji, formatowania i modyfikacji zawartości. Pomaga zapewnić integralność i poufność dokumentu.

#### P: Jak mogę usunąć ochronę dokumentów za pomocą Aspose.Words dla .NET?

Odp.: Aby usunąć ochronę dokumentów za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz instancję`Document` klasa i A`DocumentBuilder` obiekt.
2.  Użyj`DocumentBuilder` aby dodać treść do dokumentu.
3.  Zadzwoń do`Unprotect` metoda`Document` sprzeciwić się usunięciu istniejącej ochrony z dokumentu. Można to zrobić bez podawania hasła lub podając prawidłowe hasło.
4.  Zapisz niechroniony dokument za pomocą`Save` metoda`Document` obiekt.

#### P: Czy mogę usunąć ochronę z dokumentu programu Word bez hasła?

 Odp.: Tak, możesz usunąć ochronę z dokumentu Word bez hasła, używając Aspose.Words dla .NET. Dzwoniąc do`Unprotect` metoda`Document`obiektu bez podawania hasła, możesz usunąć ochronę z dokumentu, jeśli był on wcześniej chroniony bez hasła.

#### P: Jak mogę usunąć ochronę dokumentu programu Word za pomocą hasła?

 O: Aby usunąć ochronę z dokumentu programu Word, który był chroniony hasłem, należy podać prawidłowe hasło podczas wywoływania`Unprotect` metoda`Document` obiekt. Dzięki temu tylko użytkownicy posiadający prawidłowe hasło będą mogli usunąć ochronę i uzyskać dostęp do dokumentu w celu edycji.

#### P: Czy mogę usunąć określone typy ochrony z dokumentu programu Word?

 O: Tak, używając Aspose.Words dla .NET, możesz selektywnie usuwać określone typy ochrony z dokumentu Word. Dzwoniąc do`Unprotect` metoda`Document` obiektu, możesz usunąć żądany typ ochrony, taki jak ochrona tylko do odczytu lub ochrona formularza, pozostawiając inne typy ochrony bez zmian.