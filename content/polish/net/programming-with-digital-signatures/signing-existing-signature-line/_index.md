---
title: Podpisywanie istniejącej linii podpisu w dokumencie programu Word
linktitle: Podpisywanie istniejącej linii podpisu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak podpisać istniejącą linię podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/signing-existing-signature-line/
---
W tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji podpisu istniejącej linii podpisu w Aspose.Words dla .NET. Ta funkcja umożliwia cyfrowe podpisanie linii podpisu już znajdującej się w dokumencie programu Word. Wykonaj poniższe kroki:

## Krok 1: Załadowanie dokumentu i dostęp do linii podpisu

Zacznij od przesłania dokumentu zawierającego istniejącą linię podpisu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Krok 2: Ustawianie opcji podpisu

Utwórz instancję klasy SignOptions i ustaw opcje podpisu, w tym identyfikator linii podpisu i obraz linii podpisu:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Pamiętaj, aby określić poprawną ścieżkę do obrazu linii podpisu.

## Krok 3: Ładowanie certyfikatu

Zacznij od załadowania certyfikatu podpisującego przy użyciu klasy CertyfikatHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Pamiętaj, aby podać poprawną ścieżkę do certyfikatu i powiązanego hasła.

## Krok 4: Podpisanie istniejącej linii podpisu

Użyj klasy DigitalSignatureUtil, aby podpisać istniejącą linię podpisu:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Pamiętaj, aby określić prawidłowe ścieżki dokumentu źródłowego, podpisanego dokumentu i certyfikatu.

### Przykładowy kod źródłowy do podpisywania istniejącej linii podpisu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do podpisania istniejącej linii podpisu za pomocą Aspose.Words dla .NET:


```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Wykonując poniższe kroki, możesz łatwo podpisać istniejącą linię podpisu w dokumencie Word za pomocą Aspose.Words dla .NET.

## Wniosek

tym samouczku nauczyliśmy się, jak podpisywać istniejącą linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wykonując podane kroki, możesz łatwo załadować dokument, uzyskać dostęp do istniejącej linii podpisu, ustawić opcje podpisywania i podpisać dokument. Możliwość podpisania istniejącej linii podpisu zapewnia wygodny sposób dodawania podpisów cyfrowych do wcześniej zdefiniowanych obszarów w dokumentach programu Word, zapewniając integralność i uwierzytelnianie dokumentu. Aspose.Words dla .NET oferuje potężny interfejs API do przetwarzania tekstu z podpisami cyfrowymi, umożliwiając dostosowanie procesu podpisywania i zwiększenie bezpieczeństwa dokumentów programu Word.

### Często zadawane pytania

#### P: Co to jest istniejąca linia podpisu w dokumencie programu Word?

Odpowiedź: Istniejąca linia podpisu w dokumencie programu Word to wstępnie zdefiniowany obszar, w którym można umieścić podpis. Zwykle jest reprezentowany w dokumencie przez kształt lub obiekt i służy jako wyznaczone miejsce, w którym osoba podpisująca może dodać swój podpis cyfrowy.

#### P: Jak mogę podpisać istniejącą linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby podpisać istniejącą linię podpisu w dokumencie Word przy użyciu Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Załaduj dokument za pomocą`Document` class i określ ścieżkę do pliku dokumentu.
2.  Uzyskaj dostęp do istniejącej linii podpisu, korzystając z odpowiedniej metody lub właściwości. Możesz na przykład użyć`GetChild` metoda pobierania kształtu linii podpisu.
3.  Utwórz instancję`SignOptions` klasę i ustaw`SignatureLineId` właściwość na identyfikator istniejącej linii podpisu.
4.  Ustaw`SignatureLineImage` własność`SignOptions` class do obrazu przedstawiającego podpis cyfrowy.
5.  Załaduj certyfikat podpisywania za pomocą pliku`CertificateHolder` class i podaj niezbędny certyfikat i hasło.
6.  Użyj`DigitalSignatureUtil.Sign` sposób podpisania dokumentu, podając niezbędne parametry m.in`SignOptions` obiekt.

#### P: Jak uzyskać dostęp do istniejącej linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 O: Aby uzyskać dostęp do istniejącej linii podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz użyć odpowiedniej metody lub właściwości w celu pobrania kształtu linii podpisu ze struktury dokumentu. Można na przykład użyć`GetChild` metodę z odpowiednimi parametrami, aby uzyskać pożądany kształt linii podpisu.

#### P: Czy mogę dostosować wygląd podpisu cyfrowego w istniejącej linii podpisu?

O: Tak, możesz dostosować wygląd podpisu cyfrowego w istniejącej linii podpisu, dostarczając plik obrazu reprezentujący podpis. Obrazem może być logo, podpis odręczny lub inna graficzna reprezentacja podpisu. Możesz ustawić`SignatureLineImage` własność`SignOptions` class do bajtów pliku obrazu.

#### P: Czy mogę podpisać wiele istniejących linii podpisu w dokumencie programu Word?
 Odp.: Tak, możesz podpisać wiele istniejących linii podpisu w dokumencie programu Word. Musisz postępować zgodnie z instrukcjami dla każdej linii podpisu indywidualnie, ustawiając odpowiednie`SignatureLineId` I`SignatureLineImage` wartości w`SignOptions` obiekt dla każdej linii podpisu.

#### P: Jaki format powinien mieć plik obrazu dla podpisu cyfrowego w istniejącej linii podpisu?

 Odp.: Plik obrazu podpisu cyfrowego w istniejącej linii podpisu może mieć różne formaty, takie jak PNG, JPEG, BMP lub GIF. Możesz określić ścieżkę pliku lub odczytać bajty pliku obrazu i przypisać go do`SignatureLineImage` własność`SignOptions` klasa.
