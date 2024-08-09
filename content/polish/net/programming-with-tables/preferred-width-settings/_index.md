---
title: Preferowane ustawienia szerokości
linktitle: Preferowane ustawienia szerokości
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć tabele z ustawieniami szerokości bezwzględnej, względnej i automatycznej w Aspose.Words dla .NET, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-tables/preferred-width-settings/
---
## Wstęp

Tabele to skuteczny sposób organizowania i prezentowania informacji w dokumentach programu Word. Podczas pracy z tabelami w Aspose.Words dla .NET masz kilka opcji ustawiania szerokości komórek tabeli, aby mieć pewność, że idealnie pasują do układu dokumentu. Ten przewodnik przeprowadzi Cię przez proces tworzenia tabel z preferowanymi ustawieniami szerokości przy użyciu Aspose.Words dla .NET, koncentrując się na opcjach rozmiaru bezwzględnego, względnego i automatycznego. 

## Warunki wstępne

Zanim zagłębisz się w samouczek, upewnij się, że posiadasz następujące elementy:

1.  Aspose.Words dla .NET: Upewnij się, że masz zainstalowany Aspose.Words dla .NET w swoim środowisku programistycznym. Możesz go pobrać[Tutaj](https://releases.aspose.com/words/net/).

2. Środowisko programistyczne .NET: skonfiguruj środowisko programistyczne .NET, takie jak Visual Studio.

3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# pomoże Ci lepiej zrozumieć fragmenty kodu i przykłady.

4.  Dokumentacja Aspose.Words: Patrz[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/) aby uzyskać szczegółowe informacje o API i dalszą lekturę.

## Importuj przestrzenie nazw

Zanim zaczniesz kodować, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Te przestrzenie nazw zapewniają dostęp do podstawowych funkcjonalności Aspose.Words i obiektu Table, umożliwiając manipulowanie tabelami dokumentów.

Podzielmy proces tworzenia tabeli z różnymi preferowanymi ustawieniami szerokości na jasne i łatwe do wykonania etapy.

## Krok 1: Zainicjuj dokument i narzędzie DocumentBuider

Nagłówek: Tworzenie nowego dokumentu i narzędzie DocumentBuilder

 Objaśnienie: Zacznij od utworzenia nowego dokumentu programu Word i a`DocumentBuilder` przykład. The`DocumentBuilder` class zapewnia prosty sposób dodawania treści do dokumentu.

```csharp
// Zdefiniuj ścieżkę do zapisania dokumentu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Utwórz nowy dokument.
Document doc = new Document();

// Utwórz narzędzie DocumentBuilder dla tego dokumentu.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tutaj określasz katalog, w którym dokument zostanie zapisany i inicjujesz plik`Document`I`DocumentBuilder` obiekty.

## Krok 2: Wstaw pierwszą komórkę tabeli o szerokości bezwzględnej

Wstaw pierwszą komórkę do tabeli o stałej szerokości 40 punktów. Dzięki temu komórka ta zawsze zachowa szerokość 40 punktów, niezależnie od rozmiaru tabeli.

```csharp

// Wstaw komórkę o rozmiarze bezwzględnym.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

 tym kroku rozpoczynasz tworzenie tabeli i wstawiasz komórkę o szerokości bezwzględnej. The`PreferredWidth.FromPoints(40)` metoda ustawia szerokość komórki na 40 punktów, oraz`Shading.BackgroundPatternColor` stosuje jasnożółty kolor tła.

## Krok 3: Wstaw komórkę o względnym rozmiarze

Wstaw kolejną komórkę o szerokości równej 20% całkowitej szerokości tabeli. Dzięki temu względnemu rozmiarowi komórka dopasowuje się proporcjonalnie do szerokości stołu.

```csharp
// Wstaw komórkę o względnym (procentowym) rozmiarze.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

Szerokość tej komórki będzie wynosić 20% całkowitej szerokości tabeli, dzięki czemu będzie można ją dostosować do różnych rozmiarów ekranów i układów dokumentów.

### Krok 4: Wstaw komórkę o automatycznym rozmiarze

Na koniec wstaw komórkę, która automatycznie dopasuje się do pozostałego dostępnego miejsca w tabeli.

```csharp
// Wstaw komórkę o rozmiarze automatycznym.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 The`PreferredWidth.Auto` ustawienie pozwala tej komórce rozszerzać się lub kurczyć w zależności od miejsca pozostałego po uwzględnieniu innych komórek. Dzięki temu układ stołu będzie wyglądał zrównoważony i profesjonalny.

## Krok 5: Sfinalizuj i zapisz dokument

Po wstawieniu wszystkich komórek uzupełnij tabelę i zapisz dokument w określonej ścieżce.

```csharp
// Zapisz dokument.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Ten krok kończy tabelę i zapisuje dokument pod nazwą „WorkingWithTables.PreferredWidthSettings.docx” w wyznaczonym katalogu.

## Wniosek

Tworzenie tabel z preferowanymi ustawieniami szerokości w Aspose.Words dla .NET jest proste, jeśli zrozumiesz różne dostępne opcje rozmiaru. Niezależnie od tego, czy potrzebujesz stałych, względnych czy automatycznych szerokości komórek, Aspose.Words zapewnia elastyczność pozwalającą efektywnie obsługiwać różne scenariusze układu tabeli. Wykonując czynności opisane w tym przewodniku, możesz mieć pewność, że tabele w dokumentach programu Word będą miały dobrą strukturę i będą atrakcyjne wizualnie.

## Często zadawane pytania

### Jaka jest różnica między bezwzględną i względną szerokością komórek?
Bezwzględne szerokości komórek są stałe i nie ulegają zmianie, natomiast szerokości względne dostosowują się w oparciu o całkowitą szerokość tabeli.

### Czy mogę używać ujemnych wartości procentowych dla szerokości względnych?
Nie, ujemne wartości procentowe nie dotyczą szerokości komórek. Dozwolone są tylko wartości procentowe dodatnie.

### Jak działa funkcja automatycznego dopasowywania rozmiaru?
Automatyczne dopasowywanie rozmiaru dostosowuje szerokość komórki tak, aby wypełnić całą pozostałą przestrzeń w tabeli po zmianie rozmiaru innych komórek.

### Czy mogę zastosować różne style do komórek o różnych ustawieniach szerokości?
Tak, możesz zastosować różne style i formatowanie do komórek niezależnie od ich ustawień szerokości.

### Co się stanie, jeśli całkowita szerokość tabeli będzie mniejsza niż suma szerokości wszystkich komórek?
Tabela automatycznie dopasuje szerokość komórek do dostępnej przestrzeni, co może spowodować zmniejszenie niektórych komórek.