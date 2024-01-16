---
title: Ekspor Ke Penurunan Harga Dengan Penyelarasan Isi Tabel
linktitle: Ekspor Ke Penurunan Harga Dengan Penyelarasan Isi Tabel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor konten tabel dengan perataan berbeda ke file Markdown menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut yang membantu mengekspor konten ke file Markdown dengan penyelarasan konten tabel menggunakan pustaka Aspose.Words untuk .NET. Pastikan Anda telah menyertakan perpustakaan Aspose.Words di proyek Anda sebelum menggunakan kode ini.

## Langkah 1: Tetapkan jalur direktori dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda tempat dokumen yang diedit akan disimpan.

## Langkah 2: Buat dokumen dan pembuat dokumen

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di sini kita membuat sebuah instance dari`Document` kelas dan sebuah instance dari`DocumentBuilder` kelas yang memungkinkan kita memanipulasi dokumen dan menambahkan elemen.

## Langkah 3: Sisipkan sel dalam tabel dengan perataan paragraf berbeda

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Kami menggunakan Pembuat Dokumen untuk menyisipkan sel ke dalam tabel dan mengatur perataan paragraf yang berbeda untuk setiap sel.

## Langkah 4: Tetapkan opsi ekspor penurunan harga dan simpan dokumen yang dimodifikasi

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Kami mengatur opsi ekspor penurunan harga dengan perataan konten tabel yang berbeda, lalu menyimpan dokumen yang dimodifikasi menggunakan setiap opsi perataan.

### Contoh kode sumber untuk diekspor ke Markdown dengan penyelarasan konten tabel menggunakan Aspose.Words untuk .NET

```csharp

            
	// Jalur ke direktori dokumen.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Membuat semua paragraf di dalam tabel menjadi sejajar.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Penyelarasan dalam hal ini akan diambil dari paragraf pertama pada kolom tabel yang bersangkutan.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Simpan dokumen yang diubah
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
