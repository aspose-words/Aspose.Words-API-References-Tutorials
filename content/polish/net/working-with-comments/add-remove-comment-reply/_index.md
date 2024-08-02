---
title: Dodaj Usuń komentarz Odpowiedź
linktitle: Dodaj Usuń komentarz Odpowiedź
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać i usuwać odpowiedzi na komentarze w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Usprawnij współpracę nad dokumentami dzięki temu przewodnikowi krok po kroku.
type: docs
weight: 10
url: /pl/net/working-with-comments/add-remove-comment-reply/
---
## Wstęp

Praca z komentarzami i odpowiedziami na nie w dokumentach programu Word może znacznie usprawnić proces recenzji dokumentów. Dzięki Aspose.Words dla .NET możesz zautomatyzować te zadania, czyniąc przepływ pracy bardziej wydajnym i usprawnionym. Ten samouczek przeprowadzi Cię przez proces dodawania i usuwania odpowiedzi na komentarze, zapewniając krok po kroku opanowanie tej funkcji.

## Warunki wstępne

Zanim zagłębisz się w kod, upewnij się, że masz następujące elementy:

-  Aspose.Words dla .NET: Pobierz i zainstaluj z[Tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Visual Studio lub dowolne inne IDE obsługujące platformę .NET.
- Podstawowa znajomość języka C#: Znajomość programowania w języku C# jest niezbędna.

## Importuj przestrzenie nazw

Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using System;
using Aspose.Words;
```

## Krok 1: Załaduj dokument Word

Najpierw musisz załadować dokument Word zawierający komentarze, którymi chcesz zarządzać. W tym przykładzie zakładamy, że masz w swoim katalogu dokument o nazwie „Comments.docx”.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Krok 2: Uzyskaj dostęp do pierwszego komentarza

Następnie przejdź do pierwszego komentarza w dokumencie. Ten komentarz będzie celem dodawania i usuwania odpowiedzi.

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

## Krok 3: Usuń istniejącą odpowiedź

Jeśli na komentarz znajdują się już odpowiedzi, możesz je usunąć. Oto jak możesz usunąć pierwszą odpowiedź na komentarz:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

## Krok 4: Dodaj nową odpowiedź

Teraz dodajmy nową odpowiedź do komentarza. Można podać imię i nazwisko autora, inicjały, datę i godzinę wysłania odpowiedzi oraz jej treść.

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Krok 5: Zapisz zaktualizowany dokument

Na koniec zapisz zmodyfikowany dokument w swoim katalogu.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Wniosek

Programowe zarządzanie odpowiedziami na komentarze w dokumentach programu Word może zaoszczędzić dużo czasu i wysiłku, szczególnie w przypadku obszernych recenzji. Aspose.Words dla .NET sprawia, że proces ten jest prosty i wydajny. Wykonując czynności opisane w tym przewodniku, możesz łatwo dodawać i usuwać odpowiedzi na komentarze, usprawniając współpracę nad dokumentami.

## Często zadawane pytania

### Jak dodać wiele odpowiedzi do jednego komentarza?

 Możesz dodać wiele odpowiedzi do jednego komentarza, wywołując metodę`AddReply` metodę wielokrotnie na tym samym obiekcie komentarza.

### Czy mogę dostosować dane autora każdej odpowiedzi?

 Tak, możesz podać imię i nazwisko autora, inicjały oraz datę i godzinę każdej odpowiedzi, korzystając z opcji`AddReply` metoda.

### Czy można usunąć wszystkie odpowiedzi z komentarza na raz?

Aby usunąć wszystkie odpowiedzi, musisz przejść przez pętlę`Replies` zbieranie komentarzy i usuwanie każdego z osobna.

### Czy mogę uzyskać dostęp do komentarzy w określonej sekcji dokumentu?

 Tak, możesz poruszać się po sekcjach dokumentu i uzyskiwać dostęp do komentarzy w każdej sekcji za pomocą`GetChild` metoda.

### Czy Aspose.Words dla .NET obsługuje inne funkcje związane z komentarzami?

Tak, Aspose.Words dla .NET zapewnia szeroką obsługę różnych funkcji związanych z komentarzami, w tym dodawanie nowych komentarzy, ustawianie właściwości komentarzy i wiele innych.