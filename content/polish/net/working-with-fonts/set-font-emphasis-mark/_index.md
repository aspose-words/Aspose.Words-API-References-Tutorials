---
title: Ustaw znacznik wyróżnienia czcionki
linktitle: Ustaw znacznik wyróżnienia czcionki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić styl wyróżnienia czcionki w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/set-font-emphasis-mark/
---

W tym samouczku pokażemy, jak ustawić styl wyróżnienia czcionki w dokumencie programu Word za pomocą Aspose.Words dla .NET. Podkreślenie czcionki służy do wyróżniania określonych słów lub fraz w tekście.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie

## Krok 1: Zdefiniuj katalog dokumentów
Zacznij od ustawienia ścieżki katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Utwórz i dostosuj dokument
 Utwórz instancję`Document` klasa i powiązana`DocumentBuilder` do tworzenia treści dokumentu. Użyj`Font.EmphasisMark` właściwość, na którą chcesz ustawić styl wyróżnienia czcionki`EmphasisMark.UnderSolidCircle` . Następnie użyj`Write`I`Writeln` metody`DocumentBuilder` , aby dodać tekst z określonym wyróżnieniem czcionki.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Krok 3: Zapisz dokument
 Zapisz dokument za pomocą`Save` metoda`Document` z odpowiednią ścieżką i nazwą pliku.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Przykładowy kod źródłowy dla opcji Ustaw znak wyróżnienia czcionki przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Wniosek
W tym samouczku nauczyłeś się, jak ustawić styl wyróżnienia czcionki w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Eksperymentuj z różnymi stylami wyróżniania i korzystaj z tej funkcji, aby wyróżniać słowa lub frazy w dokumentach.

### Często zadawane pytania

#### P: Jak mogę dodać znaki akcentujące do określonej czcionki w dokumencie programu Word za pomocą Aspose.Words?

Odp.: Aby dodać znaki akcentujące do określonej czcionki w dokumencie programu Word za pomocą Aspose.Words, możesz użyć interfejsu API, aby przejść do żądanej czcionki i zastosować odpowiednie znaki akcentujące. Spowoduje to dodanie znaków akcentujących do tekstu wybraną czcionką.

#### P: Czy można zmienić styl znaków akcentujących w dokumencie programu Word za pomocą Aspose.Words?

Odp.: Tak, za pomocą Aspose.Words możesz zmienić styl znaków akcentujących w dokumencie Word. Interfejs API pozwala dostosować właściwości stylu, takie jak kolor, rozmiar, rodzaj linii itp., aby dostosować wygląd znaków akcentujących.

#### P: Jak mogę usunąć wszystkie akcenty z dokumentu Word za pomocą Aspose.Words?

Odp.: Aby usunąć wszystkie akcenty z dokumentu programu Word za pomocą Aspose.Words, możesz użyć interfejsu API do przeglądania dokumentu, wykryć istniejące znaki akcentu i usunąć je za pomocą odpowiednich metod. Spowoduje to usunięcie wszystkich znaków podkreślenia z dokumentu.

#### P: Czy mogę dodać znaki akcentujące do określonej części tekstu w dokumencie programu Word?

Odp.: Tak, możesz dodać znaki akcentujące do określonej części tekstu w dokumencie programu Word za pomocą Aspose.Words. Za pomocą API możesz wybrać żądany zakres tekstu i dodać odpowiednie znaki wyróżnienia do tej części tekstu.

#### P: Czy znaki akcentujące można dostosować do moich potrzeb?

Odp.: Tak, znaki akcentujące można dostosować do swoich potrzeb za pomocą Aspose.Words. Możesz dostosować właściwości stylu znaków akcentujących, takie jak kolor, rozmiar, rodzaj linii i inne, aby dopasować je do preferencji formatowania.