---
title: Zmień tabulatory Toc w dokumencie programu Word
linktitle: Zmień tabulatory Toc w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmieniać karty spisu treści w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words dla .NET to potężna biblioteka do tworzenia, edytowania i manipulowania dokumentami Word w aplikacji C#. Wśród funkcjonalności oferowanych przez Aspose.Words istnieje możliwość modyfikacji zakładek używanych w spisie treści dokumentu Word. W tym przewodniku pokażemy, jak używać kodu źródłowego C# Aspose.Words dla .NET do zmiany kart w spisie treści dokumentu.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to popularna biblioteka, która sprawia, że przetwarzanie tekstu w dokumentach Word jest łatwe i wydajne. Oferuje szeroką gamę funkcji do tworzenia, edytowania i manipulowania dokumentami programu Word, w tym zmianę zakładek spisu treści.

## Ładowanie dokumentu zawierającego spis treści

Pierwszym krokiem jest załadowanie dokumentu Word zawierającego spis treści, który chcesz zmodyfikować. Użyj klasy Document, aby załadować dokument z pliku źródłowego. Oto przykład :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

tym przykładzie ładujemy dokument „Spis treści.docx” znajdujący się w katalogu dokumentów.

## Zmiana zakładek w spisie treści

Po załadowaniu dokumentu przeglądamy każdy akapit dokumentu i sprawdzamy, czy jest on sformatowany przy użyciu stylów wynikowych spisu treści (TOC). Jeżeli tak, modyfikujemy tabulatory służące do wyrównania numeracji stron. Oto jak:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

W tym przykładzie używamy pętli do przeglądania każdego akapitu w dokumencie. Następnie sprawdzamy, czy akapit jest sformatowany przy użyciu stylów wyników spisu treści (TOC). Jeśli tak, uzyskujemy dostęp do pierwszej zakładki użytej w tym akapicie i modyfikujemy ją, usuwając starą zakładkę i dodając nową zakładkę ze zmodyfikowaną pozycją.

## Zapisz zmodyfikowany dokument

Po dokonaniu niezbędnych zmian w zakładkach spisu treści zmodyfikowany dokument można zapisać korzystając z metody Save klasy Document. Oto przykład :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

W tym przykładzie zapisujemy zmodyfikowany dokument jako „WorkingWithTableOfContent.ChangeTocTabStops.docx”.

### Przykładowy kod źródłowy funkcji „Edytuj karty spisu treści” w Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument zawierający spis treści
Document doc = new Document(dataDir + "Table of contents.docx");

// Modyfikuj zakładki spisu treści
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Wniosek

W tym przewodniku omówiliśmy, jak używać Aspose.Words dla .NET do zmiany zakładek w spisie treści dokumentu programu Word przy użyciu dostarczonego kodu źródłowego C#. Wykonując podane kroki, możesz łatwo dostosować karty spisu treści w dokumentach programu Word w aplikacji C#. Aspose.Words oferuje ogromną elastyczność i możliwości pracy ze stylami i formatowaniem dokumentów, umożliwiając tworzenie atrakcyjnych i profesjonalnych dokumentów Word.

### Często zadawane pytania dotyczące zmiany tabulatorów w dokumencie programu Word

#### P: Jaki jest cel funkcji „Zmień tabulatory Toc w dokumencie programu Word” w Aspose.Words dla .NET?

Odp.: Funkcja „Zmień tabulatory w dokumencie programu Word” w Aspose.Words dla .NET umożliwia modyfikację tabulatorów używanych w spisie treści dokumentu programu Word. Umożliwia dostosowanie wyrównania i położenia numerów stron oraz odpowiadających im nagłówków w spisie treści.

#### P: Co to jest Aspose.Words dla .NET?

Odp.: Aspose.Words dla .NET to potężna biblioteka przeznaczona do przetwarzania tekstu w dokumentach Word w aplikacjach .NET. Zapewnia wszechstronne funkcje umożliwiające programowe tworzenie, edytowanie, manipulowanie i konwertowanie dokumentów programu Word przy użyciu języka C# lub innych języków .NET.

