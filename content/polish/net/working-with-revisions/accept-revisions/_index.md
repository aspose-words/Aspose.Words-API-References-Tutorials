---
title: Zaakceptuj poprawki
linktitle: Zaakceptuj poprawki
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak akceptować poprawki w dokumencie programu Word za pomocą Aspose.Words dla .NET
type: docs
weight: 10
url: /pl/net/working-with-revisions/accept-revisions/
---

W tym samouczku przeprowadzimy Cię przez proces akceptowania poprawek w dokumencie programu Word przy użyciu funkcji Akceptuj poprawki w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i zaakceptować zmiany w dokumencie.

## Krok 1: Dodawanie i edytowanie zawartości dokumentu

W tym przykładzie tworzymy dokument i dodajemy treść. Używamy kilku akapitów do zilustrowania zmian i poprawek. Oto jak:

```csharp
//Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Dodaj tekst do pierwszego akapitu, a następnie dodaj dwa kolejne akapity.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Krok 2: Śledź recenzje i dodawaj recenzje

Umożliwiamy śledzenie wersji i dodajemy wersję do dokumentu. Oto jak:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Ten akapit jest wersją i będzie miał ustawioną odpowiednią flagę „IsInsertRevision”.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Krok 3: Usuń akapit i zarządzaj wersjami

Usuwamy akapit i sprawdzamy zapisane wersje. Oto jak:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Ponieważ śledzimy wersje, akapit nadal istnieje w dokumencie i będzie miał ustawioną flagę „IsDeleteRevision”
// i będzie wyświetlana jako recenzja w programie Microsoft Word, dopóki nie zaakceptujemy lub odrzucimy wszystkich recenzji.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Krok 4: Zaakceptuj zmiany

Akceptujemy wszelkie zmiany w dokumencie. Oto jak:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Krok 5: Przestań śledzić recenzje

Przestaniemy śledzić wersje, aby zmiany w dokumencie nie były już wyświetlane jako wersje. Oto jak:

```csharp
doc.StopTrackRevisions();
```
## Krok 6: Zapisywanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save`metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Przykładowy kod źródłowy dla akceptowania wersji przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do akceptowania zmian w dokumencie przy użyciu Aspose.Words dla .NET:


```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Dodaj tekst do pierwszego akapitu, a następnie dodaj dwa kolejne akapity.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Mamy trzy akapity, z których żaden nie jest zarejestrowany jako jakikolwiek rodzaj rewizji
// Jeśli dodamy/usuniemy jakąkolwiek treść w dokumencie podczas śledzenia wersji,
// będą one wyświetlane jako takie w dokumencie i można je zaakceptować/odrzucić.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Ten akapit jest wersją i będzie miał ustawioną odpowiednią flagę „IsInsertRevision”.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Pobierz zbiór akapitów dokumentu i usuń akapit.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Ponieważ śledzimy wersje, akapit nadal istnieje w dokumencie i będzie miał ustawioną opcję „IsDeleteRevision”
// i będzie wyświetlana jako wersja w programie Microsoft Word, dopóki nie zaakceptujemy lub odrzucimy wszystkich wersji.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Akapit dotyczący usunięcia wersji zostanie usunięty po zaakceptowaniu zmian.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Zatrzymanie śledzenia wersji powoduje, że ten tekst wygląda jak zwykły tekst.
// W przypadku zmiany dokumentu korekty nie są liczone.
doc.StopTrackRevisions();

// Zapisz dokument.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Wniosek

W tym samouczku nauczyliśmy się, jak akceptować poprawki w dokumencie programu Word za pomocą funkcji Akceptuj poprawki w Aspose.Words dla .NET. Wykonaliśmy kroki umożliwiające dodawanie i edytowanie treści dokumentu, śledzenie poprawek, usuwanie poprawionych akapitów, akceptowanie wszystkich zmian i zaprzestanie śledzenia wersji. Teraz możesz zastosować tę wiedzę, aby skutecznie zarządzać wersjami we własnych dokumentach Word za pomocą Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak włączyć śledzenie wersji w Aspose.Words dla .NET?

#### Rozwiązanie 1:

 O: Aby włączyć śledzenie wersji w Aspose.Words dla .NET, użyj`StartTrackRevisions` metoda`Document` obiektu i podaj nazwisko autora oraz datę rozpoczęcia śledzenia wersji.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Rozwiązanie 2:

 Odp.: Możesz także włączyć śledzenie wersji za pomocą`Document` konstruktor, który akceptuje`trackRevisions`I`author` parametry.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### P: Jak zaakceptować wszystkie zmiany w dokumencie za pomocą Aspose.Words dla .NET?

 O: Skorzystaj z`AcceptAllRevisions` metoda`Document` sprzeciw, aby zaakceptować wszystkie zmiany wprowadzone w dokumencie.

```csharp
doc.AcceptAllRevisions();
```

#### P: Jak zapisać zmodyfikowany dokument z zaakceptowanymi wersjami?

 Użyj`Save` metoda`Document` obiekt, aby zapisać zmodyfikowany dokument z zaakceptowanymi wersjami. Pamiętaj o podaniu prawidłowej ścieżki pliku.

```csharp
doc.Save("path/to/the/document.docx");
```

#### P: Jak zatrzymać śledzenie wersji w Aspose.Words dla .NET?

 O: Skorzystaj z`StopTrackRevisions` metoda`Document` sprzeciwić się zatrzymaniu śledzenia wersji.

```csharp
doc.StopTrackRevisions();
```

#### P: Jak usunąć poprawiony akapit w dokumencie za pomocą Aspose.Words dla .NET?

 O: Aby usunąć poprawiony akapit z dokumentu, możesz użyć metody`Remove` sposób zbierania akapitów.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```