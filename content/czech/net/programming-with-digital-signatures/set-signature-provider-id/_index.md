---
title: Nastavte ID poskytovatele podpisu v dokumentu aplikace Word
linktitle: Nastavte ID poskytovatele podpisu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit ID poskytovatele podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-digital-signatures/set-signature-provider-id/
---
V tomto tutoriálu vás provedeme kroky k použití funkce Set Signature Provider ID s Aspose.Words for .NET. Tato funkce umožňuje zadat ID poskytovatele podpisu pro řádek podpisu v dokumentu aplikace Word. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu a přístup k řádku podpisu

Začněte nahráním dokumentu obsahujícího řádek podpisu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Krok 2: Nastavení možností podpisu

Vytvořte instanci třídy SignOptions a nastavte možnosti podepisování, včetně ID poskytovatele:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Krok 3: Podepsání dokumentu

Chcete-li dokument podepsat, musíte použít třídu DigitalSignatureUtil a zadat podpisový certifikát:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Nezapomeňte zadat správné cesty pro dokument, certifikát a podepsaný dokument.

### Příklad zdrojového kódu pro Set Signature Provider Id pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro nastavení ID poskytovatele podpisu pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
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

Dokončete ID poskytovatele podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET.


## Závěr

tomto tutoriálu jsme se naučili, jak nastavit ID poskytovatele podpisu pro řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete snadno načíst dokument, získat přístup k řádku podpisu, nastavit ID poskytovatele a podepsat dokument. Možnost nastavit ID poskytovatele podpisu pomáhá stanovit identitu a důvěryhodnost podepisujícího, čímž se zvyšuje bezpečnost a integrita vašich dokumentů aplikace Word. Aspose.Words for .NET poskytuje robustní rozhraní API pro zpracování textu s digitálními podpisy, které vám umožňuje snadno přizpůsobit a spravovat proces podpisu.

### Časté dotazy k nastavení ID poskytovatele podpisu v dokumentu aplikace Word

#### Otázka: Co je ID poskytovatele podpisu v dokumentu aplikace Word?

Odpověď: ID poskytovatele podpisu v dokumentu aplikace Word je jedinečný identifikátor, který určuje poskytovatele digitálního podpisu. Pomáhá identifikovat subjekt nebo organizaci odpovědnou za vytváření a správu digitálního podpisu.

#### Otázka: Jak mohu nastavit ID poskytovatele podpisu pro řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li nastavit ID poskytovatele podpisu pro řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vložte dokument pomocí`Document` třídy a zadejte cestu k souboru dokumentu.
2.  Přístup k řádku podpisu pomocí vhodné metody nebo vlastnosti. Můžete například použít`GetChild` metoda k načtení tvaru čáry podpisu.
3. Získejte ID poskytovatele z řádku podpisu.
4.  Vytvořte instanci souboru`SignOptions` třídu a nastavte`ProviderId` vlastnost na načtené ID poskytovatele.
5.  Použijte`DigitalSignatureUtil.Sign` způsob podepsání dokumentu s uvedením nezbytných parametrů včetně`SignOptions` objekt.

#### Otázka: Jak získám přístup k řádku podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li získat přístup k řádku podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít příslušnou metodu nebo vlastnost k načtení tvaru řádku podpisu ze struktury dokumentu. Můžete například použít`GetChild` metoda s příslušnými parametry pro získání požadovaného tvaru čáry podpisu.

#### Otázka: Mohu nastavit ID poskytovatele podpisu pro více řádků podpisu v dokumentu aplikace Word?

 Odpověď: Ano, můžete nastavit ID poskytovatele podpisu pro více řádků podpisu v dokumentu aplikace Word. Můžete iterovat kolekci podpisových řádků v dokumentu a nastavit ID poskytovatele pro každý podpisový řádek jednotlivě pomocí`SignOptions.ProviderId` vlastnictví.

#### Otázka: Jaký je účel ID poskytovatele podpisu v dokumentu aplikace Word?

Odpověď: ID poskytovatele podpisu v dokumentu aplikace Word slouží k identifikaci entity nebo organizace odpovědné za vytvoření a správu digitálního podpisu. Pomáhá stanovit pravost a důvěryhodnost digitálního podpisu tím, že jej přiřadí ke konkrétnímu poskytovateli.

#### Otázka: Jaký typ digitálních certifikátů lze použít pro nastavení ID poskytovatele podpisu v dokumentu aplikace Word?

Odpověď: K nastavení ID poskytovatele podpisu v dokumentu aplikace Word můžete použít digitální certifikáty X.509 s příslušnými informacemi o poskytovateli. Digitální certifikát by měl být vydán důvěryhodnou certifikační autoritou (CA) a měl by obsahovat nezbytná metadata k identifikaci poskytovatele.