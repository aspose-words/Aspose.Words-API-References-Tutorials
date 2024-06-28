---
title: Podepisování zašifrovaného dokumentu Word
linktitle: Podepisování zašifrovaného dokumentu Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se digitálně podepisovat zašifrovaný textový dokument pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-digital-signatures/signing-encrypted-document/
---
tomto tutoriálu vás provedeme kroky k použití funkce podepisování zašifrovaného wordového dokumentu pomocí Aspose.Words for .NET. Tato funkce umožňuje digitálně podepsat dokument aplikace Word, který je zašifrován pomocí dešifrovacího hesla. Postupujte podle následujících kroků:

## Krok 1: Nastavení možností podpisu

Vytvořte instanci třídy SignOptions a nastavte heslo pro dešifrování:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Ujistěte se, že jste pro svůj zašifrovaný dokument uvedli správné dešifrovací heslo.

## Krok 2: Načtení certifikátu

Začněte načtením podpisového certifikátu pomocí třídy CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Ujistěte se, že jste zadali správnou cestu k certifikátu a související heslo.

## Krok 3: Podepsání zašifrovaného dokumentu

K podepsání zašifrovaného dokumentu použijte třídu DigitalSignatureUtil:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Nezapomeňte zadat správné cesty pro zašifrovaný dokument, podepsaný dokument a certifikát.

### Příklad zdrojového kódu pro podepisování zašifrovaného dokumentu pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro podepsání zašifrovaného dokumentu pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Pomocí těchto kroků můžete snadno podepsat zašifrovaný dokument aplikace Word pomocí Aspose.Words for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali proces podepisování zašifrovaného dokumentu Word pomocí Aspose.Words for .NET. Poskytnutím dešifrovacího hesla a podpisového certifikátu můžeme k zašifrovanému dokumentu přidat digitální podpis. Podepisování zašifrovaných dokumentů zajišťuje jejich pravost a integritu a poskytuje další vrstvu zabezpečení. Aspose.Words for .NET vám umožňuje podepisovat zašifrované dokumenty a udržovat bezpečnost a důvěryhodnost vašich souborů aplikace Word.

### FAQ

#### Otázka: Co je podepisování dokumentů v Aspose.Words pro .NET?

Odpověď: Podepisování dokumentů v Aspose.Words for .NET se týká procesu digitálního podepisování dokumentu aplikace Word, aby byla zajištěna jeho autenticita, integrita a neodmítnutí. Zahrnuje přidání digitálního podpisu do dokumentu pomocí certifikátu.

#### Otázka: Co je zašifrovaný dokument aplikace Word?

Odpověď: Šifrovaný dokument aplikace Word je dokument, který byl zašifrován pomocí hesla. Šifrování je bezpečnostní opatření, které chrání obsah dokumentu tím, že jej zašifruje a učiní jej nečitelným bez správného dešifrovacího hesla.

#### Otázka: Jak mohu podepsat zašifrovaný dokument aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li podepsat zašifrovaný dokument aplikace Word pomocí Aspose.Words for .NET, musíte spolu s podpisovým certifikátem poskytnout dešifrovací heslo. Následuj tyto kroky:
1.  Nastavte heslo pro dešifrování v`SignOptions` objekt.
2.  Načtěte podpisový certifikát pomocí`CertificateHolder` třída.
3.  Použijte`DigitalSignatureUtil.Sign` způsob podepsání zašifrovaného dokumentu s uvedením nezbytných parametrů.

#### Otázka: Jaký je účel podepsání zašifrovaného dokumentu?

Odpověď: Podepsání zašifrovaného dokumentu pomocí Aspose.Words for .NET vám umožňuje přidat k dokumentu digitální podpis, i když je zašifrován. To poskytuje další vrstvu zabezpečení a zajišťuje pravost a integritu šifrovaného obsahu. Umožňuje příjemcům ověřit původ dokumentu a odhalit jakoukoli manipulaci.

#### Otázka: Mohu podepsat zašifrovaný dokument bez zadání hesla pro dešifrování?

Odpověď: Ne, k podepsání zašifrovaného dokumentu musíte zadat správné dešifrovací heslo. Pro přístup a úpravu zašifrovaného obsahu dokumentu před použitím digitálního podpisu je vyžadováno dešifrovací heslo.

#### Otázka: Mohu podepsat zašifrovaný dokument aplikace Word pomocí jakéhokoli certifikátu?

Odpověď: K podepsání zašifrovaného dokumentu aplikace Word pomocí Aspose.Words for .NET potřebujete platný certifikát X.509. Certifikát lze získat od důvěryhodné certifikační autority (CA) nebo lze pro testovací účely použít certifikát s vlastním podpisem.

#### Otázka: Mohu podepsat více zašifrovaných dokumentů aplikace Word pomocí stejného certifikátu?

 Odpověď: Ano, pomocí stejného certifikátu můžete podepsat více zašifrovaných dokumentů aplikace Word. Jakmile načtete certifikát pomocí`CertificateHolder` třídy, můžete jej znovu použít k podepsání více zašifrovaných dokumentů.

#### Otázka: Mohu ověřit digitální podpis podepsaného zašifrovaného dokumentu?

 Odpověď: Ano, Aspose.Words for .NET poskytuje funkce pro ověření digitálního podpisu podepsaného šifrovaného dokumentu. Můžete použít`DigitalSignatureUtil.Verify` způsob kontroly platnosti a pravosti digitálního podpisu.

#### Otázka: Jaký formát souboru Aspose.Words for .NET podporuje pro podepisování šifrovaných dokumentů?

 Odpověď: Aspose.Words for .NET podporuje podepisování zašifrovaných dokumentů aplikace Word ve formátu souboru DOCX. Zašifrované soubory DOCX můžete podepsat pomocí`DigitalSignatureUtil.Sign` spolu s nezbytným dešifrovacím heslem a certifikátem.

#### Otázka: Jak podepsání zašifrovaného dokumentu ovlivňuje šifrování?

Odpověď: Podepsání zašifrovaného dokumentu pomocí Aspose.Words for .NET neovlivní šifrování dokumentu. Šifrování zůstává nedotčeno a k zašifrovanému obsahu je přidán digitální podpis. Digitální podpis poskytuje další zabezpečení a ověřování, aniž by došlo k ohrožení šifrování použitého na dokument.