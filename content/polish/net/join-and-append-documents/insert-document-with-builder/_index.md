---
title: Wstaw dokument za pomocą Buildera
linktitle: Wstaw dokument za pomocą Buildera
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak połączyć dwa dokumenty programu Word za pomocą Aspose.Words dla .NET. Przewodnik krok po kroku dotyczący wstawiania dokumentu za pomocą narzędzia DocumentBuilder i zachowywania formatowania.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/insert-document-with-builder/
---
## Wstęp

Masz więc dwa dokumenty programu Word i chcesz połączyć je w jeden. Być może zastanawiasz się: „Czy istnieje prosty sposób, aby zrobić to programowo?” Absolutnie! Dzisiaj przeprowadzę Cię przez proces wstawiania jednego dokumentu do drugiego przy użyciu biblioteki Aspose.Words dla .NET. Ta metoda jest bardzo przydatna, zwłaszcza gdy masz do czynienia z dużymi dokumentami lub chcesz zautomatyzować proces. Zanurkujmy od razu!

## Warunki wstępne

Zanim zaczniemy, upewnijmy się, że masz wszystko, czego potrzebujesz:

1.  Aspose.Words dla .NET: Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go z[Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Upewnij się, że masz zainstalowany program Visual Studio lub inny odpowiedni IDE.
3. Podstawowa znajomość języka C#: Trochę znajomości języka C# bardzo się przyda.

## Importuj przestrzenie nazw

Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności biblioteki Aspose.Words. Oto jak możesz to zrobić:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Teraz, gdy mamy już warunki wstępne, przeanalizujmy proces krok po kroku.

## Krok 1: Konfigurowanie katalogu dokumentów

Zanim zaczniemy kodować, musisz ustawić ścieżkę do katalogu dokumentów. Tutaj przechowywane są dokumenty źródłowe i docelowe.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką, w której znajdują się Twoje dokumenty. Pomoże to programowi łatwo znaleźć Twoje pliki.

## Krok 2: Ładowanie dokumentów źródłowych i docelowych

Następnie musimy załadować dokumenty, z którymi chcemy pracować. W tym przykładzie mamy dokument źródłowy i dokument docelowy.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Tutaj używamy`Document` class z biblioteki Aspose.Words, aby załadować nasze dokumenty. Upewnij się, że nazwy plików odpowiadają nazwom w Twoim katalogu.

## Krok 3: Tworzenie obiektu DocumentBuilder

 The`DocumentBuilder` class to potężne narzędzie w bibliotece Aspose.Words. Umożliwia nam nawigację i manipulowanie dokumentem.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 Na tym etapie utworzyliśmy plik`DocumentBuilder` obiekt dla naszego dokumentu docelowego. Pomoże nam to wstawić treść do dokumentu.

## Krok 4: Przejście na koniec dokumentu

Przed wstawieniem dokumentu źródłowego musimy przesunąć kursor konstruktora na koniec dokumentu docelowego.

```csharp
builder.MoveToDocumentEnd();
```

Dzięki temu dokument źródłowy zostanie wstawiony na końcu dokumentu docelowego.

## Krok 5: Wstawianie podziału strony

Aby zachować porządek, przed wstawieniem dokumentu źródłowego dodajmy podział strony. Spowoduje to rozpoczęcie zawartości dokumentu źródłowego na nowej stronie.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Podział strony gwarantuje, że treść dokumentu źródłowego rozpoczyna się na nowej stronie, dzięki czemu scalony dokument wygląda profesjonalnie.

## Krok 6: Wstawianie dokumentu źródłowego

Teraz następuje ekscytująca część — wstawianie dokumentu źródłowego do dokumentu docelowego.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 Używając`InsertDocument` metodą możemy wstawić cały dokument źródłowy do dokumentu docelowego. The`ImportFormatMode.KeepSourceFormatting` zapewnia zachowanie formatowania dokumentu źródłowego.

## Krok 7: Zapisywanie scalonego dokumentu

Na koniec zapiszmy scalony dokument. Spowoduje to połączenie dokumentów źródłowych i docelowych w jeden plik.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Zapisując dokument, kończymy proces łączenia obu dokumentów. Twój nowy dokument jest teraz gotowy i zapisany w określonym katalogu.

## Wniosek

I masz to! Pomyślnie wstawiłeś jeden dokument do drugiego za pomocą Aspose.Words dla .NET. Ta metoda jest nie tylko wydajna, ale także zachowuje formatowanie obu dokumentów, zapewniając płynne scalanie. Niezależnie od tego, czy pracujesz nad jednorazowym projektem, czy chcesz zautomatyzować przetwarzanie dokumentów, Aspose.Words dla .NET Ci pomoże.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?  
Aspose.Words dla .NET to potężna biblioteka, która pozwala programistom programowo tworzyć, edytować, konwertować i manipulować dokumentami programu Word.

### Czy mogę zachować formatowanie dokumentu źródłowego?  
 Tak, za pomocą`ImportFormatMode.KeepSourceFormatting`, formatowanie dokumentu źródłowego zostaje zachowane po wstawieniu go do dokumentu docelowego.

### Czy potrzebuję licencji, aby używać Aspose.Words dla .NET?  
 Tak, Aspose.Words dla .NET wymaga licencji dla pełnej funkcjonalności. Możesz zdobyć[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) dla ewolucji.

### Czy mogę zautomatyzować ten proces?  
Absolutnie! Opisaną metodę można włączyć do większych aplikacji w celu automatyzacji zadań związanych z przetwarzaniem dokumentów.

### Gdzie mogę znaleźć więcej zasobów i wsparcia?  
Aby uzyskać więcej informacji, możesz sprawdzić[dokumentacja](https://reference.aspose.com/words/net/) lub odwiedź stronę[forum wsparcia](https://forum.aspose.com/c/words/8) do pomocy.