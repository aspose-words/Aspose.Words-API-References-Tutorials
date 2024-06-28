---
title: Dodaj Usuń komentarz Odpowiedź
linktitle: Dodaj Usuń komentarz Odpowiedź
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać i usuwać odpowiedzi na komentarze w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-comments/add-remove-comment-reply/
---

tym kompleksowym samouczku dowiesz się, jak dodawać i usuwać odpowiedzi na komentarze w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Po przeczytaniu tego przewodnika będziesz mógł zarządzać odpowiedziami na komentarze i dostosowywać je do swoich wymagań.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Załaduj dokument
Aby rozpocząć, załaduj dokument zawierający komentarze, korzystając z klasy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Krok 2: Uzyskaj dostęp do komentarza i zarządzaj odpowiedziami
Następnie uzyskaj dostęp do komentarza z dokumentu za pomocą metody GetChild z parametrem NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Aby usunąć odpowiedź z komentarza, użyj metody RemoveReply i podaj żądany indeks odpowiedzi:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Aby dodać nową odpowiedź do komentarza, skorzystaj z metody AddReply i podaj imię i nazwisko autora, inicjały autora, datę i godzinę oraz treść odpowiedzi:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Krok 3: Zapisz dokument
Po dodaniu lub usunięciu odpowiedzi na komentarze należy zapisać dokument do pliku przy pomocy metody Save klasy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Przykładowy kod źródłowy dodawania i usuwania odpowiedzi na komentarze przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do dodawania i usuwania odpowiedzi na komentarze przy użyciu Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak dodawać i usuwać odpowiedzi na komentarze w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz zarządzać odpowiedziami na komentarze i dostosowywać je zgodnie ze swoimi wymaganiami.

Odpowiedzi na komentarze umożliwiają wspólne dyskusje i wyrażanie opinii w ramach dokumentu. Eksperymentuj z różnymi autorami odpowiedzi, inicjałami, datami i tekstami, aby usprawnić współpracę i komunikację w dokumentach.

### Często zadawane pytania

#### P: Jak mogę dodać komentarz w Aspose.Words dla .NET?

 O: Aby dodać komentarz w Aspose.Words dla .NET, możesz użyć metody`Comment.AddComment` metoda określająca treść komentarza i miejsce, w którym chcesz go dodać w dokumencie.

#### P: Jak mogę usunąć komentarz w Aspose.Words dla .NET?

O: Aby usunąć komentarz w Aspose.Words dla .NET, możesz użyć metody`Comment.Remove` metoda określająca`Comment` obiekt, który chcesz usunąć.

#### P: Czy mogę odpowiedzieć na komentarz w Aspose.Words dla .NET?

 O: Tak, możesz odpowiedzieć na komentarz w Aspose.Words dla .NET za pomocą`Comment.AddReply` metoda określająca tekst odpowiedzi i miejsce, w którym chcesz go dodać w dokumencie.

#### P: Jak mogę uzyskać dostęp do istniejących komentarzy w Aspose.Words dla .NET?

 O: Możesz uzyskać dostęp do istniejących komentarzy w Aspose.Words dla .NET za pomocą`CommentCollection` własność`Document` obiekt. Umożliwi to przeglądanie wszystkich komentarzy znajdujących się w dokumencie.

#### P: Czy mogę edytować tekst komentarza w Aspose.Words dla .NET?

 Odp.: Tak, możesz edytować tekst komentarza w Aspose.Words dla .NET, uzyskując dostęp do`Comment.Text` właściwość odpowiedniego`Comment` obiekt i modyfikując tekst według potrzeb.