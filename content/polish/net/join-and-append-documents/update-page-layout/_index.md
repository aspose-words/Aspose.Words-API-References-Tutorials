---
title: Zaktualizuj układ strony
linktitle: Zaktualizuj układ strony
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zaktualizować układ strony podczas łączenia i dołączania dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/update-page-layout/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji Aktualizuj układ strony w Aspose.Words dla .NET. Ta funkcja zapewnia prawidłową aktualizację układu strony podczas łączenia i dołączania dokumentów programu Word.

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

## Krok 3: Zaktualizuj układ strony dla dokumentu docelowego

 Aby mieć pewność, że układ strony zostanie poprawnie zaktualizowany przed dołączeniem dokumentu źródłowego, możesz wywołać metodę`UpdatePageLayout` metodę w dokumencie docelowym.

```csharp
dstDoc.UpdatePageLayout();
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Ponownie zaktualizuj układ strony

 Po dołączeniu dokumentu źródłowego należy wywołać metodę`UpdatePageLayout`metodę w dokumencie docelowym, aby upewnić się, że wszelkie zmiany wprowadzone po operacji dołączania zostaną odzwierciedlone w renderowanym wyniku.

```csharp
dstDoc.UpdatePageLayout();
```

## Krok 6: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z włączoną funkcją Aktualizuj układ strony za pomocą`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Przykładowy kod źródłowy aktualizacji układu strony przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy funkcji „Aktualizuj układ strony” w języku C# przy użyciu Aspose.Words dla .NET:

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Jeśli dokument docelowy jest renderowany do formatu PDF, obrazu itp.
	// lub UpdatePageLayout jest wywoływany przed dokumentem źródłowym. jest dołączony,
	// wówczas wszelkie zmiany wprowadzone później nie zostaną odzwierciedlone w renderowanym wyniku
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Aby zmiany zostały zaktualizowane do renderowanych danych wyjściowych, należy ponownie wywołać funkcję UpdatePageLayout.
	// Jeśli nie zostanie wywołany ponownie, dołączony dokument nie pojawi się w wynikach następnego renderowania.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję Aktualizuj układ strony przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał scaloną treść z poprawnie zaktualizowanym układem strony.