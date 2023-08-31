---
title: Использование панелей задач веб-расширений
linktitle: Использование панелей задач веб-расширений
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по использованию панелей задач веб-расширений с Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-webextension/using-web-extension-task-panes/
---

В этой статье представлено пошаговое руководство по использованию панелей задач веб-расширений с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как добавлять и настраивать панели задач для веб-расширений.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на сайте Aspose.

## Шаг 1. Определите каталог документов.

 Для начала вам необходимо определить путь к каталогу, в котором вы хотите сохранить созданный документ. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте и настройте область задач.

 Мы создаем`TaskPane` объект и добавить его в документ`s `Коллекция WebExtensionTaskPanes. Далее мы настраиваем свойства панели задач, такие как ее закрепленное состояние, видимость и ширина.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Мы также устанавливаем учетные данные веб-расширения, включая идентификатор каталога, версию и тип магазина.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Наконец, мы добавляем свойства и привязки к веб-расширению.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Шаг 3. Сохраните и загрузите документ.

Сохраняем документ с настроенными панелями задач в указанном каталоге.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Шаг 4. Отображение информации на панели задач

Затем мы загружаем документ и отображаем исходную информацию на панели задач.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Вот и все ! Вы успешно использовали панели задач веб-расширений с Aspose.Words для .NET.

### Пример исходного кода для использования панелей задач веб-расширений с Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
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
