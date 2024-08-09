---
title: Kotwica pionowa
linktitle: Kotwica pionowa
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić pionowe pozycje zakotwiczeń dla pól tekstowych w dokumentach programu Word przy użyciu Aspose.Words dla .NET. W zestawie łatwy przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-shapes/vertical-anchor/
---
## Wstęp

Czy zdarzyło Ci się kiedyś kontrolować, gdzie dokładnie pojawia się tekst w polu tekstowym w dokumencie programu Word? Może chcesz, aby tekst był zakotwiczony u góry, pośrodku lub u dołu pola tekstowego? Jeśli tak, jesteś we właściwym miejscu! W tym samouczku omówimy, jak używać Aspose.Words dla .NET do ustawiania pionowej kotwicy pól tekstowych w dokumentach programu Word. Pomyśl o zakotwiczeniu pionowym jak o magicznej różdżce, która ustawia tekst dokładnie tam, gdzie chcesz, w pojemniku. Gotowy do nurkowania? Zacznijmy!

## Warunki wstępne

Zanim zagłębimy się w podstawy kotwienia pionowego, musisz przygotować kilka rzeczy:

1.  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words dla .NET. Jeśli jeszcze tego nie masz, możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
2. Visual Studio: w tym samouczku założono, że do kodowania używasz programu Visual Studio lub innego środowiska .NET IDE.
3. Podstawowa znajomość języka C#: Znajomość języków C# i .NET ułatwi Ci płynne wykonywanie zadań.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego kodu C#. W tym miejscu informujesz aplikację, gdzie znaleźć klasy i metody, których będziesz używać. Oto jak to zrobić:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Te przestrzenie nazw udostępniają klasy potrzebne do pracy z dokumentami i kształtami.

## Krok 1: Zainicjuj dokument

Najpierw musisz utworzyć nowy dokument programu Word. Pomyśl o tym jak o ustawianiu płótna przed rozpoczęciem malowania.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tutaj,`Document` to twoje puste płótno i`DocumentBuilder` to Twój pędzel, umożliwiający dodawanie kształtów i tekstu.

## Krok 2: Wstaw kształt pola tekstowego

Teraz dodajmy pole tekstowe do naszego dokumentu. Tutaj będzie znajdować się Twój tekst. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 W tym przykładzie`ShapeType.TextBox` określa żądany kształt i`200, 200` to szerokość i wysokość pola tekstowego w punktach.

## Krok 3: Ustaw kotwicę pionową

Tutaj dzieje się magia! Można ustawić pionowe wyrównanie tekstu w polu tekstowym. Określa, czy tekst jest zakotwiczony u góry, pośrodku czy u dołu pola tekstowego.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 W tym przypadku`TextBoxAnchor.Bottom`gwarantuje, że tekst zostanie zakotwiczony u dołu pola tekstowego. Jeśli chcesz, aby był wyśrodkowany lub wyrównany do góry, użyłbyś`TextBoxAnchor.Center` Lub`TextBoxAnchor.Top`odpowiednio.

## Krok 4: Dodaj tekst do pola tekstowego

Nadszedł czas, aby dodać trochę treści do pola tekstowego. Pomyśl o tym jak o wypełnieniu płótna ostatnimi szlifami.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Tutaj,`MoveTo` zapewnia, że tekst zostanie wstawiony do pola tekstowego, i`Write` dodaje rzeczywisty tekst.

## Krok 5: Zapisz dokument

Ostatnim krokiem jest zapisanie dokumentu. To tak, jakby włożyć gotowy obraz do ramki.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Wniosek

I masz to! Właśnie nauczyłeś się kontrolować pionowe wyrównanie tekstu w polu tekstowym w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Niezależnie od tego, czy zakotwiczasz tekst na górze, na środku czy na dole, ta funkcja zapewnia precyzyjną kontrolę nad układem dokumentu. Zatem następnym razem, gdy będziesz musiał zmienić rozmieszczenie tekstu w dokumencie, będziesz wiedział, co robić!

## Często zadawane pytania

### Co to jest zakotwiczenie pionowe w dokumencie programu Word?
Zakotwiczenie w pionie kontroluje położenie tekstu w polu tekstowym, na przykład wyrównanie do góry, do środka lub do dołu.

### Czy mogę używać innych kształtów oprócz pól tekstowych?
Tak, możesz używać zakotwiczenia pionowego z innymi kształtami, chociaż pola tekstowe są najczęstszym przypadkiem użycia.

### Jak zmienić punkt kontrolny po utworzeniu pola tekstowego?
 Możesz zmienić punkt kontrolny, ustawiając`VerticalAnchor` właściwość obiektu kształtu pola tekstowego.

### Czy można zakotwiczyć tekst na środku pola tekstowego?
 Absolutnie! Po prostu użyj`TextBoxAnchor.Center` aby wyśrodkować tekst w pionie w polu tekstowym.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Words dla .NET?
 Sprawdź[Dokumentacja Aspose.Words](https://reference.aspose.com/words/net/) aby uzyskać więcej szczegółów i przewodników.