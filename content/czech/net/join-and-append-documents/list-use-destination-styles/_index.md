---
title: Seznam použít styly cíle
linktitle: Seznam použít styly cíle
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se připojovat a připojovat dokumenty aplikace Word při zachování stylů seznamu cílového dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/join-and-append-documents/list-use-destination-styles/
---

Tento výukový program vás provede procesem používání funkce Styly použití seznamu v Aspose.Words for .NET. Tato funkce umožňuje spojovat a připojovat dokumenty aplikace Word při použití stylů seznamu cílového dokumentu.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Aspose.Words for .NET nainstalován. Můžete si jej stáhnout z webu Aspose nebo nainstalovat přes NuGet.
2. Visual Studio nebo jiné vývojové prostředí C#.

## Krok 1: Inicializujte adresáře dokumentů

 Nejprve musíte nastavit cestu k adresáři dokumentů. Upravte hodnotu`dataDir` proměnnou k cestě, kde jsou umístěny vaše dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte zdrojové a cílové dokumenty

 Dále musíte načíst zdrojové a cílové dokumenty pomocí Aspose.Words`Document` třída. Aktualizujte názvy souborů v`Document` konstruktor podle názvů vašich dokumentů.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Krok 3: Nastavte zdrojový dokument na Pokračovat po cílovém dokumentu

 Abyste zajistili, že obsah ze zdrojového dokumentu bude pokračovat i po konci cílového dokumentu, musíte nastavit`SectionStart` vlastnost první sekce ve zdrojovém dokumentu na`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Krok 4: Zvládněte formátování seznamu

Chcete-li zvládnout formátování seznamu, projdete každý odstavec ve zdrojovém dokumentu a zkontrolujete, zda se jedná o položku seznamu. Pokud ano, porovnáte ID seznamu s existujícími seznamy v cílovém dokumentu. Pokud existuje seznam se stejným ID, vytvoříte kopii seznamu ve zdrojovém dokumentu a aktualizujete formát seznamu odstavce tak, aby používal zkopírovaný seznam.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Krok 5: Připojte zdrojový dokument k cílovému dokumentu

 Nyní můžete připojit zdrojový dokument k cílovému dokumentu pomocí`AppendDocument` metoda`Document` třída. The`ImportFormatMode.UseDestinationStyles` Parametr zajišťuje, že během operace připojení budou použity styly seznamu cílového dokumentu.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Krok 6: Uložte konečný dokument

Nakonec uložte sloučený dokument s povolenou funkcí Seznam použití cílových stylů pomocí`Save` metoda`Document` třída.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Příklad zdrojového kódu pro List Use Destination Styles pomocí Aspose.Words for .NET 

Zde je úplný zdrojový kód pro funkci "Seznam použití cílových stylů" v C# pomocí Aspose.Words pro .NET:


```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Nastavte zdrojový dokument tak, aby pokračoval přímo po konci cílového dokumentu.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Sledujte vytvořené seznamy.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Zkontrolujte, zda cílový dokument již obsahuje seznam s tímto ID. Pokud ano, pak může
			// způsobit, že dva seznamy běží společně. Místo toho vytvořte kopii seznamu ve zdrojovém dokumentu.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Pro toto ID již existuje nově zkopírovaný seznam, načtěte uložený seznam,
				// a použijte jej na aktuální odstavec.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Přidejte kopii tohoto seznamu do dokumentu a uložte jej pro pozdější použití.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Nastavte seznam tohoto odstavce na zkopírovaný seznam.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Připojte zdrojový dokument na konec cílového dokumentu.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

je to! Úspěšně jste implementovali funkci List Use Destination Styles pomocí Aspose.Words for .NET. Konečný dokument bude obsahovat sloučený obsah se styly seznamu z cílového dokumentu.