---
title: Odłącz nagłówki i stopki
linktitle: Odłącz nagłówki i stopki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łączyć i dołączać dokumenty programu Word podczas odłączania nagłówków i stopek za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/unlink-headers-footers/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji Odłącz nagłówki i stopki w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie dokumentów programu Word przy jednoczesnym odłączaniu nagłówków i stopek od dokumentu źródłowego.

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

## Krok 3: Odłącz nagłówki i stopki w dokumencie źródłowym

 Aby odłączyć nagłówki i stopki w dokumencie źródłowym od kontynuowania nagłówków i stopek dokumentu docelowego, należy ustawić`LinkToPrevious` własność`HeadersFooters` zbiór w pierwszej części dokumentu źródłowego do`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z włączoną funkcją Odłącz nagłówki i stopki za pomocą opcji`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Przykładowy kod źródłowy dla stopek odłączających nagłówki przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy funkcji „Odłącz stopki nagłówków” w języku C# przy użyciu Aspose.Words dla .NET:

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Aby temu zapobiec, odłącz nagłówki i stopki w dokumencie źródłowym
	// od kontynuowania nagłówków i stopek dokumentu docelowego.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję Odłącz stopki nagłówków przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał scaloną treść z nagłówkami i stopkami z dokumentu źródłowego odłączonymi od dokumentu docelowego.