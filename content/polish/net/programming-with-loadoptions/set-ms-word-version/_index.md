---
title: Ustaw wersję pani Word
linktitle: Ustaw wersję pani Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak załadować dokument z określoną wersją MS Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-loadoptions/set-ms-word-version/
---
Podczas przetwarzania tekstu z dokumentami programu Word w aplikacji C# może być konieczne określenie wersji programu Microsoft Word, która będzie używana podczas ładowania dokumentu. Dzięki bibliotece Aspose.Words dla .NET możesz łatwo ustawić wersję MS Word, która ma być używana, za pomocą opcji LoadOptions. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces korzystania z kodu źródłowego Aspose.Words for .NET C# w celu załadowania dokumentu z określoną wersją MS Word przy użyciu opcji ładowania LoadOptions.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to potężna biblioteka do tworzenia, edytowania, konwertowania i ochrony dokumentów programu Word na różnych platformach, w tym .NET. Oferuje wiele funkcji do manipulowania dokumentami, takich jak wstawianie tekstu, zmiana formatowania, dodawanie sekcji i wiele więcej.

## Konfigurowanie opcji ładowania

Pierwszym krokiem jest skonfigurowanie opcji ładowania naszego dokumentu. Użyj klasy LoadOptions, aby określić parametry ładowania. W naszym przypadku musimy ustawić właściwość MswVersion na żądaną wersję MS Word. Na przykład używamy wersji Microsoft Word 2010. Oto jak to zrobić:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Tworzymy nowy obiekt LoadOptions i ustawiamy właściwość MswVersion na MsWordVersion.Word2010, aby określić wersję MS Word 2010.

## Ładowanie dokumentu przy użyciu określonej wersji MS Word

Teraz, gdy skonfigurowaliśmy opcje ładowania, możemy załadować dokument za pomocą klasy Document i określić opcje ładowania. Oto przykład :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

tym przykładzie ładujemy dokument „Document.docx” znajdujący się w katalogu dokumentów, korzystając z określonych opcji ładowania.

### Przykładowy kod źródłowy dla LoadOptions z funkcją „Ustaw wersję MS Word” przy użyciu Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skonfiguruj opcje ładowania za pomocą funkcji „Ustaw wersję MS Word”.
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Załaduj dokument z określoną wersją MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Zapisz dokument
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Wniosek

W tym przewodniku wyjaśniliśmy, jak przesłać dokument określający konkretną wersję MS Word przy użyciu biblioteki Aspose.Words dla .NET. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo zastosować tę funkcjonalność w swojej aplikacji C#. Załadowanie dokumentu określoną wersją MS Word pozwala zapewnić odpowiednią kompatybilność i obróbkę dokumentu w Twojej aplikacji.


### Często zadawane pytania

#### P: Dlaczego miałbym określić wersję programu MS Word podczas ładowania dokumentu do aplikacji C#?

Określenie wersji programu MS Word gwarantuje, że dokument zostanie poprawnie załadowany i przetworzony, szczególnie w przypadku określonego formatowania lub funkcji, które mogą się różnić w zależności od wersji.

#### P: Jakie wersje MS Word obsługuje Aspose.Words?

Odp.: Aspose.Words dla .NET obsługuje różne wersje MS Word, w tym Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 i inne.

#### P: Czy mogę załadować dokument z inną wersją MS Word niż ta zainstalowana w moim systemie?

O: Tak, Aspose.Words umożliwia określenie innej wersji MS Word podczas ładowania dokumentu, zapewniając kompatybilność nawet jeśli system docelowy ma inną wersję MS Word.

#### P: W jaki sposób ustawienie wersji MS Word wpłynie na korzyść mojej aplikacji C#?

Odp.: Ustawienie wersji MS Word gwarantuje, że dokument zostanie przetworzony zgodnie z zamierzonym formatowaniem i funkcjami tej konkretnej wersji, zapewniając spójny wynik.

#### P: Czy Aspose.Words ogranicza się do obsługi wyłącznie dokumentów DOCX?

O: Nie, Aspose.Words obsługuje różne formaty dokumentów, w tym DOC, RTF, HTML, PDF i inne, co czyni go wszechstronnym narzędziem do obsługi różnych typów dokumentów.