---
title: Zakres znaczników dokumentu strukturalnego Rozpocznij mapowanie Xml
linktitle: Zakres znaczników dokumentu strukturalnego Rozpocznij mapowanie Xml
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dynamicznie wiązać dane XML ze znacznikami dokumentów strukturalnych w programie Word przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## Wstęp

Czy kiedykolwiek chciałeś dynamicznie wstawiać dane XML do dokumentu Word? Cóż, masz szczęście! Aspose.Words dla .NET sprawia, że to zadanie jest proste. W tym samouczku zagłębimy się w mapowanie XML w zakresie znaczników dokumentów strukturalnych. Ta funkcja umożliwia powiązanie niestandardowych części XML z kontrolkami treści, zapewniając płynną aktualizację treści dokumentu wraz z danymi XML. Gotowy do przekształcenia dokumentów w dynamiczne arcydzieła.

## Warunki wstępne

Zanim przejdziemy do części dotyczącej kodowania, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Aspose.Words dla biblioteki .NET: Upewnij się, że masz najnowszą wersję. Możesz go pobrać[Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Visual Studio lub dowolne inne IDE obsługujące C#.
3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# jest koniecznością.
4. Dokument programu Word: przykładowy dokument programu Word do pracy.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw. Dzięki temu będziemy mieli dostęp do wszystkich wymaganych klas i metod w Aspose.Words dla .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Krok 1: Skonfiguruj katalog dokumentów

Każdy projekt potrzebuje fundamentu, prawda? Tutaj ustawiamy ścieżkę do katalogu dokumentów.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokument Word

Następnie ładujemy dokument Word. To jest dokument, w którym będziemy wstawiać nasze dane XML.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Krok 3: Dodaj niestandardową część XML

Musimy skonstruować część XML zawierającą dane, które chcemy wstawić, i dodać ją do kolekcji CustomXmlPart dokumentu. Ta niestandardowa część XML będzie służyć jako źródło danych dla naszych uporządkowanych znaczników dokumentów.

### Tworzenie części XML

Najpierw wygeneruj unikalny identyfikator dla części XML i zdefiniuj jej zawartość.

```csharp
// Utwórz część XML zawierającą dane i dodaj ją do kolekcji CustomXmlPart dokumentu.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Sprawdź zawartość części XML

Aby mieć pewność, że część XML została poprawnie dodana, drukujemy jej zawartość.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Krok 4: Utwórz znacznik dokumentu strukturalnego

Znacznik dokumentu strukturalnego (SDT) to element sterujący zawartością, który można powiązać z częścią XML. Tutaj tworzymy SDT, który wyświetli zawartość naszej niestandardowej części XML.

Najpierw znajdź w dokumencie początek zakresu SDT.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Krok 5: Ustaw mapowanie XML dla SDT

Teraz nadszedł czas na powiązanie naszej części XML z SDT. Ustawiając mapowanie XML, określamy, która część danych XML powinna być wyświetlana w SDT.

 XPath wskazuje konkretny element w części XML, który chcemy wyświetlić. Tutaj wskazujemy na to drugie`<text>` element wewnątrz`<root>` element.

```csharp
// Ustaw mapowanie dla naszego StructuredDocumentTag
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Krok 6: Zapisz dokument

Na koniec zapisz dokument, aby zobaczyć zmiany w działaniu. SDT w dokumencie programu Word będzie teraz wyświetlać określoną treść XML.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Wniosek

masz to! Pomyślnie zamapowałeś część XML na znacznik dokumentu strukturalnego w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Ta zaawansowana funkcja umożliwia łatwe tworzenie dynamicznych i opartych na danych dokumentów. Niezależnie od tego, czy generujesz raporty, faktury, czy inny typ dokumentu, mapowanie XML może znacznie usprawnić przepływ pracy.

## Często zadawane pytania

### Co to jest znacznik dokumentu strukturalnego w programie Word?
Ustrukturyzowane znaczniki dokumentów, zwane także kontrolkami zawartości, to kontenery dla określonych typów treści w dokumentach programu Word. Można ich używać do wiązania danych, ograniczania edycji lub wspierania użytkowników podczas tworzenia dokumentu.

### Jak mogę dynamicznie aktualizować zawartość części XML?
 Możesz zaktualizować zawartość części XML, modyfikując plik`xmlPartContent` string przed dodaniem go do dokumentu. Po prostu zaktualizuj ciąg o nowe dane i dodaj go do`CustomXmlParts` kolekcja.

### Czy mogę powiązać wiele części XML z różnymi zestawami SDT w tym samym dokumencie?
Tak, możesz powiązać wiele części XML z różnymi SDT w tym samym dokumencie. Każdy zestaw SDT może mieć własną, unikalną część XML i mapowanie XPath.

### Czy możliwe jest mapowanie złożonych struktur XML na SDT?
Absolutnie! Możesz mapować złożone struktury XML na SDT, używając szczegółowych wyrażeń XPath, które dokładnie wskazują żądane elementy w części XML.

### Jak mogę usunąć część XML z dokumentu?
 Możesz usunąć część XML, wywołując metodę`Remove` metoda na`CustomXmlParts` zbieranie, przekazywanie`xmlPartId` części XML, którą chcesz usunąć.