---
title: Rewizja kształtu
linktitle: Rewizja kształtu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak radzić sobie z poprawkami kształtów w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając z tego obszernego przewodnika. Opanuj śledzenie zmian, wstawianie kształtów i nie tylko.
type: docs
weight: 10
url: /pl/net/working-with-revisions/shape-revision/
---
## Wstęp

Programowe edytowanie dokumentów programu Word może być trudnym zadaniem, zwłaszcza jeśli chodzi o obsługę kształtów. Niezależnie od tego, czy tworzysz raporty, projektujesz szablony, czy po prostu automatyzujesz tworzenie dokumentów, możliwość śledzenia poprawek kształtu i zarządzania nimi ma kluczowe znaczenie. Aspose.Words dla .NET oferuje potężny interfejs API, dzięki któremu proces ten jest płynny i wydajny. W tym samouczku zagłębimy się w szczegóły poprawiania kształtów w dokumentach programu Word, upewniając się, że masz narzędzia i wiedzę potrzebne do łatwego zarządzania dokumentami.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz:

-  Aspose.Words dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words. Możesz[pobierz go tutaj](https://releases.aspose.com/words/net/).
- Środowisko programistyczne: Należy mieć skonfigurowane środowisko programistyczne, takie jak Visual Studio.
- Podstawowa znajomość języka C#: Znajomość języka programowania C# i podstawowych koncepcji programowania obiektowego.
- Dokument programu Word: dokument programu Word do pracy lub można go utworzyć w trakcie samouczka.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw. Dzięki nim uzyskamy dostęp do klas i metod niezbędnych do obsługi dokumentów i kształtów Worda.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Krok 1: Konfigurowanie katalogu dokumentów

Zanim zaczniemy pracować z kształtami, musimy zdefiniować ścieżkę do naszego katalogu dokumentów. Tutaj będziemy zapisywać nasze zmodyfikowane dokumenty.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Tworzenie nowego dokumentu

Utwórzmy nowy dokument programu Word, w którym będziemy wstawiać i poprawiać kształty.

```csharp
Document doc = new Document();
```

## Krok 3: Wstawianie kształtu wbudowanego

Zaczniemy od wstawienia kształtu wbudowanego do naszego dokumentu bez śledzenia poprawek. Kształt osadzony to taki, który płynie wraz z tekstem.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Krok 4: Rozpoczęcie śledzenia wersji

Aby śledzić zmiany w naszym dokumencie, musimy włączyć śledzenie wersji. Jest to niezbędne do identyfikacji modyfikacji dokonanych w kształtach.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Krok 5: Wstawianie innego kształtu z wersjami

Teraz, gdy włączone jest śledzenie wersji, wstawmy kolejny kształt. Tym razem wszelkie zmiany będą śledzone.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Krok 6: Odzyskiwanie i modyfikowanie kształtów

Możemy pobrać wszystkie kształty z dokumentu i zmodyfikować je według potrzeb. Tutaj zdobędziemy kształty i usuniemy pierwszy.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Krok 7: Zapisywanie dokumentu

Po dokonaniu zmian musimy zapisać dokument. Dzięki temu wszystkie poprawki i modyfikacje zostaną zapisane.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Krok 8: Obsługa wersji przeniesionych kształtów

Kiedy kształt jest przenoszony, Aspose.Words śledzi to jako wersję. Oznacza to, że będą dwa wystąpienia kształtu: jedno w pierwotnym położeniu i drugie w nowym położeniu.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Wniosek

I masz to! Pomyślnie nauczyłeś się, jak obsługiwać poprawki kształtów w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Niezależnie od tego, czy zarządzasz szablonami dokumentów, automatyzujesz raporty, czy po prostu śledzisz zmiany, umiejętności te są nieocenione. Postępując zgodnie z tym przewodnikiem krok po kroku, nie tylko opanowałeś podstawy, ale także zyskałeś wgląd w bardziej zaawansowane techniki obsługi dokumentów.

## Często zadawane pytania

### Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka, która umożliwia programistom tworzenie, modyfikowanie i konwertowanie dokumentów programu Word programowo przy użyciu języka C#.

### Czy mogę śledzić zmiany wprowadzone w innych elementach w dokumencie programu Word?
Tak, Aspose.Words dla .NET obsługuje śledzenie zmian w różnych elementach, w tym w tekście, tabelach i innych.

### Jak mogę uzyskać bezpłatną wersję próbną Aspose.Words dla .NET?
 Możesz uzyskać bezpłatną wersję próbną Aspose.Words dla .NET[Tutaj](https://releases.aspose.com/).

### Czy możliwe jest programowe akceptowanie lub odrzucanie poprawek?
Tak, Aspose.Words dla .NET udostępnia metody programowego akceptowania lub odrzucania wersji.

### Czy mogę używać Aspose.Words dla .NET z innymi językami .NET oprócz C#?
Absolutnie! Aspose.Words dla .NET może być używany z dowolnym językiem .NET, w tym VB.NET i F#.