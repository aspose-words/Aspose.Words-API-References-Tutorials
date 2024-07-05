---
title: Wstaw dokument przy zamianie
linktitle: Wstaw dokument przy zamianie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak bezproblemowo wstawić jeden dokument programu Word do drugiego za pomocą Aspose.Words dla .NET, korzystając z naszego szczegółowego przewodnika krok po kroku. Idealny dla programistów chcących usprawnić przetwarzanie dokumentów.
type: docs
weight: 10
url: /pl/net/clone-and-combine-documents/insert-document-at-replace/
---
## Wstęp

Hej, mistrzowie dokumentów! Czy kiedykolwiek zagłębiłeś się w kod i próbowałeś dowiedzieć się, jak płynnie wstawić jeden dokument programu Word do drugiego? Nie obawiaj się, ponieważ dzisiaj zagłębiamy się w świat Aspose.Words dla .NET, dzięki któremu to zadanie stanie się proste. Przeanalizujemy szczegółowy przewodnik krok po kroku dotyczący korzystania z tej potężnej biblioteki do wstawiania dokumentów w określonych momentach operacji wyszukiwania i zamiany. Gotowy, aby zostać kreatorem Aspose.Words? Zacznijmy!

## Warunki wstępne

Zanim przejdziemy do kodu, jest kilka rzeczy, które musisz mieć na miejscu:

-  Visual Studio: Upewnij się, że na komputerze jest zainstalowany program Visual Studio. Jeśli jeszcze go nie masz, możesz go pobrać ze strony[Tutaj](https://visualstudio.microsoft.com/).
-  Aspose.Words dla .NET: Będziesz potrzebować biblioteki Aspose.Words. Można go zdobyć z[Strona Aspose](https://releases.aspose.com/words/net/).
- Podstawowa znajomość języka C#: Podstawowa znajomość języków C# i .NET pomoże Ci postępować zgodnie z tym samouczkiem.

Dobra, skoro już ich nie ma, zajmijmy się kodem!

## Importuj przestrzenie nazw

Po pierwsze, musimy zaimportować niezbędne przestrzenie nazw, aby móc pracować z Aspose.Words. To jakby zebrać wszystkie narzędzia przed rozpoczęciem projektu. Dodaj te dyrektywy using na górze pliku C#:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Teraz, gdy mamy już warunki wstępne, podzielmy proces na krótkie etapy. Każdy krok jest kluczowy i przybliża nas do celu.

## Krok 1: Konfigurowanie katalogu dokumentów

Najpierw musimy określić katalog, w którym przechowywane są nasze dokumenty. To jak przygotowanie sceny przed wielkim występem.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Zastępować`"YOUR DOCUMENT DIRECTORY"` ze ścieżką do swojego katalogu. To tutaj Twoje dokumenty będą żyć i oddychać.

## Krok 2: Załaduj dokument główny

Następnie ładujemy dokument główny, do którego chcemy wstawić kolejny dokument. Pomyśl o tym jak o naszej głównej scenie, na której będzie się rozgrywać cała akcja.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Ten kod ładuje główny dokument z określonego katalogu.

## Krok 3: Ustaw opcje Znajdź i zamień

Aby znaleźć konkretną lokalizację, w której chcemy wstawić nasz dokument, korzystamy z funkcji znajdź i zamień. To jakby używać mapy do znalezienia dokładnego miejsca dla naszego nowego dodatku.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Tutaj ustawiamy kierunek na wstecz i określamy niestandardową procedurę obsługi wywołania zwrotnego, którą zdefiniujemy dalej.

## Krok 4: Wykonaj operację zamiany

Teraz mówimy naszemu dokumentowi głównemu, aby szukał określonego tekstu zastępczego i zastępował go niczym, jednocześnie korzystając z naszego niestandardowego wywołania zwrotnego w celu wstawienia innego dokumentu.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Ten kod wykonuje operację znajdowania i zamiany, a następnie zapisuje zaktualizowany dokument.

## Krok 5: Utwórz niestandardową procedurę obsługi wywołania zwrotnego zastępującego

Nasza niestandardowa procedura obsługi wywołań zwrotnych to miejsce, w którym dzieje się magia. Ta procedura obsługi zdefiniuje sposób wstawiania dokumentu podczas operacji znajdowania i zamiany.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Wstaw dokument po akapicie zawierającym dopasowany tekst.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Usuń akapit z pasującym tekstem.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Tutaj ładujemy dokument, który ma zostać wstawiony, a następnie wywołujemy metodę pomocniczą w celu wykonania wstawienia.

## Krok 6: Zdefiniuj metodę wstawiania dokumentu

Ostatnim elementem naszej układanki jest metoda, która faktycznie wstawia dokument w określonym miejscu.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Przejdź przez wszystkie węzły na poziomie bloków w treści sekcji,
		// następnie sklonuj i wstaw każdy węzeł, który nie jest ostatnim pustym akapitem sekcji.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

Ta metoda polega na zaimportowaniu węzłów z dokumentu do wstawienia i umieszczeniu ich w odpowiednim miejscu w dokumencie głównym.

## Wniosek

I masz to! Kompleksowy przewodnik dotyczący wstawiania jednego dokumentu do drugiego za pomocą Aspose.Words dla .NET. Wykonując poniższe kroki, możesz łatwo zautomatyzować zadania składania i manipulowania dokumentami. Niezależnie od tego, czy budujesz system zarządzania dokumentami, czy po prostu chcesz usprawnić przepływ pracy w przetwarzaniu dokumentów, Aspose.Words jest Twoim zaufanym pomocnikiem.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do programowego manipulowania dokumentami programu Word. Umożliwia łatwe tworzenie, modyfikowanie, konwertowanie i przetwarzanie dokumentów programu Word.

### Czy mogę wstawić wiele dokumentów jednocześnie?
Tak, możesz zmodyfikować procedurę obsługi wywołania zwrotnego, aby obsługiwała wielokrotne wstawienia, iterując po kolekcji dokumentów.

### Czy dostępny jest bezpłatny okres próbny?
 Absolutnie! Możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).

### Jak uzyskać wsparcie dla Aspose.Words?
Możesz uzyskać wsparcie, odwiedzając stronę[Forum Aspose.Words](https://forum.aspose.com/c/words/8).

### Czy mogę zachować formatowanie wstawionego dokumentu?
 Tak`NodeImporter` class pozwala określić sposób obsługi formatowania podczas importowania węzłów z jednego dokumentu do drugiego.