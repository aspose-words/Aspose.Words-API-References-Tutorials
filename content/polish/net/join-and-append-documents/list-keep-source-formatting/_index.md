---
title: Lista Zachowaj formatowanie źródła
linktitle: Lista Zachowaj formatowanie źródła
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zachować formatowanie listy podczas łączenia i dołączania dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/list-keep-source-formatting/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji List Keep Source Formatting w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie dokumentów programu Word przy jednoczesnym zachowaniu formatowania źródłowego list.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Ustaw dokument źródłowy na ciągły przepływ

 Aby mieć pewność, że zawartość dokumentu źródłowego będzie stale przepływać po dołączeniu do dokumentu docelowego, należy ustawić opcję`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting`Parametr zapewnia, że formatowanie źródła, w tym formatowanie list, zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 5: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z włączoną funkcją List Keep Source Formatting za pomocą`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Przykładowy kod źródłowy dla formatowania źródła List Keep przy użyciu Aspose.Words dla .NET 

Oto pełny kod źródłowy funkcji List Keep Source Formatting w języku C# przy użyciu Aspose.Words dla .NET:

```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Dołącz treść dokumentu, aby przebiegała w sposób ciągły.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję List Keep Source Formatting przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał scaloną treść z zachowanym formatowaniem listy dokumentu źródłowego.