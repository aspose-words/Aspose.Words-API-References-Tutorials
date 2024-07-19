---
title: Usuń zawartość stopki nagłówka
linktitle: Usuń zawartość stopki nagłówka
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak usunąć zawartość nagłówka i stopki z dokumentu programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-section/delete-header-footer-content/
---

tym samouczku pokażemy, jak usunąć zawartość nagłówka i stopki z dokumentu programu Word przy użyciu biblioteki Aspose.Words dla .NET. Usuwanie treści z nagłówków i stopek może być przydatne, gdy chcesz zresetować lub usunąć te elementy z dokumentu. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie
- Dokument programu Word zawierający nagłówki i stopki, które chcesz usunąć

## Krok 1: Zdefiniuj katalog dokumentów
 Najpierw musisz ustawić ścieżkę katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument i przejdź do sekcji
 Następnie załadujemy dokument programu Word do instancji pliku`Document` klasa. Dostęp do pierwszej sekcji dokumentu uzyskamy przy użyciu indeksu 0.

```csharp
// Załaduj dokument
Document doc = new Document(dataDir + "Document.docx");

// Uzyskaj dostęp do sekcji
Section section = doc.Sections[0];
```

## Krok 3: Usuń zawartość nagłówka i stopki
 Aby usunąć zawartość nagłówka i stopki z sekcji, użyjemy metody`ClearHeadersFooters` metoda.

```csharp
section.ClearHeadersFooters();
```

### Przykładowy kod źródłowy dla usuwania zawartości stopki nagłówka przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Wniosek
tym samouczku widzieliśmy, jak usunąć zawartość nagłówka i stopki z dokumentu programu Word za pomocą Aspose.Words dla .NET. Usunięcie treści z nagłówków i stopek umożliwia zresetowanie lub usunięcie tych konkretnych elementów z dokumentu. Możesz swobodnie dostosowywać i używać tej funkcji zgodnie ze swoimi konkretnymi potrzebami.

### Często zadawane pytania dotyczące usuwania zawartości stopki nagłówka

#### P: Jak ustawić katalog dokumentów w Aspose.Words dla .NET?

O: Aby ustawić ścieżkę do katalogu zawierającego Twoje dokumenty, musisz ją zastąpić`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką. Oto jak to zrobić:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### P: Jak załadować sekcję dokumentu i dostępu do Aspose.Words dla .NET?

 Odp.: Aby załadować dokument programu Word do instancji pliku`Document` klasa tzw`doc` i uzyskaj dostęp do pierwszej sekcji dokumentu przy użyciu indeksu 0, możesz użyć następującego kodu:

```csharp
// Załaduj dokument
Document doc = new Document(dataDir + "Document.docx");

// Uzyskaj dostęp do sekcji
Section section = doc.Sections[0];
```

#### P: Jak usunąć zawartość nagłówka i stopki w Aspose.Words dla .NET?

 O: Aby usunąć zawartość nagłówka i stopki z sekcji, możesz użyć metody`ClearHeadersFooters` metoda:

```csharp
section.ClearHeadersFooters();
```

#### P: Jak zapisać zmodyfikowany dokument w Aspose.Words dla .NET?

Odp.: Po usunięciu zawartości nagłówka i stopki możesz zapisać zmodyfikowany dokument w pliku, używając następującego kodu:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```