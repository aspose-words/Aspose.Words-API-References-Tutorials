---
title: Pisahkan Dokumen Word Berdasarkan Bagian
linktitle: Pisahkan Dokumen Word Berdasarkan Bagian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membagi dokumen Word menjadi beberapa bagian terpisah menggunakan Aspose.Words untuk .NET dengan contoh kode lengkap.
type: docs
weight: 10
url: /id/net/split-document/by-sections/
---

Dalam contoh ini, kami akan menunjukkan kepada Anda cara membagi dokumen Word menjadi beberapa bagian terpisah menggunakan fitur Berdasarkan Bagian dari Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan mendapatkan dokumen terpisah untuk setiap bagian.

## Langkah 1: Memuat dokumen

Untuk memulai, kita perlu menentukan direktori dokumen Anda dan memuat dokumen ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Langkah 2: Bagilah dokumen menjadi beberapa bagian

Sekarang kita akan mengulangi setiap bagian dokumen dan memecah dokumen menjadi bagian-bagian yang lebih kecil, bagian demi bagian. Berikut cara melakukannya:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Pisahkan dokumen menjadi bagian-bagian yang lebih kecil, dalam hal ini, pisahkan berdasarkan bagian.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Simpan setiap bagian sebagai dokumen terpisah.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Contoh kode sumber untuk Bagian Berdasarkan menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fitur By Sections Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

for (int i = 0; i < doc.Sections.Count; i++)
{
	//Pisahkan dokumen menjadi beberapa bagian yang lebih kecil, dalam hal ini, pisahkan berdasarkan bagian.
	Section section = doc.Sections[i].Clone();

	Document newDoc = new Document();
	newDoc.Sections.Clear();

	Section newSection = (Section) newDoc.ImportNode(section, true);
	newDoc.Sections.Add(newSection);

	// Simpan setiap bagian sebagai dokumen terpisah.
	newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
}
```

Dengan kode ini Anda akan dapat membagi dokumen Word menjadi beberapa bagian terpisah menggunakan Aspose.Words untuk .NET.

Sekarang Anda dapat dengan mudah bekerja dengan bagian tertentu.

### Kesimpulan

Dalam tutorial ini, kita menjelajahi fungsionalitas Split Document By Sections dari Aspose.Words untuk .NET. Kami mempelajari cara membagi dokumen Word menjadi beberapa bagian terpisah, membuat dokumen individual untuk setiap bagian. Dengan memuat dokumen, mengulangi setiap bagian, dan menyimpannya sebagai dokumen terpisah, kami dapat bekerja secara efektif dengan bagian tertentu.

Menggunakan fitur Pisahkan Dokumen Berdasarkan Bagian dapat bermanfaat ketika Anda perlu memanipulasi atau menganalisis bagian tertentu dari dokumen, seperti bab, bagian, atau divisi lainnya. Aspose.Words untuk .NET memberikan solusi yang andal dan mudah untuk menangani pemisahan bagian, memungkinkan pemrosesan dokumen yang efisien.

Jangan ragu untuk menjelajahi fitur canggih lainnya yang ditawarkan oleh Aspose.Words untuk .NET untuk meningkatkan kemampuan pemrosesan dokumen dan menyederhanakan alur kerja Anda.

### FAQ

#### Q1: Dapatkah saya membagi dokumen Word menjadi beberapa bagian berdasarkan kriteria tertentu selain pemisah bagian?
Ya, Anda dapat menyesuaikan kriteria pemisahan sesuai dengan kebutuhan spesifik Anda. Selain hentian bagian, Anda dapat membagi dokumen berdasarkan elemen lain seperti judul, bookmark, atau konten tertentu menggunakan berbagai fitur dan metode yang disediakan oleh Aspose.Words untuk .NET.

#### Q2: Apakah mungkin untuk menggabungkan kembali bagian-bagian tersebut menjadi satu dokumen?
 Ya, Anda dapat menggabungkan kembali bagian-bagian yang terpisah menjadi satu dokumen dengan mengimpor dan menggabungkan bagian-bagian dari beberapa dokumen menggunakan`ImportNode` Dan`Sections.Add` metode. Hal ini memungkinkan Anda membalikkan proses pemisahan dan merekonstruksi dokumen asli.

#### Q3: Apakah ada batasan jumlah bagian yang dapat dibagi menggunakan fitur "Berdasarkan Bagian"?
Jumlah bagian yang dapat dipisahkan menggunakan fitur "Berdasarkan Bagian" bergantung pada kemampuan Aspose.Words untuk .NET dan sumber daya sistem yang tersedia. Secara umum, ini mendukung pemisahan dokumen dengan jumlah bagian yang banyak, namun dokumen yang sangat panjang atau jumlah bagian yang sangat banyak mungkin memerlukan sumber daya sistem tambahan dan waktu pemrosesan.

#### Q4: Dapatkah saya melakukan operasi tertentu pada setiap bagian setelah pemisahan?
Ya, setelah membagi dokumen menjadi beberapa bagian terpisah, Anda dapat melakukan operasi spesifik pada setiap bagian satu per satu. Anda dapat memanipulasi konten, menerapkan pemformatan, mengekstrak informasi spesifik, atau melakukan tugas pemrosesan dokumen lainnya sesuai kebutuhan Anda.

#### Q5: Dapatkah saya membagi dokumen Word yang dilindungi kata sandi atau terenkripsi menggunakan fitur "Berdasarkan Bagian"?
Tidak, fitur "Berdasarkan Bagian" berfungsi pada dokumen Word yang tidak dilindungi. Jika dokumen dilindungi kata sandi atau dienkripsi, Anda harus memberikan kata sandi yang benar dan menghapus perlindungan sebelum membagi dokumen menjadi beberapa bagian.
