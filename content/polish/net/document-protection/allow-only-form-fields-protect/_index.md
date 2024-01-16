---
title: Zezwalaj na ochronę tylko pól formularzy w dokumencie programu Word
linktitle: Zezwalaj na ochronę tylko pól formularzy w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać Aspose.Words dla .NET do ochrony dokumentów w formacie Word i zezwalania na edycję tylko pól formularzy.
type: docs
weight: 10
url: /pl/net/document-protection/allow-only-form-fields-protect/
---
Ochrona dokumentów jest istotną funkcją podczas przetwarzania słów z plikami w aplikacji C#. Dzięki bibliotece Aspose.Words dla .NET możesz łatwo chronić swoje dokumenty i zezwalać na edycję jedynie pól formularzy. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces używania kodu źródłowego C#, aby zezwalać na edycję tylko pól formularzy za pomocą funkcji Zezwalaj tylko na ochronę pól formularzy w Aspose.Words dla .NET.

## Krok 1: Ustawianie katalogu dokumentów

Pierwszym krokiem jest zdefiniowanie katalogu dokumentu. Musisz określić ścieżkę, w której chcesz zapisać chroniony dokument. Na przykład :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Wstawianie sekcji i tekstu

Następnie musisz wstawić sekcje i tekst do swojego dokumentu. Użyj klasy DocumentBuilder udostępnionej przez Aspose.Words, aby zbudować zawartość swojego dokumentu. Oto prosty przykład:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

tym przykładzie tworzymy nowy pusty dokument, a następnie używamy narzędzia DocumentBuilder do dodania wiersza tekstu.

## Krok 3: Włączanie ochrony dokumentów

 Ochrona dokumentów działa tylko wtedy, gdy ochrona dokumentów jest włączona. Możesz włączyć ochronę dokumentów za pomocą`Protect` metoda klasy Dokument. Oto jak:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

W tym przykładzie włączamy ochronę dokumentów poprzez określenie typu ochrony `

ZezwólOnlyFormFields i ustawienie hasła.

## Krok 4: Zezwalanie tylko na pola formularzy

Teraz, gdy ochrona dokumentów jest włączona, musimy określić, że dozwolona jest tylko edycja pól formularza. Dzięki temu użytkownicy będą mogli edytować tylko te części dokumentu, które są polami formularzy. Oto jak:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Pamiętaj, aby zastąpić „hasło” hasłem ustawionym wcześniej.

## Krok 5: Zapisywanie chronionego dokumentu

 Na koniec możesz zapisać chroniony dokument za pomocą`Save` metoda klasy Dokument. Określ pełną ścieżkę pliku i żądaną nazwę pliku. Na przykład :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Pamiętaj, aby zastąpić „dataDir” ścieżką do katalogu dokumentów.

### Przykładowy kod źródłowy funkcji Zezwalaj tylko na ochronę pól formularzy przy użyciu Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Wstaw dwie sekcje z tekstem.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Ochrona dokumentów działa tylko wtedy, gdy ochrona dokumentów jest włączona i dozwolona jest tylko edycja w polach formularzy.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Zapisz chroniony dokument.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Wniosek

W tym przewodniku omówiliśmy, jak używać biblioteki Aspose.Words dla .NET do ochrony dokumentu i zezwalania na edycję tylko pól formularzy. Wykonując podane kroki, możesz łatwo zaimplementować tę funkcję w aplikacji C#. Ochrona dokumentów jest niezbędna, aby zapewnić bezpieczeństwo i poufność dokumentów.

### Często zadawane pytania dotyczące ochrony tylko pól formularzy w dokumencie programu Word

#### P: Jaka jest ochrona dokumentów w Aspose.Words dla .NET?

Odp.: Ochrona dokumentów w Aspose.Words dla .NET to funkcja, która pozwala zabezpieczyć dokumenty poprzez ograniczenie niektórych działań, takich jak edycja, formatowanie lub modyfikacja treści. Pomaga zachować integralność i poufność dokumentów, zapobiegając nieautoryzowanym zmianom.

#### P: Jak mogę chronić dokument i zezwolić na edycję tylko pól formularzy za pomocą Aspose.Words dla .NET?

Odp.: Aby chronić dokument i zezwolić na edycję tylko pól formularzy za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1. Zdefiniuj ścieżkę katalogu dla swojego dokumentu.
2.  Wstaw sekcje i tekst do dokumentu za pomocą`DocumentBuilder` klasa.
3.  Włącz ochronę dokumentów za pomocą`Protect` metoda`Document` class, określając typ ochrony jako`AllowOnlyFormFields` i podanie hasła.
4.  Zapisz chroniony dokument za pomocą`Save` metoda`Document` klasa.

#### P: Czy mogę wstawić pola formularza do chronionego dokumentu za pomocą Aspose.Words dla .NET?

Odp.: Tak, możesz wstawiać pola formularzy do chronionego dokumentu za pomocą Aspose.Words dla .NET. Ochrona dokumentów za pomocą`AllowOnlyFormFields` type pozwala użytkownikom edytować tylko pola formularza, chroniąc resztę zawartości dokumentu. Możesz skorzystać z`DocumentBuilder` class, aby wstawić pola formularza do dokumentu przed włączeniem ochrony.

#### P: Czy mogę usunąć ochronę dokumentu z chronionego dokumentu?

 Odp.: Tak, możesz usunąć ochronę dokumentu z chronionego dokumentu za pomocą Aspose.Words dla .NET. Aby usunąć ochronę, możesz użyć`Unprotect` metoda`Document` class i podaj prawidłowe hasło. Spowoduje to usunięcie ochrony i umożliwi nieograniczoną edycję dokumentu.

#### P: Czy można chronić dokument za pomocą wielu typów ochrony?

 Odp.: Nie, Aspose.Words dla .NET pozwala na zastosowanie tylko jednego typu ochrony do dokumentu na raz. Jednakże`AllowOnlyFormFields` typ ochrony może skutecznie ograniczyć edycję do pól formularzy, jednocześnie zezwalając na inne typy ochrony, takie jak`AllowOnlyComments` Lub`AllowOnlyRevisions`do połączenia z zabezpieczeniem pola formularza.

#### P: Czy mogę ustawić różne hasła dla różnych typów ochrony w dokumencie?

O: Nie, Aspose.Words dla .NET umożliwia ustawienie jednego hasła do ochrony dokumentów, niezależnie od typu ochrony. To samo hasło będzie używane do włączania i wyłączania ochrony dokumentów.