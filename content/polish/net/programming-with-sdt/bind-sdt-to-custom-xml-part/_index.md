---
title: Powiąż SDT z niestandardową częścią Xml
linktitle: Powiąż SDT z niestandardową częścią Xml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak powiązać znaczniki dokumentów strukturalnych (SDT) z niestandardowymi częściami XML w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając z tego samouczka krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---
## Wstęp

Tworzenie dynamicznych dokumentów programu Word, które wchodzą w interakcję z niestandardowymi danymi XML, może znacznie zwiększyć elastyczność i funkcjonalność aplikacji. Aspose.Words dla .NET zapewnia solidne funkcje wiązania znaczników dokumentów strukturalnych (SDT) z niestandardowymi częściami XML, umożliwiając tworzenie dokumentów, które dynamicznie wyświetlają dane. W tym samouczku przeprowadzimy Cię krok po kroku przez proces wiązania SDT z niestandardową częścią XML. Zanurzmy się!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

-  Aspose.Words dla .NET: Możesz pobrać najnowszą wersję z[Aspose.Words dla wydań .NET](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Visual Studio lub dowolne inne kompatybilne środowisko .NET IDE.
- Podstawowa znajomość C#: Znajomość języka programowania C# i frameworku .NET.

## Importuj przestrzenie nazw

Aby efektywnie używać Aspose.Words dla .NET, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu. Dodaj następujące dyrektywy using na górze pliku kodu:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Saving;
```

Podzielmy proces na łatwe do wykonania kroki, aby ułatwić jego przestrzeganie. Każdy krok będzie dotyczył określonej części zadania.

## Krok 1: Zainicjuj dokument

Najpierw musisz utworzyć nowy dokument i skonfigurować środowisko.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Zainicjuj nowy dokument
Document doc = new Document();
```

Na tym etapie inicjujemy nowy dokument, który będzie zawierał nasze niestandardowe dane XML i SDT.

## Krok 2: Dodaj niestandardową część XML

Następnie dodajemy do dokumentu niestandardową część XML. Ta część będzie zawierać dane XML, które chcemy powiązać z SDT.

```csharp
// Dodaj niestandardową część XML do dokumentu
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

Tutaj tworzymy nową niestandardową część XML z unikalnym identyfikatorem i dodajemy przykładowe dane XML.

## Krok 3: Utwórz znacznik dokumentu strukturalnego (SDT)

Po dodaniu niestandardowej części XML tworzymy SDT do wyświetlania danych XML.

```csharp
// Utwórz znacznik dokumentu strukturalnego (SDT)
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

Tworzymy SDT typu PlainText i dołączamy go do pierwszej sekcji treści dokumentu.

## Krok 4: Powiąż SDT z niestandardową częścią XML

Teraz wiążemy SDT z niestandardową częścią XML za pomocą wyrażenia XPath.

```csharp
// Powiąż SDT z niestandardową częścią XML
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

 Ten krok mapuje SDT na`<text>` element wewnątrz`<root>` węzeł naszej niestandardowej części XML.

## Krok 5: Zapisz dokument

Na koniec zapisujemy dokument we wskazanym katalogu.

```csharp
// Zapisz dokument
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

To polecenie zapisuje dokument z powiązanym SDT w wyznaczonym katalogu.

## Wniosek

Gratulacje! Pomyślnie powiązałeś SDT z niestandardową częścią XML za pomocą Aspose.Words dla .NET. Ta zaawansowana funkcja umożliwia tworzenie dynamicznych dokumentów, które można łatwo aktualizować o nowe dane, po prostu modyfikując zawartość XML. Niezależnie od tego, czy generujesz raporty, tworzysz szablony, czy automatyzujesz obieg dokumentów, Aspose.Words dla .NET oferuje narzędzia, których potrzebujesz, aby Twoje zadania były łatwiejsze i wydajniejsze.

## Często zadawane pytania

### Co to jest znacznik dokumentu strukturalnego (SDT)?
Znacznik dokumentu strukturalnego (SDT) to element kontroli treści w dokumentach programu Word, którego można używać do wiązania danych dynamicznych, dzięki czemu dokumenty są interaktywne i oparte na danych.

### Czy mogę powiązać wiele SDT z różnymi częściami XML w jednym dokumencie?
Tak, możesz powiązać wiele SDT z różnymi częściami XML w tym samym dokumencie, co pozwala na tworzenie złożonych szablonów opartych na danych.

### Jak zaktualizować dane XML w niestandardowej części XML?
 Możesz zaktualizować dane XML, uzyskując dostęp do pliku`CustomXmlPart` obiekt i bezpośrednio modyfikując jego zawartość XML.

### Czy można powiązać SDT z atrybutami XML zamiast z elementami?
Tak, można powiązać SDT z atrybutami XML, określając odpowiednie wyrażenie XPath, które odnosi się do żądanego atrybutu.

### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Words dla .NET?
 Obszerną dokumentację dotyczącą Aspose.Words dla .NET można znaleźć pod adresem[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/).