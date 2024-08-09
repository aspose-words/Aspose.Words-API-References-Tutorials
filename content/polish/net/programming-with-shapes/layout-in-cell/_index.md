---
title: Układ W Komórce
linktitle: Układ W Komórce
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić układ w komórce za pomocą Aspose.Words dla .NET, korzystając z tego obszernego przewodnika. Idealny dla programistów chcących dostosować dokumenty programu Word.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/layout-in-cell/
---
## Wstęp

Jeśli kiedykolwiek chciałeś programowo dostosować układ komórek tabeli w dokumentach programu Word, jesteś we właściwym miejscu. Dzisiaj zajmiemy się ustawianiem układu w komórce za pomocą Aspose.Words dla .NET. Omówimy praktyczny przykład, dzieląc go krok po kroku, abyś mógł z łatwością go śledzić.

## Warunki wstępne

Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words dla .NET. Jeśli tego nie zrobiłeś, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Będziesz potrzebować środowiska programistycznego skonfigurowanego z platformą .NET. Visual Studio to świetny wybór, jeśli szukasz rekomendacji.
3. Podstawowa znajomość języka C#: chociaż wyjaśnię każdy krok, podstawowa znajomość języka C# ułatwi ci wykonanie wszystkich czynności.
4.  Katalog dokumentów: Przygotuj ścieżkę katalogu, w którym będziesz zapisywać swoje dokumenty. Będziemy to nazywać`YOUR DOCUMENT DIRECTORY`.

## Importuj przestrzenie nazw

Aby rozpocząć, upewnij się, że importujesz niezbędne przestrzenie nazw w swoim projekcie:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Podzielmy proces na łatwe do wykonania etapy.

## Krok 1: Utwórz nowy dokument

 Najpierw utworzymy nowy dokument Word i zainicjujemy plik`DocumentBuilder` obiekt, który pomoże nam konstruować naszą treść.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Uruchom tabelę i ustaw format wiersza

Zaczniemy konstruować tabelę i określimy wysokość oraz regułę wysokości wierszy.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Krok 3: Wstaw komórki i wypełnij treścią

Następnie wykonujemy pętlę, aby wstawić komórki do tabeli. Za każde 7 komórek zakończymy wiersz, aby utworzyć nowy.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Krok 4: Dodaj kształt znaku wodnego

 Teraz dodajmy znak wodny do naszego dokumentu. Stworzymy`Shape` obiekt i ustawić jego właściwości.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Wyświetl kształt poza komórką tabeli, jeśli zostanie on umieszczony w komórce.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Krok 5: Dostosuj wygląd znaku wodnego

Będziemy dalej dostosowywać wygląd znaku wodnego, ustawiając jego właściwości koloru i tekstu.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Krok 6: Wstaw znak wodny do dokumentu

Znajdziemy ostatni przebieg w dokumencie i wstawimy znak wodny w tym miejscu.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Krok 7: Zoptymalizuj dokument dla programu Word 2010

Aby zapewnić kompatybilność, zoptymalizujemy dokument dla programu Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Krok 8: Zapisz dokument

Na koniec zapiszemy nasz dokument we wskazanym katalogu.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Wniosek

I masz to! Pomyślnie utworzyłeś dokument Word z dostosowanym układem tabeli i dodałeś znak wodny za pomocą Aspose.Words dla .NET. Celem tego samouczka było zapewnienie jasnego przewodnika krok po kroku, który pomoże Ci zrozumieć każdą część procesu. Dzięki tym umiejętnościom możesz teraz programowo tworzyć bardziej wyrafinowane i dostosowane dokumenty programu Word.

## Często zadawane pytania

### Czy mogę użyć innej czcionki w tekście znaku wodnego?
 Tak, możesz zmienić czcionkę, ustawiając`watermark.TextPath.FontFamily` właściwość do żądanej czcionki.

### Jak dostosować położenie znaku wodnego?
 Możesz modyfikować`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , I`VerticalAlignment` właściwości umożliwiające dostosowanie położenia znaku wodnego.

### Czy w znaku wodnym można użyć obrazu zamiast tekstu?
 Absolutnie! Możesz stworzyć`Shape` z typem`ShapeType.Image` i ustaw jego obraz za pomocą`ImageData.SetImage` metoda.

### Czy mogę tworzyć tabele o różnej wysokości wierszy?
Tak, możesz ustawić różne wysokości dla każdego wiersza, zmieniając`RowFormat.Height` właściwość przed wstawieniem komórek do tego wiersza.

### Jak usunąć znak wodny z dokumentu?
 Możesz usunąć znak wodny, lokalizując go w kolekcji kształtów dokumentu i wywołując metodę`Remove` metoda.