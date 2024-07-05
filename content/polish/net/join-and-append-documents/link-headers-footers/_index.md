---
title: Nagłówki linków, stopki
linktitle: Nagłówki linków, stopki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łączyć nagłówki i stopki podczas łączenia i dołączania dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/link-headers-footers/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji Link Headers Footers w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie wielu dokumentów programu Word podczas łączenia nagłówków i stopek dokumentu źródłowego z poprzednią sekcją w dokumencie docelowym.

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

## Krok 3: Ustaw dołączony dokument tak, aby pojawiał się na nowej stronie

 Aby mieć pewność, że treść dokumentu źródłowego pojawi się na nowej stronie w dokumencie docelowym, należy ustawić opcję`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Krok 4: Połącz nagłówki i stopki z poprzednią sekcją

 Aby połączyć nagłówki i stopki dokumentu źródłowego z poprzednią sekcją w dokumencie docelowym, możesz użyć metody`LinkToPrevious` metoda`HeadersFooters` kolekcja. Przechodząc`true` jako parametr zastępujesz wszelkie istniejące nagłówki i stopki w dokumencie źródłowym.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Krok 5: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z połączonymi nagłówkami i stopkami, używając metody`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Przykładowy kod źródłowy dla stopek nagłówków linków przy użyciu Aspose.Words dla .NET 

Oto pełny kod źródłowy funkcji „Stopki nagłówków linków” w języku C# przy użyciu Aspose.Words dla .NET:


```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ustaw dołączony dokument tak, aby pojawiał się na nowej stronie.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Połącz nagłówki i stopki w dokumencie źródłowym z poprzednią sekcją.
	// Spowoduje to zastąpienie wszelkich nagłówków i stopek znajdujących się już w dokumencie źródłowym.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję Stopki nagłówków łączy przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał połączoną treść z nagłówkami i stopkami z dokumentu źródłowego połączonymi z poprzednią sekcją w dokumencie docelowym.