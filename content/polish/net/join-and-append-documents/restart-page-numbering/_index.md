---
title: Uruchom ponownie numerację stron
linktitle: Uruchom ponownie numerację stron
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ponownie uruchomić numerowanie stron podczas łączenia i dołączania dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/restart-page-numbering/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji ponownego uruchamiania numerowania stron w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie dokumentów programu Word podczas ponownego rozpoczynania numeracji stron w dokumencie źródłowym.

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

## Krok 3: Ustaw dokument źródłowy na ponowne rozpoczęcie numerowania stron

 Aby ponownie uruchomić numerację stron w dokumencie źródłowym, należy ustawić`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.NewPage` i ustaw`RestartPageNumbering`własność do`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z włączoną funkcją Uruchom ponownie numerowanie stron za pomocą`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Przykładowy kod źródłowy dla ponownego uruchomienia numerowania stron przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy funkcji „Uruchom ponownie numerowanie stron” w języku C# przy użyciu Aspose.Words dla .NET:
 

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję Uruchom ponownie numerację stron przy użyciu Aspose.Words dla .NET. Dokument końcowy będzie zawierał scaloną treść z wznowioną numeracją stron w dokumencie źródłowym.