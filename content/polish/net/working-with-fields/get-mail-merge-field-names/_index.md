---
title: Pobierz nazwy pól korespondencji seryjnej
linktitle: Pobierz nazwy pól korespondencji seryjnej
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak uzyskać nazwy pól korespondencji seryjnej w dokumentach programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/get-mail-merge-field-names/
---

Oto przewodnik krok po kroku wyjaśniający poniższy kod źródłowy C#, który wykorzystuje funkcję „Pobierz nazwy pól scalanych” w Aspose.Words dla .NET. Pamiętaj, aby dokładnie wykonać każdy krok, aby uzyskać pożądane rezultaty.

## Krok 1: Konfiguracja katalogu dokumentów

W podanym kodzie musisz określić katalog swoich dokumentów. Zastąp wartość „TWOJ KATALOG DOKUMENTÓW” odpowiednią ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Załaduj dokument

Pierwszym krokiem jest załadowanie dokumentu, w którym chcesz uzyskać nazwy pól scalania.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Pamiętaj, aby zastąpić „TWOJ PLIK DOKUMENTU” nazwą własnego pliku.

## Krok 3: Uzyskaj nazwy pól scalających

 Używamy`GetFieldNames()` metodę, aby uzyskać tablicę zawierającą nazwy pól scalających występujących w dokumencie.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 The`fieldNames` zmienna zawiera teraz nazwy pól scalania.

### Przykład kodu źródłowego dla opcji Get Merge Field Names with Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Uzyskaj nazwy pól scalających.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Wyświetl liczbę pól scalania.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 W tym przykładzie załadowaliśmy dokument, otrzymaliśmy nazwy pól scalania za pomocą`GetFieldNames()` metodę i wyświetlił liczbę pól scalania występujących w dokumencie.

Na tym kończy się nasz przewodnik dotyczący korzystania z funkcji „Uzyskaj scalanie nazw pól” w Aspose.Words dla .NET.

### Często zadawane pytania

#### P1: Co to jest korespondencja seryjna w Aspose.Words?

Korespondencja seryjna w Aspose.Words to proces łączenia danych z zewnętrznego źródła (np. arkusza kalkulacyjnego Excel lub bazy danych) z szablonowym dokumentem Word w celu tworzenia spersonalizowanych dokumentów. Ułatwia to automatyczne generowanie pism, raportów i innych podobnych dokumentów.

#### P2: Jak uzyskać listę pól korespondencji seryjnej dostępnych w dokumencie programu Word?

Aby uzyskać listę pól korespondencji seryjnej dostępnych w dokumencie programu Word, wykonaj następujące kroki:

1. Zaimportuj klasy Document i MailMergeFieldNames z przestrzeni nazw Aspose.Words.
2. Utwórz instancję dokumentu, ładując dokument programu Word.
3. Użyj metody GetMailMergeFieldNames obiektu Document, aby uzyskać listę dostępnych pól korespondencji seryjnej.

Oto przykładowy kod ilustrujący proces:

```csharp
// Zaimportuj niezbędne przestrzenie nazw
using Aspose.Words;
using Aspose.Words.MailMerging;

// Załaduj istniejący dokument
Document document = new Document("FilePath");

// Pobierz listę pól korespondencji seryjnej
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Przełączaj dostępne pola korespondencji seryjnej
foreach (string fieldName in fieldNames)
{
     // Zrób coś z nazwą pola
     Console.WriteLine(fieldName);
}
```
### Często zadawane pytania

#### P: Co to jest korespondencja seryjna w Aspose.Words?

Odp.: Korespondencja seryjna w Aspose.Words to proces łączenia danych ze źródła zewnętrznego (np. arkusza kalkulacyjnego lub bazy danych Excel) z szablonowym dokumentem programu Word w celu tworzenia spersonalizowanych dokumentów. Ułatwia to automatyczne generowanie pism, raportów i innych podobnych dokumentów.

#### P: Jak uzyskać listę pól korespondencji seryjnej dostępnych w dokumencie programu Word?

Odp.: Aby uzyskać listę pól korespondencji seryjnej dostępnych w dokumencie programu Word, możesz wykonać następujące kroki:

1. Zaimportuj klasy Document i MailMergeFieldNames z przestrzeni nazw Aspose.Words.
2. Utwórz instancję dokumentu, ładując dokument programu Word.
3. Użyj metody GetMailMergeFieldNames obiektu Document, aby uzyskać listę dostępnych pól korespondencji seryjnej.

#### P: Czy mogę uzyskać pola korespondencji seryjnej z zewnętrznego źródła danych, takiego jak arkusz kalkulacyjny programu Excel?

O: Tak, pola korespondencji seryjnej można uzyskać z zewnętrznego źródła danych, takiego jak arkusz kalkulacyjny programu Excel. W tym celu możesz użyć funkcji wiązania danych Aspose.Words, aby nawiązać połączenie ze źródłem danych i uzyskać nazwy dostępnych pól.

#### P: Czy można filtrować pola korespondencji seryjnej na podstawie określonych kryteriów?

O: Tak, możliwe jest filtrowanie pól korespondencji seryjnej na podstawie określonych kryteriów. Możesz używać wyrażeń regularnych lub określonych warunków, aby filtrować pola korespondencji seryjnej i wyświetlać tylko te, które spełniają określone kryteria.

#### P: Jak mogę manipulować polami korespondencji seryjnej w Aspose.Words?

O: Aby manipulować polami korespondencji seryjnej w Aspose.Words, możesz użyć metod i właściwości udostępnianych przez obiekty Document i MailMergeField. Możesz dodawać, usuwać lub aktualizować pola korespondencji seryjnej, a także pobierać i edytować wartości skojarzone z polami.