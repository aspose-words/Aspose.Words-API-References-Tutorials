---
title: Wstaw pole bloku adresu korespondencji seryjnej przy użyciu modelu DOM
linktitle: Wstaw pole bloku adresu korespondencji seryjnej przy użyciu modelu DOM
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić pole bloku adresu korespondencji seryjnej do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole bloku adresu korespondencji seryjnej” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

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

 Używamy narzędzia DocumentBuilder`MoveTo()` metoda przesunięcia kursora do akapitu, w którym chcemy wstawić pole bloku adresu korespondencji seryjnej.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Krok 4: Wstawianie pola bloku adresu korespondencji seryjnej

 Używamy narzędzia DocumentBuilder`InsertField()` metoda wstawienia pola bloku adresu korespondencji seryjnej do akapitu.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Następnie konfigurujemy właściwości pola bloku adresu, określając odpowiednie opcje, takie jak włączenie nazwy kraju/regionu, formatowanie adresu zgodnie z krajem/regionem, wykluczenie nazw krajów/regionów, format nazwy i adresu oraz identyfikator języka.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Na koniec nazywamy`Update()` metoda aktualizacji pola.

```csharp
field. Update();
```

### Przykładowy kod źródłowy do wstawiania pola bloku adresu korespondencji seryjnej za pomocą Aspose.Words dla .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Chcemy wstawić blok adresu korespondencji seryjnej w następujący sposób:
// { BLOK ADRESU \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// {BLOK ADRESU \\c 1" }
field.IncludeCountryOrRegionName = "1";

// {BLOK ADRESU \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { BLOK ADRESU \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { BLOK ADRESU \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { BLOK ADRESU \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### Często zadawane pytania

#### P: Jak mogę dostosować format adresu pocztowego w dokumencie Word za pomocą Aspose.Words dla .NET?

 Odp.: Możesz dostosować format adresu pocztowego w dokumencie Word za pomocą Aspose.Words dla .NET, korzystając z właściwości`FieldAddressBlock`obiekt. Możesz ustawić opcje formatowania, takie jak styl adresu, separatory, elementy opcjonalne itp., aby uzyskać żądany format.

#### P: Jak mogę określić dane źródłowe dla pola adresu pocztowego w Aspose.Words dla .NET?

 O: Aby określić dane źródłowe dla pola adresu pocztowego w Aspose.Words dla .NET, możesz użyć`FieldAddressBlock.StartAddress` I`FieldAddressBlock.EndAddress` nieruchomości. Właściwości te służą do definiowania zakresów adresów w zewnętrznym źródle danych takim jak plik CSV, baza danych itp.

#### P: Czy mogę dołączyć opcjonalne elementy w polu adresu pocztowego w Aspose.Words dla .NET?

 Odp.: Tak, możesz dołączyć opcjonalne elementy w polu adresu pocztowego za pomocą Aspose.Words dla .NET. Możesz zdefiniować elementy opcjonalne za pomocą`FieldAddressBlock.OmitOptional` metoda określająca, czy uwzględnić lub wykluczyć elementy opcjonalne, takie jak nazwa odbiorcy, nazwa firmy itp.

#### P: Czy wstawienie pola adresu pocztowego przy użyciu DOM wpływa na strukturę dokumentu Worda w Aspose.Words dla .NET?

Odp.: Wstawienie pola adresu pocztowego za pomocą DOM nie ma bezpośredniego wpływu na strukturę dokumentu Word. Dodaje jednak nowy element pola do treści dokumentu. Możesz manipulować strukturą dokumentu, dodając, usuwając lub modyfikując istniejące elementy zgodnie ze swoimi potrzebami.