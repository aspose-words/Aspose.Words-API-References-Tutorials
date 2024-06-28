---
title: Zmień ustawienia regionalne
linktitle: Zmień ustawienia regionalne
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak zmienić ustawienia regionalne dla formatowania daty i liczb w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/change-locale/
---

W tym samouczku przeprowadzimy Cię przez proces zmiany ustawień regionalnych w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Modyfikując ustawienia regionalne, możesz kontrolować formatowanie dat i liczb podczas operacji korespondencji seryjnej. Dostarczymy Ci niezbędny kod źródłowy C# i instrukcje krok po kroku, jak to osiągnąć.

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

## Krok 2: Wstaw pole
Następnie wstaw do dokumentu pole scalania za pomocą metody InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

W powyższym kodzie wstawiamy do dokumentu pole scalania o nazwie „Data”.

## Krok 3: Zmień ustawienia regionalne
Aby zmienić ustawienia regionalne formatowania daty i liczb, możesz zmodyfikować bieżącą kulturę wątku. W tym przykładzie ustawimy ustawienia regionalne na niemieckie („de-DE”):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

W powyższym kodzie przechowujemy bieżącą kulturę, a następnie ustawiamy kulturę bieżącego wątku na niemiecką.

## Krok 4: Wykonaj korespondencję seryjną
Wykonaj operację korespondencji seryjnej i podaj wartość daty w polu „Data”:

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

W tym fragmencie kodu wykonujemy operację korespondencji seryjnej i jako wartość w polu „Data” podajemy bieżącą datę.

## Krok 5: Przywróć oryginalne ustawienia regionalne
Po zakończeniu korespondencji seryjnej przywróć oryginalną kulturę wątku:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

W powyższym kodzie przywracamy pierwotną kulturę wątku.

## Krok 6: Zapisz dokument
Zapisz zmodyfikowany dokument do pliku korzystając z metody Save klasy Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Przykładowy kod źródłowy do zmiany ustawień regionalnych przy użyciu Aspose.Words dla .NET
Oto kompletny kod źródłowy do zmiany ustawień regionalnych w dokumentach Word przy użyciu Aspose.Words dla .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się zmieniać ustawienia regionalne w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonego kodu źródłowego, możesz teraz kontrolować formatowanie dat i liczb podczas operacji korespondencji seryjnej. Dostosuj ustawienia regionalne zgodnie ze swoimi wymaganiami, aby zapewnić dokładne i spójne formatowanie w dokumentach.

### Często zadawane pytania

#### P: Czy Aspose.Words jest kompatybilny z różnymi wersjami Microsoft Word?

Odp.: Tak, Aspose.Words jest kompatybilny z różnymi wersjami Microsoft Word, w tym Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 i Word 2019.

#### P: Czy Aspose.Words obsługuje złożone struktury pól?

Odp.: Absolutnie! Aspose.Words oferuje szeroką obsługę złożonych struktur pól, w tym pól zagnieżdżonych, obliczeń i wyrażeń warunkowych. Możesz użyć tego potężnego interfejsu API do pracy z dowolnym typem struktury pól.

#### P: Czy Aspose.Words obsługuje operacje aktualizacji w terenie?

Odp.: Tak, Aspose.Words umożliwia aktualizację pól zgodnie z harmonogramem. Za pomocą interfejsu API możesz łatwo aktualizować wartości pól, odświeżać obliczenia i wykonywać inne operacje związane z polami.

#### P: Czy można konwertować pola na zwykły tekst za pomocą Aspose.Words?

Odp.: Oczywiście! Aspose.Words udostępnia metody konwersji pól na zwykły tekst. Może to być przydatne, gdy trzeba wyodrębnić treść bez żadnych funkcji związanych z formatowaniem lub polami.

#### P: Czy możliwe jest generowanie dokumentów Word z polami dynamicznymi przy użyciu Aspose.Words?

Odp.: Absolutnie! Aspose.Words oferuje solidną funkcjonalność do generowania dokumentów Word z polami dynamicznymi. Możesz tworzyć szablony z predefiniowanymi polami i dynamicznie wypełniać je danymi, zapewniając elastyczne i wydajne rozwiązanie do generowania dokumentów.