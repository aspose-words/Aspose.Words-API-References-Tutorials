---
title: Korzystanie z okienek zadań rozszerzenia sieciowego
linktitle: Korzystanie z okienek zadań rozszerzenia sieciowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Przewodnik krok po kroku dotyczący korzystania z okienek zadań rozszerzenia sieciowego w Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-webextension/using-web-extension-task-panes/
---

Ten artykuł zawiera przewodnik krok po kroku dotyczący korzystania z okienek zadań rozszerzeń sieciowych w Aspose.Words dla .NET. Szczegółowo wyjaśnimy każdą część kodu. Pod koniec tego samouczka będziesz mógł zrozumieć, jak dodawać i konfigurować okienka zadań dla rozszerzeń internetowych.

Zanim zaczniesz, upewnij się, że w swoim projekcie zainstalowałeś i skonfigurowałeś bibliotekę Aspose.Words for .NET. Bibliotekę i instrukcje instalacji można znaleźć na stronie internetowej Aspose.

## Krok 1: Zdefiniuj katalog dokumentów

 Aby rozpocząć, należy zdefiniować ścieżkę do katalogu, w którym chcemy zapisać wygenerowany dokument. Zastępować`"YOUR DOCUMENT DIRECTORY"` z rzeczywistą ścieżką do katalogu dokumentów.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Utwórz i skonfiguruj okienko zadań

 Tworzymy`TaskPane` obiekt i dodaj go do dokumentu`s `Kolekcja WebExtensionTaskPanes. Następnie konfigurujemy właściwości panelu zadań, takie jak stan zadokowania, widoczność i szerokość.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Ustawiamy także dane uwierzytelniające rozszerzenia internetowego, w tym identyfikator katalogu, wersję i typ sklepu.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Na koniec dodajemy właściwości i powiązania do rozszerzenia internetowego.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Krok 3: Zapisz i załaduj dokument

Zapisujemy dokument ze skonfigurowanymi okienkami zadań w określonym katalogu.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Krok 4: Wyświetl informacje w okienkach zadań

Następnie ładujemy dokument i wyświetlamy informacje o źródle panelu zadań.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

To wszystko ! Pomyślnie użyłeś okienek zadań rozszerzenia sieciowego w Aspose.Words dla .NET.

### Przykładowy kod źródłowy do korzystania z okienek zadań rozszerzeń sieciowych z Aspose.Words dla .NET


```csharp

	// Ścieżka do katalogu dokumentów.
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
