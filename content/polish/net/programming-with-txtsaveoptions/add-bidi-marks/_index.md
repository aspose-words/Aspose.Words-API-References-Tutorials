---
title: Dodaj znaki BiDi w dokumencie programu Word
linktitle: Dodaj znaki BiDi w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodawać znaki BiDi do dokumentu programu Word za pomocą Aspose.Words dla .NET i tworzyć profesjonalne dokumenty wielojęzyczne.
type: docs
weight: 10
url: /pl/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words dla .NET to potężna biblioteka do tworzenia, edytowania i manipulowania dokumentami Word w aplikacji C#. Wśród funkcji oferowanych przez Aspose.Words jest możliwość dodawania znaków BiDi (dwukierunkowych) do dokumentu. W tym przewodniku przeprowadzimy Cię przez proces używania kodu źródłowego C# Aspose.Words dla .NET w celu dodania znaków BiDi do dokumentu.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to popularna biblioteka, która sprawia, że przetwarzanie tekstu w dokumentach Word jest łatwe i wydajne. Oferuje szeroką gamę funkcji do tworzenia, edytowania i manipulowania dokumentami Word, w tym dodawania znaków BiDi.

## Tworzenie dokumentu i dodawanie treści

Pierwszym krokiem jest utworzenie nowego dokumentu i dodanie do niego treści. Użyj klasy Document, aby utworzyć nową instancję dokumentu. Następnie użyj klasy DocumentBuilder, aby dodać tekst do dokumentu. Oto przykład :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

tym przykładzie tworzymy nowy dokument i używamy narzędzia DocumentBuilder do dodania tekstu. Dodaliśmy trzy wiersze tekstu: jeden w języku angielskim, jeden w języku hebrajskim i jeden w języku arabskim, aby zademonstrować dodawanie treści w różnych językach.

## Dodano znaki BiDi

Po dodaniu treści możemy teraz dodać do dokumentu znaki BiDi. Używamy w tym celu klasy TxtSaveOptions i ustawiamy właściwość AddBidiMarks na true. Oto jak:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

W tym przykładzie tworzymy instancję TxtSaveOptions i ustawiamy właściwość AddBidiMarks na true. Następnie za pomocą metody Save klasy Document zapisujemy dokument ze znakami BiDi.

### Przykładowy kod źródłowy funkcji „Dodaj znaki Bidi” w Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i dodaj treść
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Dodaj znaki BiDi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Wniosek

tym przewodniku wyjaśniliśmy, jak używać Aspose.Words dla .NET do dodawania znaczników BiDi do dokumentu programu Word przy użyciu dostarczonego kodu źródłowego C#. Wykonując podane kroki, możesz łatwo dodać znaczniki BiDi do dokumentów programu Word w aplikacji C#. Aspose.Words oferuje ogromną elastyczność i możliwości przetwarzania tekstu z formatowaniem tekstu i zarządzaniem językiem, umożliwiając profesjonalne tworzenie wielojęzycznych dokumentów.

### Często Zadawane Pytania

#### P: Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do tworzenia, edytowania i manipulowania dokumentami Word w aplikacji C#. Oferuje wiele funkcji do przetwarzania słów w dokumentach Word, w tym dodawanie znaków BiDi (dwukierunkowych).

#### P: Jakie funkcje oferuje Aspose.Words dla .NET?
Aspose.Words dla .NET oferuje szeroką gamę funkcji do tworzenia, edytowania i manipulowania dokumentami Word. Niektóre z tych funkcji obejmują tworzenie dokumentów, dodawanie treści, formatowanie tekstu, zarządzanie tabelami, łączenie i dzielenie dokumentów, konwertowanie dokumentów i wiele innych.

#### P: Jak mogę dodać znaczniki BiDi do dokumentu programu Word przy użyciu Aspose.Words dla .NET?
Możesz dodać znaki BiDi do dokumentu programu Word, wykonując następujące kroki:

 Utwórz nowy dokument za pomocą`Document` klasa.

 Użyj`DocumentBuilder` class, aby dodać treść do dokumentu.

 Po dodaniu treści użyj`TxtSaveOptions` klasę i ustaw`AddBidiMarks`własność do`true`.

 Zapisz dokument ze znakami BiDi za pomocą`Save` metoda`Document` klasa.

#### P: Czy Aspose.Words obsługuje wiele języków przy dodawaniu znaków BiDi?
Tak, Aspose.Words obsługuje wiele języków dodawania znaków BiDi. Możesz dodawać znaki BiDi do tekstu w różnych językach, takich jak angielski, hebrajski i arabski, używając Aspose.Words dla .NET.

#### P: Czy są jakieś dodatkowe możliwości zapisania dokumentu ze znakami BiDi?
 Tak, możesz określić inne opcje podczas zapisywania dokumentu ze znakami BiDi za pomocą`TxtSaveOptions` klasa. Można na przykład ustawić format zapisywania dokumentu, opcje kodowania itp.