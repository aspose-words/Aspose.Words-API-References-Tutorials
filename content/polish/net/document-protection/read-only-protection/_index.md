---
title: Ochrona tylko do odczytu w dokumencie programu Word
linktitle: Ochrona tylko do odczytu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak chronić dokumenty tylko do odczytu w programie Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-protection/read-only-protection/
---
tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji ochrony tylko do odczytu w Aspose.Words dla .NET. Ta funkcja umożliwia ustawienie dokumentu programu Word jako tylko do odczytu, aby zapobiec nieupoważnionym modyfikacjom. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i zastosowanie ochrony

Zacznij od utworzenia instancji klasy Document i obiektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Zapisz treść w dokumencie
Użyj obiektu DocumentBuilder, aby zapisać treść w dokumencie:

```csharp
builder.Write("Open document as read-only");
```

## Krok 3: Ustaw hasło i ustaw dokument jako tylko do odczytu

Ustaw hasło do dokumentu za pomocą właściwości SetPassword() obiektu WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Pamiętaj, aby zastąpić „Moje hasło” rzeczywistym hasłem, którego chcesz używać.

## Krok 4: Zastosuj dokument tylko do odczytu

Ustaw dokument tylko do odczytu, ustawiając właściwość ReadOnlyRecommended na true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Krok 5: Zastosuj ochronę tylko do odczytu i zapisz dokument

Na koniec zastosuj ochronę tylko do odczytu za pomocą metody Protect() obiektu Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać chroniony dokument.

### Przykładowy kod źródłowy ochrony tylko do odczytu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy ochrony tylko do odczytu przy użyciu Aspose.Words dla .NET:

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Wprowadź hasło o długości do 15 znaków.
doc.WriteProtection.SetPassword("MyPassword");

// Ustaw dokument jako tylko do odczytu.
doc.WriteProtection.ReadOnlyRecommended = true;

// Zastosuj ochronę przed zapisem jako tylko do odczytu.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Wykonując poniższe kroki, możesz łatwo chronić swoje dokumenty

## Wniosek

W tym samouczku zbadaliśmy funkcję ochrony tylko do odczytu w Aspose.Words dla .NET, która pozwala ustawić dokumenty programu Word jako tylko do odczytu, aby zapobiec nieautoryzowanym modyfikacjom. Wykonując podane kroki, możesz łatwo zastosować ochronę tylko do odczytu dla swoich dokumentów i zwiększyć ich bezpieczeństwo. Ochrona tylko do odczytu pomaga zapewnić integralność i dokładność treści dokumentu, ograniczając możliwości edycji. Aspose.Words dla .NET zapewnia potężny i elastyczny interfejs API do obsługi ochrony dokumentów i obsługuje różne inne funkcje umożliwiające dostosowywanie i zabezpieczanie dokumentów programu Word.

### Często zadawane pytania dotyczące ochrony tylko do odczytu w dokumencie programu Word

#### P: Co to jest ochrona tylko do odczytu w Aspose.Words dla .NET?

O: Ochrona tylko do odczytu w Aspose.Words dla .NET to funkcja, która pozwala ustawić dokument programu Word jako tylko do odczytu, zapobiegając nieautoryzowanym modyfikacjom. Gdy dokument jest ustawiony jako tylko do odczytu, użytkownicy mogą go otwierać i przeglądać, ale nie mogą wprowadzać żadnych zmian w jego zawartości.

#### P: Jak mogę zastosować ochronę tylko do odczytu do dokumentu programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby zastosować ochronę tylko do odczytu do dokumentu programu Word za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz instancję`Document` klasa i A`DocumentBuilder` obiekt.
2.  Użyj`DocumentBuilder` aby zapisać treść w dokumencie.
3.  Ustaw hasło do dokumentu za pomocą`SetPassword` metoda`WriteProtection` obiekt.
4.  Ustaw`ReadOnlyRecommended` własność`WriteProtection` oponować`true` aby zalecić otwarcie dokumentu w trybie tylko do odczytu.
5.  Zastosuj ochronę tylko do odczytu za pomocą`Protect` metoda`Document` obiekt, określając`ProtectionType` Jak`ReadOnly`.
6.  Zapisz chroniony dokument za pomocą`Save` metoda`Document` obiekt.

#### P: Czy mogę usunąć ochronę tylko do odczytu z dokumentu programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Tak, możesz usunąć ochronę tylko do odczytu z dokumentu programu Word za pomocą Aspose.Words dla .NET. Aby to zrobić, możesz użyć`Unprotect` metoda`Document` class, która usuwa wszelką istniejącą ochronę z dokumentu.

#### P: Czy mogę ustawić inne hasło w celu ochrony tylko do odczytu w dokumencie programu Word?

 O: Nie, ochrona tylko do odczytu w Aspose.Words dla .NET nie pozwala na ustawienie osobnego hasła specjalnie dla ochrony tylko do odczytu. Hasło ustawione za pomocą`SetPassword` metoda`WriteProtection` obiekt dotyczy ogólnej ochrony dokumentów, obejmującej zarówno ochronę tylko do odczytu, jak i ochronę do odczytu i zapisu.

#### P: Czy użytkownicy mogą ominąć ochronę tylko do odczytu w dokumencie programu Word?

O: Ochrona dokumentu programu Word tylko do odczytu ma na celu zniechęcanie do przypadkowych lub nieautoryzowanych modyfikacji i zapobieganie im. Chociaż zapewnia poziom ochrony, może zostać ominięty przez użytkowników posiadających wystarczającą wiedzę techniczną lub uprawnienia do edycji. Jednakże ochrona tylko do odczytu działa odstraszająco i pomaga zachować integralność dokumentu.