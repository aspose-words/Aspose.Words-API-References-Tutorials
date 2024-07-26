---
title: Upravit ovládací prvky obsahu
linktitle: Upravit ovládací prvky obsahu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se upravovat text, rozevírací seznamy a obrázky v ovládacích prvcích obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/modify-content-controls/
---

Tento kurz vysvětluje, jak upravit různé typy ovládacích prvků obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET. V ovládacích prvcích obsahu můžete aktualizovat text, vybranou hodnotu rozevíracího seznamu nebo nahradit obrázek.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument a iterujte ovládací prvky obsahu
 Načtěte dokument aplikace Word pomocí`Document` konstruktor, předá cestu k dokumentu jako parametr. Iterujte všechny tagy strukturovaného dokumentu v dokumentu pomocí a`foreach` smyčka.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Provádějte akce na základě typu kontroly obsahu
}
```

## Krok 3: Upravte ovládací prvek obsahu prostého textu
 Pro ovládací prvky obsahu typu`SdtType.PlainText`, odstraňte všechny existující podřízené položky, vytvořte nový odstavec a připojte běh s požadovaným textem.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Krok 4: Upravte ovládací prvek obsahu rozevíracího seznamu
 Pro ovládací prvky obsahu typu`SdtType.DropDownList` , aktualizujte vybranou hodnotu nastavením na konkrétní`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Krok 5: Upravte ovládání obsahu obrázku
 Pro ovládací prvky obsahu typu`SdtType.Picture`, načtěte tvar v ovládacím prvku obsahu a nahraďte jeho obrázek novým.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Krok 6: Uložte upravený dokument
 Uložte upravený dokument do zadaného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithSdt.ModifyContentControls.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Příklad zdrojového kódu pro úpravu ovládacích prvků obsahu pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

A je to! Úspěšně jste upravili různé typy ovládacích prvků obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET.