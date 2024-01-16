---
title: Użyj źródła ostrzeżenia
linktitle: Użyj źródła ostrzeżenia
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak korzystać ze źródła ostrzeżeń w Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-markdown/use-warning-source/
---

W tym przykładzie pokażemy, jak używać źródła ostrzeżeń w Aspose.Words dla .NET. Źródło ostrzeżenia wskazuje pochodzenie ostrzeżenia podczas korzystania z funkcji wywołania zwrotnego.

## Krok 1: Ładowanie dokumentu

 Załadujemy istniejący dokument zawierający ostrzeżenia za pomocą`Load` metoda`Document` klasa.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Krok 3: Korzystanie ze źródła ostrzeżeń

 Użyjemy źródła ostrzeżenia, ustawiając document`WarningCallback` własność do kolekcji`WarningInfo` obiekty.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Krok 4: Zapisywanie dokumentu

Wreszcie możemy zapisać dokument w żądanym formacie.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Przykładowy kod źródłowy użycia źródła ostrzeżeń w Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Gratulacje! Nauczyłeś się teraz, jak korzystać ze źródła ostrzeżeń w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Czy możemy dostosować wygląd tagu „Ostrzeżenie”?

 Odp.: Formatowanie znacznika „Ostrzeżenie” zależy od użytego modułu renderującego Markdown. W większości przypadków można dostosować wygląd za pomocą CSS`blockquote` tag w swoim dokumencie.

#### P: Czy można dodać ikony do tagu „Ostrzeżenie”?

O: Tak, możliwe jest dodanie ikon do znacznika „Ostrzeżenie” przy użyciu kodu HTML w dokumencie Markdown. Możesz wstawić A`span` tag z odpowiednią klasą, aby wyświetlić ikonę obok tekstu ostrzeżenia.

#### P: Czy tag „Ostrzeżenie” jest kompatybilny ze wszystkimi czytnikami Markdown?

 Odp.: Zgodność znacznika „Ostrzeżenie” zależy od użytego renderowania Markdown. Większość czytelników Markdown będzie obsługiwać`blockquote` tag, aby wyświetlić zaznaczony tekst, ale dokładny wygląd może się różnić.