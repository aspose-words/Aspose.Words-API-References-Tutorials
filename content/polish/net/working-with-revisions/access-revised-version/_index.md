---
title: Uzyskaj dostęp do poprawionej wersji
linktitle: Uzyskaj dostęp do poprawionej wersji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Uzyskaj dostęp do poprawionej wersji dokumentu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/access-revised-version/
---

W tym przewodniku krok po kroku pokażemy, jak uzyskać dostęp do poprawionej wersji dokumentu programu Word za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Ładowanie dokumentu

Pierwszym krokiem jest przesłanie dokumentu zawierającego poprawki.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Krok 2: Uzyskaj dostęp do poprawionej wersji

Przejdźmy teraz do poprawionej wersji dokumentu.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Krok 3: Przeglądaj wersje

Następnie przejrzymy wersje obecne w dokumencie i wyświetlimy określone informacje dotyczące akapitów będących elementami listy.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Przykładowy kod źródłowy poprawionej wersji programu Access przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający dostęp do poprawionej wersji dokumentu przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Przejdź do poprawionej wersji dokumentu.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak uzyskać dostęp do poprawionej wersji dokumentu programu Word za pomocą Aspose.Words dla .NET. Ładując dokument, przechodząc do poprawionej wersji i przeglądając poprawki, mogliśmy uzyskać szczegółowe informacje na temat akapitów będących pozycjami listy. Aspose.Words dla .NET oferuje zaawansowane funkcje do manipulowania dokumentami Word, w tym dostęp do recenzji. Możesz teraz wykorzystać tę wiedzę, aby uzyskać dostęp do poprawionej wersji własnych dokumentów programu Word za pomocą Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak załadować dokument z wersjami do Aspose.Words dla .NET?

 O: Skorzystaj z`Document` klasa Aspose.Words dla .NET, aby załadować dokument z pliku zawierającego poprawki. Można określić pełną ścieżkę dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Jak uzyskać dostęp do poprawionej wersji dokumentu w Aspose.Words dla .NET?

 O: Skorzystaj z`RevisionsView` własność`Document` sprzeciwić się dostępowi do poprawionej wersji dokumentu. Można ustawić wartość`RevisionsView`własność do`RevisionsView.Final` aby wyświetlić wersję ostateczną bez poprawek.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### P: Jak przeglądać wersje dokumentów w Aspose.Words dla .NET?

Odp.: użyj a`foreach` pętla do iteracji po wersjach znajdujących się w dokumencie. Możesz skorzystać z`Revisions` własność`Document` obiekt, aby uzyskać kolekcję wszystkich wersji dokumentu.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Przetwarzaj tutaj każdą wersję
}
```

#### P: Jak sprawdzić, czy akapit jest pozycją na liście w Aspose.Words dla .NET?

 O: Skorzystaj z`IsListItem` własność`Paragraph` obiekt, aby sprawdzić, czy akapit jest elementem listy. The`IsListItem` zwroty własności`true` jeśli akapit jest elementem listy, w przeciwnym razie zwraca`false`.

```csharp
if (paragraph.IsListItem)
{
     // Akapit jest elementem listy
}
else
{
     // Akapit nie jest pozycją na liście
}
```