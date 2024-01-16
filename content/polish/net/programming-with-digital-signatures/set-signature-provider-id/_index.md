---
title: Ustaw identyfikator dostawcy podpisu w dokumencie programu Word
linktitle: Ustaw identyfikator dostawcy podpisu w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić identyfikator dostawcy podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/set-signature-provider-id/
---
W tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji Ustaw identyfikator dostawcy podpisu w Aspose.Words dla .NET. Ta funkcja umożliwia określenie identyfikatora dostawcy podpisu dla linii podpisu w dokumencie programu Word. Wykonaj poniższe kroki:

## Krok 1: Załadowanie dokumentu i dostęp do linii podpisu

Zacznij od przesłania dokumentu zawierającego linię podpisu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Krok 2: Ustawianie opcji podpisu

Utwórz instancję klasy SignOptions i ustaw opcje podpisywania, w tym identyfikator dostawcy:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Krok 3: Podpisanie dokumentu

Aby podpisać dokument należy skorzystać z klasy DigitalSignatureUtil i określić certyfikat podpisujący:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Pamiętaj, aby podać prawidłowe ścieżki dokumentu, certyfikatu i podpisanego dokumentu.

### Przykładowy kod źródłowy dla Ustaw identyfikator dostawcy podpisu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający ustawienie identyfikatora dostawcy podpisu za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Dokończ identyfikator dostawcy podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET.


## Wniosek

tym samouczku nauczyliśmy się, jak ustawić identyfikator dostawcy podpisu dla linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wykonując podane kroki, możesz łatwo załadować dokument, uzyskać dostęp do linii podpisu, ustawić identyfikator dostawcy i podpisać dokument. Możliwość ustawienia identyfikatora dostawcy podpisu pomaga ustalić tożsamość i wiarygodność osoby podpisującej, zwiększając bezpieczeństwo i integralność dokumentów programu Word. Aspose.Words dla .NET zapewnia solidne API do przetwarzania słów z podpisami cyfrowymi, umożliwiając łatwe dostosowywanie i zarządzanie procesem podpisywania.

### Często zadawane pytania dotyczące ustawiania identyfikatora dostawcy podpisu w dokumencie programu Word

#### P: Co to jest identyfikator dostawcy podpisu w dokumencie programu Word?

Odp.: Identyfikator dostawcy podpisu w dokumencie programu Word to unikalny identyfikator określający dostawcę podpisu cyfrowego. Pomaga zidentyfikować podmiot lub organizację odpowiedzialną za tworzenie podpisu cyfrowego i zarządzanie nim.

#### P: Jak mogę ustawić identyfikator dostawcy podpisu dla linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby ustawić identyfikator dostawcy podpisu dla linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Załaduj dokument za pomocą`Document` class i określ ścieżkę do pliku dokumentu.
2.  Uzyskaj dostęp do linii podpisu, korzystając z odpowiedniej metody lub właściwości. Możesz na przykład użyć`GetChild` metoda pobierania kształtu linii podpisu.
3. Pobierz identyfikator dostawcy z linii podpisu.
4.  Utwórz instancję`SignOptions` klasę i ustaw`ProviderId` właściwość na pobrany identyfikator dostawcy.
5.  Użyj`DigitalSignatureUtil.Sign` sposób podpisania dokumentu, podając niezbędne parametry m.in`SignOptions` obiekt.

#### P: Jak uzyskać dostęp do linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby uzyskać dostęp do linii podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz użyć odpowiedniej metody lub właściwości w celu pobrania kształtu linii podpisu ze struktury dokumentu. Można na przykład użyć`GetChild` metodę z odpowiednimi parametrami, aby uzyskać pożądany kształt linii podpisu.

#### P: Czy mogę ustawić identyfikator dostawcy podpisu dla wielu wierszy podpisu w dokumencie programu Word?

 O: Tak, możesz ustawić identyfikator dostawcy podpisu dla wielu wierszy podpisu w dokumencie programu Word. Możesz przeglądać kolekcję linii podpisu w dokumencie i ustawić identyfikator dostawcy dla każdej linii podpisu indywidualnie, korzystając z opcji`SignOptions.ProviderId` nieruchomość.

#### P: Jaki jest cel identyfikatora dostawcy podpisu w dokumencie programu Word?

Odpowiedź: Identyfikator dostawcy podpisu w dokumencie programu Word służy do identyfikacji podmiotu lub organizacji odpowiedzialnej za tworzenie podpisu cyfrowego i zarządzanie nim. Pomaga ustalić autentyczność i wiarygodność podpisu cyfrowego poprzez powiązanie go z konkretnym dostawcą.

#### P: Jakiego typu certyfikatów cyfrowych można użyć do ustawienia identyfikatora dostawcy podpisu w dokumencie programu Word?

Odp.: Możesz użyć certyfikatów cyfrowych X.509 z odpowiednimi informacjami o dostawcy, aby ustawić identyfikator dostawcy podpisu w dokumencie programu Word. Certyfikat cyfrowy powinien być wystawiony przez zaufany urząd certyfikacji (CA) i zawierać metadane niezbędne do identyfikacji dostawcy.