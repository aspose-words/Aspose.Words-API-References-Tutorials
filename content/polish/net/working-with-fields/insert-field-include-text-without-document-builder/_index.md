---
title: Wstaw pole Dołącz tekst bez narzędzia do tworzenia dokumentów
linktitle: Wstaw FieldIncludeText bez narzędzia do tworzenia dokumentów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pole FieldIncludeText do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole FieldIncludeText” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu i akapitu

Zaczynamy od utworzenia nowego dokumentu i zainicjowania akapitu.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Krok 3: Wstawianie pola FieldIncludeText

 Używamy`AppendField()` metoda wstawiania pola FieldIncludeText do akapitu.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Następnie konfigurujemy właściwości pola FieldIncludeText podając nazwę zakładki i nazwę pliku źródłowego.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Następnie dodajemy akapit do treści dokumentu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Na koniec nazywamy`Update()` metoda aktualizacji pola.

```csharp
fieldIncludeText.Update();
```

### Przykład kodu źródłowego do wstawienia pola FieldIncludeText za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i akapit.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Wstaw pole FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

W tym przykładzie utworzyliśmy nowy dokument, zainicjowaliśmy akapit, wstawiliśmy FieldIncludeTexten określający nazwę zakładki i nazwę pliku źródłowego, a następnie zapisaliśmy dokument z określoną nazwą pliku.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Wstaw poleIncludeText” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak mogę określić plik źródłowy dla pola włączenia tekstu w Aspose.Words dla .NET?

 O: Aby określić plik źródłowy dla pola włączenia tekstu w Aspose.Words dla .NET, możesz użyć`FieldIncludeText.SourceFullName`właściwość, aby ustawić pełną ścieżkę pliku źródłowego. Upewnij się, że plik źródłowy jest dostępny i zawiera treść, którą chcesz umieścić w polu włączenia tekstu.

#### P: Czy mogę dołączyć tekst z makra do pola włączenia tekstu w Aspose.Words dla .NET?

 Odp.: Tak, możesz dołączyć tekst z makra w polu włączenia tekstu za pomocą Aspose.Words dla .NET. Możesz skorzystać z`FieldIncludeText.IncludeText` właściwość określająca nazwę makra, którego zawartość ma zostać uwzględniona w polu.

#### P: Czy wstawienie pola zawierającego tekst bez narzędzia do tworzenia dokumentów wpływa na strukturę dokumentu programu Word w Aspose.Words dla .NET?

Odp.: Wstawienie pola zawierającego tekst bez narzędzia do tworzenia dokumentów nie ma bezpośredniego wpływu na strukturę dokumentu programu Word. Dodaje jednak nowy element pola do treści dokumentu. Możesz manipulować strukturą dokumentu, dodając, usuwając lub modyfikując istniejące elementy zgodnie ze swoimi potrzebami.

#### P: Czy mogę dostosować wygląd pola włączenia tekstu w dokumencie programu Word za pomocą Aspose.Words dla .NET?

Odp.: Pole włączenia tekstu nie dostosowuje bezpośrednio jego wyglądu w dokumencie programu Word. Można jednak sformatować dołączony tekst, korzystając z właściwości akapitu, właściwości czcionki i innych obiektów formatujących dostępnych w Aspose.Words dla .NET.