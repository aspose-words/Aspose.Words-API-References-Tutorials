---
title: Kod pola
linktitle: Kod pola
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku, jak uzyskać kod pola i wynik pola w dokumentach programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/field-code/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który korzysta z funkcji „Pobierz kod pola” Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument

Pierwszym krokiem jest przesłanie dokumentu, w którym chcesz uzyskać kody pól.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Pamiętaj, aby zastąpić „Hyperlinks.docx” nazwą własnego pliku.

## Krok 3: Przeglądaj pola dokumentu

 Używamy A`foreach` pętla, aby przeglądać wszystkie pola obecne w dokumencie.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 W każdej iteracji pętli otrzymujemy kod pola za pomocą metody`GetFieldCode()` metoda. Wynik pola przechowujemy również w zmiennej.

### Przykład kodu źródłowego dla Pobierz kod pola z Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Pętla po polach dokumentu.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Zrób coś z kodem pola i wynikiem.
}
```

W tym przykładzie załadowaliśmy dokument, a następnie przejrzeliśmy wszystkie pola obecne w dokumencie. Przy każdej iteracji otrzymywaliśmy kod i wynik działania pola. W razie potrzeby możesz dodać własną logikę do przetwarzania kodu i pól wyników.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Pobierz kod pola” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak mogę wstawić pole do dokumentu programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby wstawić pole do dokumentu programu Word za pomocą Aspose.Words dla .NET, możesz użyć metody`DocumentBuilder.InsertField` metoda określająca odpowiedni kod pola. Możesz na przykład użyć`builder.InsertField("MERGEFIELD CustomerName")` , aby wstawić pole scalania do dokumentu.

#### P: Jak mogę zaktualizować pola w dokumencie przy użyciu Aspose.Words dla .NET?

 Odp.: Aby zaktualizować pola dokumentu za pomocą Aspose.Words dla .NET, możesz użyć`Document.UpdateFields`metoda. Spowoduje to aktualizację wszystkich pól obecnych w dokumencie, takich jak pola scalania, pola daty itp.

#### P: Jak mogę pobrać wartość określonego pola w Aspose.Words dla .NET?

 O: Aby pobrać wartość określonego pola w Aspose.Words dla .NET, możesz użyć metody`Field.GetResult` metodę poprzez określenie indeksu pola w pliku`Document.Range.Fields` kolekcja. Możesz na przykład użyć`string value = document.Range.Fields[0].GetResult()` aby pobrać wartość pierwszego pola w dokumencie.

#### P: Jak mogę usunąć pole z dokumentu za pomocą Aspose.Words dla .NET?

 Odp.: Aby usunąć pole z dokumentu za pomocą Aspose.Words dla .NET, możesz użyć`Field.Remove` metoda określająca`Field` obiekt, który chcesz usunąć. Spowoduje to usunięcie pola z dokumentu.