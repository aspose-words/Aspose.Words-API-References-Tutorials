---
title: Usuń ograniczenie tylko do odczytu
linktitle: Usuń ograniczenie tylko do odczytu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak usunąć ograniczenie tylko do odczytu z dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-protection/remove-read-only-restriction/
---
tym samouczku przeprowadzimy Cię przez kroki, aby użyć funkcji usuwania ograniczeń tylko do odczytu Aspose.Words dla .NET. Ta funkcja umożliwia usunięcie ograniczenia tylko do odczytu z dokumentu programu Word, aby umożliwić jego edycję. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i ustawianie ochrony

Zacznij od utworzenia instancji klasy Document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Ustaw hasło do dokumentu za pomocą właściwości SetPassword() obiektu WriteProtection:

Pamiętaj, aby zastąpić „Moje hasło” rzeczywistym hasłem użytym do ochrony dokumentu.

## Krok 2: Usuń ograniczenie tylko do odczytu

Aby usunąć ograniczenie tylko do odczytu, ustaw właściwość ReadOnlyRecommended na false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Krok 3: Zastosuj nieograniczoną ochronę

Na koniec zastosuj nieograniczoną ochronę za pomocą metody Protect() obiektu Document:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać dokument bez ograniczeń tylko do odczytu.

### Przykładowy kod źródłowy usuwania ograniczenia tylko do odczytu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do usuwania ograniczenia tylko do odczytu przy użyciu Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Wprowadź hasło o długości do 15 znaków.
doc.WriteProtection.SetPassword("MyPassword");

//Usuń opcję tylko do odczytu.
doc.WriteProtection.ReadOnlyRecommended = false;

// Zastosuj ochronę przed zapisem bez żadnej ochrony.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Wykonując te kroki, możesz łatwo usunąć ograniczenie tylko do odczytu z dokumentu Word za pomocą Aspose.Words dla .NET.


## Wniosek

W tym samouczku nauczyliśmy się, jak usunąć ograniczenie tylko do odczytu z dokumentu programu Word za pomocą Aspose.Words dla .NET. Wykonując podane kroki, możesz łatwo usunąć ograniczenie i ponownie udostępnić dokument do edycji. Aspose.Words dla .NET oferuje kompleksowy zestaw funkcji do zarządzania ochroną dokumentów i ograniczeniami, zapewniając elastyczność i kontrolę nad bezpieczeństwem i możliwościami edycji dokumentów Word.

### Często zadawane pytania

#### P: Jakie są ograniczenia tylko do odczytu w Aspose.Words dla .NET?

O: Ograniczenie tylko do odczytu w Aspose.Words dla .NET odnosi się do funkcji, która pozwala ustawić dokument programu Word jako tylko do odczytu, uniemożliwiając użytkownikom wprowadzanie jakichkolwiek modyfikacji zawartości lub formatowania. To ograniczenie pomaga chronić integralność dokumentu i zapewnia, że nie zostanie on przypadkowo lub złośliwie zmodyfikowany.

#### P: Jak mogę usunąć ograniczenie tylko do odczytu za pomocą Aspose.Words dla .NET?

Odp.: Aby usunąć ograniczenie tylko do odczytu z dokumentu programu Word za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz instancję`Document` class i ustaw hasło do dokumentu za pomocą`SetPassword` metoda`WriteProtection` obiekt.
2.  Ustaw`ReadOnlyRecommended` własność`WriteProtection` oponować`false` aby usunąć zalecenie tylko do odczytu.
3.  Zastosuj nieograniczoną ochronę dokumentu za pomocą`Protect` metoda`Document` obiekt z`NoProtection` rodzaj ochrony.
4.  Zapisz dokument bez ograniczeń tylko do odczytu, używając pliku`Save` metoda`Document` obiekt.

#### P: Czy mogę usunąć ograniczenie tylko do odczytu z dokumentu programu Word bez hasła?

Odp.: Nie, nie można usunąć ograniczenia tylko do odczytu z dokumentu programu Word bez podania prawidłowego hasła. Ograniczenie tylko do odczytu jest ustawione ze względów bezpieczeństwa i usunięcie go bez hasła podważa cel, jakim jest ochrona integralności dokumentu.

#### P: Czy mogę usunąć ograniczenie tylko do odczytu z dokumentu programu Word z nieprawidłowym hasłem?

Odp.: Nie, nie można usunąć ograniczenia tylko do odczytu z dokumentu programu Word z nieprawidłowym hasłem. Aby usunąć ograniczenie tylko do odczytu i umożliwić ponowną edycję dokumentu, należy podać prawidłowe hasło. Dzięki temu tylko autoryzowani użytkownicy z prawidłowym hasłem będą mogli modyfikować dokument.

#### P: Czy można usunąć inne rodzaje ochrony dokumentów za pomocą Aspose.Words dla .NET?

Odp.: Tak, Aspose.Words dla .NET udostępnia różne metody usuwania innych typów ochrony dokumentów, takich jak ochrona hasłem, ochrona formularzy lub ograniczenia edycji dokumentów. W zależności od rodzaju ochrony zastosowanej w dokumencie możesz użyć odpowiednich metod i właściwości dostarczonych przez Aspose.Words, aby usunąć określoną ochronę i umożliwić edycję dokumentu.
