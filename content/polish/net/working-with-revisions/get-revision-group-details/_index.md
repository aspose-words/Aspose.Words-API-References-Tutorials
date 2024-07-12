---
title: Uzyskaj szczegóły grupy wersji
linktitle: Uzyskaj szczegóły grupy wersji
second_title: Aspose.Words API do przetwarzania dokumentów
description: Uzyskaj szczegółowe informacje o grupie wersji w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/get-revision-group-details/
---

W tym przewodniku krok po kroku pokażemy, jak uzyskać szczegóły grupy wersji w dokumencie programu Word za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Ładowanie dokumentu

Pierwszym krokiem jest przesłanie dokumentu zawierającego poprawki.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Przeglądaj wersje

Następnie przejrzymy wersje obecne w dokumencie i wyświetlimy ich szczegóły, takie jak typ, autor, data i poprawiony tekst.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Przykładowy kod źródłowy dla opcji Pobierz szczegóły grupy wersji przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający uzyskanie szczegółów grupy wersji w dokumencie przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak uzyskać szczegóły grupy wersji w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Używając pętli i odpowiednich właściwości, mogliśmy wyświetlić szczegóły, takie jak typ wersji, autor, data i poprawiony tekst. Aspose.Words dla .NET oferuje wiele zaawansowanych funkcji do manipulowania dokumentami Word, w tym zarządzanie wersjami. Możesz teraz wykorzystać tę wiedzę, aby uzyskać szczegółowe informacje o grupach wersji we własnych dokumentach programu Word przy użyciu Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak załadować dokument z wersjami do Aspose.Words dla .NET?

 O: Skorzystaj z`Document` klasa Aspose.Words dla .NET, aby załadować dokument z pliku zawierającego poprawki. Można określić pełną ścieżkę dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Jak uzyskać szczegółowe informacje na temat grupy wersji w Aspose.Words dla .NET?

O: Przeglądaj wersje dokumentu za pomocą pętli i uzyskaj dostęp do właściwości każdej wersji, aby uzyskać żądane szczegóły. Możesz skorzystać z`RevisionType`, `Author`, `DateTime`I`ParentNode` właściwości, aby uzyskać odpowiednio typ wersji, autora, datę i poprawiony tekst.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### P: Jak sprawdzić, czy wersja należy do grupy w Aspose.Words dla .NET?

 O: Skorzystaj z`Group` własność`Revision` obiekt, aby sprawdzić, czy wersja należy do grupy. Jeśli`Group` własność jest`null`, oznacza to, że wersja nie należy do żadnej grupy.

```csharp
if (revision.Group != null)
{
      // Wersja należy do grupy
}
else
{
      // Wersja nie należy do żadnej grupy
}
```