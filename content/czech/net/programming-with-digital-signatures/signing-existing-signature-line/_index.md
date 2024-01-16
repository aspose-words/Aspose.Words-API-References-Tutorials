---
title: Podepisování existujícího řádku podpisu v dokumentu aplikace Word
linktitle: Podepisování existujícího řádku podpisu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak podepsat existující řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-digital-signatures/signing-existing-signature-line/
---
V tomto tutoriálu vás provedeme kroky k použití funkce podpisu existujícího řádku podpisu s Aspose.Words pro .NET. Tato funkce umožňuje digitálně podepsat řádek podpisu, který se již nachází v dokumentu aplikace Word. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu a přístup k řádku podpisu

Začněte nahráním dokumentu obsahujícího existující řádek podpisu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Krok 2: Nastavení možností podpisu

Vytvořte instanci třídy SignOptions a nastavte možnosti podpisu, včetně ID řádku podpisu a obrázku řádku podpisu:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Ujistěte se, že jste zadali správnou cestu k obrazu podpisového řádku.

## Krok 3: Načtení certifikátu

Začněte načtením podpisového certifikátu pomocí třídy CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ujistěte se, že jste zadali správnou cestu k certifikátu a související heslo.

## Krok 4: Podepsání stávajícího podpisového řádku

Pomocí třídy DigitalSignatureUtil podepište existující řádek podpisu:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Nezapomeňte zadat správné cesty pro zdrojový dokument, podepsaný dokument a certifikát.

### Příklad zdrojového kódu pro podepisování existujícího podpisového řádku pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro podepsání existujícího řádku podpisu pomocí Aspose.Words pro .NET:


```csharp

	// Cesta k adresáři dokumentů.
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

Pomocí následujících kroků můžete snadno podepsat existující řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Závěr

tomto tutoriálu jsme se naučili, jak podepsat existující řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle uvedených kroků můžete snadno načíst dokument, získat přístup k existujícímu řádku podpisu, nastavit možnosti podepisování a podepsat dokument. Možnost podepsat existující řádek podpisu poskytuje pohodlný způsob, jak přidat digitální podpisy do předdefinovaných oblastí ve vašich dokumentech aplikace Word, čímž je zajištěna integrita dokumentu a ověřování. Aspose.Words for .NET nabízí výkonné rozhraní API pro zpracování textu s digitálními podpisy, které vám umožní přizpůsobit proces podepisování a zvýšit zabezpečení vašich dokumentů aplikace Word.

### FAQ

#### Otázka: Co je existující řádek podpisu v dokumentu aplikace Word?

Odpověď: Existující řádek podpisu v dokumentu aplikace Word je předdefinovaná oblast, kam lze umístit podpis. Obvykle je reprezentován tvarem nebo objektem v dokumentu a slouží jako vyhrazený prostor pro podepisující osobu, aby mohl přidat svůj digitální podpis.

#### Otázka: Jak mohu podepsat existující řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li podepsat existující řádek podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete postupovat takto:
1.  Vložte dokument pomocí`Document` třídy a zadejte cestu k souboru dokumentu.
2.  Zpřístupněte existující řádek podpisu pomocí vhodné metody nebo vlastnosti. Můžete například použít`GetChild` metoda k načtení tvaru čáry podpisu.
3.  Vytvořte instanci souboru`SignOptions` třídu a nastavte`SignatureLineId` vlastnost na ID stávajícího řádku podpisu.
4.  Nastav`SignatureLineImage` vlastnictvím`SignOptions` třídy k obrázku představujícímu digitální podpis.
5.  Načtěte podpisový certifikát pomocí`CertificateHolder` třídy a poskytněte potřebný certifikát a heslo.
6.  Použijte`DigitalSignatureUtil.Sign` způsob podepsání dokumentu s uvedením nezbytných parametrů včetně`SignOptions` objekt.

#### Otázka: Jak získám přístup k existujícímu řádku podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li získat přístup k existujícímu řádku podpisu v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít příslušnou metodu nebo vlastnost k načtení tvaru řádku podpisu ze struktury dokumentu. Můžete například použít`GetChild` metoda s příslušnými parametry pro získání požadovaného tvaru čáry podpisu.

#### Otázka: Mohu upravit vzhled digitálního podpisu v existujícím řádku podpisu?

Odpověď: Ano, vzhled digitálního podpisu v existujícím řádku podpisu můžete upravit poskytnutím souboru obrázku představujícího podpis. Obrázek může být logo, vlastnoruční podpis nebo jakékoli jiné grafické znázornění podpisu. Můžete nastavit`SignatureLineImage` vlastnictvím`SignOptions` třídy na bajty souboru obrázku.

#### Otázka: Mohu podepsat více existujících podpisových řádků v dokumentu aplikace Word?
 Odpověď: Ano, v dokumentu aplikace Word můžete podepsat více existujících podpisových řádků. Musíte postupovat podle kroků pro každý řádek podpisu jednotlivě a nastavit příslušné`SignatureLineId` a`SignatureLineImage` hodnoty v`SignOptions` objekt pro každý řádek podpisu.

#### Otázka: Jaký formát by měl mít soubor obrázku pro digitální podpis v existujícím řádku podpisu?

 Odpověď: Soubor obrázku pro digitální podpis v existujícím řádku podpisu může být v různých formátech, jako je PNG, JPEG, BMP nebo GIF. Můžete zadat cestu k souboru nebo přečíst bajty souboru obrázku a přiřadit jej k`SignatureLineImage` vlastnictvím`SignOptions` třída.
