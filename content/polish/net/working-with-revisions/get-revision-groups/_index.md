---
title: Pobierz grupy wersji
linktitle: Pobierz grupy wersji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Uzyskaj grupy wersji w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/get-revision-groups/
---

W tym przewodniku krok po kroku powiemy Ci, jak uzyskać grupy wersji w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Ładowanie dokumentu

Pierwszym krokiem jest przesłanie dokumentu zawierającego poprawki.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Przeglądaj grupy wersji

Następnie przejdziemy przez grupy wersji obecne w dokumencie i wyświetlimy ich szczegóły, takie jak autor, typ wersji i poprawiony tekst.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Przykładowy kod źródłowy dla opcji Pobierz grupy wersji przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający pobranie grup wersji w dokumencie przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Wniosek

tym samouczku nauczyliśmy się, jak uzyskać grupy wersji w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępowaliśmy zgodnie z instrukcjami, aby załadować dokument i przeglądać grupy recenzji, wyświetlając szczegóły, takie jak autor i typ recenzji. Możesz teraz zastosować tę wiedzę do analizy wersji własnego dokumentu programu Word przy użyciu Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak przesłać dokument do Aspose.Words dla .NET?

 O: Skorzystaj z`Document` klasa Aspose.Words dla .NET, aby załadować dokument z pliku. Można określić pełną ścieżkę dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Jak przeglądać grupy wersji w dokumencie w Aspose.Words dla .NET?

 O: Skorzystaj z`Groups` własność dokumentu`Revisions` obiekt, aby uzyskać kolekcję grup wersji. Następnie możesz użyć pętli, aby przeglądać każdą grupę recenzji.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Przetwórz tutaj każdą grupę recenzji
}
```

#### P: Jak zdobyć autora grupy recenzji w Aspose.Words dla .NET?

 O: Skorzystaj z`Author` własność`RevisionGroup` obiekt, aby uzyskać autora grupy wersji.

```csharp
string author = group.Author;
```

#### P: Jak uzyskać typ wersji grupy wersji w Aspose.Words dla .NET?

 O: Skorzystaj z`RevisionType` własność`RevisionGroup`obiekt, aby uzyskać typ wersji grupy.

```csharp
string revisionType = group.RevisionType;
```