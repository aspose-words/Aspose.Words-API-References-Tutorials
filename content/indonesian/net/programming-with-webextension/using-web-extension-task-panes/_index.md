---
title: Menggunakan Panel Tugas Ekstensi Web
linktitle: Menggunakan Panel Tugas Ekstensi Web
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menggunakan Panel Tugas Ekstensi Web dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-webextension/using-web-extension-task-panes/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan panel tugas ekstensi web dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara menambahkan dan mengonfigurasi panel tugas untuk ekstensi web.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori dokumen

 Untuk memulai, Anda perlu menentukan jalur ke direktori tempat Anda ingin menyimpan dokumen yang dihasilkan. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat dan konfigurasikan panel tugas

 Kami membuat`TaskPane` objek dan menambahkannya ke dokumen`s `Koleksi WebExtensionTaskPanes`. Selanjutnya, kita mengonfigurasi properti panel tugas, seperti status dock, visibilitas, dan lebarnya.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Kami juga mengatur kredensial ekstensi web termasuk id katalog, versi dan jenis toko.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Terakhir, kami menambahkan properti dan binding ke ekstensi web.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Langkah 3: Simpan dan muat dokumen

Kami menyimpan dokumen dengan panel tugas yang dikonfigurasi di direktori yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Langkah 4: Tampilkan informasi panel tugas

Selanjutnya, kita memuat dokumen dan menampilkan informasi sumber panel tugas.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Itu saja ! Anda telah berhasil menggunakan panel tugas ekstensi web dengan Aspose.Words untuk .NET.

### Contoh kode sumber untuk menggunakan panel tugas ekstensi web dengan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
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
