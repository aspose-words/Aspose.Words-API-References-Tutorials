---
title: Dodaj przedrostek nazwy klasy CSS
linktitle: Dodaj przedrostek nazwy klasy CSS
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać przedrostek nazwy klasy CSS podczas zapisywania dokumentów programu Word jako HTML przy użyciu Aspose.Words dla .NET. Zawiera przewodnik krok po kroku, fragmenty kodu i często zadawane pytania.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Wstęp

Powitanie! Jeśli nurkujesz w świecie Aspose.Words dla .NET, czeka Cię prawdziwa gratka. Dzisiaj przyjrzymy się, jak dodać przedrostek nazwy klasy CSS podczas zapisywania dokumentu programu Word jako HTML przy użyciu Aspose.Words dla .NET. Ta funkcja jest bardzo przydatna, jeśli chcesz uniknąć konfliktów nazw klas w plikach HTML.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

-  Aspose.Words dla .NET: Jeśli jeszcze go nie zainstalowałeś,[pobierz go tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Visual Studio lub dowolne inne IDE C#.
-  Dokument programu Word: Będziemy używać dokumentu o nazwie`Rendering.docx`. Umieść go w katalogu swojego projektu.

## Importuj przestrzenie nazw

Najpierw upewnij się, że do projektu C# zaimportowano niezbędne przestrzenie nazw. Dodaj je na górze pliku kodu:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Przejdźmy teraz do przewodnika krok po kroku!

## Krok 1: Skonfiguruj swój projekt

Zanim zaczniemy dodawać przedrostek nazwy klasy CSS, skonfigurujmy nasz projekt.

### Krok 1.1: Utwórz nowy projekt

 Uruchom program Visual Studio i utwórz nowy projekt aplikacji konsolowej. Nazwij to czymś chwytliwym, np`AsposeCssPrefixExample`.

### Krok 1.2: Dodaj Aspose.Words dla .NET

Jeśli jeszcze tego nie zrobiłeś, dodaj Aspose.Words dla .NET do swojego projektu za pośrednictwem NuGet. Po prostu otwórz konsolę Menedżera pakietów NuGet i uruchom:

```bash
Install-Package Aspose.Words
```

Świetnie! Teraz jesteśmy gotowi, aby rozpocząć kodowanie.

## Krok 2: Załaduj swój dokument

Pierwszą rzeczą, którą musimy zrobić, to załadować dokument Word, który chcemy przekonwertować na HTML.

### Krok 2.1: Zdefiniuj ścieżkę dokumentu

 Ustaw ścieżkę do katalogu dokumentów. Na potrzeby tego samouczka załóżmy, że dokument znajduje się w folderze o nazwie`Documents` w katalogu Twojego projektu.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Krok 2.2: Załaduj dokument

Teraz załadujmy dokument za pomocą Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania HTML

Następnie musimy skonfigurować opcje zapisywania HTML, aby zawierały przedrostek nazwy klasy CSS.

### Krok 3.1: Utwórz opcje zapisu HTML

 Utwórz instancję`HtmlSaveOptions` obiekt i ustaw typ arkusza stylów CSS na`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Krok 3.2: Ustaw prefiks nazwy klasy CSS

 Teraz ustawmy`CssClassNamePrefix` właściwość do żądanego przedrostka. W tym przykładzie użyjemy`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Krok 4: Zapisz dokument jako HTML

Na koniec zapiszmy dokument jako plik HTML z naszymi skonfigurowanymi opcjami.


Określ ścieżkę wyjściowego pliku HTML i zapisz dokument.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Krok 5: Sprawdź dane wyjściowe

 Po uruchomieniu projektu przejdź do pliku`Documents` falcówka. Powinieneś znaleźć plik HTML o nazwie`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Otwórz ten plik w edytorze tekstu lub przeglądarce, aby sprawdzić, czy klasy CSS mają przedrostek`pfx_`.

## Wniosek

I masz to! Wykonując te kroki, pomyślnie dodałeś przedrostek nazwy klasy CSS do danych wyjściowych HTML za pomocą Aspose.Words dla .NET. Ta prosta, ale zaawansowana funkcja może pomóc w utrzymaniu przejrzystych i pozbawionych konfliktów stylów w dokumentach HTML.

## Często zadawane pytania

### Czy mogę użyć innego prefiksu dla każdej operacji zapisywania?
 Tak, możesz dostosować prefiks za każdym razem, gdy zapisujesz dokument, zmieniając`CssClassNamePrefix` nieruchomość.

### Czy ta metoda obsługuje wbudowany CSS?
 The`CssClassNamePrefix`Właściwość działa z zewnętrznym CSS. W przypadku wbudowanego CSS będziesz potrzebować innego podejścia.

### Jak mogę uwzględnić inne opcje zapisywania HTML?
 Można skonfigurować różne właściwości`HtmlSaveOptions` aby dostosować wyjście HTML. Sprawdź[dokumentacja](https://reference.aspose.com/words/net/) aby uzyskać więcej szczegółów.

### Czy można zapisać kod HTML w strumieniu?
 Absolutnie! Możesz zapisać dokument w strumieniu, przekazując obiekt strumienia do`Save` metoda.

### Jak uzyskać pomoc, jeśli napotkam problemy?
 Możesz uzyskać wsparcie od[forum dyskusyjne](https://forum.aspose.com/c/words/8).