---
title: Wstaw dokument przy zamianie
linktitle: Wstaw dokument przy zamianie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić dokument dotyczący wymiany za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/clone-and-combine-documents/insert-document-at-replace/
---
W tym samouczku przeprowadzimy Cię przez proces wstawiania dokumentu do innego dokumentu podczas zastępowania za pomocą funkcji Wstaw dokument podczas zastępowania w Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i wstawić dokument.

## Krok 1: Ładowanie głównego dokumentu

Aby rozpocząć, określ katalog dla swoich dokumentów i załaduj główny dokument do obiektu Dokument. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Krok 2: Skonfiguruj opcje wyszukiwania i zamiany

Teraz skonfigurujemy opcje wyszukiwania i zamiany, określając kierunek wyszukiwania i wywołanie zwrotne zamiany, aby wstawić dokument do innego dokumentu. Oto jak:

```csharp
// Skonfiguruj opcje wyszukiwania i zamiany.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Krok 3: Wywołanie metody zastępczej

Wywołamy teraz metodę zamiany, aby znaleźć i zamienić określony tekst na pusty ciąg znaków, korzystając ze skonfigurowanych opcji. Oto jak:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Przykładowy kod źródłowy dla Wstaw dokument przy zamianie przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy funkcji Wstaw dokument podczas zastępowania Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Ustaw opcje wyszukiwania i zamiany.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Wywołaj metodę zamiany.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Wniosek

W tym samouczku omówiliśmy, jak wstawić dokument do innego dokumentu podczas zastępowania, korzystając z funkcji Wstaw dokument podczas zastępowania w Aspose.Words dla .NET. Konfigurując opcje wyszukiwania i zamiany oraz podając niezbędne dane, możesz dynamicznie składać dokumenty, zastępując określone symbole zastępcze zawartością innych szablonów dokumentów lub sekcji. Aspose.Words dla .NET oferuje potężny i elastyczny sposób zarządzania złożonymi zadaniami manipulacji dokumentami, co czyni go cennym narzędziem do automatyzacji scenariuszy tworzenia dokumentów i wstawiania treści.

### Często zadawane pytania

#### P: Jaki jest cel wstawiania dokumentu do innego dokumentu podczas zastępowania?

Odp.: Wstawianie dokumentu do innego dokumentu podczas zastępowania umożliwia dynamiczne zastępowanie określonego obiektu zastępczego zawartością osobnego dokumentu. Ta funkcja jest szczególnie przydatna, gdy chcesz złożyć większy dokument, łącząc różne wstępnie zdefiniowane szablony dokumentów lub sekcje w określone symbole zastępcze.

#### P: Jak wstawić dokument do innego dokumentu podczas zastępowania za pomocą Aspose.Words dla .NET?

O: Aby wstawić dokument do innego dokumentu podczas zastępowania za pomocą Aspose.Words dla .NET, wykonaj następujące kroki:
1. Załaduj główny dokument zawierający symbole zastępcze do obiektu Dokument.
2. Skonfiguruj opcje wyszukiwania i zamiany, w tym kierunek wyszukiwania i wywołanie zwrotne zamiany w celu obsługi wstawiania dokumentu.
3. Wywołaj metodę zamiany odpowiednim wzorcem wyszukiwania, zastępując symbole zastępcze pustym ciągiem znaków, korzystając ze skonfigurowanych opcji.

#### P: Czy mogę dostosować sposób wstawiania podczas zastępowania?

O: Tak, możesz dostosować zachowanie wstawiania podczas zastępowania, implementując niestandardową funkcję ReplacingCallback. Dziedzicząc z interfejsu IReplacingCallback, możesz kontrolować sposób wstawiania i łączenia dokumentów w oparciu o określone wymagania podczas zastępowania symboli zastępczych.

#### P: Czy mogę zastąpić wiele symboli zastępczych różnymi dokumentami?

O: Tak, możesz zastąpić wiele obiektów zastępczych różnymi dokumentami, określając odpowiednie wzorce wyszukiwania dla każdego obiektu zastępczego i podając odpowiednie dokumenty do wstawienia.