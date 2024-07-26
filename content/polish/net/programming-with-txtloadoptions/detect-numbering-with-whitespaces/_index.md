---
title: Wykryj numerację ze spacjami
linktitle: Wykryj numerację ze spacjami
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wykrywać numery list ze spacjami w Aspose.Words dla .NET. Z łatwością poprawiaj strukturę swoich dokumentów.
type: docs
weight: 10
url: /pl/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
tym samouczku przyjrzymy się kodowi źródłowemu C# udostępnionemu dla funkcji „Wykrywanie numeracji ze spacjami” w Aspose.Words dla .NET. Ta funkcja umożliwia wykrywanie i tworzenie list na podstawie dokumentu tekstowego zawierającego numery list, po których następują białe znaki.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne za pomocą Aspose.Words dla .NET. Upewnij się, że dodałeś niezbędne odniesienia i zaimportowałeś odpowiednie przestrzenie nazw.

## Krok 2: Tworzenie dokumentu tekstowego

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Na tym etapie tworzymy ciąg tekstowy symulujący dokument tekstowy zawierający numery list, po których następują białe spacje. Używamy różnych ograniczników list, takich jak kropka, prawy nawias, symbol punktora i białe spacje.

## Krok 3: Konfiguracja opcji przesyłania

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 W tym kroku konfigurujemy opcje ładowania dokumentu. Tworzymy nowe`TxtLoadOptions` obiekt i ustaw`DetectNumberingWithWhitespaces`własność do`true`. Umożliwi to Aspose.Words wykrywanie numerów list, nawet jeśli następują po nich białe spacje.

## Krok 4: Załaduj dokument i zapisz

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 W tym kroku ładujemy dokument przy użyciu określonego ciągu tekstowego i opcji ładowania. Używamy A`MemoryStream` do konwersji ciągu tekstowego na strumień pamięci. Następnie zapisujemy powstały dokument w formacie .docx.

### Przykładowy kod źródłowy funkcji wykrywania numerowania białych znaków w Aspose.Words dla .NET.

```csharp

            
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Utwórz dokument w postaci zwykłego tekstu w postaci ciągu znaków z częściami, które można interpretować jako listy.
// Po załadowaniu pierwsze trzy listy będą zawsze wykrywane przez Aspose.Words,
// i Listy zostaną dla nich utworzone po załadowaniu.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Czwarta lista, ze spacjami pomiędzy numerem listy a zawartością elementu listy,
// zostanie wykryty jako lista tylko wtedy, gdy „DetectNumberingWithWhitespaces” w obiekcie LoadOptions ma wartość true,
// aby uniknąć omyłkowego rozpoznania akapitów rozpoczynających się od liczb jako list.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Załaduj dokument, stosując LoadOptions jako parametr i sprawdź wynik.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Teraz możesz uruchomić kod źródłowy, aby załadować dokument tekstowy zawierający numery list ze spacjami, a następnie utworzyć dokument .docx z wykrytymi listami. Plik wyjściowy zostanie zapisany w określonym katalogu pod nazwą „WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx”.

## Wniosek
W tym samouczku omówiliśmy funkcję wykrywania numerowania białych znaków w Aspose.Words dla .NET. Dowiedzieliśmy się, jak tworzyć listy z dokumentu tekstowego zawierającego numery list, po których następują białe spacje.

Funkcja ta jest niezwykle przydatna przy przetwarzaniu dokumentów zawierających numery list sformatowane na różne sposoby. Używając odpowiednich opcji ładowania, Aspose.Words jest w stanie wykryć te numery list, nawet jeśli następują po nich białe spacje, i przekonwertować je na uporządkowane listy w dokumencie końcowym.

Korzystanie z tej funkcji może zaoszczędzić czas i poprawić efektywność przepływu pracy. Możesz łatwo wyodrębnić informacje z dokumentów tekstowych i przekształcić je w dokumenty o dobrze zorganizowanej strukturze z odpowiednimi listami.

Pamiętaj, aby wziąć pod uwagę opcje ładowania, takie jak skonfigurowanie wykrywania wybierania białych znaków, aby osiągnąć pożądane wyniki.

Aspose.Words dla .NET oferuje wiele zaawansowanych funkcji do manipulowania i generowania dokumentów. Dalsze zapoznawanie się z dokumentacją i przykładami dostarczonymi przez Aspose.Words umożliwi pełne wykorzystanie możliwości tej potężnej biblioteki.

Nie wahaj się zatem zintegrować wykrywania numerowania białych znaków ze swoimi projektami Aspose.Words for .NET i skorzystaj z jego zalet, aby tworzyć dobrze zorganizowane i czytelne dokumenty.


