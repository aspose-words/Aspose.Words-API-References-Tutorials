---
title: Převod Docx na Mhtml a odesílání e-mailů
linktitle: Převod Docx na Mhtml a odesílání e-mailů
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se převádět dokumenty Word z Docx do MHTML a odesílat je jako e-maily pomocí Aspose.Words a Aspose.Email. Výukový program krok za krokem.
type: docs
weight: 10
url: /cs/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

V tomto podrobném tutoriálu vás provedeme tím, jak používat Aspose.Words pro .NET k převodu dokumentu aplikace Word ve formátu Docx do MHTML a jeho odeslání jako e-mailu pomocí Aspose.Email. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte ve svém vývojovém prostředí nainstalované a nastavené knihovny Aspose.Words for .NET a Aspose.Email. Pokud jste tak neučinili, stáhněte si a nainstalujte knihovny z[Aspose.Releases](https://releases.aspose.com/words/net/).

## Krok 1: Inicializace objektu dokumentu

 Nejprve inicializujte`Document`objekt s cestou k vašemu zdrojovému dokumentu ve formátu Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Krok 2: Uložení dokumentu ve formátu MHTML

 Dále uložte dokument do a`Stream` objekt ve formátu MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Krok 3: Přetočení streamu zpět

Protože Aspose.Email potřebuje číst stream od začátku, přetočte stream na začátek:

```csharp
stream.Position = 0;
```

## Krok 4: Vytvoření zprávy MIME Aspose.Email

 Vytvořit`MailMessage` objekt z proudu pomocí`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Neváhejte a přizpůsobte vlastnosti zprávy, jako je odesílatel, příjemce a předmět.

## Krok 5: Odeslání e-mailu

 Použijte Aspose.Email's`SmtpClient` poslat email:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Ujistěte se, že zadáváte správnou adresu hostitele serveru SMTP.

A je to! Úspěšně jste převedli dokument aplikace Word ve formátu Docx do MHTML a odeslali jej jako e-mail pomocí Aspose.Words pro .NET a Aspose.Email.

### Příklad zdrojového kódu pro Docx To Mhtml a odesílání e-mailů pomocí Aspose.Words pro .NET

```csharp

	// Dokument doc = nový dokument(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Přetočte stream na začátek, aby jej Aspose.Email mohl přečíst.
	stream.Position = 0;

	// Vytvořte e-mailovou zprávu Aspose.Email MIME ze streamu.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Odešlete zprávu pomocí Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej podle svých konkrétních požadavků.

### Nejčastější dotazy

#### Jak převést soubor DOCX na MHTML?

Chcete-li převést soubor DOCX na MHTML, můžete použít softwarové nástroje nebo knihovny, které tuto funkci poskytují. Spolehlivou možností pro tento převod je Aspose.Words for .NET. K načtení souboru DOCX a jeho uložení ve formátu MHTML můžete použít rozhraní API knihovny.

#### Jak mohu odeslat e-mail s přílohou souboru MHTML?

Chcete-li odeslat e-mail se souborem MHTML jako přílohou, můžete použít knihovny nebo nástroje specifické pro odesílání e-mailů, jako je System.Net.Mail v .NET. Před odesláním zprávy musíte vytvořit e-mailovou zprávu, zadat příjemce, předmět a obsah a poté ke zprávě přidat soubor MHTML jako přílohu.

#### Jaká jsou omezení procesu konverze a odesílání e-mailů?

Omezení procesu konverze a odesílání e-mailů závisí na konkrétních nástrojích, které používáte. Některé nástroje mohou mít omezení týkající se velikosti souboru, nastavení zabezpečení nebo podporovaných e-mailových protokolů. Je důležité vybrat nástroje, které vyhovují vašim potřebám, a při implementaci zohlednit tato omezení.

#### Je Aspose spolehlivým nástrojem pro konverzi DOCX do MHTML a odesílání e-mailů?

Ano, Aspose.Words for .NET je spolehlivý nástroj pro konverzi DOCX do MHTML a odesílání e-mailů. Je široce používán vývojáři a profesionály pro svůj výkon a kvalitu. Nástroj nabízí komplexní dokumentaci, pokročilé funkce a vyhrazenou technickou podporu, takže je pro tyto úkoly doporučenou volbou.