---
title: Wstaw pole zaawansowane bez narzędzia do tworzenia dokumentów
linktitle: Wstaw pole zaawansowane bez narzędzia do tworzenia dokumentów
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawić zaawansowane pole do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Zaawansowane wstawianie pól bez narzędzia DocumentBuilder” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

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

## Krok 3: Wstawianie pól zaawansowanych

 Używamy`AppendField()` metoda wstawiania zaawansowanego pola do akapitu.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Następnie konfigurujemy różne właściwości pola zaawansowanego, określając żądane wartości.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Na koniec nazywamy`Update()` metoda aktualizacji pola.

```csharp
field. Update();
```

### Przykład kodu źródłowego do wstawienia zaawansowanego pola bez DocumentBuilder z Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Wstaw pole zaawansowane.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

W tym przykładzie utworzyliśmy nowy dokument, wstawiliśmy zaawansowane pole bez użycia narzędzia DocumentBuilder, skonfigurowaliśmy różne właściwości pola i zapisaliśmy dokument z określoną nazwą pliku.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Wstaw zaawansowane pole bez narzędzia DocumentBuilder” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Co to jest zaawansowane pole w Aspose.Words?

Odp.: Pole Advance w Aspose.Words to specjalny typ pola, który umożliwia wykonywanie obliczeń, uwzględnianie warunków i wykonywanie złożonych operacji w dokumencie programu Word. Oferuje dużą elastyczność w tworzeniu pól dynamicznych i niestandardowych.

#### P: Jak wstawić zaawansowane pole do dokumentu Word bez korzystania z Konstruktora dokumentów w Aspose.Words?

Odp.: Aby wstawić zaawansowane pole do dokumentu Word bez korzystania z Konstruktora dokumentów w Aspose.Words, możesz wykonać następujące kroki:

1. Zaimportuj klasę Dokument i Pole z przestrzeni nazw Aspose.Words.Fields.
2. Utwórz instancję dokumentu, ładując istniejący dokument.
3. Użyj metody InsertField, aby wstawić pole zaawansowane, określając kod pola zaawansowanego.
4. Zapisz dokument.

#### P: Jak uzyskać wynik zaawansowanego pola w dokumencie programu Word?

Odp.: Aby uzyskać wynik zaawansowanego pola w dokumencie Worda, możesz skorzystać z właściwości Result dostępnej w klasie Pole. Ta właściwość zwraca obliczony wynik pola.

#### P: Czy mogę zmodyfikować formułę pola zaawansowanego po wstawieniu go do dokumentu Word?

Odp.: Tak, możesz edytować formułę pola zaawansowanego po wstawieniu go do dokumentu Word. Można to zrobić, uzyskując dostęp do właściwości FieldCode klasy Field i aktualizując formułę, modyfikując tekst formuły.