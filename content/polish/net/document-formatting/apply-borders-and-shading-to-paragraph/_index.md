---
title: Zastosuj obramowanie i cieniowanie do akapitu w dokumencie programu Word
linktitle: Zastosuj obramowanie i cieniowanie do akapitu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zastosować obramowanie i cieniowanie do akapitu w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
tym samouczku pokażemy, jak zastosować obramowanie i cieniowanie do akapitu w dokumencie programu Word, korzystając z funkcjonalności Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zastosować zmiany w formatowaniu.

## Krok 1: Tworzenie i konfiguracja dokumentu

Aby rozpocząć, utwórz nowy dokument i powiązany obiekt DocumentBuilder. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Konfiguracja granic

Teraz skonfigurujmy obramowanie akapitu, określając styl obramowania dla każdej strony. Oto jak:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Krok 3: Konfiguracja wypełnienia

Teraz skonfigurujemy wypełnienie akapitu, określając teksturę i kolory wypełnienia. Oto jak:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Krok 4: Dodaj treść

Zamierzamy dodać sformatowaną treść do akapitu. Oto jak:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Krok 3: Zapisywanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save` metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Przykładowy kod źródłowy dla zastosowania obramowań i cieniowania do akapitu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji Zastosuj obramowania i cieniowanie do akapitu w Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Wniosek

 tym samouczku nauczyliśmy się, jak zastosować obramowanie i cieniowanie do akapitu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Konfigurując akapit`Borders` I`Shading` właściwości, mogliśmy ustawić styl obramowania, kolor linii i kolor wypełnienia akapitu. Aspose.Words dla .NET zapewnia potężne możliwości formatowania, aby dostosować wygląd akapitów i ulepszyć wizualną reprezentację dokumentów.

### Często zadawane pytania

#### P: Jak zastosować obramowanie i cieniowanie do akapitu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby zastosować obramowanie i cieniowanie do akapitu w dokumencie programu Word przy użyciu Aspose.Words dla .NET, wykonaj następujące kroki:
1.  Utwórz nowy dokument i a`DocumentBuilder` obiekt.
2.  Skonfiguruj obramowanie akapitów, uzyskując dostęp do pliku`Borders` własność`ParagraphFormat` i ustawienie stylu obramowania dla każdej strony.
3.  Skonfiguruj wypełnienie akapitu, uzyskując dostęp do`Shading` własność`ParagraphFormat` oraz określenie tekstury i kolorów wypełnienia.
4.  Dodaj treść do akapitu za pomocą`Write` metoda`DocumentBuilder`.
5.  Zapisz dokument za pomocą`Save` metoda.

#### P: Jak ustawić styl obramowania dla każdej strony akapitu?

 O: Aby ustawić styl obramowania dla każdej strony akapitu, możesz uzyskać dostęp do opcji`Borders` własność`ParagraphFormat` i ustaw`LineStyle` własność dla każdego`BorderType` (np,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Można określić różne style linii, np`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`itp.

#### P: Jak określić teksturę i kolory wypełnienia dla cieniowania akapitu?

 O: Aby określić teksturę i kolory wypełnienia cieniowania akapitu, możesz uzyskać dostęp do opcji`Shading` własność`ParagraphFormat` i ustaw`Texture` właściwość do żądanego indeksu tekstury (np.`TextureIndex.TextureDiagonalCross` ). Można także ustawić`BackgroundPatternColor` I`ForegroundPatternColor` właściwości do żądanych kolorów za pomocą`System.Drawing.Color` klasa.