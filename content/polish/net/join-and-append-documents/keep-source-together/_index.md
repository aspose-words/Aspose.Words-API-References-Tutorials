---
title: Zachowajcie źródło razem
linktitle: Zachowajcie źródło razem
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak używać Aspose.Words dla .NET do łączenia i dołączania dokumentów programu Word, zachowując jednocześnie treść źródłową z dokumentem docelowym.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/keep-source-together/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji Keep Source Together w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie wielu dokumentów programu Word, zachowując jednocześnie zawartość dokumentu źródłowego z zawartością dokumentu docelowego. 

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

Następnie musisz załadować dokumenty źródłowe i docelowe za pomocą Aspose.Words.`Document` klasa. Zaktualizuj nazwy plików w`Document` konstruktor zgodnie z nazwami dokumentów.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Ustaw dokument źródłowy tak, aby pojawiał się po treści dokumentu docelowego

 Aby mieć pewność, że dokument źródłowy pojawi się bezpośrednio po treści dokumentu docelowego, należy ustawić opcję`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Ustaw formatowanie akapitu „Zachowuj z następnym” dla dokumentu źródłowego

 Aby zachować razem akapity w dokumencie źródłowym, możesz przeglądać każdy akapit w dokumencie i ustawić opcję`KeepWithNext`własność do`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Krok 5: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.KeepSourceFormatting` Parametr gwarantuje, że formatowanie źródłowe zostanie zachowane podczas operacji dołączania.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Krok 6: Zapisz dokument końcowy

 Na koniec zapisz scalony dokument z włączoną funkcją „Zachowaj źródło razem” za pomocą pliku`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Przykładowy kod źródłowy dla Keep Source Together przy użyciu Aspose.Words dla .NET 

Oto pełny kod źródłowy funkcji „Keep Source Together” w języku C# przy użyciu Aspose.Words dla .NET:


```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ustaw dokument źródłowy tak, aby pojawiał się bezpośrednio po treści dokumentu docelowego.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję Keep Source Together przy użyciu Aspose.Words dla .NET. Dokument końcowy będzie zawierał połączoną treść z akapitami dokumentu źródłowego przechowywanymi razem.