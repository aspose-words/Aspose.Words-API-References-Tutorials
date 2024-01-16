---
title: Zamień hiperłącza
linktitle: Zamień hiperłącza
second_title: Aspose.Words API do przetwarzania dokumentów
description: Zamień hiperłącza w dokumentach programu Word za pomocą Aspose.Words dla .NET. Instrukcje krok po kroku dotyczące zastępowania hiperłączy.
type: docs
weight: 10
url: /pl/net/working-with-fields/replace-hyperlinks/
---

Oto przewodnik krok po kroku wyjaśniający następujący kod źródłowy C# służący do zastępowania hiperłączy przy użyciu funkcjonalności Aspose.Words dla .NET. Zanim użyjesz tego kodu, upewnij się, że w swoim projekcie umieściłeś bibliotekę Aspose.Words.

## Krok 1: Ustaw ścieżkę katalogu dokumentów

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Pamiętaj, aby podać poprawną ścieżkę do katalogu dokumentów zawierającego plik`Hyperlinks.docx` plik.

## Krok 2: Załaduj dokument zawierający hiperłącza

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Tutaj tworzymy instancję`Document` class z określonego pliku.

## Krok 3: Przeglądaj pola, aby znaleźć hiperłącza

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Niektóre hiperłącza mogą mieć charakter lokalny (linki do zakładek w dokumencie), ignorujemy je.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Ta pętla przechodzi przez wszystkie pola w dokumencie w poszukiwaniu pól typu`FieldType.FieldHyperlink` . Po znalezieniu pola tego typu sprawdzamy, czy jest to łącze lokalne, zaznaczając`SubAddress` nieruchomość. Jeśli nie, zastępujemy adres linku przez`"http://www.aspose.com"` i wynik z`"Aspose - The .NET & Java Component Editor"`.

## Krok 4: Zapisz zmodyfikowany dokument

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Na koniec zapisujemy zmodyfikowany dokument z zastąpionymi hiperłączami do określonego pliku.

### Przykładowy kod źródłowy do zamiany hiperłączy na Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Niektóre hiperłącza mogą mieć charakter lokalny (linki do zakładek w dokumencie), ignorujemy je.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

To jest przykładowy kod źródłowy zastępujący hiperłącza w dokumencie przy użyciu Aspose.Words dla .NET.

### Często zadawane pytania

#### P: Jak mogę zastąpić hiperłącza w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby zastąpić hiperłącza w dokumencie programu Word za pomocą programu Aspose.Words dla .NET, możesz użyć metody`Document.Range.Replace`metoda określająca tekst do wyszukania i tekst zastępczy. Pamiętaj, aby użyć odpowiednich opcji, aby ustawić parametry wyszukiwania i zamiany.

#### P: Czy możliwe jest zastąpienie tylko niektórych hiperłączy w dokumencie programu Word za pomocą Aspose.Words dla .NET?

Odp.: Tak, możliwe jest zastąpienie tylko niektórych hiperłączy w dokumencie Word za pomocą Aspose.Words dla .NET. Możesz filtrować zastępowane hiperłącza, korzystając z określonych kryteriów, takich jak adres URL łącza, tekst łącza lub inna istotna właściwość. Następnie możesz zastosować zamianę tylko do pasujących hiperłączy.

#### P: Jak mogę zignorować hiperłącza w nagłówkach, stopkach lub przypisach podczas zastępowania za pomocą Aspose.Words dla .NET?

O: Aby zignorować hiperłącza w nagłówkach, stopkach lub przypisach podczas zastępowania za pomocą Aspose.Words dla .NET, możesz skorzystać z zaawansowanych opcji wyszukiwania i określić odpowiednie limity wyszukiwania. Można na przykład ograniczyć wyszukiwanie do głównych sekcji dokumentu i wykluczyć nagłówki, stopki i przypisy.

#### P: Czy możliwe jest zastąpienie hiperłączy wewnętrznymi łączami do innych części dokumentu?

 Odp.: Tak, możliwe jest zastąpienie hiperłączy wewnętrznymi łączami do innych części dokumentu za pomocą Aspose.Words dla .NET. Możesz użyć kotwic lub identyfikatorów tekstowych, aby utworzyć linki wewnętrzne, a następnie zastąpić je za pomocą`Document.Range.Replace` metodę z odpowiednimi opcjami.

#### P: Czy zastąpienie hiperłączy programem Aspose.Words dla .NET zachowuje właściwości łącza, takie jak kolory i style?

Odp.: Tak, podczas zastępowania hiperłączy przez Aspose.Words dla .NET, właściwości łącza, takie jak kolory i style, zostają zachowane. Aby uzyskać spójny wynik, możesz określić te same właściwości formatowania w tekście zastępczym.