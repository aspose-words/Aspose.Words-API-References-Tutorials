---
title: Hapus Daftar Isi Dalam Dokumen Word
linktitle: Hapus Daftar Isi Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghapus daftar isi dalam dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/remove-content/remove-table-of-contents/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara menghapus daftar isi dalam dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Daftar isi terkadang berlebihan atau tidak diperlukan, dan kode ini akan membantu Anda menghapusnya secara efektif. Kami akan memberikan panduan langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda sendiri.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda
- Dokumen Word berisi daftar isi yang ingin Anda hapus

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Unggah dokumen
 Selanjutnya, kita akan memuat dokumen Word ke dalam sebuah instance`Document` kelas menggunakan`Load` metode.

```csharp
// Muat dokumen
Document doc = new Document(dataDir + "your-document.docx");
```

## Langkah 3: Hapus daftar isi
 Untuk menghapus daftar isi, kita akan mengulang tipe TOC (daftar isi).`FieldStart` node dalam dokumen. Kami akan menyimpan node ini sehingga kami dapat mengaksesnya dengan cepat dan membuat daftar node untuk dihapus.

```csharp
// Simpan node FieldStart dari bidang TOC dalam dokumen untuk akses cepat.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Ini adalah daftar untuk menyimpan node yang ditemukan di dalam TOC yang ditentukan. Mereka akan dihapus pada akhir metode ini.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Periksa apakah indeks TOC yang ditentukan ada.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Lebih aman menyimpan node-node ini dan menghapus semuanya pada akhirnya.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Saat kita menemukan node FieldEnd bertipe FieldTOC,
     //kami tahu kami berada di akhir TOC saat ini dan kami berhenti di sini.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Contoh kode sumber untuk Menghapus Daftar Isi menggunakan Aspose.Words untuk .NET 
```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Muat dokumen
Document doc = new Document(dataDir + "your-document.docx");

// Simpan node FieldStart dari bidang TOC dalam dokumen untuk akses cepat.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Ini adalah daftar untuk menyimpan node yang ditemukan di dalam TOC yang ditentukan. Mereka akan dihapus pada akhir metode ini.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Pastikan TOC yang ditentukan oleh indeks yang diteruskan ada.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Lebih aman menyimpan node ini dan menghapus semuanya sekaligus nanti.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Setelah kita menemukan node FieldEnd bertipe FieldTOC,
	// kita tahu kita berada di akhir TOC saat ini dan berhenti di sini.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Kesimpulan
Dalam tutorial ini, kami menyajikan panduan langkah demi langkah untuk menghapus daftar isi dari dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Dengan mengikuti kode dan instruksi yang diberikan, Anda dapat dengan mudah menghilangkan daftar isi dan memperbaiki tata letak dokumen Anda. Ingatlah untuk menyesuaikan jalur direktori dan nama file agar sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Mengapa saya harus menggunakan Aspose.Words untuk menghapus daftar isi di dokumen Word?

J: Aspose.Words adalah perpustakaan kelas yang kuat dan serbaguna untuk memanipulasi dokumen Word dalam aplikasi .NET. Dengan menggunakan Aspose.Words, Anda dapat menghapus daftar isi dari dokumen Anda secara efektif, yang dapat berguna jika daftar isi berlebihan atau tidak diperlukan. Ini memungkinkan Anda untuk menyesuaikan konten dokumen Anda dan meningkatkan presentasinya secara keseluruhan.

#### T: Bagaimana cara mengunggah dokumen di Aspose.Words untuk .NET?

A: Untuk menghapus daftar isi di dokumen Word, Anda harus memuat dokumen ke dalam memori terlebih dahulu menggunakan metode Load() dari Aspose.Words. Berikut ini contoh kode untuk memuat dokumen dari direktori tertentu:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "your-document.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda.

#### Q: Bagaimana cara menghapus daftar isi dokumen menggunakan Aspose.Words?

 J: Untuk menghapus TOC, Anda perlu melakukan iterasi melalui`FieldStart` ketik node TOC dalam dokumen. Anda dapat menyimpan node ini untuk akses cepat dan membuat daftar node untuk dihapus. Berikut ini contoh kodenya:

```csharp
// Simpan node FieldStart dari bidang TOC dalam dokumen untuk akses cepat.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Ini adalah daftar untuk menyimpan node yang ditemukan di dalam TOC yang ditentukan. Mereka akan dihapus pada akhir metode ini.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Periksa apakah indeks daftar isi yang ditentukan ada.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Lebih aman menyimpan node-node ini dan menghapus semuanya pada akhirnya.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Saat kita menemukan node FieldEnd bertipe FieldTOC,
//kami tahu kami berada di akhir TOC saat ini dan kami berhenti di sini.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### T: Bagaimana cara menyimpan dokumen yang diedit di Aspose.Words untuk .NET?

A: Setelah menghapus daftar isi, Anda harus menyimpan dokumen yang diubah menggunakan metode Save(). Tentukan jalur dan format file keluaran yang diinginkan (misalnya, DOCX) untuk dokumen yang diedit. Berikut ini contoh kodenya:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```