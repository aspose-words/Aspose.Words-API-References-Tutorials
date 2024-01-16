---
title: Použití podoken úloh webového rozšíření
linktitle: Použití podoken úloh webového rozšíření
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce používáním podoken úloh rozšíření webu s Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-webextension/using-web-extension-task-panes/
---

Tento článek poskytuje krok za krokem průvodce, jak používat podokna úloh webového rozšíření s Aspose.Words for .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto kurzu budete schopni porozumět tomu, jak přidávat a konfigurovat podokna úloh pro webová rozšíření.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Pro začátek je potřeba definovat cestu k adresáři, kam chcete vygenerovaný dokument uložit. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte a nakonfigurujte podokno úloh

 Vytváříme a`TaskPane` objekt a přidejte jej do dokumentu`s `Kolekce WebExtensionTaskPanes. Dále nakonfigurujeme vlastnosti podokna úloh, jako je jeho ukotvený stav, viditelnost a šířka.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Nastavili jsme také přihlašovací údaje webového rozšíření včetně ID katalogu, verze a typu obchodu.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Nakonec do webového rozšíření přidáme vlastnosti a vazby.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Krok 3: Uložte a načtěte dokument

Dokument uložíme s podokny úloh nakonfigurovanými v zadaném adresáři.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Krok 4: Zobrazte informace v podoknech úloh

Dále načteme dokument a zobrazíme informace o zdroji podokna úloh.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

To je vše ! Úspěšně jste použili podokna úloh webového rozšíření s Aspose.Words pro .NET.

### Příklad zdrojového kódu pro použití podoken úloh webového rozšíření s Aspose.Words pro .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	TaskPane taskPane = new TaskPane();
	doc.WebExtensionTaskPanes.Add(taskPane);

	taskPane.DockState = TaskPaneDockState.Right;
	taskPane.IsVisible = true;
	taskPane.Width = 300;

	taskPane.WebExtension.Reference.Id = "wa102923726";
	taskPane.WebExtension.Reference.Version = "1.0.0.0";
	taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
	taskPane.WebExtension.Reference.Store = "th-TH";
	taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
	taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
		WebExtensionBindingType.Text, "194740422"));

	doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	
	
	doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	Console.WriteLine("Task panes sources:\n");

	foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
	{
		WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
		Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
	}
 
```
