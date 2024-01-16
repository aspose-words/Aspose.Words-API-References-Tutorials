---
title: Wstaw pole scalania za pomocą DOM
linktitle: Wstaw pole scalania za pomocą DOM
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać niestandardowe pola scalania pól do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-merge-field-using-dom/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole scalania pola” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu i narzędzia DocumentBuilder

Zaczynamy od utworzenia nowego dokumentu i zainicjowania narzędzia DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Przesunięcie kursora do akapitu

 Używamy`MoveTo()` metoda DocumentBuilder, aby przenieść kursor do akapitu, w którym chcemy wstawić pole scalania pól.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Krok 4: Wstawienie pola scalania pól

 Używamy narzędzia DocumentBuilder`InsertField()` metoda wstawiania pola scalania pól do akapitu.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Następnie konfigurujemy właściwości pola scalania pól, określając odpowiednie opcje, takie jak nazwa pola, tekst przed i za polem oraz opcje formatowania pionowego.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Na koniec nazywamy`Update()` metoda aktualizacji pola.

```csharp
field. Update();
```

### Przykładowy kod źródłowy do wstawiania pola scalania pól za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i narzędzie DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Przesuń kursor do akapitu.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Wstaw pole scalania pól.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Zaktualizuj pole.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

W tym przykładzie utworzyliśmy nowy dokument, przesunęliśmy kursor do żądanego akapitu, a następnie wstawiliśmy do dokumentu pole scalania pól.

### Często zadawane pytania

#### P: Jak mogę wstawić pole scalania do dokumentu programu Word przy użyciu Aspose.Words dla .NET z DOM?

Odp.: Aby wstawić pole scalania do dokumentu programu Word przy użyciu Aspose.Words dla .NET z DOM, możesz wykonać następujące kroki:

1. Przejdź do akapitu, w którym chcesz wstawić pole scalania.
2.  Stwórz`FieldMergeField` obiekt.
3. Ustaw właściwości pola scalania, takie jak nazwa pola i opcje formatowania.
4.  Dodaj pole scalania do akapitu za pomocą`Paragraph.AppendChild` metoda.

#### P: Jak mogę określić dane źródłowe dla pola scalania w Aspose.Words dla .NET?

O: Aby określić dane źródłowe dla pola scalania w Aspose.Words dla .NET, możesz użyć`FieldMergeField.FieldName` metoda ustawiania nazwy pola scalania, czyli nazwy pola w zewnętrznym źródle danych, takim jak plik CSV, baza danych itp. Można również użyć metody`FieldMergeField.Text` metoda bezpośredniego ustawiania wartości pola scalania.

#### P: Czy mogę dostosować wygląd pola scalania w dokumencie programu Word za pomocą Aspose.Words dla .NET?

 Odp.: Tak, możesz dostosować wygląd pola scalania w dokumencie Word za pomocą Aspose.Words dla .NET. Możesz ustawić opcje formatowania, takie jak wielkość liter, czcionka, kolor itp., korzystając z właściwości pliku`FieldMergeField` obiekt.

#### P: Jak mogę sprawdzić, czy pole scalania zostało pomyślnie wstawione do dokumentu programu Word za pomocą Aspose.Words dla .NET?

 Odp.: Aby sprawdzić, czy pole scalania zostało pomyślnie wstawione, możesz przeglądać zawartość dokumentu i wyszukiwać wystąpienia pól scalania. Można używać metod i właściwości metody`Document` obiekt, aby uzyskać dostęp do akapitów, pól i innych elementów dokumentu.

#### P: Czy wstawienie pola scalania przy użyciu DOM wpływa na strukturę dokumentu Worda w Aspose.Words dla .NET?

Odp.: Wstawienie pola scalania przy użyciu modelu DOM nie ma bezpośredniego wpływu na strukturę dokumentu programu Word. Dodaje jednak nowy element pola do treści dokumentu. Możesz manipulować strukturą dokumentu, dodając, usuwając lub modyfikując istniejące elementy zgodnie ze swoimi potrzebami.