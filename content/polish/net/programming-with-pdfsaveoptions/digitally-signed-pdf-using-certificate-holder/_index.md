---
title: Dodaj podpis cyfrowy do pliku PDF za pomocą posiadacza certyfikatu
linktitle: Dodaj podpis cyfrowy do pliku PDF za pomocą posiadacza certyfikatu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dodać podpis cyfrowy do pliku PDF za pomocą posiadacza certyfikatu w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

W tym samouczku przeprowadzimy Cię przez kolejne etapy dodawania podpisu cyfrowego do pliku PDF przy użyciu posiadacza certyfikatu w Aspose.Words dla .NET. Podpis cyfrowy dodaje warstwę bezpieczeństwa i integralności do dokumentu PDF. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i dodanie treści

Zacznij od utworzenia instancji klasy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Dodaj treść do dokumentu

 Następnie użyj`DocumentBuilder`aby dodać treść do dokumentu. Na przykład, aby dodać akapit zawierający tekst „Testuj podpisany plik PDF”, użyj rozszerzenia`Writeln` metoda:

```csharp
builder.Writeln("Test Signed PDF.");
```

W razie potrzeby możesz dodać inne elementy treści.

## Krok 3: Ustaw opcje zapisywania plików PDF

Utwórz instancję klasy PdfSaveOptions i podaj szczegóły podpisu cyfrowego:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Pamiętaj, aby podać poprawną ścieżkę do certyfikatu i powiązanego hasła. Możesz także dostosować powód i lokalizację podpisu.

## Krok 4: Zapisz dokument jako plik PDF podpisany cyfrowo

 Użyj`Save` metoda zapisania dokumentu w formacie PDF poprzez określenie opcji zapisywania:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Upewnij się, że określono poprawną ścieżkę do zapisania cyfrowo podpisanego pliku PDF.

Wykonując poniższe kroki, możesz łatwo utworzyć podpisany cyfrowo plik PDF z certyfikatem przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla cyfrowo podpisanego pliku PDF przy użyciu posiadacza certyfikatu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy podpisanego cyfrowo pliku PDF przy użyciu posiadacza certyfikatu z dokumentu przy użyciu Aspose.Words dla .NET:

```csharp

            // Ścieżka do katalogu dokumentów.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Wniosek

tym samouczku omówiliśmy kroki dodawania podpisu cyfrowego do dokumentu PDF przy użyciu certyfikatu w Aspose.Words dla .NET. Podpis cyfrowy dodaje do dokumentu warstwę bezpieczeństwa i integralności, gwarantując tym samym jego autentyczność i umożliwiając wykrycie wszelkich późniejszych modyfikacji. Wykonując podane kroki, możesz łatwo utworzyć podpisany cyfrowo plik PDF przy użyciu certyfikatu w Aspose.Words dla .NET.

### Często Zadawane Pytania

#### P: Co to jest podpis cyfrowy i dlaczego jest ważny w dokumencie PDF?
Odp.: Podpis cyfrowy to technika zabezpieczeń, która pomaga zapewnić autentyczność, integralność i niezaprzeczalność dokumentu elektronicznego, takiego jak plik PDF. Wykorzystuje certyfikat cyfrowy, aby dodać warstwę zabezpieczeń do dokumentu, co pomaga zweryfikować tożsamość autora i wykryć wszelkie późniejsze zmiany w treści.

#### P: Jak mogę dodać podpis cyfrowy do dokumentu PDF przy użyciu certyfikatu w Aspose.Words dla .NET?
Odp.: Aby dodać podpis cyfrowy do dokumentu PDF przy użyciu certyfikatu w Aspose.Words dla .NET, wykonaj następujące kroki:

 Utwórz instancję`Document` klasa reprezentująca dokument.

 Użyj`DocumentBuilder` class, aby dodać żądaną treść do dokumentu.

 Utwórz instancję`PdfSaveOptions` class i określ szczegóły podpisu cyfrowego za pomocą`PdfDigitalSignatureDetails` klasa. Będziesz musiał podać ścieżkę do certyfikatu (`CertificateHolder.Create`), powiązane hasło oraz powód i lokalizację podpisania.

 Użyj`Save` metodę zapisania dokumentu w formacie PDF określając opcje zapisu.

#### P: Jak uzyskać certyfikat umożliwiający dodanie podpisu cyfrowego do dokumentu PDF?
O: Aby uzyskać certyfikat umożliwiający dodanie podpisu cyfrowego do dokumentu PDF, zazwyczaj można skontaktować się z urzędem certyfikacji (CA) lub dostawcą usług zaufania. Podmioty te wydają certyfikaty cyfrowe po zweryfikowaniu Twojej tożsamości i zatwierdzeniu Twojego żądania. Po uzyskaniu certyfikatu możesz go użyć w swojej aplikacji do dodawania podpisów cyfrowych do dokumentów PDF.

#### P: Czy można dostosować szczegóły podpisu cyfrowego, takie jak powód i lokalizacja?
 Odpowiedź: Tak, możesz dostosować szczegóły podpisu cyfrowego, podając przyczynę i lokalizację podpisu. W podanym przykładowym kodzie możesz modyfikować wartości pliku`reason` I`location` parametry podczas tworzenia pliku`PdfDigitalSignatureDetails` obiekt. Pamiętaj, aby podać odpowiednie informacje dla każdego parametru, aby odzwierciedlić przyczynę i lokalizację podpisu w dokumencie PDF.