#### P: Jak załadować dokument Word zawierający spis treści przy użyciu Aspose.Words dla .NET?

 Odp.: Aby załadować dokument Word zawierający spis treści przy użyciu Aspose.Words dla .NET, możesz użyć`Document` klasa i jej konstruktor. Podając ścieżkę pliku dokumentu, możesz załadować go do pliku`Document` obiekt. Oto przykład:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Ten fragment kodu ładuje dokument „Spis treści.docx” znajdujący się w określonym katalogu.

#### P: Jak mogę zmienić karty używane w spisie treści przy użyciu Aspose.Words dla .NET?

O: Po załadowaniu dokumentu możesz przeglądać każdy akapit dokumentu i sprawdzać, czy jest on sformatowany przy użyciu stylów wynikowych spisu treści (TOC). Jeśli akapit jest sformatowany w stylu spisu treści, możesz modyfikować tabulatory używane do wyrównywania numerów stron. W Aspose.Words dla .NET możesz uzyskać dostęp do`ParagraphFormat` właściwość każdego akapitu, aby pobrać i zmodyfikować tabulatory. Oto przykład:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

W tym kodzie pętla wykonuje iterację po każdym akapicie dokumentu. Jeśli akapit ma styl spisu treści, uzyskuje dostęp do pierwszego tabulatora użytego w tym akapicie, usuwa go i dodaje nowy tabulator ze zmodyfikowaną pozycją.

#### P: Czy mogę zmieniać karty dla wielu poziomów spisu treści przy użyciu Aspose.Words dla .NET?

Odp.: Tak, możesz zmieniać zakładki dla wielu poziomów spisu treści za pomocą Aspose.Words dla .NET. Przeglądając każdy akapit i sprawdzając styl spisu treści, możesz modyfikować karty osobno dla każdego poziomu. Można uzyskać dostęp do żądanego poziomu spisu treści i odpowiednio dostosować tabulatory.

#### P: Jak zapisać zmodyfikowany dokument po zmianie zakładek w spisie treści przy użyciu Aspose.Words dla .NET?

 Odp.: Po dokonaniu niezbędnych zmian w zakładkach spisu treści, możesz zapisać zmodyfikowany dokument za pomocą`Save` metoda`Document` klasa. Podaj żądaną ścieżkę pliku i nazwę dokumentu wyjściowego jako parametr pliku`Save` metoda. Oto przykład:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Ten kod zapisuje zmodyfikowany dokument jako „WorkingWithTableOfContent.ChangeTocTabStops.docx”.

#### P: Czy mogę dostosować inne aspekty spisu treści za pomocą Aspose.Words dla .NET?

O: Tak, dzięki Aspose.Words dla .NET możesz dostosować różne aspekty spisu treści. Oprócz zmiany zakładek możesz modyfikować style czcionki, rozmiar, wyrównanie i inne właściwości formatowania wpisów spisu treści i numerów stron. Dodatkowo możesz dostosować wcięcia, odstępy i formatowanie odpowiednich nagłówków.

#### Q:. Czy mogę zmienić wyrównanie tabulatorów i znaki wiodące w spisie treści za pomocą Aspose.Words dla .NET?

Odp.: Tak, możesz zmienić wyrównanie tabulatorów i znaki wiodące w spisie treści za pomocą Aspose.Words dla .NET. Uzyskując dostęp do tabulatorów i dostosowując ich wyrównanie oraz właściwości wiodące, można kontrolować wyrównanie i wygląd numerów stron i odpowiadających im nagłówków w spisie treści.

#### P: Czy Aspose.Words dla .NET obsługuje zmianę innych stylów i formatowanie w dokumentach Word?

O: Tak, Aspose.Words dla .NET zapewnia szerokie wsparcie dla zmiany różnych stylów i formatowania w dokumentach Word. Umożliwia modyfikowanie stylów różnych elementów, takich jak akapity, nagłówki, tabele, listy i inne. Możesz zmieniać czcionki, kolory, wyrównanie, wcięcia, odstępy i inne aspekty formatowania zgodnie z własnymi wymaganiami.

#### P: Czy mogę modyfikować karty w spisie treści w istniejącym dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Tak, możesz modyfikować karty spisu treści w istniejącym dokumencie programu Word przy użyciu Aspose.Words dla .NET. Ładując dokument, przeglądając akapity i wprowadzając niezbędne zmiany w tabulatorach, możesz zaktualizować tabulatory w spisie treści. Na koniec zapisz dokument, aby zastosować modyfikacje.