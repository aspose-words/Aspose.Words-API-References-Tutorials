---
title: Webbővítmény munkaablak használata
linktitle: Webbővítmény munkaablak használata
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a webbővítmény munkaablakok használatához az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/programming-with-webextension/using-web-extension-task-panes/
---

Ez a cikk lépésről lépésre bemutatja a webbővítmény munkaablakainak használatát az Aspose.Words for .NET programmal. Részletesen elmagyarázzuk a kód minden részét. Az oktatóanyag végén megtudhatja, hogyan adhat hozzá és konfigurálhat munkaablakokat webbővítményekhez.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 A kezdéshez meg kell határoznia annak a könyvtárnak az elérési útját, ahová a generált dokumentumot menteni szeretné. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre és konfiguráljon egy munkaablakot

 Létrehozunk a`TaskPane` objektumot, és adja hozzá a dokumentumhoz`s `WebExtensionTaskPanes gyűjtemény. Ezután konfiguráljuk a munkaablak tulajdonságait, például dokkolt állapotát, láthatóságát és szélességét.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Beállítjuk a webbővítmény hitelesítő adatait is, beleértve a katalógusazonosítót, a verziót és az üzlet típusát.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Végül tulajdonságokat és kötéseket adunk a webbővítményhez.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## 3. lépés: Mentse el és töltse be a dokumentumot

A dokumentumot a megadott könyvtárban konfigurált munkaablakokkal mentjük.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## 4. lépés: Jelenítse meg a munkaablak adatait

Ezután betöltjük a dokumentumot, és megjelenítjük a munkaablak forrásinformációit.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Ez minden ! Sikeresen használta az Aspose.Words for .NET webbővítmény munkaablakait.

### Példa forráskódra webbővítmény munkaablakok használatához az Aspose.Words for .NET használatával


```csharp

	// A dokumentumok könyvtárának elérési útja.
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
