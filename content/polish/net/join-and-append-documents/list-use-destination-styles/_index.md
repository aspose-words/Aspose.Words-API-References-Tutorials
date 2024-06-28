---
title: Lista Użyj stylów miejsc docelowych
linktitle: Lista Użyj stylów miejsc docelowych
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak łączyć i dołączać dokumenty programu Word, zachowując jednocześnie style listy dokumentów docelowych, korzystając z Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/list-use-destination-styles/
---

Ten samouczek poprowadzi Cię przez proces korzystania z funkcji stylów docelowych użycia listy w Aspose.Words dla .NET. Ta funkcja umożliwia łączenie i dołączanie dokumentów programu Word podczas korzystania ze stylów list dokumentu docelowego.

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

## Krok 3: Ustaw dokument źródłowy na kontynuację po dokumencie docelowym

 Aby mieć pewność, że treść dokumentu źródłowego będzie kontynuowana po zakończeniu dokumentu docelowego, należy ustawić opcję`SectionStart` właściwość pierwszej sekcji dokumentu źródłowego do`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Formatowanie listy obsługi

Aby obsłużyć formatowanie listy, przejrzyj każdy akapit w dokumencie źródłowym i sprawdź, czy jest to element listy. Jeśli tak, porównasz identyfikator listy z istniejącymi listami w dokumencie docelowym. Jeśli istnieje lista o tym samym identyfikatorze, utworzysz kopię listy w dokumencie źródłowym i zaktualizujesz format listy akapitu, aby używać skopiowanej listy.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Krok 5: Dołącz dokument źródłowy do dokumentu docelowego

 Teraz możesz dołączyć dokument źródłowy do dokumentu docelowego za pomocą`AppendDocument` metoda`Document` klasa. The`ImportFormatMode.UseDestinationStyles` Parametr zapewnia, że podczas operacji dołączania zostaną użyte style listy dokumentu docelowego.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Krok 6: Zapisz dokument końcowy

Na koniec zapisz scalony dokument z włączoną funkcją Listuj style miejsca docelowego za pomocą opcji`Save` metoda`Document` klasa.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Przykładowy kod źródłowy dla stylów docelowych użycia listy przy użyciu Aspose.Words dla .NET 

Oto pełny kod źródłowy funkcji „Lista użycia stylów docelowych” w języku C# przy użyciu Aspose.Words dla .NET:


```csharp
	// Ścieżka do katalogu dokumentów
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Ustaw dokument źródłowy tak, aby był kontynuowany bezpośrednio po zakończeniu dokumentu docelowego.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Śledź utworzone listy.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Sprawdź, czy dokument docelowy zawiera już listę z tym identyfikatorem. Jeśli tak się stanie, to może to
			// spowodować, że obie listy będą działać razem. Zamiast tego utwórz kopię listy w dokumencie źródłowym.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Dla tego identyfikatora istnieje już nowo skopiowana lista, pobierz zapisaną listę,
				// i użyj go w bieżącym akapicie.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Dodaj kopię tej listy do dokumentu i zachowaj ją do późniejszego wykorzystania.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Ustaw listę tego akapitu na skopiowaną listę.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Dołącz dokument źródłowy na końcu dokumentu docelowego.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Otóż to! Pomyślnie zaimplementowałeś funkcję Lista stylów docelowych przy użyciu Aspose.Words dla .NET. Ostateczny dokument będzie zawierał połączoną treść ze stylami listy z dokumentu docelowego.