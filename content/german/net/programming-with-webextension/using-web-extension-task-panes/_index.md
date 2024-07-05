---
title: Verwenden von Web-Erweiterungsaufgabenbereichen
linktitle: Verwenden von Web-Erweiterungsaufgabenbereichen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Verwendung von Web Extension Task Panes mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-webextension/using-web-extension-task-panes/
---

Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zur Verwendung der Aufgabenbereiche der Weberweiterung mit Aspose.Words für .NET. Wir werden jeden Teil des Codes im Detail erklären. Am Ende dieses Tutorials werden Sie wissen, wie Sie Aufgabenbereiche für Weberweiterungen hinzufügen und konfigurieren.

Stellen Sie vor dem Start sicher, dass Sie die Aspose.Words für .NET-Bibliothek in Ihrem Projekt installiert und konfiguriert haben. Sie finden die Bibliothek und Installationsanweisungen auf der Aspose-Website.

## Schritt 1: Dokumentverzeichnis festlegen

 Zunächst müssen Sie den Pfad zum Verzeichnis angeben, in dem Sie das generierte Dokument speichern möchten. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Erstellen und Konfigurieren eines Aufgabenbereichs

 Wir schaffen eine`TaskPane` Objekt und fügen Sie es dem Dokument hinzu`s `WebExtensionTaskPanes-Sammlung. Als Nächstes konfigurieren wir die Eigenschaften des Aufgabenbereichs, beispielsweise seinen angedockten Status, seine Sichtbarkeit und seine Breite.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Wir legen auch die Anmeldeinformationen für die Web-Erweiterung fest, einschließlich Katalog-ID, Version und Store-Typ.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Schließlich fügen wir der Web-Erweiterung Eigenschaften und Bindungen hinzu.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Schritt 3: Speichern und Laden des Dokuments

Wir speichern das Dokument mit den konfigurierten Aufgabenbereichen im angegebenen Verzeichnis.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Schritt 4: Informationen zu den Aufgabenbereichen anzeigen

Als Nächstes laden wir das Dokument und zeigen die Quellinformationen des Aufgabenbereichs an.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Das ist alles! Sie haben die Aufgabenbereiche der Weberweiterung erfolgreich mit Aspose.Words für .NET verwendet.

### Beispielquellcode für die Verwendung von Web-Erweiterungsaufgabenbereichen mit Aspose.Words für .NET


```csharp

	// Der Pfad zum Dokumentverzeichnis.
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
