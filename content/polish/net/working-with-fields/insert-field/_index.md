---
title: Wstaw pole
linktitle: Wstaw pole
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pole do dokumentów programu Word za pomocą Aspose.Words dla .NET. Personalizuj swoje dokumenty za pomocą pól dynamicznych.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-field/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu i narzędzia DocumentBuilder

Zaczynamy od utworzenia nowego dokumentu i zainicjowania narzędzia DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstawianie pola

 Używamy`InsertField()` metoda DocumentBuilder, aby wstawić pole do dokumentu. W tym przykładzie wstawiamy pole scalania (MERGEFIELD) z nazwą pola „MyFieldName” i formatem scalania.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Przykład kodu źródłowego do wstawienia pola za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i narzędzie DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Wstaw pole.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

W tym przykładzie utworzyliśmy nowy dokument, zainicjowaliśmy narzędzie DocumentBuilder, a następnie wstawiliśmy pole scalania o nazwie pola „MyFieldName” i formacie scalania. Dokument jest następnie zapisywany pod określoną nazwą pliku.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Wstaw pole” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Co to jest pole w programie Word?

Odp.: Pole w programie Word to element umożliwiający wstawianie i manipulowanie danymi dynamicznymi w dokumencie. Można go używać do wyświetlania informacji zmiennych, takich jak daty, numery stron, tabele, wzory matematyczne itp.

#### P: Jak wstawić pole do dokumentu programu Word?

Odp.: Aby wstawić pole do dokumentu programu Word, możesz wykonać następujące kroki:

1. Umieść kursor w miejscu, w którym chcesz wstawić pole.
2. Przejdź do zakładki „Wstaw” na wstążce.
3. Kliknij przycisk „Pole” w grupie „Tekst”, aby otworzyć okno dialogowe pól.
4. Z listy rozwijanej wybierz typ pola, które chcesz wstawić.
5. Skonfiguruj opcje pola według potrzeb.
6. Kliknij przycisk „OK”, aby wstawić pole do dokumentu.

#### P: Jakie są powszechnie używane typy pól w programie Word?

Odp.: Program Word oferuje szeroką gamę typów pól, których można używać w dokumentach. Oto niektóre z powszechnie używanych typów pól:

- Data i godzina: wyświetla aktualną datę i godzinę.
- Numer strony: wyświetla numer bieżącej strony.
- Spis treści: automatycznie generuje spis treści w oparciu o style Twoich tytułów.
- Obliczenia: wykonuje obliczenia matematyczne za pomocą wzorów.
- Tekst wypełniający: Generuje losowy tekst do wypełnienia dokumentu.

#### P: Czy mogę dostosować wygląd pól w programie Word?

Odp.: Tak, możesz dostosować wygląd pól w programie Word, korzystając z dostępnych opcji formatowania. Można na przykład zmienić czcionkę, rozmiar, kolor i styl tekstu w polu. Można także zastosować efekty formatowania, takie jak pogrubienie, kursywa i podkreślenie.
  