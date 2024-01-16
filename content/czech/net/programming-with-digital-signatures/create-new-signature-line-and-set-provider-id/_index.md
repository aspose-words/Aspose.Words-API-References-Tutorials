---
title: Vytvořte nový řádek podpisu a nastavte ID poskytovatele
linktitle: Vytvořte nový řádek podpisu a nastavte ID poskytovatele
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit nový řádek podpisu a nastavit ID poskytovatele v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
tomto tutoriálu vás provedeme kroky k použití funkce Create New Signature Line a Set Provider ID s Aspose.Words for .NET. Tato funkce umožňuje vložit řádek podpisu do dokumentu aplikace Word, nastavit vlastní možnosti a podepsat dokument. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a generátoru

Začněte vytvořením instance třídy Document a objektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Nastavení možností podpisové linky

Vytvořte instanci třídy SignatureLineOptions a nastavte požadované možnosti:

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

## Krok 3: Vložení řádku podpisu

Pomocí metody InsertSignatureLine() objektu DocumentBuilder vložte řádek podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Krok 4: Nastavte ID poskytovatele

Nastavte ID poskytovatele pro řádek podpisu pomocí vlastnosti ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Nezapomeňte zadat správné ID poskytovatele pro váš případ použití.

## Krok 5: Uložte dokument

Uložte upravený dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro uložení dokumentu.

## Krok 6: Podepsání dokumentu

Chcete-li dokument podepsat, musíte nastavit možnosti podpisu a použít třídu DigitalSignatureUtil:

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

Nezapomeňte zadat správné cesty pro dokument, certifikát a podepsaný dokument.

### Příklad zdrojového kódu pro Create New Signature Line and Set Provider Id using Aspose.Words for .NET

Zde je úplný zdrojový kód pro vytvoření nového řádku podpisu a nastavení ID poskytovatele pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
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

Pomocí následujících kroků můžete snadno vytvořit nový řádek podpisu a nastavit ID poskytovatele v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr

tomto tutoriálu jsme prozkoumali funkci vytvoření nového řádku podpisu a nastavení ID poskytovatele v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete snadno vložit řádek podpisu s vlastními možnostmi a přiřadit jej ke konkrétnímu poskytovateli pomocí ID poskytovatele. Přidání podpisových řádků a přizpůsobení informací o poskytovateli zvyšuje autentičnost a důvěryhodnost vašich dokumentů. Aspose.Words for .NET poskytuje výkonné rozhraní API pro zpracování textu s podpisovými řádky a digitálními certifikáty v dokumentech aplikace Word, což vám umožňuje automatizovat proces podepisování a zajistit platnost vašich dokumentů.

### FAQ

#### Otázka: Co je ID poskytovatele v řádku podpisu?

Odpověď: ID poskytovatele v řádku podpisu je jedinečný identifikátor, který představuje poskytovatele digitálního podpisu. Pomáhá identifikovat zdroj nebo organizaci odpovědnou za podpis.

#### Otázka: Jak mohu vytvořit nový řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li vytvořit nový řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vytvořte instanci souboru`Document` třída a a`DocumentBuilder` objekt.
2.  Vytvořte instanci souboru`SignatureLineOptions` třídy a nastavte požadované možnosti řádku podpisu.
3.  Použijte`InsertSignatureLine` metoda`DocumentBuilder` objekt pro vložení řádku podpisu do dokumentu.

#### Otázka: Mohu přizpůsobit možnosti řádku podpisu, jako je jméno podepisujícího, titul a pokyny?

 Odpověď: Ano, můžete přizpůsobit možnosti řádku podpisu. The`SignatureLineOptions` třída poskytuje vlastnosti pro nastavení požadovaných možností, jako je např`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, atd. Tyto vlastnosti můžete upravit před vložením řádku podpisu.

#### Otázka: Jaký je účel nastavení ID poskytovatele pro podpisovou linku?

Odpověď: Nastavení ID poskytovatele pro řádek podpisu pomáhá identifikovat zdroj nebo organizaci odpovědnou za digitální podpis. Umožňuje vám spojit podpis s konkrétním poskytovatelem nebo subjektem a poskytuje další informace o původu a důvěryhodnosti podpisu.

#### Otázka: Jak mohu nastavit ID poskytovatele pro řádek podpisu pomocí Aspose.Words for .NET?

A: Chcete-li nastavit ID poskytovatele pro řádek podpisu pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Po vložení řádku podpisu přejděte na`ProviderId` vlastnictvím`SignatureLine` objekt.
2.  Nastav`ProviderId` vlastnost na požadovanou hodnotu ID poskytovatele pomocí`Guid` datový typ.

#### Otázka: Mohu dokument podepsat po vytvoření nového řádku podpisu a nastavení ID poskytovatele?

 Odpověď: Ano, po vytvoření nového podpisového řádku a nastavení ID poskytovatele můžete dokument podepsat. Chcete-li dokument podepsat, musíte nastavit možnosti podpisu, včetně ID řádku podpisu, ID poskytovatele, komentářů a času podpisu. Poté použijte`DigitalSignatureUtil.Sign` způsob podepsání dokumentu pomocí digitálního certifikátu.

#### Otázka: Mohu zadat konkrétní ID poskytovatele pro každý řádek podpisu v dokumentu aplikace Word?

Odpověď: Ano, můžete zadat konkrétní ID poskytovatele pro každý řádek podpisu v dokumentu aplikace Word. Po vložení každého podpisového řádku můžete nastavit ID poskytovatele pro tento konkrétní podpisový řádek přístupem k`ProviderId` majetek příslušného`SignatureLine` objekt.

#### Otázka: Jak mohu uložit upravený dokument po vytvoření nového řádku podpisu a nastavení ID poskytovatele?

 A: Chcete-li uložit upravený dokument po vytvoření nového řádku podpisu a nastavení ID poskytovatele, můžete použít`Save` metoda`Document` objekt. Chcete-li dokument uložit, zadejte správnou cestu a název souboru.

#### Otázka: Jaký formát souboru Aspose.Words for .NET podporuje pro vytváření a podepisování podpisových řádků?

Odpověď: Aspose.Words for .NET podporuje vytváření a podepisování podpisových řádků ve formátu souboru DOCX. Pomocí poskytnutých metod a tříd můžete vytvářet a podepisovat řádky podpisu v souborech DOCX.

#### Otázka: Mohu upravit ID poskytovatele nebo jiné možnosti podpisového řádku poté, co byl podepsán?

Odpověď: Jakmile je řádek podpisu podepsán, stává se součástí obsahu dokumentu a nelze jej samostatně upravovat. Jakékoli úpravy podpisového řádku, jako je změna ID poskytovatele nebo jiné možnosti, by vyžadovaly odstranění stávajícího podpisu a vytvoření nového podpisového řádku.