---
title: Utwórz nową linię podpisu i ustaw identyfikator dostawcy
linktitle: Utwórz nową linię podpisu i ustaw identyfikator dostawcy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć nową linię podpisu i ustawić identyfikator dostawcy w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji Utwórz nową linię podpisu i Ustaw identyfikator dostawcy w Aspose.Words dla .NET. Ta funkcja umożliwia wstawienie linii podpisu do dokumentu programu Word, ustawienie opcji niestandardowych i podpisanie dokumentu. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i generatora

Zacznij od utworzenia instancji klasy Document i obiektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Ustawianie opcji linii podpisu

Utwórz instancję klasy SignatureLineOptions i ustaw żądane opcje:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Krok 3: Wstawianie linii podpisu

Użyj metody InsertSignatureLine() obiektu DocumentBuilder, aby wstawić linię podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Krok 4: Ustaw identyfikator dostawcy

Ustaw identyfikator dostawcy dla linii podpisu, korzystając z właściwości ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Pamiętaj, aby podać poprawny identyfikator dostawcy dla swojego przypadku użycia.

## Krok 5: Zapisz dokument

Zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać dokument.

## Krok 6: Podpisanie dokumentu

Aby podpisać dokument należy ustawić opcje podpisu i skorzystać z klasy DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Pamiętaj, aby podać prawidłowe ścieżki dokumentu, certyfikatu i podpisanego dokumentu.

### Przykładowy kod źródłowy dla opcji Utwórz nową linię podpisu i ustaw identyfikator dostawcy za pomocą Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający utworzenie nowej linii podpisu i ustawienie identyfikatora dostawcy za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Wykonując poniższe kroki, możesz łatwo utworzyć nową linię podpisu i ustawić identyfikator dostawcy w dokumencie Word za pomocą Aspose.Words dla .NET.

## Wniosek

tym samouczku zbadaliśmy funkcję tworzenia nowej linii podpisu i ustawiania identyfikatora dostawcy w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Postępując zgodnie z podanymi krokami, możesz łatwo wstawić linię podpisu z niestandardowymi opcjami i powiązać ją z konkretnym dostawcą za pomocą identyfikatora dostawcy. Dodawanie linii podpisu i dostosowywanie informacji o dostawcy zwiększa autentyczność i wiarygodność Twoich dokumentów. Aspose.Words dla .NET zapewnia potężny interfejs API do przetwarzania słów z liniami podpisu i certyfikatami cyfrowymi w dokumentach Word, umożliwiając automatyzację procesu podpisywania i zapewniając ważność dokumentów.

### Często zadawane pytania

#### P: Co to jest identyfikator dostawcy w linii podpisu?

Odpowiedź: Identyfikator dostawcy w wierszu podpisu to unikalny identyfikator reprezentujący dostawcę podpisu cyfrowego. Pomaga zidentyfikować źródło lub organizację odpowiedzialną za podpis.

#### P: Jak mogę utworzyć nową linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby utworzyć nową linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz instancję`Document` klasa i A`DocumentBuilder` obiekt.
2.  Utwórz instancję`SignatureLineOptions` class i ustaw żądane opcje linii podpisu.
3.  Użyj`InsertSignatureLine` metoda`DocumentBuilder` obiekt, aby wstawić linię podpisu do dokumentu.

#### P: Czy mogę dostosować opcje linii podpisu, takie jak imię i nazwisko osoby podpisującej, stanowisko i instrukcje?

 Odp.: Tak, możesz dostosować opcje linii podpisu. The`SignatureLineOptions` class udostępnia właściwości umożliwiające ustawienie żądanych opcji, takich jak`Signer`, `SignerTitle`, `Instructions`, `AllowComments`itp. Możesz modyfikować te właściwości przed wstawieniem linii podpisu.

#### P: Jaki jest cel ustawienia identyfikatora dostawcy dla linii podpisu?

O: Ustawienie identyfikatora dostawcy dla linii podpisu pomaga zidentyfikować źródło lub organizację odpowiedzialną za podpis cyfrowy. Umożliwia powiązanie podpisu z konkretnym dostawcą lub podmiotem, dostarczając dodatkowych informacji o pochodzeniu i wiarygodności podpisu.

#### P: Jak mogę ustawić identyfikator dostawcy dla linii podpisu za pomocą Aspose.Words dla .NET?

Odp.: Aby ustawić identyfikator dostawcy dla linii podpisu za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Po wstawieniu linii podpisu uzyskaj dostęp do`ProviderId` własność`SignatureLine` obiekt.
2.  Ustaw`ProviderId` właściwość na żądaną wartość identyfikatora dostawcy przy użyciu metody`Guid` typ danych.

#### P: Czy mogę podpisać dokument po utworzeniu nowej linii podpisu i ustawieniu identyfikatora dostawcy?

 Odp.: Tak, po utworzeniu nowej linii podpisu i ustawieniu ID dostawcy możesz podpisać dokument. Aby podpisać dokument, musisz ustawić opcje podpisu, w tym identyfikator linii podpisu, identyfikator dostawcy, komentarze i godzinę podpisania. Następnie skorzystaj z`DigitalSignatureUtil.Sign` metoda podpisania dokumentu za pomocą certyfikatu cyfrowego.

#### P: Czy mogę określić konkretny identyfikator dostawcy dla każdej linii podpisu w dokumencie programu Word?

Odpowiedź: Tak, możesz określić konkretny identyfikator dostawcy dla każdej linii podpisu w dokumencie programu Word. Po wstawieniu każdej linii podpisu możesz ustawić identyfikator dostawcy dla tej konkretnej linii podpisu, uzyskując dostęp do`ProviderId` własność danego`SignatureLine` obiekt.

#### P: Jak mogę zapisać zmodyfikowany dokument po utworzeniu nowej linii podpisu i ustawieniu identyfikatora dostawcy?

 O: Aby zapisać zmodyfikowany dokument po utworzeniu nowej linii podpisu i ustawieniu identyfikatora dostawcy, możesz skorzystać z opcji`Save` metoda`Document` obiekt. Podaj poprawną ścieżkę i nazwę pliku, aby zapisać dokument.

#### P: Jaki format pliku obsługuje Aspose.Words dla .NET do tworzenia i podpisywania linii podpisu?

Odp.: Aspose.Words dla .NET obsługuje tworzenie i podpisywanie linii podpisu w formacie pliku DOCX. Możesz tworzyć i podpisywać linie podpisu w plikach DOCX, korzystając z dostarczonych metod i klas.

#### P: Czy mogę zmodyfikować identyfikator dostawcy lub inne opcje linii podpisu po jego podpisaniu?

Odpowiedź: Po podpisaniu linia podpisu staje się częścią treści dokumentu i nie można jej oddzielnie modyfikować. Wszelkie modyfikacje linii podpisu, takie jak zmiana identyfikatora dostawcy lub innych opcji, wymagałyby usunięcia istniejącego podpisu i utworzenia nowej linii podpisu.