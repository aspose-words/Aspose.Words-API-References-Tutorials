---
title: Zmień tabulatory Toc w dokumencie programu Word
linktitle: Zmień tabulatory Toc w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmieniać tabulatory spisu treści w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Ten przewodnik krok po kroku pomoże Ci stworzyć profesjonalnie wyglądający spis treści.
type: docs
weight: 10
url: /pl/net/programming-with-table-of-content/change-toc-tab-stops/
---
## Wstęp

Czy zastanawiałeś się kiedyś, jak urozmaicić spis treści (TOC) w dokumentach programu Word? Może chcesz, aby te tabulatory były idealnie dopasowane, aby zapewnić profesjonalny wygląd. Jesteś we właściwym miejscu! Dzisiaj zagłębiamy się w to, jak zmieniać tabulatory spisu treści za pomocą Aspose.Words dla .NET. Zostań, a obiecuję, że wyjdziesz z całą wiedzą, jak sprawić, by Twój spis treści wyglądał efektownie i schludnie.

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Aspose.Words dla .NET: Można[pobierz go tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Visual Studio lub dowolne IDE zgodne z C#.
3. Dokument programu Word: w szczególności taki, który zawiera spis treści.

Masz to wszystko? Wspaniały! Rzućmy się.

## Importuj przestrzenie nazw

Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw. To jak pakowanie narzędzi przed rozpoczęciem projektu.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Podzielmy ten proces na proste, zrozumiałe etapy. Przejdziemy przez ładowanie dokumentu, modyfikowanie tabulatorów spisu treści i zapisywanie zaktualizowanego dokumentu.

## Krok 1: Załaduj dokument

Dlaczego? Musimy uzyskać dostęp do dokumentu Word zawierającego spis treści, który chcemy zmodyfikować.

Jak? Oto prosty fragment kodu na początek:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument zawierający spis treści
Document doc = new Document(dataDir + "Table of contents.docx");
```

Wyobraź sobie, że Twój dokument jest jak ciasto, a my zaraz dodamy trochę lukru. Pierwszym krokiem jest wyjęcie ciasta z pudełka.

## Krok 2: Zidentyfikuj akapity spisu treści

Dlaczego? Musimy wskazać akapity tworzące spis treści. 

Jak? Przejrzyj akapity i sprawdź ich styl:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Znaleziono akapit spisu treści
    }
}
```

Pomyśl o tym jak o skanowaniu tłumu w celu znalezienia przyjaciół. Tutaj szukamy akapitów stylizowanych na wpisy w spisie treści.

## Krok 3: Zmodyfikuj tabulatory

Dlaczego? To tutaj dzieje się magia. Zmiana tabulatorów nadaje spisowi treści bardziej przejrzysty wygląd.

Jak? Usuń istniejący tabulator i dodaj nowy w zmodyfikowanej pozycji:

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

To jak dostosowywanie mebli w salonie, aż będą odpowiednie. Poprawiamy te tabulatory, aby były idealne.

## Krok 4: Zapisz zmodyfikowany dokument

Dlaczego? Aby mieć pewność, że cała Twoja ciężka praca zostanie zapisana i będzie można ją przeglądać lub udostępniać.

Jak? Zapisz dokument pod nową nazwą, aby zachować oryginał:

```csharp
// Zapisz zmodyfikowany dokument
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

I voila! Twój spis treści zawiera teraz tabulatory dokładnie tam, gdzie chcesz.

## Wniosek

Zmiana tabulatorów spisu treści w dokumencie programu Word za pomocą Aspose.Words dla .NET jest prosta po podzieleniu na części. Ładując dokument, identyfikując akapity spisu treści, modyfikując tabulatory i zapisując dokument, możesz uzyskać dopracowany i profesjonalny wygląd. Pamiętaj, że praktyka czyni mistrza, więc eksperymentuj z różnymi pozycjami tabulatorów, aby uzyskać dokładnie taki układ, jakiego pragniesz.

## Często zadawane pytania

### Czy mogę oddzielnie modyfikować tabulatory dla różnych poziomów spisu treści?
Tak, możesz! Po prostu sprawdź każdy konkretny poziom TOC (Toc1, Toc2 itp.) i odpowiednio dostosuj.

### Co się stanie, jeśli mój dokument zawiera wiele spisów treści?
Kod skanuje wszystkie akapity ze stylem TOC, zatem modyfikuje wszystkie spisy treści obecne w dokumencie.

### Czy można dodać wiele tabulatorów we wpisie spisu treści?
 Absolutnie! Możesz dodać dowolną liczbę tabulatorów, dostosowując opcję`para.ParagraphFormat.TabStops` kolekcja.

### Czy mogę zmienić wyrównanie tabulatora i styl linii wiodącej?
Tak, podczas dodawania nowego tabulatora można określić różne wyrównania i style linii wiodących.

### Czy potrzebuję licencji, aby używać Aspose.Words dla .NET?
 Tak, potrzebujesz ważnej licencji, aby używać Aspose.Words dla .NET po okresie próbnym. Możesz zdobyć[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) Lub[kup jeden](https://purchase.aspose.com/buy).