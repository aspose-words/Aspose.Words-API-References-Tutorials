---
title: Přidejte digitální podpis do PDF pomocí držitele certifikátu
linktitle: Přidejte digitální podpis do PDF pomocí držitele certifikátu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přidat digitální podpis do PDF pomocí držitele certifikátu s Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

V tomto tutoriálu vás provedeme kroky pro přidání digitálního podpisu do PDF pomocí držitele certifikátu s Aspose.Words pro .NET. Digitální podpis dodává dokumentu PDF vrstvu zabezpečení a integrity. Postupujte podle následujících kroků:

## Krok 1: Vytvoření dokumentu a přidání obsahu

Začněte vytvořením instance třídy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Přidejte obsah do dokumentu

 Poté použijte`DocumentBuilder`pro přidání obsahu do dokumentu. Chcete-li například přidat odstavec obsahující text "Test Signed PDF", použijte`Writeln` metoda:

```csharp
builder.Writeln("Test Signed PDF.");
```

Podle potřeby můžete přidat další položky obsahu.

## Krok 3: Nastavte možnosti uložení PDF

Vytvořte instanci třídy PdfSaveOptions a zadejte podrobnosti o digitálním podpisu:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Ujistěte se, že jste zadali správnou cestu k certifikátu a související heslo. Můžete také upravit důvod a umístění podpisu.

## Krok 4: Uložte dokument jako digitálně podepsaný PDF

 Použijte`Save` způsob uložení dokumentu jako PDF zadáním možností uložení:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu k uložení digitálně podepsaného PDF.

Podle těchto kroků můžete snadno vytvořit digitálně podepsaný PDF s certifikátem pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro digitálně podepsané PDF pomocí držitele certifikátu pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód digitálně podepsaného PDF pomocí držitele certifikátu z dokumentu pomocí Aspose.Words pro .NET:

```csharp

            // Cesta k adresáři dokumentů.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Závěr

tomto tutoriálu jsme prozkoumali kroky pro přidání digitálního podpisu do dokumentu PDF pomocí certifikátu s Aspose.Words for .NET. Digitální podpis dodává dokumentu vrstvu zabezpečení a integrity, čímž zaručuje jeho pravost a umožňuje odhalit případné následné úpravy. Podle uvedených kroků můžete snadno vytvořit digitálně podepsaný PDF pomocí certifikátu s Aspose.Words for .NET.

### Často kladené otázky

#### Otázka: Co je digitální podpis a proč je důležitý v dokumentu PDF?
Odpověď: Digitální podpis je bezpečnostní technika, která pomáhá zajistit pravost, integritu a nepopiratelnost elektronického dokumentu, jako je soubor PDF. Používá digitální certifikát k přidání vrstvy zabezpečení do dokumentu, což pomáhá ověřit identitu autora a odhalit případné následné změny obsahu.

#### Otázka: Jak mohu přidat digitální podpis do dokumentu PDF pomocí certifikátu s Aspose.Words for .NET?
Odpověď: Chcete-li přidat digitální podpis do dokumentu PDF pomocí certifikátu s Aspose.Words for .NET, postupujte takto:

 Vytvořte instanci souboru`Document` třídy reprezentovat dokument.

 Použijte`DocumentBuilder` třídy přidat požadovaný obsah do dokumentu.

 Vytvořte instanci souboru`PdfSaveOptions` třídy a zadejte podrobnosti digitálního podpisu pomocí`PdfDigitalSignatureDetails` třída. Budete muset zadat cestu k certifikátu (`CertificateHolder.Create`), související heslo a důvod a umístění podpisu.

 Použijte`Save` způsob uložení dokumentu ve formátu PDF s uvedením možností uložení.

#### Otázka: Jak získám certifikát pro přidání digitálního podpisu do dokumentu PDF?
Odpověď: Chcete-li získat certifikát pro přidání digitálního podpisu do dokumentu PDF, můžete obvykle kontaktovat certifikační autoritu (CA) nebo poskytovatele důvěryhodných služeb. Tyto entity vydávají digitální certifikáty po ověření vaší identity a ověření vaší žádosti. Jakmile certifikát získáte, můžete jej použít ve své aplikaci k přidávání digitálních podpisů do dokumentů PDF.

#### Otázka: Je možné upravit podrobnosti digitálního podpisu, jako je důvod a umístění?
 Odpověď: Ano, podrobnosti digitálního podpisu můžete přizpůsobit zadáním důvodu a umístění podpisu. V uvedeném příkladu kódu můžete upravit hodnoty`reason`a`location` parametry při vytváření`PdfDigitalSignatureDetails` objekt. Ujistěte se, že jste pro každý parametr poskytli příslušné informace, aby odrážely důvod a umístění podpisu v dokumentu PDF.