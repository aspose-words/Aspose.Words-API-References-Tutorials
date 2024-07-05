---
title: Zmień pole Aktualizuj źródło kultury
linktitle: Zmień pole Aktualizuj źródło kultury
second_title: Aspose.Words API do przetwarzania dokumentów
description: Zmień pole Aktualizacja źródła kultury, Przewodnik krok po kroku dotyczący modyfikowania źródła kultury w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/change-field-update-culture-source/
---

tym samouczku przeprowadzimy Cię przez proces zmiany źródła kultury aktualizacji pola w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Modyfikując źródło kultury, możesz kontrolować formatowanie daty podczas operacji aktualizacji pól i korespondencji seryjnej. Dostarczymy Ci niezbędny kod źródłowy C# i instrukcje krok po kroku, jak to osiągnąć.

## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim systemie.

## Krok 1: Utwórz dokument i narzędzie do tworzenia dokumentów
Na początek utwórz instancję klasy Document i obiektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstaw treść z określonymi ustawieniami regionalnymi
Następnie ustaw ustawienia regionalne na niemieckie i wstaw pola z formatowaniem daty:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

W powyższym kodzie ustawiamy ustawienia regionalne czcionki na niemieckie (identyfikator ustawień regionalnych 1031) i wstawiamy dwa pola z określonym formatowaniem daty.

## Krok 3: Zmień źródło kultury aktualizacji pola
Aby zmienić źródło kultury aktualizacji pola, użyj klasy FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

W tym przykładzie ustawiamy kulturę używaną podczas aktualizacji pola na wybraną spośród kultury używanej przez pole.

## Krok 4: Wykonaj korespondencję seryjną
Wykonaj operację korespondencji seryjnej i podaj wartość daty w polu „Data2”:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

W tym fragmencie kodu wykonujemy operację korespondencji seryjnej i podajemy wartość DateTime w polu „Date2”.

## Krok 5: Zapisz dokument
Zapisz zmodyfikowany dokument do pliku korzystając z metody Save klasy Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Przykładowy kod źródłowy zmiany źródła kultury aktualizacji pola przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do zmiany źródła kultury aktualizacji pola w dokumentach programu Word przy użyciu Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się zmieniać źródło kultury aktualizacji pola w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i wykorzystując dostarczony kod źródłowy, możesz teraz kontrolować kulturę używaną do formatowania daty podczas operacji aktualizacji pól i korespondencji seryjnej. Dostosuj źródło kultury zgodnie ze swoimi wymaganiami, aby zapewnić dokładną i spójną datę.

### Często zadawane pytania

#### P: Jak mogę zmienić źródło kultury aktualizacji pola w Aspose.Words dla .NET?

 O: Aby zmienić źródło kultury aktualizacji pola w Aspose.Words dla .NET, możesz użyć metody`Document.FieldOptions.CultureSource` właściwość i ustaw jej wartość na`FieldCultureSource.FieldCode` Lub`FieldCultureSource.CurrentThread` . Możesz na przykład użyć`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` aby użyć kultury zdefiniowanej w kodzie pola.

#### P: Jak mogę określić konkretną kulturę aktualizowania pól w Aspose.Words dla .NET?

 O: Aby określić konkretną kulturę aktualizowania pól w Aspose.Words dla .NET, możesz użyć metody`Document.FieldOptions.FieldUpdateCultureInfo` właściwość i ustaw`CultureInfo` obiekt odpowiadający pożądanej kulturze. Możesz na przykład użyć`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` aby określić kulturę francuską (francuską).

#### P: Czy można wyłączyć automatyczne aktualizowanie pól w Aspose.Words dla .NET?

 O: Tak, możliwe jest wyłączenie automatycznej aktualizacji pól w Aspose.Words dla .NET. Możesz skorzystać z`Document.FieldOptions.UpdateFields` właściwość i ustaw ją na`false` aby zapobiec automatycznej aktualizacji pól. Dzięki temu możesz ręcznie kontrolować aktualizację pól w razie potrzeby.

#### P: Jak mogę ręcznie zaktualizować pola dokumentu w Aspose.Words dla .NET?

 Odp.: Aby ręcznie zaktualizować pola w dokumencie w Aspose.Words dla .NET, możesz użyć`Field.Update` metoda dla każdego pola indywidualnie. Możesz na przykład użyć`field.Update()` aby zaktualizować określone pole.