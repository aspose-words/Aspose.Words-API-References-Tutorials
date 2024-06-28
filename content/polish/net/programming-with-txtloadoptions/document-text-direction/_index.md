---
title: Kierunek tekstu dokumentu
linktitle: Kierunek tekstu dokumentu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak określić kierunek tekstu w dokumentach za pomocą Aspose.Words dla .NET. Poprawiono wyświetlanie języków pisanych od prawej do lewej.
type: docs
weight: 10
url: /pl/net/programming-with-txtloadoptions/document-text-direction/
---

tym samouczku przyjrzymy się kodowi źródłowemu C# udostępnionemu dla funkcji „Kierunek tekstu dokumentu” w Aspose.Words dla .NET. Ta funkcja pozwala określić kierunek tekstu w dokumencie, co jest szczególnie przydatne w przypadku języków pisanych od prawej do lewej, takich jak hebrajski czy arabski.

## Krok 1: Konfigurowanie środowiska

Zanim zaczniesz, upewnij się, że skonfigurowałeś środowisko programistyczne za pomocą Aspose.Words dla .NET. Upewnij się, że dodałeś niezbędne odniesienia i zaimportowałeś odpowiednie przestrzenie nazw.

## Krok 2: Konfiguracja opcji przesyłania

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 W tym kroku konfigurujemy opcje ładowania dokumentu. Tworzymy nowe`TxtLoadOptions` obiekt i ustaw`DocumentDirection`własność do`DocumentDirection.Auto`. Ta wartość mówi Aspose.Words, aby automatycznie określił kierunek tekstu na podstawie zawartości dokumentu.

## Krok 3: Załaduj dokument

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 W tym kroku ładujemy dokument za pomocą`Document` metodę i przekazanie ścieżki do pliku tekstowego do załadowania. Korzystamy również z określonych opcji ładowania.

## Krok 4: Manipuluj akapitem i wyświetl kierunek tekstu

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Na tym etapie uzyskujemy dostęp do pierwszego akapitu dokumentu za pomocą`FirstSection` I`Body` nieruchomości. Następnie uzyskujemy dostęp do`ParagraphFormat.Bidi` właściwość, aby uzyskać kierunek tekstu akapitu. Następnie wyświetlamy tę wartość w konsoli.

## Krok 5: Zapisz dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 W tym ostatnim kroku zapisujemy powstały dokument w formacie .docx za pomocą`Save` metodę i przekazanie ścieżki do pliku wyjściowego.

Teraz możesz uruchomić kod źródłowy, aby załadować dokument tekstowy i określić kierunek tekstu. Powstały dokument zostanie zapisany w określonym katalogu pod nazwą „WorkingWithTxtLoadOptions.DocumentTextDirection.docx”.

### Przykładowy kod źródłowy funkcji kierunku tekstu dokumentu w Aspose.Words dla .NET.


```csharp

            
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Wniosek

W tym samouczku omówiliśmy funkcję kierunku tekstu dokumentu w Aspose.Words dla .NET. Dowiedzieliśmy się, jak określić kierunek tekstu w dokumencie, szczególnie w przypadku języków pisanych od prawej do lewej, takich jak hebrajski czy arabski.

Ta funkcja jest niezbędna, aby zapewnić prawidłowe wyświetlanie tekstu w dokumentach wielojęzycznych. Korzystając z odpowiednich opcji ładowania, Aspose.Words może automatycznie wykryć kierunek tekstu i zastosować go do dokumentu.

Dzięki Aspose.Words możesz łatwo manipulować kierunkiem tekstu w dokumentach, zapewniając użytkownikom płynne i intuicyjne czytanie.

Należy zauważyć, że ta funkcja jest szczególnie przydatna podczas przetwarzania słów w językach wymagających określonego kierunku tekstu. Aspose.Words ułatwia to zadanie, udostępniając potężne narzędzia do zarządzania kierunkiem tekstu w dokumentach.

Pamiętaj, aby użyć odpowiednich opcji ładowania, takich jak ustawienie automatycznego kierunku tekstu, aby uzyskać oczekiwane rezultaty w swoich dokumentach.

Aspose.Words dla .NET oferuje wiele zaawansowanych funkcji do manipulowania i generowania dokumentów. Dalsze zapoznawanie się z dokumentacją i przykładami dostarczonymi przez Aspose.Words umożliwi pełne wykorzystanie możliwości tej potężnej biblioteki.

Nie wahaj się więc zintegrować kierunku tekstu dokumentu z projektami Aspose.Words for .NET i skorzystaj z jego zalet, aby stworzyć atrakcyjne i wysokiej jakości wielojęzyczne dokumenty.