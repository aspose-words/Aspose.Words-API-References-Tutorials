---
title: Wstaw pole autora
linktitle: Wstaw pole autora
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pole AUTOR w dokumentach programu Word za pomocą Aspose.Words dla .NET. Podaj nazwisko autora, aby spersonalizować swoje dokumenty.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-author-field/
---


Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole AUTHOR” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

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

## Krok 3: Wstaw pole AUTOR

 Używamy`AppendField()` metoda wstawienia pola AUTOR do akapitu.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Następnie konfigurujemy pole`AuthorName` właściwość określająca nazwisko autora.

```csharp
field. AuthorName = "Test1";
```

 Na koniec nazywamy`Update()` metoda aktualizacji pola.

```csharp
field. Update();
```

### Przykład kodu źródłowego do wstawienia pola AUTHOR za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Wstaw pole AUTOR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

W tym przykładzie utworzyliśmy nowy dokument, wstawiliśmy pole AUTHOR, skonfigurowaliśmy nazwisko autora i zapisaliśmy dokument pod określoną nazwą pliku.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Wstaw pole AUTOR” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Co to jest pole autora w Aspose.Words?

O: Pole autora w Aspose.Words to specjalne pole, które automatycznie wstawia i aktualizuje nazwisko autora w dokumencie Word. Często jest używany do wskazania, kto utworzył lub zmodyfikował dokument.

#### P: Jak zaktualizować pole autora w dokumencie Word za pomocą Aspose.Words?

Odp.: Pole autora w dokumencie programu Word można zaktualizować, aby odzwierciedlało nazwisko bieżącego autora. Można w tym celu skorzystać z metody UpdateFields dostępnej w klasie Document. Ta metoda zaktualizuje wszystkie pola w dokumencie, w tym pole autora.

#### P: Czy można dostosować format pola autora w dokumencie programu Word?

Odp.: Tak, możliwe jest dostosowanie formatu pola autora w dokumencie programu Word. Domyślnie w polu autora wyświetlane jest po prostu nazwisko autora. Możesz jednak dodać dodatkowe informacje, takie jak data i godzina modyfikacji, korzystając z opcji formatowania dostępnych w Aspose.Words.

#### P: Czy pole autora jest wrażliwe na późniejsze zmiany nazwiska autora?

Odpowiedź: Tak, pole autora jest wrażliwe na późniejsze zmiany nazwiska autora. Jeśli zmienisz nazwę autora we właściwościach dokumentu, pole autora zostanie automatycznie zaktualizowane o nową nazwę podczas aktualizacji pól dokumentu.