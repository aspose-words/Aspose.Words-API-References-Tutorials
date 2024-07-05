---
title: Osadź podzbiór czcionek w dokumencie PDF
linktitle: Osadź podzbiór czcionek w dokumencie PDF
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący osadzania podzbiorów czcionek w dokumencie PDF przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z funkcji osadzania podzbioru czcionek w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz w stanie zrozumieć, jak osadzać podzbiory czcionek w dokumencie i generować plik PDF zawierający tylko glify użyte w dokumencie.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Na początek musisz zdefiniować ścieżkę do katalogu, w którym znajdują się Twoje dokumenty. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Prześlij dokument

Następnie musimy załadować dokument, który chcemy przetworzyć. W tym przykładzie zakładamy, że dokument nazywa się „Rendering.docx” i znajduje się w określonym katalogu dokumentów.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Skonfiguruj opcje zapisywania jako PDF

 Aby utworzyć plik PDF zawierający tylko podzbiory czcionek używanych w dokumencie, musimy skonfigurować`PdfSaveOptions` obiekt z`EmbedFullFonts` właściwość ustawiona na`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Krok 4: Zapisz dokument jako plik PDF z podzestawami czcionek

 Wreszcie możemy zapisać dokument jako plik PDF, korzystając z podzbiorów czcionek. Określ nazwę pliku wyjściowego i`saveOptions` obiekt, który skonfigurowaliśmy w poprzednim kroku.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

To wszystko ! Pomyślnie osadziłeś podzestawy czcionek w dokumencie i wygenerowałeś plik PDF zawierający tylko glify użyte w dokumencie za pomocą Aspose.Words dla .NET.

### Przykładowy kod źródłowy do osadzania podzbiorów czcionek w Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Wyjściowy plik PDF będzie zawierał podzbiory czcionek w dokumencie.
	// Czcionki PDF uwzględniają wyłącznie glify użyte w dokumencie.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Wniosek

W tym samouczku nauczyliśmy się, jak osadzać podzbiory czcionek w dokumencie PDF za pomocą Aspose.Words dla .NET. Osadzanie podzbiorów czcionek pomaga zmniejszyć rozmiar pliku PDF, zachowując jednocześnie wygląd dokumentu poprzez użycie tylko faktycznie używanych znaków. Zapewnia to lepszą kompatybilność i wydajność podczas przeglądania i drukowania plików PDF. Zachęcamy do dalszego odkrywania funkcji Aspose.Words dla .NET w celu optymalizacji generowania dokumentów PDF z osadzonymi podzbiorami czcionek.

### Często Zadawane Pytania

#### P: Na czym polega osadzanie podzbiorów czcionek w dokumencie PDF?
O: Osadzanie podzbiorów czcionek w dokumencie PDF polega na dołączaniu jedynie glifów użytych w dokumencie, a nie wszystkich pełnych czcionek. Zmniejsza to rozmiar pliku PDF, włączając tylko dane czcionki niezbędne do wyświetlenia znaków faktycznie używanych w dokumencie.

#### P: Jaka jest różnica pomiędzy osadzaniem pełnych czcionek a osadzaniem podzbiorów czcionek?
Odp.: Pełne osadzanie czcionek oznacza włączenie wszystkich czcionek użytych w dokumencie w pliku PDF, co gwarantuje, że dokument będzie wyświetlany dokładnie tak, jak został zaprojektowany, ale może zwiększyć rozmiar pliku PDF. Natomiast osadzanie podzbiorów czcionek zawiera tylko glify użyte w dokumencie, zmniejszając w ten sposób rozmiar pliku PDF, ale ograniczając możliwość dokładnego odtworzenia wyglądu dokumentu w przypadku późniejszego dodania dodatkowych znaków.

#### P: Jak mogę osadzić podzbiory czcionek w dokumencie PDF przy użyciu Aspose.Words dla .NET?
O: Aby osadzić podzbiory czcionek w dokumencie PDF za pomocą Aspose.Words dla .NET, wykonaj następujące kroki:

 Ustaw ścieżkę katalogu dokumentu, zastępując`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

 Załaduj dokument, który chcesz przetworzyć za pomocą`Document` klasa i ścieżka dokumentu.

 Skonfiguruj opcje zapisywania plików PDF, tworząc instancję pliku`PdfSaveOptions` klasę i ustawienie`EmbedFullFonts`własność do`false`Dzięki temu w pliku PDF zostaną uwzględnione tylko podzbiory czcionek użyte w dokumencie.

 Zapisz dokument w formacie PDF z osadzonymi podzestawami czcionek, korzystając z pliku`Save` metoda`Document` obiektu, podając nazwę pliku wyjściowego i skonfigurowane wcześniej opcje zapisu.

#### P: Jakie są korzyści z osadzania podzbiorów czcionek w dokumencie PDF?
O: Korzyści z osadzania podzbiorów czcionek w dokumencie PDF są następujące:

Zmniejszony rozmiar pliku PDF: uwzględnienie tylko glifów używanych w dokumencie powoduje zmniejszenie rozmiaru pliku PDF w porównaniu do osadzania pełnych czcionek.

Zachowanie wyglądu dokumentu: Podzbiory czcionek zawarte w pliku PDF umożliwiają odtworzenie wyglądu dokumentu przy użyciu wyłącznie faktycznie używanych znaków.

Zgodność z ograniczeniami Licencji: Osadzanie podzbiorów czcionek może być preferowane w przypadkach, gdy pełne czcionki nie mogą być legalnie osadzone ze względu na ograniczenia licencyjne.