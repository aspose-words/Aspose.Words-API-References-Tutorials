---
title: Vytváření a podepisování nového podpisového řádku
linktitle: Vytváření a podepisování nového podpisového řádku
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit a podepsat nový řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
V tomto tutoriálu vás provedeme kroky k použití funkce vytvoření a podepsání nového řádku podpisu pomocí Aspose.Words pro .NET. Tato funkce umožňuje vložit řádek podpisu do dokumentu aplikace Word, nastavit vlastní možnosti a podepsat dokument. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a generátoru

Začněte vytvořením instance třídy Document a objektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vložení řádku podpisu

Použijte metodu InsertSignatureLine() objektu DocumentBuilder k vložení nového řádku podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Krok 3: Uložte dokument

Uložte upravený dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro uložení dokumentu.

## Krok 4: Podepsání dokumentu

Chcete-li dokument podepsat, musíte nastavit možnosti podpisu a použít třídu DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Nezapomeňte zadat správné cesty pro dokument, obrázek řádku podpisu a podepsaný dokument.

### Příklad zdrojového kódu pro vytvoření a podepsání nového řádku podpisu pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro vytvoření a podepsání nového řádku podpisu pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Podle těchto kroků budete moci snadno vytvořit a podepsat nový řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr

tomto tutoriálu jsme se naučili, jak vytvořit a podepsat nový řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete do dokumentu snadno vložit řádek podpisu, přizpůsobit jeho možnosti a podepsat dokument pomocí digitálního certifikátu. Přidáním podpisových řádků a digitálních podpisů do vašich dokumentů zvýšíte jejich autenticitu a integritu, díky čemuž budou bezpečnější a důvěryhodnější. Aspose.Words for .NET poskytuje výkonné rozhraní API pro zpracování textu s podpisy a digitálními certifikáty v dokumentech aplikace Word, což vám umožňuje automatizovat proces podepisování a zajistit platnost vašich dokumentů.

### FAQ

#### Otázka: Co je řádek podpisu v dokumentu aplikace Word?

Odpověď: Řádek podpisu v dokumentu aplikace Word je zástupný symbol, který označuje, kam by měl být podpis umístěn. Obvykle obsahuje jméno, titul a datum a poskytuje prostor pro ručně psaný nebo digitální podpis.

#### Otázka: Jak mohu vytvořit řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li vytvořit řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vytvořte instanci souboru`Document` třída a a`DocumentBuilder` objekt.
2.  Použijte`InsertSignatureLine` metoda`DocumentBuilder` objekt pro vložení nového řádku podpisu do dokumentu.
3. Uložte upravený dokument.

#### Otázka: Mohu přizpůsobit možnosti řádku podpisu, jako je jméno, název a datum?

 Odpověď: Ano, můžete přizpůsobit možnosti řádku podpisu. The`SignatureLineOptions` třída poskytuje vlastnosti pro nastavení požadovaných možností, jako je např`Signer`, `SignerTitle`, `ShowDate`, atd. Tyto vlastnosti můžete upravit před vložením řádku podpisu.

#### Otázka: Jak mohu podepsat dokument po vytvoření řádku pro podpis?

 A: Chcete-li podepsat dokument po vytvoření řádku podpisu, musíte nastavit možnosti podpisu a použít`DigitalSignatureUtil` třída. Zde jsou kroky:
1.  Nastav`SignatureLineId` nemovitost v`SignOptions` objekt k ID řádku podpisu.
2.  Nastav`SignatureLineImage` nemovitost v`SignOptions` objekt k obrázku podpisu, který chcete použít.
3.  Načtěte podpisový certifikát pomocí`CertificateHolder` třída.
4.  Použijte`DigitalSignatureUtil.Sign` způsob podepsání dokumentu s uvedením potřebných parametrů.

#### Otázka: Mohu k podpisu dokumentu použít obrázek digitálního podpisu?

 Odpověď: Ano, k podepsání dokumentu můžete použít obrázek digitálního podpisu. Chcete-li to provést, musíte poskytnout soubor obrázku v`SignOptions` objekt pomocí`SignatureLineImage`vlastnictví. Obrázek může být v jakémkoli podporovaném formátu obrázku, jako je JPEG, PNG nebo EMF.

#### Otázka: Jaký je účel vytvoření a podepsání nového řádku podpisu v dokumentu aplikace Word?

Odpověď: Vytvoření a podepsání nového řádku podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET vám umožňuje přidat zástupný symbol pro podpis a poté dokument podepsat pomocí digitálního certifikátu. Tento proces zajišťuje pravost a integritu dokumentu a poskytuje důkaz o schválení nebo dohodě.

#### Otázka: Mohu vytvořit a podepsat více podpisových řádků v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Ano, můžete vytvořit a podepsat více podpisových řádků v dokumentu aplikace Word pomocí Aspose.Words for .NET. Každý řádek podpisu může mít své vlastní jedinečné ID a možnosti. Opakováním kroků můžete vytvořit a podepsat další řádky podpisu v dokumentu.

#### Otázka: Mohu upravit řádek podpisu nebo přidat další informace poté, co byl podepsán?

Odpověď: Jakmile je řádek podpisu podepsán, stává se součástí obsahu dokumentu a nelze jej samostatně upravovat. Za podepsaný řádek podpisu však můžete přidat další informace nebo obsah.

#### Otázka: Mohu ověřit digitální podpis dokumentu, který obsahuje řádek podpisu?

 Odpověď: Ano, Aspose.Words for .NET poskytuje funkce pro ověření digitálního podpisu dokumentu, který obsahuje řádek podpisu. Můžete použít`DigitalSignatureUtil.Verify` způsob kontroly platnosti a pravosti digitálního podpisu.

#### Otázka: Jaký formát souboru Aspose.Words for .NET podporuje pro vytváření a podepisování podpisových řádků?

Odpověď: Aspose.Words for .NET podporuje vytváření a podepisování podpisových řádků ve formátu souboru DOCX. Pomocí poskytnutých metod a tříd můžete vytvářet a podepisovat řádky podpisu v souborech DOCX.