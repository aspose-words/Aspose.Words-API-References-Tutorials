---
title: Rewizja kształtu
linktitle: Rewizja kształtu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Poprawiaj kształty w dokumencie Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-revisions/shape-revision/
---

tym przewodniku krok po kroku przeprowadzimy Cię przez proces wprowadzania poprawek do kształtów w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Dostarczymy Ci pełny kod źródłowy i pokażemy, jak sformatować wynik przeceny.

## Krok 1: Tworzenie dokumentu i dodawanie kształtów

Pierwszym krokiem jest utworzenie nowego dokumentu i dodanie kształtów.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Krok 2: Śledź poprawki i dodaj kolejny kształt

Włączymy śledzenie wersji i dodamy kolejny kształt.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Krok 3: Pobierz kolekcję kształtów i sprawdź, czy nie ma poprawek.

Pobierzemy kolekcję kształtów z dokumentu i sprawdzimy wersje powiązane z każdym kształtem.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Krok 4: Sprawdzanie wersji przenoszenia kształtu

Załadujemy istniejący dokument zawierający wersje przemieszczeń kształtu i sprawdzimy powiązane wersje.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Przykładowy kod źródłowy dla Shape Revision przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający wprowadzanie poprawek do kształtów w dokumencie przy użyciu Aspose.Words dla .NET:

```csharp
Document doc = new Document();

//Wstaw kształt osadzony bez śledzenia wersji.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Rozpocznij śledzenie wersji, a następnie wstaw inny kształt.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Pobierz kolekcję kształtów dokumentu, która zawiera tylko dwa dodane przez nas kształty.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Usuń pierwszy kształt.
shapes[0].Remove();

// Ponieważ usunęliśmy ten kształt podczas śledzenia zmian, kształt liczy się jako usunięta wersja.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Śledząc zmiany, wstawiliśmy kolejny kształt, więc ten kształt będzie się liczył jako wersja wstawiania.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Dokument zawiera jeden kształt, który został przeniesiony, ale wersje polegające na przeniesieniu kształtu będą miały dwa wystąpienia tego kształtu.
// Jeden będzie kształtem w miejscu docelowym, a drugi będzie kształtem w jego pierwotnej lokalizacji.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Jest to ruch do rewizji, także kształtu w miejscu docelowym.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Jest to przejście od rewizji, czyli kształtu w jego pierwotnym położeniu.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Wniosek

tym samouczku nauczyliśmy się, jak wprowadzać poprawki do kształtów w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z etapami tworzenia dokumentu, włączając śledzenie wersji, sprawdzając wersje powiązane z każdym kształtem i sprawdzając wersje pod kątem przenoszenia kształtów, byliśmy w stanie pomyślnie zarządzać wersjami. Aspose.Words dla .NET oferuje potężne API do przetwarzania tekstu z recenzjami i formularzami w dokumentach Word.

### Często zadawane pytania

#### P: Jak mogę utworzyć nowy dokument i dodać kształty w Aspose.Words dla .NET?

O: Aby utworzyć nowy dokument i dodać kształty w Aspose.Words dla .NET, możesz użyć poniższego kodu. Tutaj dodajemy dwa kształty, sześcian i słońce, do pierwszej części dokumentu:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### P: Jak włączyć śledzenie wersji w Aspose.Words dla .NET?

 O: Aby włączyć śledzenie wersji w Aspose.Words dla .NET, możesz użyć`StartTrackRevisions` metoda`Document` obiekt. Ta metoda przyjmuje jako parametr nazwisko autora wersji:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### P: Jak mogę sprawdzić wersje powiązane z każdym kształtem w dokumencie Aspose.Words dla .NET?

O: Aby sprawdzić wersje powiązane z każdym kształtem w dokumencie Aspose.Words for .NET, możesz uzyskać kolekcję kształtów dokumentu za pomocą`GetChildNodes` metoda z`NodeType.Shape` typ węzła. Następnie możesz uzyskać dostęp do każdego kształtu`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , I`IsMoveToRevision` właściwości, aby określić, jaki typ rewizji jest powiązany z kształtem:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### P: Jak mogę sprawdzić przemieszczenia kształtów w dokumencie Aspose.Words dla .NET?

 Odp.: Aby sprawdzić zmiany przemieszczeń kształtu w dokumencie Aspose.Words for .NET, możesz załadować istniejący dokument zawierający wersje przesunięć kształtu. Następnie możesz uzyskać dostęp do każdego kształtu`IsMoveFromRevision` I`IsMoveToRevision` właściwości, aby określić, czy jest przenoszony, a jeśli tak, skąd i dokąd:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```