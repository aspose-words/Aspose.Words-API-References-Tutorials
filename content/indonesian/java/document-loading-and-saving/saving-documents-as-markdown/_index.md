---
title: Menyimpan Dokumen sebagai Penurunan Harga di Aspose.Words untuk Java
linktitle: Menyimpan Dokumen sebagai Penurunan Harga
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara mengonversi dokumen Word ke Markdown dengan Aspose.Words untuk Java. Panduan langkah demi langkah ini mencakup penyelarasan tabel, penanganan gambar, dan banyak lagi.
type: docs
weight: 18
url: /id/java/document-loading-and-saving/saving-documents-as-markdown/
---

## Pengantar Menyimpan Dokumen sebagai Penurunan Harga di Aspose.Words untuk Java

Dalam panduan langkah demi langkah ini, kami akan mendemonstrasikan cara menyimpan dokumen sebagai Markdown menggunakan Aspose.Words untuk Java. Markdown adalah bahasa markup ringan yang biasa digunakan untuk memformat dokumen teks. Dengan Aspose.Words untuk Java, Anda dapat dengan mudah mengonversi dokumen Word Anda ke format Markdown. Kami akan membahas berbagai aspek dalam menyimpan file Markdown, termasuk penyelarasan konten tabel dan penanganan gambar.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Words untuk perpustakaan Java. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/java/).

## Langkah 1: Membuat Dokumen Word

Mari kita mulai dengan membuat dokumen Word yang nantinya akan kita konversi ke format Markdown. Anda dapat menyesuaikan dokumen ini sesuai kebutuhan Anda.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan tabel dengan dua sel
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// Simpan dokumen sebagai penurunan harga
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 Dalam contoh ini, kita membuat tabel sederhana dengan dua sel dan mengatur perataan paragraf di dalam sel tersebut. Kemudian, kami menyimpan dokumen sebagai Markdown menggunakan`MarkdownSaveOptions`.

## Langkah 2: Sesuaikan Perataan Isi Tabel

Aspose.Words untuk Java memungkinkan Anda menyesuaikan perataan konten tabel saat menyimpan sebagai Penurunan Harga. Anda bisa meratakan isi tabel ke kiri, kanan, tengah, atau membiarkannya ditentukan secara otomatis berdasarkan paragraf pertama di setiap kolom tabel.

Berikut cara menyesuaikan perataan konten tabel:

```java
// Atur perataan isi tabel ke kiri
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// Atur perataan isi tabel ke kanan
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// Atur perataan isi tabel ke tengah
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//Atur perataan isi tabel ke otomatis (ditentukan oleh paragraf pertama)
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 Dengan mengubah`TableContentAlignment` properti, Anda dapat mengontrol bagaimana konten di dalam tabel disejajarkan saat mengonversi ke Penurunan harga.

## Langkah 3: Menangani Gambar

 Untuk memasukkan gambar ke dalam dokumen Markdown, Anda perlu menentukan folder tempat gambar tersebut berada. Aspose.Words untuk Java memungkinkan Anda mengatur folder gambar di`MarkdownSaveOptions`.

Berikut cara mengatur folder gambar dan menyimpan dokumen dengan gambar:

```java
// Muat dokumen yang berisi gambar
Document doc = new Document("document_with_images.docx");

// Atur jalur folder gambar
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// Simpan dokumen dengan gambar
doc.save("document_with_images.md", saveOptions);
```

 Pastikan untuk mengganti`"document_with_images.docx"` dengan jalur ke dokumen Word Anda yang berisi gambar dan`"images_folder/"` dengan jalur sebenarnya ke folder tempat gambar Anda disimpan.

## Kode Sumber Lengkap Untuk Menyimpan Dokumen sebagai Penurunan Harga di Aspose.Words untuk Java

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// Membuat semua paragraf di dalam tabel menjadi sejajar.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// Penyelarasan dalam hal ini akan diambil dari paragraf pertama pada kolom tabel yang bersangkutan.
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## Kesimpulan

Dalam panduan ini, kita telah mempelajari cara menyimpan dokumen sebagai Markdown menggunakan Aspose.Words untuk Java. Kami membahas pembuatan dokumen Word, menyesuaikan perataan konten tabel, dan menangani gambar dalam file Markdown. Anda kini dapat mengonversi dokumen Word Anda ke format Markdown secara efisien, sehingga cocok untuk berbagai platform penerbitan dan kebutuhan dokumentasi.

## FAQ

### Bagaimana cara menginstal Aspose.Words untuk Java?

 Aspose.Words untuk Java dapat diinstal dengan menyertakan perpustakaan dalam proyek Java Anda. Anda dapat mengunduh perpustakaan dari[Di Sini](https://releases.aspose.com/words/java/) dan ikuti petunjuk instalasi yang disediakan dalam dokumentasi.

### Bisakah saya mengonversi dokumen Word yang kompleks dengan tabel dan gambar ke Markdown?

Ya, Aspose.Words untuk Java mendukung konversi dokumen Word yang kompleks dengan tabel, gambar, dan berbagai elemen pemformatan ke Markdown. Anda dapat menyesuaikan keluaran Penurunan harga sesuai dengan kompleksitas dokumen Anda.

### Bagaimana cara menangani gambar dalam file Markdown?

 Untuk memasukkan gambar dalam file Markdown, atur jalur folder gambar menggunakan`setImagesFolder`metode di`MarkdownSaveOptions`. Pastikan file gambar disimpan di folder yang ditentukan, dan Aspose.Words for Java akan menangani referensi gambar sesuai dengan itu.

### Apakah ada versi uji coba Aspose.Words untuk Java yang tersedia?

Ya, Anda bisa mendapatkan versi uji coba Aspose.Words untuk Java dari situs web Aspose. Versi uji coba memungkinkan Anda mengevaluasi kemampuan perpustakaan sebelum membeli lisensi.

### Di mana saya dapat menemukan lebih banyak contoh dan dokumentasi?

 Untuk contoh lebih lanjut, dokumentasi, dan informasi rinci tentang Aspose.Words untuk Java, silakan kunjungi[dokumentasi](https://reference.aspose.com/words/java/).