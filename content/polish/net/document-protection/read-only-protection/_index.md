---
title: Ochrona tylko do odczytu w dokumencie programu Word
linktitle: Ochrona tylko do odczytu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak chronić dokumenty programu Word, stosując ochronę tylko do odczytu za pomocą Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku.
type: docs
weight: 10
url: /pl/net/document-protection/read-only-protection/
---
## Wstęp

Jeśli chodzi o zarządzanie dokumentami programu Word, czasami trzeba ustawić je jako tylko do odczytu, aby chronić ich zawartość. Niezależnie od tego, czy chodzi o udostępnianie ważnych informacji bez ryzyka przypadkowych zmian, czy o zapewnienie integralności dokumentów prawnych, ochrona tylko do odczytu jest cenną funkcją. W tym samouczku omówimy, jak zaimplementować ochronę tylko do odczytu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez każdy krok w szczegółowy i wciągający sposób, dzięki czemu będziesz mógł łatwo wykonać wszystkie kroki.

## Warunki wstępne

Zanim zagłębimy się w kod, musisz spełnić kilka warunków wstępnych:

1.  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words dla .NET. Można go pobrać z[Strona z wydaniami Aspose](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Skonfiguruj środowisko programistyczne z zainstalowaną platformą .NET. Visual Studio to dobry wybór.
3. Podstawowa znajomość języka C#: W tym samouczku założono, że masz podstawową wiedzę na temat programowania w języku C#.

## Importuj przestrzenie nazw

Najpierw upewnijmy się, że zaimportowaliśmy niezbędne przestrzenie nazw. Jest to kluczowe, ponieważ pozwala nam uzyskać dostęp do klas i metod, których potrzebujemy z Aspose.Words dla .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Krok 1: Skonfiguruj dokument

W tym kroku utworzymy nowy dokument i kreator dokumentów. Stanowi to podstawę naszej działalności.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Napisz jakiś tekst do dokumentu.
builder.Write("Open document as read-only");
```

Wyjaśnienie:

- Zaczynamy od zdefiniowania ścieżki katalogu, w którym zostanie zapisany dokument.
-  Nowy`Document` obiekt jest tworzony, oraz a`DocumentBuilder` jest z tym powiązany.
- Za pomocą kreatora dodajemy do dokumentu prostą linijkę tekstu.

## Krok 2: Ustaw hasło ochrony przed zapisem

Następnie musimy ustawić hasło zabezpieczające przed zapisem. To hasło może mieć maksymalnie 15 znaków.

```csharp
//Wprowadź hasło o długości do 15 znaków.
doc.WriteProtection.SetPassword("MyPassword");
```

Wyjaśnienie:

-  The`SetPassword` metoda jest wywoływana na`WriteProtection` własność dokumentu.
- Podajemy hasło (w tym przypadku „Moje hasło”), które będzie wymagane do usunięcia ochrony.

## Krok 3: Włącz zalecenie tylko do odczytu

Na tym etapie ustawiamy dokument jako zalecany tylko do odczytu. Oznacza to, że po otwarciu dokumentu użytkownik zostanie poproszony o otwarcie go w trybie tylko do odczytu.

```csharp
// Ustaw dokument jako zalecany tylko do odczytu.
doc.WriteProtection.ReadOnlyRecommended = true;
```

Wyjaśnienie:

-  The`ReadOnlyRecommended` właściwość jest ustawiona na`true`.
- Spowoduje to monitowanie użytkowników o otwarcie dokumentu w trybie tylko do odczytu, chociaż mogą zignorować to zalecenie.

## Krok 4: Zastosuj ochronę tylko do odczytu

Na koniec stosujemy ochronę dokumentu tylko do odczytu. Ten krok wymusza ochronę.

```csharp
// Zastosuj ochronę przed zapisem jako tylko do odczytu.
doc.Protect(ProtectionType.ReadOnly);
```

Wyjaśnienie:

-  The`Protect` metoda jest wywoływana w dokumencie za pomocą`ProtectionType.ReadOnly` jako argument.
- Ta metoda wymusza ochronę tylko do odczytu, uniemożliwiając jakąkolwiek modyfikację dokumentu bez hasła.

## Krok 5: Zapisz dokument

Ostatnim krokiem jest zapisanie dokumentu z zastosowanymi ustawieniami ochrony.

```csharp
// Zapisz chroniony dokument.
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Wyjaśnienie:

-  The`Save` metoda jest wywoływana na dokumencie, podając ścieżkę i nazwę pliku.
- Dokument zostanie zapisany z włączonym zabezpieczeniem tylko do odczytu.

## Wniosek

I masz to! Pomyślnie utworzyłeś dokument programu Word chroniony tylko do odczytu przy użyciu Aspose.Words dla .NET. Ta funkcja zapewnia, że zawartość dokumentu pozostanie nienaruszona i niezmieniona, zapewniając dodatkową warstwę bezpieczeństwa. Niezależnie od tego, czy udostępniasz poufne informacje, czy dokumenty prawne, ochrona tylko do odczytu jest niezbędnym narzędziem w Twoim arsenale zarządzania dokumentami.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka, która pozwala programistom tworzyć, modyfikować, konwertować i chronić dokumenty programu Word programowo przy użyciu języka C# lub innych języków .NET.

### Czy mogę usunąć ochronę tylko do odczytu z dokumentu?
 Tak, możesz usunąć ochronę tylko do odczytu, używając`Unprotect` metodę i podaniu prawidłowego hasła.

### Czy hasło ustawione w dokumencie jest zaszyfrowane?
Tak, Aspose.Words szyfruje hasło, aby zapewnić bezpieczeństwo chronionego dokumentu.

### Czy mogę zastosować inne rodzaje ochrony za pomocą Aspose.Words dla .NET?
Tak, Aspose.Words dla .NET obsługuje różne rodzaje ochrony, w tym zezwalanie tylko na komentowanie, wypełnianie formularzy lub śledzenie zmian.

### Czy dostępna jest bezpłatna wersja próbna Aspose.Words dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Strona z wydaniami Aspose](https://releases.aspose.com/).