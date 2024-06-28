---
title: Podepište dokument aplikace Word
linktitle: Podepište dokument aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak digitálně podepsat dokument Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-digital-signatures/sign-document/
---
V tomto tutoriálu vás provedeme kroky k použití funkce podepisování dokumentů s Aspose.Words pro .NET. Tato funkce umožňuje digitálně podepsat dokument aplikace Word pomocí certifikátu. Postupujte podle následujících kroků:

## Krok 1: Načtení certifikátu

Začněte načtením podpisového certifikátu pomocí třídy CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ujistěte se, že jste zadali správnou cestu k certifikátu a související heslo.

## Krok 2: Podepsání dokumentu

K podepsání dokumentu použijte třídu DigitalSignatureUtil:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Nezapomeňte zadat správné cesty pro zdrojový dokument a podepsaný dokument.

### Příklad zdrojového kódu pro podepsat dokument pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro podepsání dokumentu pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Pomocí následujících kroků můžete snadno podepsat dokument aplikace Word pomocí Aspose.Words for .NET.

## Závěr

 V tomto tutoriálu jsme prozkoumali funkci podepisování dokumentů v Aspose.Words pro .NET. Načtením podpisového certifikátu a použitím`DigitalSignatureUtil.Sign` můžeme digitálně podepsat dokument aplikace Word. Podepisování dokumentů zajišťuje autentizaci a zajišťuje integritu obsahu dokumentu, což z něj činí cennou funkci pro bezpečnou a důvěryhodnou správu dokumentů.

### Časté dotazy pro dokument znakového slova

#### Otázka: Co je podepisování dokumentů v Aspose.Words pro .NET?

Odpověď: Podepisování dokumentů v Aspose.Words pro .NET se týká procesu digitálního podepisování dokumentu aplikace Word pomocí certifikátu. Tato funkce přidá k dokumentu digitální podpis, který zajistí autenticitu, integritu a nepopiratelnost obsahu dokumentu.

#### Otázka: Jak mohu načíst podpisový certifikát v Aspose.Words pro .NET?

 A: Chcete-li načíst podpisový certifikát v Aspose.Words pro .NET, můžete použít`CertificateHolder` třída. Vytvořte instanci`CertificateHolder` zadáním cesty k souboru certifikátu a souvisejícího hesla. Zde je příklad:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Ujistěte se, že jste uvedli správnou cestu k certifikátu a související heslo.

#### Otázka: Jak podepíšu dokument aplikace Word pomocí Aspose.Words for .NET?

 A: Chcete-li podepsat dokument aplikace Word pomocí Aspose.Words for .NET, můžete použít`DigitalSignatureUtil` třída. Zavolej`Sign` metoda, která poskytuje cestu ke zdrojovému dokumentu, cestu k podepsanému dokumentu (výstup) a`CertificateHolder` objekt. Zde je příklad:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Ujistěte se, že poskytujete správné cesty pro zdrojový dokument a podepsaný dokument (výstup).

#### Otázka: Jaký je účel podepisování dokumentů?

Odpověď: Podepisování dokumentů slouží jako způsob zajištění pravosti a integrity dokumentu. Digitálním podepsáním dokumentu můžete poskytnout důkaz o jeho původu, ověřit, že jeho obsah nebyl změněn, a prokázat, že nelze odmítnout. Podepisování dokumentů se běžně používá pro právní, finanční a citlivé dokumenty.

#### Otázka: Mohu použít jakýkoli certifikát pro podepisování dokumentů v Aspose.Words for .NET?

Odpověď: Pro podepisování dokumentů v Aspose.Words for .NET musíte použít platný certifikát X.509. Tento certifikát lze získat od důvěryhodné certifikační autority (CA) nebo lze pro testovací účely použít certifikát s vlastním podpisem.

#### Otázka: Jaký formát souboru podporuje Aspose.Words for .NET pro podepisování dokumentů?

 Odpověď: Aspose.Words for .NET podporuje podepisování dokumentů Wordu ve formátu souboru DOCX. Soubory DOCX můžete podepsat pomocí`DigitalSignatureUtil` třídy a příslušného certifikátu.

#### Otázka: Mohu podepsat více dokumentů aplikace Word pomocí stejného certifikátu?

Odpověď: Ano, pomocí stejného certifikátu můžete podepsat více dokumentů aplikace Word. Jakmile načtete certifikát pomocí`CertificateHolder` třídy, můžete ji znovu použít k podepsání více dokumentů voláním`DigitalSignatureUtil.Sign` metoda s různými cestami ke zdroji a podepsanému dokumentu.

#### Otázka: Mění podepisování dokumentu původní dokument?

Odpověď: Podepisování dokumentů pomocí Aspose.Words for .NET nemění původní dokument. Místo toho vytvoří digitálně podepsanou kopii dokumentu a ponechá původní dokument nedotčený. Digitálně podepsaná kopie obsahuje přidaný digitální podpis, který zajišťuje integritu obsahu dokumentu.

#### Otázka: Mohu ověřit digitální podpis podepsaného dokumentu pomocí Aspose.Words for .NET?

 Odpověď: Ano, Aspose.Words for .NET poskytuje funkce pro ověření digitálního podpisu podepsaného dokumentu. Můžete použít`DigitalSignatureUtil.Verify` způsob kontroly platnosti a pravosti digitálního podpisu.