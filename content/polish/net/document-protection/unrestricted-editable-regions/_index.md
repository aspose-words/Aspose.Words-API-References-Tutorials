---
title: Nieograniczone edytowalne regiony w dokumencie programu Word
linktitle: Nieograniczone edytowalne regiony w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak tworzyć nieograniczone obszary edytowalne w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-protection/unrestricted-editable-regions/
---
W tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji nieograniczonej edycji obszarów Aspose.Words dla .NET. Ta funkcja umożliwia definiowanie obszarów w dokumencie programu Word, w których zawartość może być edytowana bez ograniczeń, nawet jeśli pozostała część dokumentu jest przeznaczona tylko do odczytu. Wykonaj poniższe kroki:

## Krok 1: Załaduj dokument i ustaw ochronę

Zacznij od załadowania istniejącego dokumentu:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Chroń dokument, ustawiając typ ochrony i hasło tylko do odczytu

## Krok 2: Tworzenie obszaru edytowalnego

Zacznij od utworzenia obszaru edytowalnego przy użyciu obiektów EditableRangeStart i EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Dla obiektu EditableRangeStart, który właśnie utworzyliśmy, tworzony jest obiekt EditableRange.
EditableRange editableRange = edRangeStart.EditableRange;

// Umieść coś w zakresie edytowalnym.
builder.Writeln("Paragraph inside first editable range");

// Zakres edytowalny jest dobrze utworzony, jeśli ma początek i koniec.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Krok 3: Dodaj treść poza obszarami edytowalnymi

Możesz dodać treść poza obszarami edytowalnymi, które pozostaną tylko do odczytu:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Krok 4: Zapisz dokument

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać dokument z obszarami edytowalnymi.

### Przykładowy kod źródłowy dla nieograniczonych edytowalnych regionów przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy nieograniczonych obszarów edytowalnych przy użyciu Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Prześlij dokument i ustaw go jako tylko do odczytu.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Rozpocznij edytowalny zakres.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Dla obiektu EditableRangeStart, który właśnie utworzyliśmy, tworzony jest obiekt EditableRange.
EditableRange editableRange = edRangeStart.EditableRange;

// Umieść coś w zakresie edytowalnym.
builder.Writeln("Paragraph inside first editable range");

// Zakres edytowalny jest dobrze utworzony, jeśli ma początek i koniec.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Wykonując poniższe kroki, możesz łatwo utworzyć nieograniczone obszary do edycji w dokumencie programu Word za pomocą Aspose.Words dla .NET.

## Wniosek
W tym samouczku nauczyliśmy się, jak tworzyć nieograniczone edytowalne regiony w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wykonując podane kroki, możesz zdefiniować określone obszary w dokumencie, w których użytkownicy będą mogli swobodnie edytować treść, pozostawiając resztę dokumentu w trybie tylko do odczytu. Aspose.Words dla .NET oferuje zaawansowane funkcje ochrony i dostosowywania dokumentów, zapewniając kontrolę nad możliwościami edycji dokumentów Word.

### Często zadawane pytania dotyczące nieograniczonych edytowalnych regionów w dokumencie Word

#### P: Jakie są nieograniczone edytowalne regiony w Aspose.Words dla .NET?

O: Nieograniczone edytowalne regiony w Aspose.Words for .NET to obszary w dokumencie Word, w których zawartość może być edytowana bez żadnych ograniczeń, nawet jeśli reszta dokumentu jest ustawiona jako tylko do odczytu. Regiony te umożliwiają zdefiniowanie określonych części dokumentu, które użytkownicy mogą modyfikować, zachowując jednocześnie ogólną ochronę dokumentu.

#### P: Jak mogę utworzyć nieograniczone edytowalne regiony za pomocą Aspose.Words dla .NET?

Odp.: Aby utworzyć nieograniczone edytowalne regiony w dokumencie programu Word przy użyciu Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Załaduj istniejący dokument za pomocą`Document` klasa.
2.  Ustaw ochronę dokumentu na tylko do odczytu za pomocą`Protect` metoda`Document` obiekt.
3.  Użyj`DocumentBuilder` class, aby utworzyć edytowalny zakres, dodając klasę`EditableRangeStart` obiekt i`EditableRangeEnd` obiekt.
4.  Dodaj zawartość w edytowalnym zakresie za pomocą`DocumentBuilder`.
5.  Zapisz zmodyfikowany dokument za pomocą`Save` metoda`Document` obiekt.

#### P: Czy mogę mieć wiele nieograniczonych edytowalnych regionów w dokumencie programu Word?

Odp.: Tak, w dokumencie programu Word możesz mieć wiele nieograniczonych edytowalnych regionów. Aby to osiągnąć, możesz utworzyć wiele zestawów`EditableRangeStart` I`EditableRangeEnd` obiekty za pomocą`DocumentBuilder` klasa. Każdy zestaw obiektów będzie definiował oddzielny region edytowalny, w którym użytkownicy będą mogli modyfikować zawartość bez żadnych ograniczeń.

#### P: Czy mogę zagnieżdżać edytowalne regiony jeden w drugim?

 O: Nie, nie można zagnieżdżać edytowalnych regionów w sobie przy użyciu Aspose.Words dla .NET. Każdy edytowalny region zdefiniowany przez plik`EditableRangeStart` I`EditableRangeEnd` para powinna być niezależna i nie może nakładać się na siebie ani być zagnieżdżona w innym edytowalnym regionie. Zagnieżdżone regiony edytowalne nie są obsługiwane.

#### P: Czy mogę usunąć zabezpieczenie tylko do odczytu z dokumentu znajdującego się w edytowalnym regionie?

O: Nie, nie można usunąć zabezpieczenia tylko do odczytu z dokumentu znajdującego się w obszarze edytowalnym. Ochrona tylko do odczytu dotyczy całego dokumentu i nie można jej selektywnie usunąć w obrębie określonych edytowalnych regionów. Celem edytowalnych regionów jest umożliwienie modyfikacji treści przy jednoczesnym zachowaniu całego dokumentu w trybie tylko do odczytu.