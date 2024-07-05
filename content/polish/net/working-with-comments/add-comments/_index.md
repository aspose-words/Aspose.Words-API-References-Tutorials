---
title: Dodaj Komentarze
linktitle: Dodaj Komentarze
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać komentarze do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-comments/add-comments/
---

W tym obszernym samouczku dowiesz się, jak dodawać komentarze do dokumentu programu Word za pomocą Aspose.Words dla .NET. Przeprowadzimy Cię przez proces i udostępnimy niezbędne fragmenty kodu C#. Pod koniec tego przewodnika będziesz mógł wstawiać komentarze i dostosowywać ich treść w swoich dokumentach.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz nowy dokument i narzędzie DocumentBuider
Aby rozpocząć, utwórz nowy dokument za pomocą klasy Document i zainicjuj obiekt DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Dodaj treść do dokumentu
Następnie dodaj żądaną treść do dokumentu za pomocą obiektu DocumentBuilder. W tym przykładzie dodajemy tekst:

```csharp
builder.Write("Some text is added.");
```

## Krok 3: Utwórz komentarz i dodaj treść
Aby dodać komentarz należy utworzyć instancję klasy Comment, przekazując obiekt Document, nazwisko autora, inicjały autora oraz aktualną datę:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Następnie dołącz komentarz do bieżącego akapitu:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Dodaj treść do komentarza, na przykład akapit i tekst:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Krok 4: Zapisz dokument
Po dodaniu komentarza i jego zawartości zapisz dokument do pliku korzystając z metody Save klasy Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Przykładowy kod źródłowy dodawania komentarzy przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do dodawania komentarzy przy użyciu Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dodawać komentarze do dokumentu programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z udostępnionego kodu źródłowego, możesz teraz wstawiać komentarze i dostosowywać ich treść w swoich dokumentach.

Komentarze są przydatne do współpracy, dostarczania dodatkowych informacji lub robienia notatek w dokumencie. Eksperymentuj z różnymi nazwiskami autorów, inicjałami i treścią komentarzy, aby spełnić Twoje specyficzne wymagania.

### Często zadawane pytania

#### P: Jak mogę dodać komentarz w dokumencie Aspose.Words for .NET?

Odp.: Aby dodać komentarz w dokumencie Aspose.Words for .NET, musisz wykonać kroki wymienione w samouczku.

#### P: Czy mogę sformatować tekst komentarza w Aspose.Words dla .NET?

O: Tak, możesz sformatować tekst komentarza w Aspose.Words dla .NET, korzystając z dostępnych właściwości formatowania.

#### P: Jak mogę odzyskać wszystkie komentarze znajdujące się w dokumencie?

 Odp.: Możesz pobrać wszystkie komentarze znajdujące się w dokumencie za pomocą`Document.Comments` nieruchomość.

#### P: Czy mogę usunąć konkretny komentarz w Aspose.Words dla .NET?

 O: Tak, możesz usunąć konkretny komentarz w Aspose.Words dla .NET za pomocą`Comment.Remove` metoda.

#### P: Jak mogę zmodyfikować tekst istniejącego komentarza w Aspose.Words dla .NET?

 O: Aby zmodyfikować tekst istniejącego komentarza w Aspose.Words dla .NET, możesz uzyskać dostęp do`Comment.Text` właściwość odpowiedniego`Comment` obiekt i zmodyfikuj tekst według potrzeb.