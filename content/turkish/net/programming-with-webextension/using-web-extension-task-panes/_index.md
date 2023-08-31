---
title: Web Uzantısı Görev Bölmelerini Kullanma
linktitle: Web Uzantısı Görev Bölmelerini Kullanma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Web Uzantısı Görev Bölmelerini kullanma konusunda adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-webextension/using-web-extension-task-panes/
---

Bu makale, web uzantısı görev bölmelerinin Aspose.Words for .NET ile nasıl kullanılacağına ilişkin adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda web uzantıları için görev bölmelerini nasıl ekleyeceğinizi ve yapılandıracağınızı anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için oluşturulan belgeyi kaydetmek istediğiniz dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Görev bölmesi oluşturun ve yapılandırın

 Biz bir yaratıyoruz`TaskPane` nesneyi seçin ve belgeye ekleyin`s `WebExtensionTaskPanes koleksiyonu. Daha sonra, görev bölmesinin yerleşik durumu, görünürlüğü ve genişliği gibi özelliklerini yapılandırıyoruz.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Ayrıca katalog kimliği, sürüm ve mağaza türü dahil olmak üzere web uzantısı kimlik bilgilerini de ayarlıyoruz.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Son olarak web uzantısına özellikler ve bağlamalar ekliyoruz.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## 3. Adım: Belgeyi kaydedin ve yükleyin

Belgeyi belirtilen dizinde yapılandırılmış görev bölmeleri ile kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## 4. Adım: Görev bölmesi bilgilerini görüntüleyin

Daha sonra belgeyi yüklüyoruz ve görev bölmesi kaynak bilgilerini görüntülüyoruz.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Bu kadar ! Aspose.Words for .NET ile web uzantısı görev panellerini başarıyla kullandınız.

### Aspose.Words for .NET ile web uzantısı görev bölmelerini kullanmak için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
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
