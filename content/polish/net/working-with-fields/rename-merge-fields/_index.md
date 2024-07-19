---
title: Zmień nazwę pola scalania
linktitle: Zmień nazwę pola scalania
second_title: Aspose.Words API do przetwarzania dokumentów
description: W tym samouczku dowiesz się, jak zmienić nazwę pól scalania w dokumencie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/rename-merge-fields/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję zmiany nazwy pola scalającego w Aspose.Words dla .NET. Uważnie postępuj zgodnie z każdym krokiem, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu i wstawianie pól scalających

Zaczynamy od utworzenia nowego dokumentu i użycia pliku`DocumentBuilder` , aby wstawić pola scalania.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Krok 3: Zmiana nazwy pól scalających

Przechodzimy przez każde pole w zakresie dokumentu i jeśli jest to pole scalone, zmieniamy nazwę pola, dodając „_Przemianowano przyrostek”.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Krok 4: Zapisanie dokumentu

 Na koniec nazywamy`Save()` metoda zapisania zmodyfikowanego dokumentu.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Przykład kodu źródłowego zmiany nazw pól scalania za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i wstaw pola scalania.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Zmień nazwę pól scalających.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Zapisz dokument.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Wykonaj poniższe kroki, aby zmienić nazwę pól scalania w dokumencie przy użyciu Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak mogę zmienić nazwę scalonych pól w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby zmienić nazwę scalonych pól w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz przeglądać pola w dokumencie za pomocą`FieldMergingArgs` klasę i użyj`FieldMergingArgs.FieldName` metoda zmiany nazwy pola.

#### P: Czy można zmienić nazwy tylko niektórych scalonych pól w dokumencie programu Word za pomocą Aspose.Words dla .NET?

Odp.: Tak, możliwa jest zmiana nazw tylko niektórych scalonych pól w dokumencie Word za pomocą Aspose.Words dla .NET. Możesz filtrować nazwy pól, których nazwy chcesz zmienić, korzystając z określonych kryteriów, takich jak nazwa pola lub inne odpowiednie właściwości. Następnie możesz zmienić nazwy odpowiednich pól za pomocą`FieldMergingArgs.FieldName` metoda.

#### P: Jak mogę sprawdzić, czy nazwa scalonego pola została pomyślnie zmieniona w dokumencie programu Word za pomocą Aspose.Words dla .NET?

 Odp.: Aby sprawdzić, czy nazwa scalonego pola została pomyślnie zmieniona w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz użyć`FieldMergedArgs` klasę i uzyskaj dostęp do`FieldMergedArgs.IsMerged` aby określić, czy nazwa pola została zmieniona w wyniku trafienia.

#### P: Jakie są konsekwencje zmiany nazwy scalonego pola w dokumencie programu Word za pomocą Aspose.Words dla .NET?

Odp.: Kiedy zmieniasz nazwę scalonego pola w dokumencie programu Word za pomocą Aspose.Words dla .NET, zmienia to nazwę pola w dokumencie, co może mieć wpływ na inne funkcje lub procesy zależne od nazwy pola. Przed zmianą nazwy scalonych pól pamiętaj o rozważeniu tych potencjalnych konsekwencji.

#### P: Czy można przywrócić oryginalną nazwę scalonego pola po zmianie jego nazwy na Aspose.Words dla .NET?

O: Tak, możliwe jest przywrócenie oryginalnej nazwy scalonego pola po zmianie jego nazwy za pomocą Aspose.Words dla .NET. Możesz zapisać oryginalną nazwę pola w zmiennej lub liście, a następnie użyć tych informacji, aby w razie potrzeby przywrócić oryginalną nazwę.