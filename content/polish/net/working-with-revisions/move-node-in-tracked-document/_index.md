---
title: Przesuń węzeł w śledzonym dokumencie
linktitle: Przesuń węzeł w śledzonym dokumencie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przenieś węzły w śledzonym dokumencie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/move-node-in-tracked-document/
---

W tym przewodniku krok po kroku przeprowadzimy Cię przez proces przenoszenia węzła w śledzonym dokumencie programu Word za pomocą Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Tworzenie dokumentu

Pierwszym krokiem jest utworzenie nowego dokumentu i dodanie akapitów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Krok 2: Śledź poprawki

Zamierzamy włączyć śledzenie wersji w dokumencie.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Krok 3: Przenieś węzeł

Podczas generowania wersji przesuniemy węzeł (akapit) z jednej pozycji na drugą.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Krok 4: Przestań śledzić recenzje

Przestaniemy śledzić zmiany w dokumencie.

```csharp
doc.StopTrackRevisions();
```

## Krok 5: Zapisanie dokumentu

 Po wstawieniu pola formularza wprowadzania tekstu zapisz dokument w wybranej lokalizacji za pomocą przycisku`Save` metoda. Upewnij się, że podałeś odpowiednią ścieżkę pliku:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Przykładowy kod źródłowy dla przenoszenia węzła w śledzonym dokumencie przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy do przenoszenia węzła w śledzonym dokumencie przy użyciu Aspose.Words dla .NET:


```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Rozpocznij śledzenie wersji.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generuj wersje podczas przenoszenia węzła z jednej lokalizacji do drugiej.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Zatrzymaj proces śledzenia wersji.
doc.StopTrackRevisions();

// W zakresie ruchu od znajdują się 3 dodatkowe akapity.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Wniosek

W tym samouczku nauczyliśmy się, jak przenosić węzeł w śledzonym dokumencie programu Word za pomocą Aspose.Words dla .NET. Wykonując kroki tworzenia dokumentu, włączając śledzenie wersji, przesuwając węzeł i zatrzymując śledzenie wersji, udało nam się pomyślnie przeprowadzić tę manipulację. Aspose.Words dla .NET to potężne narzędzie do przetwarzania tekstu w dokumentach Word i oferuje zaawansowane funkcje zarządzania wersjami. Teraz możesz wykorzystać tę wiedzę do przenoszenia węzłów we własnych dokumentach programu Word, jednocześnie śledząc wersje za pomocą Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak mogę włączyć śledzenie wersji w dokumencie Aspose.Words dla .NET?

O: Aby włączyć śledzenie wersji w dokumencie Aspose.Words dla .NET, możesz użyć opcji`StartTrackRevisions` metoda`Document` obiekt. Metoda ta przyjmuje jako parametry imię i nazwisko autora wersji oraz datę rozpoczęcia monitorowania wersji.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### P: Jak mogę przenieść węzeł w śledzonym dokumencie bez generowania poprawek?

 Odp.: Jeśli chcesz przenieść węzeł w śledzonym dokumencie bez generowania wersji, możesz użyć opcji`Remove` I`InsertAfter` Lub`InsertBefore` metody`Node` obiekt. Na przykład, aby przenieść akapit za innym akapitem, możesz użyć następującego kodu:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### P: Jak mogę zatrzymać śledzenie wersji w dokumencie Aspose.Words dla .NET?

 O: Aby zatrzymać śledzenie wersji w dokumencie Aspose.Words dla .NET, możesz użyć opcji`StopTrackRevisions` metoda`Document` obiekt.

```csharp
doc.StopTrackRevisions();
```