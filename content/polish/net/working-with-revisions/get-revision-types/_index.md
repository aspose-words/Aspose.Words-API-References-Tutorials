---
title: Uzyskaj typy wersji słów
linktitle: Uzyskaj typy wersji słów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Uzyskaj typy wersji słów w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/get-revision-types/
---

W tym przewodniku krok po kroku powiemy Ci, jak uzyskać typy wersji słów w dokumencie programu Word za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Ładowanie dokumentu

Pierwszym krokiem jest przesłanie dokumentu zawierającego poprawki.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Przejdź przez akapity

Następnie przejrzymy akapity dokumentu i sprawdzimy typy wersji słów powiązanych z każdym akapitem.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Przykładowy kod źródłowy dla opcji Pobierz typy wersji przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy umożliwiający uzyskanie typów wersji w dokumencie przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak uzyskać typy wersji słów w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępowaliśmy zgodnie z instrukcjami, aby załadować dokument, przejrzeć akapity i sprawdzić typy recenzji słownych powiązanych z każdym akapitem. Teraz możesz zastosować tę wiedzę do analizowania recenzji słów we własnych dokumentach Word przy użyciu Aspose.Words dla .NET.

### Często zadawane pytania dotyczące typów wersji słów

#### P: Jak przesłać dokument do Aspose.Words dla .NET?

 O: Skorzystaj z`Document` klasa Aspose.Words dla .NET, aby załadować dokument z pliku. Można określić pełną ścieżkę dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Jak przeglądać akapity w dokumencie w Aspose.Words dla .NET?

 O: Skorzystaj z`Paragraphs` właściwość sekcji dokumentu, aby uzyskać zbiór akapitów. Następnie możesz użyć pętli, aby przeglądać każdy akapit.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Przetwórz każdy akapit tutaj
}
```

#### P: Jak sprawdzić, czy akapit został przeniesiony (usunięty) w Aspose.Words dla .NET?

 O: Użyj akapitu`IsMoveFromRevision`właściwość, aby sprawdzić, czy została przeniesiona (usunięta).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Akapit został przeniesiony (usunięty)
}
```

#### P: Jak sprawdzić, czy akapit został przeniesiony (wstawiony) w Aspose.Words dla .NET?

 O: Użyj akapitu`IsMoveToRevision` właściwość, aby sprawdzić, czy została przeniesiona (wstawiona).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Akapit został przeniesiony (wstawiony)
}
```