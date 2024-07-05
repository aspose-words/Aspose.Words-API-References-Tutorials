---
title: Usuń stopki nagłówków źródłowych
linktitle: Usuń stopki nagłówków źródłowych
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak usuwać nagłówki i stopki podczas łączenia i dołączania dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/remove-source-headers-footers/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji Usuń stopki nagłówków źródłowych w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie dokumentów programu Word podczas usuwania nagłówków i stopek z dokumentu źródłowego.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. Zainstalowano Aspose.Words dla .NET. Możesz pobrać go ze strony Aspose lub zainstalować za pomocą NuGet.
2. Visual Studio lub dowolne inne środowisko programistyczne C#.

## Krok 1: Zainicjuj katalogi dokumentów

 Najpierw musisz ustawić ścieżkę do katalogu dokumentów. Zmodyfikuj wartość`dataDir` zmienną na ścieżkę, w której znajdują się Twoje dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Załaduj dokumenty źródłowe i docelowe

Następnie musisz załadować dokumenty źródłowe i docelowe za pomocą Aspose.Words`Document` klasa. Zaktualizuj nazwy plików w`Document` konstruktor zgodnie z nazwami dokumentów.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Usuń nagłówki i stopki z sekcji dokumentu źródłowego

 Aby usunąć nagłówki i stopki z każdej sekcji dokumentu źródłowego, możesz przeglądać sekcje za pomocą a`foreach` zapętl i wywołaj`ClearHeadersFooters` metoda.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Krok 4: Wyłącz ustawienie „LinkToPrevious” dla nagłówków i stopek

Nawet po wyczyszczeniu nagłówków i stopek z dokumentu źródłowego istnieje możliwość, że ustawienie „LinkToPrevious” dla`HeadersFooters` nadal można ustawić. Aby uniknąć tego zachowania, musisz jawnie ustawić je na`false` dla pierwszej sekcji`HeadersFooters` nieruchomość.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Krok 5: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z włączoną funkcją Usuń stopki nagłówków źródłowych za pomocą opcji`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Przykładowy kod źródłowy narzędzia Usuń stopki nagłówków źródłowych przy użyciu Aspose.Words dla platformy .NET 

Oto pełny kod źródłowy funkcji „Usuń stopki nagłówków źródłowych” w języku C# przy użyciu Aspose.Words dla .NET:


```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Usuń nagłówki i stopki z każdej sekcji dokumentu źródłowego.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Nawet po usunięciu nagłówków i stopek z dokumentu źródłowego ustawienie „LinkToPrevious”.
	// dla NagłówkówStopki można nadal ustawić. Spowoduje to kontynuację nagłówków i stopek od miejsca docelowego
	// dokument. Aby uniknąć takiego zachowania, należy ustawić wartość false.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Otóż to! Pomyślnie zaimplementowałeś funkcję Usuń stopki nagłówków źródłowych przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał scaloną treść z nagłówkami i stopkami usuniętymi z dokumentu źródłowego.