---
title: Ustaw folder obrazów
linktitle: Ustaw folder obrazów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić folder obrazów podczas eksportowania do Markdown za pomocą Aspose.Words dla .NET. Dostosuj rozmieszczenie obrazów, aby zapewnić lepszą organizację i integrację.
type: docs
weight: 10
url: /pl/net/programming-with-markdownsaveoptions/set-images-folder/
---

Oto przewodnik krok po kroku wyjaśniający następujący kod źródłowy C#, który pomaga ustawić folder obrazów dla opcji eksportu Markdown przy użyciu biblioteki Aspose.Words dla .NET. Zanim użyjesz tego kodu, upewnij się, że w swoim projekcie umieściłeś bibliotekę Aspose.Words.

## Krok 1: Ustaw ścieżkę katalogu dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów, w którym znajduje się dokument zawierający obrazy.

## Krok 2: Załaduj dokument zawierający obrazy

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Ładujemy określony dokument zawierający obrazy, które chcemy wyeksportować za pomocą opcji Markdown.

## Krok 3: Ustaw folder obrazów dla opcji eksportu Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Tworzymy instancję`MarkdownSaveOptions` i ustaw ścieżkę do folderu obrazów za pomocą`ImagesFolder` nieruchomość. Upewnij się, że podałeś poprawną ścieżkę do folderu, w którym chcesz zapisać wyeksportowane obrazy.

## Krok 4: Zapisz dokument z opcjami eksportu Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Zapisujemy dokument w strumieniu pamięci, korzystając z określonych opcji eksportu Markdown. Następnie możesz użyć przepływu do wykonania innych operacji, takich jak zapisanie zawartości Markdown w pliku.

### Przykładowy kod źródłowy do ustawiania folderu obrazów dla MarkdownSaveOptions za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Ten kod źródłowy pokazuje, jak załadować dokument zawierający obrazy, a następnie ustawić folder obrazów dla opcji eksportu Markdown. Korzystając z określonych opcji, dokument jest następnie zapisywany w strumieniu pamięci. Umożliwia to dostosowanie lokalizacji folderu obrazów podczas eksportowania zawartości Markdown.