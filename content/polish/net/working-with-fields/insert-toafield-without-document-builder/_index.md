---
title: Wstaw pole TOA bez narzędzia do tworzenia dokumentów
linktitle: Wstaw pole TOA bez narzędzia do tworzenia dokumentów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku, jak wstawić pole TOA bez Konstruktora dokumentów przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-toafield-without-document-builder/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstawianie pola TOA” w Aspose.Words dla .NET. Uważnie postępuj zgodnie z każdym krokiem, aby uzyskać pożądane rezultaty.

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

## Krok 3: Wstawienie pola TA

Do wstawienia pola TA do akapitu używamy klasy FieldTA.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Krok 4: Dodanie akapitu do treści dokumentu

Do treści dokumentu dodajemy akapit zawierający pole TA.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Krok 5: Tworzenie akapitu dla pola TOA

Tworzymy nowy akapit dla pola TOA.

```csharp
para = new Paragraph(doc);
```

## Krok 6: Wstawienie pola TOA

Aby wstawić pole TOA do akapitu, używamy klasy FieldToa.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Krok 7: Dodanie akapitu do treści dokumentu

Do treści dokumentu dodajemy akapit zawierający pole TOA.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Krok 8: Zaktualizuj pole TOA

 Na koniec nazywamy`Update()` metoda aktualizacji pola TOA.

```csharp
fieldToa.Update();
```

### Przykładowy kod źródłowy do wstawiania pola TOA bez Konstruktora dokumentów z Aspose.Words dla .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Chcemy wstawić pola TA i TOA w następujący sposób:
// { TA \c 1 \l "Wartość 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Często zadawane pytania

#### P: Jak dostosować wygląd pola TOA wstawionego w dokumencie Word za pomocą Aspose.Words dla .NET?

 Odp.: Możesz dostosować wygląd wstawionego pola TOA, korzystając z właściwości pliku`FieldTOA` obiekt, aby określić opcje formatowania.

#### P: Czy mogę dodać wiele pól TOA w jednym dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Tak, możesz dodać wiele pól TOA w jednym dokumencie programu Word przy użyciu Aspose.Words dla .NET. Po prostu powtórz kroki wstawiania dla każdego pola.

#### P: Jak mogę sprawdzić, czy pole TOA zostało pomyślnie wstawione do dokumentu Word za pomocą Aspose.Words dla .NET?

Odp.: Aby sprawdzić, czy pole TOA zostało pomyślnie wstawione, możesz przeglądać zawartość dokumentu i wyszukiwać wystąpienia pól TOA.

#### P: Czy wstawienie pola TOA bez użycia narzędzia DocumentBuilder wpływa na formatowanie dokumentu programu Word za pomocą Aspose.Words dla .NET?

Odp.: Wstawienie pola TOA bez użycia narzędzia DocumentBuilder nie ma bezpośredniego wpływu na formatowanie dokumentu programu Word. Jednak opcje formatowania pola TOA mogą mieć wpływ na ogólne formatowanie dokumentu.