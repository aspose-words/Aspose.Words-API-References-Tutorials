---
title: Użyj znaku spacji na poziomie dla wcięcia listy
linktitle: Użyj znaku spacji na poziomie dla wcięcia listy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący używania znaku spacji na każdym poziomie w celu wcięcia listy w Aspose.Words dla .NET. Z łatwością twórz dobrze zorganizowane dokumenty programu Word.
type: docs
weight: 10
url: /pl/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words dla .NET to potężna biblioteka do tworzenia, edytowania i manipulowania dokumentami Word w aplikacji C#. Wśród funkcji oferowanych przez Aspose.Words jest możliwość użycia jednego znaku spacji na poziom do wcięcia list. W tym przewodniku pokażemy, jak używać kodu źródłowego C# Aspose.Words dla .NET do wdrożenia tej funkcjonalności.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to popularna biblioteka, która sprawia, że przetwarzanie tekstu w dokumentach Word jest łatwe i wydajne. Oferuje szeroką gamę funkcjonalności umożliwiających tworzenie, modyfikowanie i manipulowanie dokumentami Word, w tym zarządzanie listami i wcięciami.

## Tworzenie dokumentu i dodawanie treści

Pierwszym krokiem jest utworzenie nowego dokumentu i dodanie do niego treści. Użyj klasy Document, aby utworzyć nową instancję dokumentu. Następnie użyj klasy DocumentBuilder, aby dodać tekst i utworzyć listę z wieloma poziomami wcięć. Oto przykład :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utwórz listę z trzema poziomami wcięć
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

W tym przykładzie tworzymy nowy dokument i za pomocą narzędzia DocumentBuilder dodajemy tekst i tworzymy listę z trzema poziomami wcięć. Dodaliśmy do listy trzy pozycje, przy czym każda pozycja wskazuje dodatkowy poziom.

## Użycie jednego znaku spacji na poziom w celu wcięcia listy

Po dodaniu treści możemy teraz skonfigurować wcięcie list, używając jednego znaku spacji na poziom. W tym celu używamy klasy TxtSaveOptions i ustawiamy właściwość ListIndentation.Count na liczbę poziomów wcięć, a właściwość ListIndentation.Character na używany znak spacji. Oto jak:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

tym przykładzie tworzymy instancję TxtSaveOptions i ustawiamy właściwość ListIndentation.Count na 3, aby wskazać, że na liście są trzy poziomy wcięć. Ustawiamy także właściwość ListIndentation.Character na znak spacji („ ”), którego chcemy użyć do wcięcia.

### Przykładowy kod źródłowy funkcji „Użyj jednego znaku spacji na poziom dla wcięcia listy” w Aspose.Words dla .NET

Oto kompletny przykładowy kod źródłowy funkcji „Użyj jednego znaku spacji na poziom dla wcięcia listy” w Aspose.Words dla .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Ścieżka do katalogu dokumentów
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Utwórz dokument i dodaj treść
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Utwórz listę z trzema poziomami wcięć
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Do wcięcia listy użyj jednego znaku spacji na poziom
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Zapisz dokument z określonymi opcjami
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Wniosek

tym przewodniku wyjaśniliśmy, jak używać Aspose.Words dla .NET do zastosowania funkcji „Użyj jednego znaku spacji na poziom dla wcięcia listy”. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo skonfigurować wcięcia list w dokumentach programu Word, używając jednego znaku spacji na poziom. Aspose.Words oferuje ogromną elastyczność i możliwości przetwarzania tekstu z formatowaniem tekstu i zarządzaniem listami, umożliwiając tworzenie dokumentów o dobrze zorganizowanej strukturze w aplikacji C#.

### Często Zadawane Pytania

#### P: Co to jest Aspose.Words dla .NET?
Aspose.Words dla .NET to potężna biblioteka do tworzenia, edytowania i manipulowania dokumentami Word w aplikacji C#. Oferuje wiele funkcji do przetwarzania słów w dokumentach Word, w tym możliwość użycia jednej spacji na poziom w przypadku list wcięć.

#### P: Jak mogę użyć jednej spacji na poziom do wcięcia listy w Aspose.Words dla .NET?
Możesz użyć jednej spacji na poziom dla wcięcia listy, wykonując następujące kroki:

 Utwórz nowy dokument za pomocą`Document` klasa.

 Użyj`DocumentBuilder`class, aby dodać treść do dokumentu i utworzyć listę z wieloma poziomami wcięć.

 Po dodaniu treści i skonfigurowaniu wcięcia listy użyj opcji`TxtSaveOptions` klasę i ustaw`ListIndentation.Count` właściwość do liczby poziomów wcięcia i`ListIndentation.Character` własność przestrzeni (`' '`) używać.

 Zapisz dokument z określonymi opcjami za pomocą`Save` metoda`Document` klasa.

#### P: Czy Aspose.Words obsługuje inne znaki w przypadku wcięcia listy?
Tak, Aspose.Words obsługuje inne znaki w przypadku list wcięć. Można używać znaków innych niż białe znaki, takich jak tabulatory (`'\t'` ) lub inne znaki specjalne, ustawiając opcję`ListIndentation.Character` właściwość do żądanego znaku.

#### P: Czy można dostosować liczbę spacji na poziom dla wcięcia listy?
 Tak, możesz dostosować liczbę spacji na poziom wcięcia listy, zmieniając wartość parametru`ListIndentation.Count` nieruchomość w`TxtSaveOptions` klasa. Możesz określić liczbę spacji dla każdego poziomu wcięcia.

#### P: Jakie inne funkcje oferuje Aspose.Words do zarządzania listami?
Aspose.Words oferuje wiele funkcji do zarządzania listami w dokumentach Word. Możesz tworzyć listy numerowane lub punktowane, ustawiać poziomy wcięć, dostosowywać styl list, dodawać elementy list i nie tylko.