---
title: Prosty dokument dołączania
linktitle: Prosty dokument dołączania
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łączyć i dołączać dokumenty programu Word z zachowanym formatowaniem przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/simple-append-document/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji prostego dodawania dokumentów w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie dokumentów programu Word bez dodatkowych opcji.

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

## Krok 3: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 4: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument za pomocą funkcji prostego dołączenia dokumentu, korzystając z pliku`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Przykładowy kod źródłowy dla prostego dołączenia dokumentu przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy funkcji „Simple Append Document” w języku C# przy użyciu Aspose.Words dla .NET:

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Dołącz dokument źródłowy do dokumentu docelowego, nie korzystając z dodatkowych opcji.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję prostego dołączania dokumentu przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał scaloną treść z zachowanym formatowaniem źródłowym.