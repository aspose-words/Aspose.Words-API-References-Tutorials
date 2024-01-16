---
title: Pokaż poprawki w dymkach
linktitle: Pokaż poprawki w dymkach
second_title: Aspose.Words API do przetwarzania dokumentów
description: Pokaż wersje w dymkach za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/show-revisions-in-balloons/
---

W tym przewodniku krok po kroku pokażemy, jak wyświetlić wersje w dymkach w dokumencie programu Word za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Ładowanie dokumentu

Pierwszym krokiem jest przesłanie dokumentu zawierającego poprawki.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Skonfiguruj opcje wyświetlania recenzji

Skonfigurujemy opcje wyświetlania, aby poprawki były widoczne w dymkach.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Krok 3: Zapisz dokument w formacie PDF

Na koniec zapiszemy dokument w formacie PDF z wersjami pokazanymi w dymkach.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Formaty wyjściowe Markdown

Dane wyjściowe można sformatować w formacie przeceny, aby poprawić czytelność. Na przykład :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Przykładowy kod źródłowy dla opcji Pokaż poprawki w dymkach przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy pokazujący wersje w dymkach w dokumencie przy użyciu Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Renderuje wstawianie wersji inline, usuwanie i formatowanie wersji w dymkach.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Renderuje paski wersji po prawej stronie strony.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Wniosek

tym samouczku nauczyliśmy się wyświetlać wersje w dymkach w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Dzięki zastosowaniu odpowiednich opcji wyświetlania udało nam się uwidocznić rewizje w dymkach z paskami rewizji po prawej stronie. Aspose.Words dla .NET oferuje wiele zaawansowanych funkcji do manipulowania dokumentami Word, w tym zarządzanie wersjami. Teraz możesz wykorzystać tę wiedzę do wyświetlania wersji w dymkach we własnych dokumentach programu Word przy użyciu Aspose.Words dla .NET.


### Często zadawane pytania

#### P: Jak przesłać dokument do Aspose.Words dla .NET?

 O: Skorzystaj z`Document` klasa Aspose.Words dla .NET, aby załadować dokument z pliku. Można określić pełną ścieżkę dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Jak wyświetlić wersje w dymkach za pomocą Aspose.Words dla .NET?

 O: Skorzystaj z`ShowInBalloons` własność`RevisionOptions` obiekt, aby skonfigurować wyświetlanie wersji w dymkach. Możesz ustawić tę właściwość`ShowInBalloons.FormatAndDelete` aby wyświetlić wersje w dymkach z wersjami do usunięcia i formatowania.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### P: Jak zapisać dokument w formacie PDF za pomocą Aspose.Words dla .NET?

 O: Skorzystaj z`Save` metoda`Document` obiekt, aby zapisać dokument w formacie PDF. Należy podać pełną ścieżkę docelową z rozszerzeniem „.pdf”.

```csharp
doc.Save("path/to/destination/document.pdf");
```