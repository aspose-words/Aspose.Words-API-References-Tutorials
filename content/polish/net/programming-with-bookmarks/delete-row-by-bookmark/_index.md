---
title: Usuń wiersz według zakładki w dokumencie programu Word
linktitle: Usuń wiersz według zakładki w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak usunąć wiersz tabeli na podstawie określonej zakładki w dokumencie programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/delete-row-by-bookmark/
---

W tym artykule przeanalizujemy powyższy kod źródłowy C#, aby zrozumieć, jak używać funkcji Usuń wiersz według zakładek w bibliotece Aspose.Words dla .NET. Ta funkcja umożliwia usunięcie wiersza tabeli na podstawie określonej zakładki w dokumencie programu Word.

## Warunki wstępne

- Podstawowa znajomość języka C#.
- Środowisko programistyczne .NET z zainstalowaną biblioteką Aspose.Words.

## Krok 1: Uzyskanie zakładki

 Używamy`Bookmarks` właściwość zakresu dokumentu, aby uzyskać konkretną zakładkę, której chcemy użyć do usunięcia wiersza tabeli:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Krok 2: Usuwanie wiersza tabeli

 Używamy`GetAncestor` metoda uzyskania`Row` wpisz element nadrzędny zakładki. Następnie używamy`Remove` metoda usunięcia wiersza tabeli:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Przykładowy kod źródłowy dla opcji Usuń wiersz według zakładek przy użyciu Aspose.Words dla .NET

Oto pełny przykładowy kod źródłowy demonstrujący usuwanie wiersza tabeli na podstawie określonej zakładki przy użyciu Aspose.Words dla .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Wniosek

W tym artykule zbadaliśmy kod źródłowy C#, aby zrozumieć, jak korzystać z funkcji Usuń wiersz według zakładki w Aspose.Words dla .NET. Postępowaliśmy zgodnie z przewodnikiem krok po kroku, aby usunąć wiersz tabeli na podstawie określonej zakładki w dokumencie.

### Często zadawane pytania dotyczące usuwania wierszy po zakładkach w dokumencie programu Word

#### P: Czy mogę usunąć wiele wierszy za pomocą tej samej zakładki?

Odp.: Tak, możesz usunąć wiele wierszy za pomocą tej samej zakładki. Musisz jednak zająć się logiką swojego kodu, aby określić liczbę wierszy do usunięcia i wprowadzić niezbędne zmiany w dostarczonym fragmencie kodu.

#### P: Co się stanie, jeśli zakładka nie istnieje w dokumencie?

Odpowiedź: Jeśli określona zakładka nie istnieje w dokumencie, fragment kodu zwróci wartość null dla obiektu zakładki. Dlatego przed próbą usunięcia wiersza tabeli należy obsłużyć ten scenariusz w swoim kodzie, dodając odpowiednie kontrole.

#### P: Czy korzystanie z biblioteki Aspose.Words jest bezpłatne?

 Odp.: Biblioteka Aspose.Words jest biblioteką komercyjną i możesz potrzebować ważnej licencji, aby używać jej w swoich projektach. Możesz odwiedzić[Aspose.Words dla referencji .NET API](https://reference.aspose.com/words/net/) aby dowiedzieć się więcej o opcjach licencjonowania i cenach.

#### P: Czy mogę usunąć wiersze z tabeli w określonej sekcji dokumentu programu Word?

Odp.: Tak, możesz usuwać wiersze z tabeli w określonej sekcji dokumentu programu Word. Możesz zmodyfikować dostarczony fragment kodu, aby kierować reklamy na określoną sekcję, używając odpowiedniego zakresu lub zakładki w tej sekcji.