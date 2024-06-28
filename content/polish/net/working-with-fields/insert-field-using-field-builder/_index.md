---
title: Wstaw pole za pomocą narzędzia do tworzenia pól
linktitle: Wstaw pole za pomocą narzędzia do tworzenia pól
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać niestandardowe pola do dokumentów programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/insert-field-using-field-builder/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Wstaw pole za pomocą FieldBuilder” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Tworzenie dokumentu

Zaczynamy od utworzenia nowego dokumentu.

```csharp
Document doc = new Document();
```

## Krok 3: Budowa pola JEŻELI przy użyciu narzędzia FieldBuilder

Do skonstruowania pola JEŻELI z dwoma zagnieżdżonymi polami MERGEFIELD używamy klasy FieldBuilder. W tym przykładzie pole JEŻELI wyświetla imię i nazwisko na podstawie warunku.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Krok 4: Wstawienie pola JEŻELI do dokumentu

 Używamy`BuildAndInsert()` metoda budowania i wstawiania pola JEŻELI w określonym miejscu dokumentu.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Przykładowy kod źródłowy do wstawienia pola przy użyciu FieldBuilder z Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tworzenie dokumentów.
Document doc = new Document();

// Konstrukcja pola IF przy użyciu programu FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Wstaw pole JEŻELI do dokumentu.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

W tym przykładzie utworzyliśmy nowy dokument, skonstruowaliśmy pole JEŻELI z zagnieżdżonymi polami MERGEFIELD, a następnie wstawiliśmy to pole do dokumentu w określonym miejscu. Dokument jest następnie zapisywany pod określoną nazwą pliku.

### Często zadawane pytania

#### P: Czym jest konstruktor pól w Aspose.Words?

Odp.: Konstruktor pól w Aspose.Words to potężne narzędzie do tworzenia pól w dokumencie Word i manipulowania nimi. Oferuje zaawansowane funkcje tworzenia i dostosowywania pól, w tym wstawiania kodów pól i zarządzania opcjami formatowania.

#### P: Jakie typy pól można wstawiać za pomocą narzędzia do tworzenia pól?

Odp.: Kreator pól w Aspose.Words umożliwia wstawianie różnych typów pól do dokumentu Word. Oto kilka przykładów powszechnie używanych typów pól:

- MERGEFIELD: służy do łączenia danych ze źródeł zewnętrznych.
- DATA: wyświetla aktualną datę.
- STRONA: wyświetla numer bieżącej strony.
- JEŻELI: pozwala uzależnić wyświetlanie treści od warunku.
- Spis treści: automatycznie generuje spis treści na podstawie stylów tytułów dokumentów.

#### P: Jak dostosować pola wstawione za pomocą narzędzia do tworzenia pól?

Odp.: Kreator pól oferuje opcje dostosowywania wstawionych pól. Metod i właściwości konstruktora pól można używać do ustawiania opcji, takich jak formatowanie pól, argumenty, przełączniki i wartości domyślne. Na przykład możesz ustawić format daty, format liczb, separator tysięcy itp.
  