---
title: Wstaw pole ASKField bez narzędzia do tworzenia dokumentów
linktitle: Wstaw pole ASKField bez narzędzia do tworzenia dokumentów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pole ASK do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole ASK bez narzędzia DocumentBuilder” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu i akapitu

Zaczynamy od utworzenia nowego dokumentu i pobrania pierwszego akapitu.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Krok 3: Wstawienie pola ASK

 Używamy`AppendField()` metoda wstawienia pola ASK do akapitu.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Następnie konfigurujemy różne właściwości pola ASK, podając żądane wartości.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Na koniec nazywamy`Update()` metoda aktualizacji pola.

```csharp
field. Update();
```

### Przykład kodu źródłowego do wstawienia pola ASK bez DocumentBuilder z Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Wstaw pole ZAPYTAJ.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

tym przykładzie utworzyliśmy nowy dokument, wstawiliśmy pole ASK bez użycia narzędzia DocumentBuilder, skonfigurowaliśmy różne właściwości pola i zapisaliśmy dokument pod określoną nazwą pliku.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Wstaw pole ASK bez narzędzia DocumentBuilder” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Co to jest pole ASK w Aspose.Words?

O: Pole ASK w Aspose.Words służy do zadawania użytkownikowi pytania podczas otwierania dokumentu. Często służy do żądania określonych informacji lub opinii, które mogą się różnić w zależności od użytkownika.

#### P: Jak wstawić pole ASK do dokumentu Word bez użycia Konstruktora dokumentów w Aspose.Words?

Odp.: Aby wstawić pole ASK do dokumentu Word bez korzystania z Konstruktora dokumentów w Aspose.Words, możesz wykonać następujące kroki:

1. Zaimportuj klasę Dokument i Pole z przestrzeni nazw Aspose.Words.Fields.
2. Utwórz instancję dokumentu, ładując istniejący dokument.
3. Użyj metody InsertField, aby wstawić pole ASK, podając nazwę pytania.
4. Zapisz dokument.

#### P: Jak uzyskać odpowiedź użytkownika na pole ASK w dokumencie programu Word?

O: Aby uzyskać odpowiedź użytkownika na pole ASK w dokumencie programu Word, można skorzystać z metody GetFieldNames dostępnej w klasie Dokument. Metoda ta zwraca listę nazw pól występujących w dokumencie. Następnie możesz sprawdzić, czy nazwa pola ASK znajduje się na liście i pobrać powiązaną odpowiedź.

#### P: Czy można użyć pola ASK, aby poprosić użytkownika o więcej informacji?

Odpowiedź: Tak, pola ASK można używać do żądania od użytkownika wielu informacji. Możesz wstawić do swojego dokumentu wiele pól ASK, każde z innym pytaniem. Po otwarciu dokumentu użytkownik zostanie poproszony o podanie odpowiednich odpowiedzi.