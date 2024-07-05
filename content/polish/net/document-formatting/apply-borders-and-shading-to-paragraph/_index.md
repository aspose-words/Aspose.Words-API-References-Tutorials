---
title: Zastosuj obramowanie i cieniowanie do akapitu w dokumencie programu Word
linktitle: Zastosuj obramowanie i cieniowanie do akapitu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Zastosuj obramowania i cieniowanie do akapitów w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby ulepszyć formatowanie dokumentu.
type: docs
weight: 10
url: /pl/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## Wstęp

Hej, zastanawiałeś się kiedyś, jak sprawić, by dokumenty programu Word wyróżniały się fantazyjnymi obramowaniami i cieniowaniem? Cóż, jesteś we właściwym miejscu! Dzisiaj zagłębiamy się w świat Aspose.Words dla .NET, aby urozmaicić nasze akapity. Wyobraź sobie, że Twój dokument wygląda tak elegancko, jak praca profesjonalnego projektanta przy zaledwie kilku linijkach kodu. Gotowy żeby zacząć? Chodźmy!

## Warunki wstępne

Zanim zakasamy rękawy i zagłębimy się w kodowanie, upewnijmy się, że mamy wszystko, czego potrzebujemy. Oto Twoja krótka lista kontrolna:

-  Aspose.Words dla .NET: Musisz mieć zainstalowaną tę bibliotekę. Można go pobrać z[Strona Aspose](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Visual Studio lub dowolne inne IDE obsługujące platformę .NET.
- Podstawowa znajomość języka C#: wystarczająca do zrozumienia i ulepszenia fragmentów kodu.
- Ważna licencja: albo a[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) lub kupiony od[Załóż](https://purchase.aspose.com/buy).

## Importuj przestrzenie nazw

Zanim przejdziemy do kodu, musimy się upewnić, że do naszego projektu zaimportowaliśmy niezbędne przestrzenie nazw. Dzięki temu wszystkie fajne funkcje Aspose.Words są dla nas dostępne.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

Podzielmy teraz proces na małe kroki. Każdy krok będzie miał nagłówek i szczegółowe wyjaśnienie. Gotowy? Chodźmy!

## Krok 1: Skonfiguruj katalog dokumentów

Po pierwsze, potrzebujemy miejsca na zapisanie naszego pięknie sformatowanego dokumentu. Ustawmy ścieżkę do katalogu dokumentów.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 W tym katalogu zostanie zapisany ostateczny dokument. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką na twoim komputerze.

## Krok 2: Utwórz nowy dokument i narzędzie DocumentBuider

 Następnie musimy utworzyć nowy dokument i plik`DocumentBuilder` obiekt. The`DocumentBuilder` to nasza magiczna różdżka, która pozwala nam manipulować dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 The`Document` obiekt reprezentuje cały nasz dokument Worda, a`DocumentBuilder` pomaga nam dodawać i formatować treści.

## Krok 3: Zdefiniuj granice akapitu

Teraz dodajmy kilka stylowych obramowań do naszego akapitu. Określimy odległość od tekstu i ustawimy różne style obramowania.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

Tutaj ustawiamy 20-punktową odległość między tekstem a krawędziami. Granice ze wszystkich stron (lewej, prawej, górnej, dolnej) są ustawione jako podwójne linie. Fantazyjne, prawda?

## Krok 4: Zastosuj cieniowanie do akapitu

Granice są świetne, ale zwiększmy poziom, dodając trochę cieniowania. Aby wyróżnić nasz akapit, użyjemy ukośnego wzoru krzyża z mieszanką kolorów.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

Na tym etapie zastosowaliśmy ukośną teksturę krzyżową z jasnym koralem jako kolorem tła i jasnym łososiem jako kolorem pierwszego planu. To jak ubieranie swojego akapitu w markowe ciuchy!

## Krok 5: Dodaj tekst do akapitu

Czym jest akapit bez tekstu? Dodajmy przykładowe zdanie, aby zobaczyć nasze formatowanie w akcji.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

Ta linia wstawia nasz tekst do dokumentu. Proste, ale teraz oprawione w stylową ramkę i cieniowane tło.

## Krok 6: Zapisz dokument

Wreszcie nadszedł czas, aby zapisać naszą pracę. Zapiszmy dokument we wskazanym katalogu o opisowej nazwie.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 Spowoduje to zapisanie naszego dokumentu z nazwą`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` w katalogu, który podaliśmy wcześniej.

## Wniosek

I masz to! Za pomocą zaledwie kilku linijek kodu przekształciliśmy zwykły akapit w atrakcyjną wizualnie treść. Aspose.Words dla .NET sprawia, że dodawanie profesjonalnie wyglądającego formatowania do dokumentów jest niezwykle łatwe. Niezależnie od tego, czy przygotowujesz raport, list, czy jakikolwiek dokument, te triki pomogą Ci zrobić świetne wrażenie. Więc śmiało, wypróbuj i zobacz, jak Twoje dokumenty ożywają!

## Często zadawane pytania

### Czy mogę używać różnych stylów linii dla każdej krawędzi?  
 Absolutnie! Aspose.Words dla .NET umożliwia indywidualne dostosowanie każdej ramki. Po prostu ustaw`LineStyle` dla każdego typu obramowania, jak pokazano w przewodniku.

### Jakie inne tekstury cieniowania są dostępne?  
 Można użyć kilku tekstur, takich jak pełny, poziomy pasek, pionowy pasek i inne. Sprawdź[Złóż dokumentację](https://reference.aspose.com/words/net/) aby uzyskać pełną listę.

### Jak mogę zmienić kolor obramowania?  
 Kolor obramowania można ustawić za pomocą`Color` własność każdej granicy. Na przykład,`borders[BorderType.Left].Color = Color.Red;`.

### Czy można zastosować obramowanie i cieniowanie w określonej części tekstu?  
 Tak, możesz zastosować obramowania i cieniowanie do określonych ciągów tekstu za pomocą`Run` obiekt w`DocumentBuilder`.

### Czy mogę zautomatyzować ten proces dla wielu akapitów?  
Zdecydowanie! Możesz przeglądać akapity w pętli i programowo stosować te same ustawienia obramowań i cieniowania.
