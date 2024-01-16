---
title: Komentarz rozwiązany i odpowiedzi
linktitle: Komentarz rozwiązany i odpowiedzi
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak rozwiązywać komentarze i odpowiedzi na nie w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-comments/comment-resolved-and-replies/
---

tym kompleksowym samouczku dowiesz się, jak rozwiązywać komentarze i odpowiedzi na nie w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł zarządzać rozstrzyganiem komentarzy oraz aktualizować status komentarzy i odpowiedzi na nie.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Załaduj dokument i uzyskaj dostęp do komentarzy
Aby rozpocząć, załaduj dokument zawierający komentarze za pomocą klasy Document i uzyskaj dostęp do kolekcji komentarzy:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Krok 2: Rozpatrz komentarze i odpowiedzi na nie
Następnie przejrzyj komentarze i odpowiedzi na nie, aby oznaczyć je jako rozwiązane:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

W powyższym kodzie uzyskujemy dostęp do komentarza nadrzędnego i przeglądamy zawarte w nim odpowiedzi. Możemy pobrać identyfikator komentarza nadrzędnego i status jego rozwiązania. Następnie aktualizujemy znacznik „Gotowe” w każdej odpowiedzi na komentarz, aby wskazać rozwiązanie.

## Krok 3: Zapisz dokument
Po rozwiązaniu komentarzy i zaktualizowaniu ich statusu zapisz zmodyfikowany dokument do pliku, korzystając z metody Save klasy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Przykładowy kod źródłowy do rozwiązywania komentarzy i ich odpowiedzi przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do rozwiązywania komentarzy i odpowiedzi na nie przy użyciu Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Pamiętaj, aby dostosować kod zgodnie ze swoimi specyficznymi wymaganiami, w tym ścieżką pliku dokumentu i dodatkowymi dostosowaniami

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak rozwiązywać komentarze i odpowiedzi na nie w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz zarządzać rozpatrywaniem komentarzy oraz aktualizować status komentarzy i odpowiedzi na nie zgodnie ze swoimi wymaganiami.

Rozwiązywanie komentarzy pomaga w śledzeniu i zarządzaniu opiniami w dokumencie. Eksperymentuj z różnymi statusami komentarzy i dostosowuj je, aby usprawnić procesy współpracy i przeglądania dokumentów.

### Często zadawane pytania

#### P: Jak rozwiązać komentarz w Aspose.Words dla .NET?

 O: Aby rozwiązać komentarz w Aspose.Words dla .NET, możesz użyć metody`Comment.Resolve` metoda określająca`Comment` obiekt, który chcesz rozwiązać. Spowoduje to oznaczenie komentarza jako rozwiązanego i ukrycie go w dokumencie końcowym.

#### P: Jak dodać odpowiedź na rozwiązany komentarz w Aspose.Words dla .NET?

 O: Chociaż rozwiązane komentarze są domyślnie ukryte w dokumencie końcowym, nadal możesz dodać odpowiedź do rozwiązanego komentarza za pomocą przycisku`Comment.AddReply` metoda określająca tekst odpowiedzi i miejsce, w którym chcesz go dodać.

#### P: Jak wyświetlić rozwiązane komentarze w Aspose.Words dla .NET?

 Odpowiedź: Domyślnie rozwiązane komentarze są ukryte w dokumencie końcowym. Można je jednak wyświetlić za pomocą metody`CommentOptions.ShowResolvedComments` własność`Document` obiekt i ustawienie go`true`.

#### P: Jak mogę ukryć wszystkie komentarze, w tym odpowiedzi, w Aspose.Words dla .NET?

 O: Aby ukryć wszystkie komentarze, w tym odpowiedzi, w Aspose.Words dla .NET, możesz użyć opcji`CommentOptions.CommentDisplayMode` własność`Document` obiekt i ustaw go na`CommentDisplayMode.None`.

#### P: Czy mogę edytować tekst rozwiązanego komentarza w Aspose.Words dla .NET?

 O: Tak, możesz edytować tekst rozwiązanego komentarza w Aspose.Words dla .NET, uzyskując dostęp do`Comment.Text` właściwość odpowiedniego`Comment` obiekt i modyfikując tekst według potrzeb.