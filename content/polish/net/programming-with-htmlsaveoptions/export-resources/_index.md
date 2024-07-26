---
title: Eksportuj zasoby
linktitle: Eksportuj zasoby
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak eksportować zasoby, takie jak CSS i czcionki, jednocześnie zapisując dokumenty programu Word jako HTML przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-resources/
---
## Wstęp

Witajcie, entuzjaści technologii! Jeśli kiedykolwiek musiałeś przekonwertować dokumenty Word na HTML, jesteś we właściwym miejscu. Dzisiaj zanurzamy się w cudowny świat Aspose.Words dla .NET. Ta potężna biblioteka ułatwia programową pracę z dokumentami programu Word. W tym samouczku omówimy kroki eksportowania zasobów, takich jak czcionki i CSS, podczas zapisywania dokumentu programu Word jako HTML przy użyciu Aspose.Words dla .NET. Zapnij pasy i wybierz się na zabawną i pouczającą przejażdżkę!

## Warunki wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć. Oto krótka lista kontrolna:

1.  Visual Studio: Upewnij się, że na komputerze jest zainstalowany program Visual Studio. Można go pobrać z[Witryna internetowa programu Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words dla .NET: Będziesz potrzebować biblioteki Aspose.Words dla .NET. Jeśli jeszcze go nie masz, skorzystaj z bezpłatnej wersji próbnej[Wydania Aspose](https://releases.aspose.com/words/net/) lub kup go w sklepie[Sklep Aspose](https://purchase.aspose.com/buy).
3. Podstawowa znajomość języka C#: Podstawowa znajomość języka C# pomoże Ci postępować zgodnie z przykładami kodu.

Masz to wszystko? Świetnie! Przejdźmy do importowania niezbędnych przestrzeni nazw.

## Importuj przestrzenie nazw

Aby używać Aspose.Words dla .NET, musisz uwzględnić odpowiednie przestrzenie nazw w swoim projekcie. Oto jak to zrobić:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Te przestrzenie nazw są kluczowe dla uzyskania dostępu do klas i metod Aspose.Words, których będziemy używać w naszym samouczku.

Rozłóżmy proces eksportowania zasobów podczas zapisywania dokumentu Word jako HTML. Zrobimy to krok po kroku, aby było łatwo to śledzić.

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, musisz określić ścieżkę do katalogu dokumentów. Tutaj znajduje się dokument programu Word i miejsce, w którym zostanie zapisany plik HTML.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu.

## Krok 2: Załaduj dokument Word

 Następnie załadujmy dokument Word, który chcesz przekonwertować na HTML. W tym samouczku użyjemy dokumentu o nazwie`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Ta linia kodu ładuje dokument z określonego katalogu.

## Krok 3: Skonfiguruj opcje zapisywania HTML

Aby wyeksportować zasoby, takie jak CSS i czcionki, musisz skonfigurować plik`HtmlSaveOptions`. Ten krok ma kluczowe znaczenie dla zapewnienia, że dane wyjściowe HTML mają dobrą strukturę i zawierają niezbędne zasoby.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://przykład.com/zasoby”
};
```

Rozłóżmy działanie każdej opcji:
- `CssStyleSheetType = CssStyleSheetType.External`: ta opcja określa, że style CSS powinny być zapisywane w zewnętrznym arkuszu stylów.
- `ExportFontResources = true`: Umożliwia eksport zasobów czcionek.
- `ResourceFolder = dataDir + "Resources"`: Określa folder lokalny, w którym będą zapisywane zasoby (takie jak czcionki i pliki CSS).
- `ResourceFolderAlias = "http://example.com/resources"`: Ustawia alias folderu zasobów, który będzie używany w pliku HTML.

## Krok 4: Zapisz dokument jako HTML

Po skonfigurowaniu opcji zapisywania ostatnim krokiem jest zapisanie dokumentu jako pliku HTML. Oto jak to zrobić:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Ta linia kodu zapisuje dokument w formacie HTML wraz z wyeksportowanymi zasobami.

## Wniosek

masz to! Pomyślnie wyeksportowałeś zasoby podczas zapisywania dokumentu Word jako HTML przy użyciu Aspose.Words dla .NET. Dzięki tej potężnej bibliotece programowa obsługa dokumentów programu Word staje się dziecinnie prosta. Niezależnie od tego, czy pracujesz nad aplikacją internetową, czy po prostu chcesz przekonwertować dokumenty do użytku w trybie offline, Aspose.Words pomoże Ci.

## Często zadawane pytania

### Czy mogę eksportować obrazy wraz z czcionkami i CSS?
 Tak, możesz! Aspose.Words dla .NET obsługuje również eksportowanie obrazów. Tylko pamiętaj o skonfigurowaniu`HtmlSaveOptions` odpowiednio.

### Czy istnieje sposób na osadzenie CSS zamiast korzystania z zewnętrznego arkusza stylów?
 Absolutnie. Możesz ustawić`CssStyleSheetType` Do`CssStyleSheetType.Embedded` jeśli wolisz style osadzone.

### Jak mogę dostosować nazwę wyjściowego pliku HTML?
 Możesz określić dowolną nazwę pliku w pliku`doc.Save` metoda. Na przykład,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Czy Aspose.Words obsługuje inne formaty oprócz HTML?
 Tak, obsługuje różne formaty, w tym PDF, DOCX, TXT i inne. Sprawdź[dokumentacja](https://reference.aspose.com/words/net/) aby uzyskać pełną listę.

### Gdzie mogę uzyskać więcej wsparcia i zasobów?
Aby uzyskać dodatkową pomoc, odwiedź stronę[Forum wsparcia Aspose.Words](https://forum.aspose.com/c/words/8) . Szczegółową dokumentację i przykłady można również znaleźć na stronie[Strona Aspose](https://reference.aspose.com/words/net/).