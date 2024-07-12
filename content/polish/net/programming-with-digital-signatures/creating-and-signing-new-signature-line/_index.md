---
title: Tworzenie i podpisywanie nowej linii podpisu
linktitle: Tworzenie i podpisywanie nowej linii podpisu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć i podpisać cyfrowo linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET, korzystając z tego samouczka krok po kroku. Idealny do automatyzacji dokumentów.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Wstęp

No hej! Masz więc dokument Word i musisz dodać linię podpisu, a następnie podpisać go cyfrowo. Brzmi trudne? Zupełnie nie! Dzięki Aspose.Words dla .NET możesz to osiągnąć bezproblemowo za pomocą zaledwie kilku linijek kodu. W tym samouczku przeprowadzimy Cię przez cały proces, od skonfigurowania środowiska po zapisanie dokumentu z nowym, błyszczącym podpisem. Gotowy? Zanurzmy się!

## Warunki wstępne

Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz:
1.  Aspose.Words dla .NET - Możesz[Pobierz to tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne .NET — zdecydowanie zaleca się program Visual Studio.
3. Dokument do podpisania — utwórz prosty dokument Word lub użyj istniejącego.
4.  Plik certyfikatu — jest potrzebny w przypadku podpisów cyfrowych. Możesz użyć A`.pfx` plik.
5. Obrazy do linii podpisu — opcjonalnie plik obrazu do podpisu.

## Importuj przestrzenie nazw

Najpierw musimy zaimportować niezbędne przestrzenie nazw. Ten krok jest kluczowy, ponieważ konfiguruje środowisko do korzystania z funkcjonalności Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Krok 1: Konfigurowanie katalogu dokumentów

Każdy projekt wymaga dobrego początku. Ustawmy ścieżkę do katalogu dokumentów. Tutaj będą zapisywane i pobierane Twoje dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Tworzenie nowego dokumentu

Teraz utwórzmy nowy dokument programu Word przy użyciu Aspose.Words. To będzie nasze płótno, na którym dodamy linię podpisu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Wstawianie linii podpisu

 To tutaj dzieje się magia. Wstawiamy linię podpisu do naszego dokumentu za pomocą`DocumentBuilder` klasa.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Krok 4: Zapisywanie dokumentu z linią podpisu

Gdy linia podpisu jest już na swoim miejscu, musimy zapisać dokument. Jest to etap pośredni przed przystąpieniem do jego podpisania.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Krok 5: Konfigurowanie opcji podpisywania

Teraz skonfigurujmy opcje podpisywania dokumentu. Obejmuje to określenie identyfikatora linii podpisu i obrazu, który ma zostać użyty.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Krok 6: Ładowanie certyfikatu

Podpisy cyfrowe wymagają certyfikatu. Tutaj ładujemy plik certyfikatu, który posłuży do podpisania dokumentu.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Krok 7: Podpisanie dokumentu

 To jest ostatni krok. Używamy`DigitalSignatureUtil`klasie do podpisania dokumentu. Podpisany dokument zostanie zapisany pod nową nazwą.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Wniosek

I masz to! Wykonując te kroki, pomyślnie utworzyłeś nowy dokument Word, dodałeś linię podpisu i podpisałeś go cyfrowo za pomocą Aspose.Words dla .NET. To potężne narzędzie, dzięki któremu automatyzacja dokumentów jest dziecinnie prosta. Niezależnie od tego, czy masz do czynienia z umowami, porozumieniami czy jakimikolwiek formalnymi dokumentami, ta metoda zapewnia ich bezpieczne podpisanie i uwierzytelnienie.

## Często zadawane pytania

### Czy mogę użyć innych formatów obrazu w linii podpisu?
Tak, możesz używać różnych formatów obrazów, takich jak PNG, JPG, BMP itp.

###  Czy konieczne jest użycie tzw`.pfx` file for the certificate?
 Tak`.pfx` plik to powszechny format przechowywania informacji kryptograficznych, w tym certyfikatów i kluczy prywatnych.

### Czy mogę dodać wiele linii podpisu w jednym dokumencie?
Absolutnie! Można wstawić wiele wierszy podpisu, powtarzając krok wstawiania dla każdego podpisu.

### Co się stanie, jeśli nie mam certyfikatu cyfrowego?
Będziesz musiał uzyskać certyfikat cyfrowy od zaufanego urzędu certyfikacji lub wygenerować go za pomocą narzędzi takich jak OpenSSL.

### Jak zweryfikować podpis cyfrowy w dokumencie?
Możesz otworzyć podpisany dokument w programie Word i przejść do szczegółów podpisu, aby zweryfikować autentyczność i integralność podpisu.