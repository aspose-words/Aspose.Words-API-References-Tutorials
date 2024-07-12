---
title: Określ ustawienia regionalne na poziomie pola
linktitle: Określ ustawienia regionalne na poziomie pola
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak określić lokalizację na poziomie pola w dokumentach programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/specify-locale-at-field-level/
---

Oto przewodnik krok po kroku wyjaśniający następujący kod źródłowy C#, który umożliwia określenie lokalizacji na poziomie pola przy użyciu funkcji Aspose.Words dla .NET. Zanim użyjesz tego kodu, upewnij się, że w swoim projekcie umieściłeś bibliotekę Aspose.Words.

## Krok 1: Ustaw ścieżkę katalogu dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów, w którym zostanie zapisany edytowany dokument.

## Krok 2: Utwórz generator dokumentów

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Tutaj tworzymy instancję`DocumentBuilder` klasa, która umożliwi nam dodanie pól do dokumentu.

## Krok 3: Wstaw pole daty z konkretną lokalizacją

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Do wstawienia pola typu używamy generatora dokumentów`FieldType.FieldDate` do dokumentu. Ustawiając`LocaleId`własność do`1049`, podajemy rosyjską lokalizację tego pola.

## Krok 4: Zapisz zmodyfikowany dokument

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Na koniec zapisujemy zmodyfikowany dokument z określoną lokalizacją do określonego pliku.

### Przykładowy kod źródłowy do określania lokalizacji na poziomie pola za pomocą Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

To był przykładowy kod źródłowy określający lokalizację na poziomie pola w dokumencie przy użyciu Aspose.Words dla .NET. Możesz użyć tego kodu, aby wstawić pola daty z określonymi lokalizacjami w dokumentach programu Word.

### Często zadawane pytania

#### P: Jak mogę określić ustawienia regionalne na poziomie pola w Aspose.Words dla .NET?

 O: Aby określić ustawienia regionalne na poziomie pola w Aspose.Words dla .NET, możesz użyć opcji`FieldOptions` klasa i jej`FieldLocale` właściwość, aby ustawić żądane ustawienia regionalne. Możesz na przykład użyć`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` aby określić ustawienia regionalne języka francuskiego (Francja).

#### P: Czy możliwe jest określenie różnych ustawień regionalnych dla każdego pola w Aspose.Words dla .NET?

 O: Tak, możliwe jest określenie różnych ustawień regionalnych dla każdego pola w Aspose.Words dla .NET. Możesz skorzystać z`FieldOptions.FieldLocale` właściwość przed utworzeniem lub aktualizacją określonego pola w celu przypisania mu innych ustawień regionalnych.

#### P: Jak mogę uzyskać aktualnie używane ustawienia regionalne dla pola w Aspose.Words dla .NET?

 O: Aby uzyskać aktualnie używane ustawienia regionalne dla pola w Aspose.Words dla .NET, możesz użyć`Field.LocaleId`nieruchomość. Umożliwi to uzyskanie identyfikatora ustawień regionalnych powiązanego z polem.