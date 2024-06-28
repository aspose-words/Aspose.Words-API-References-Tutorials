---
title: Daftar Gunakan Gaya Tujuan
linktitle: Daftar Gunakan Gaya Tujuan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan dan menambahkan dokumen Word sambil mempertahankan gaya daftar dokumen tujuan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/list-use-destination-styles/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Daftar Gunakan Gaya Tujuan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word saat menggunakan gaya daftar dokumen tujuan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk .NET diinstal. Anda dapat mendownloadnya dari situs Aspose atau menginstalnya melalui NuGet.
2. Visual Studio atau lingkungan pengembangan C# lainnya.

## Langkah 1: Inisialisasi Direktori Dokumen

 Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ubah nilai`dataDir` variabel ke jalur di mana dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Sumber dan Tujuan

Selanjutnya, Anda perlu memuat dokumen sumber dan tujuan menggunakan Aspose.Words.`Document` kelas. Perbarui nama file di`Document` konstruktor sesuai dengan nama dokumen Anda.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Langkah 3: Atur Dokumen Sumber untuk Dilanjutkan setelah Dokumen Tujuan

 Untuk memastikan bahwa konten dari dokumen sumber berlanjut setelah akhir dokumen tujuan, Anda perlu mengaturnya`SectionStart` properti bagian pertama dalam dokumen sumber ke`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Langkah 4: Tangani Pemformatan Daftar

Untuk menangani pemformatan daftar, Anda akan mengulangi setiap paragraf dalam dokumen sumber dan memeriksa apakah itu merupakan item daftar. Jika ya, Anda akan membandingkan ID daftar dengan daftar yang ada di dokumen tujuan. Jika ada daftar dengan ID yang sama, Anda akan membuat salinan daftar di dokumen sumber dan memperbarui format daftar paragraf untuk menggunakan daftar yang disalin.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Langkah 5: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.UseDestinationStyles` parameter memastikan bahwa gaya daftar dokumen tujuan digunakan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Langkah 6: Simpan Dokumen Akhir

Terakhir, simpan dokumen yang digabungkan dengan fitur Daftar Gunakan Gaya Tujuan yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Contoh kode sumber untuk Daftar Gunakan Gaya Tujuan menggunakan Aspose.Words untuk .NET 

Berikut kode sumber lengkap untuk fitur "Daftar Gunakan Gaya Tujuan" di C# menggunakan Aspose.Words untuk .NET:


```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Atur dokumen sumber agar dilanjutkan tepat setelah akhir dokumen tujuan.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Melacak daftar yang dibuat.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Periksa apakah dokumen tujuan sudah berisi daftar dengan ID ini. Jika ya, maka hal ini mungkin terjadi
			// menyebabkan kedua daftar berjalan bersamaan. Buat salinan daftar di dokumen sumber.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Daftar yang baru disalin sudah ada untuk ID ini, ambil daftar yang disimpan,
				// dan menggunakannya pada paragraf saat ini.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Tambahkan salinan daftar ini ke dokumen dan simpan untuk referensi nanti.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Atur daftar paragraf ini ke daftar yang disalin.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Tambahkan dokumen sumber ke akhir dokumen tujuan.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Daftar Gunakan Gaya Tujuan menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten gabungan dengan gaya daftar dari dokumen tujuan.