---
title: Menyimpan Dokumen sebagai Format OOXML di Aspose.Words untuk Java
linktitle: Menyimpan Dokumen sebagai Format OOXML
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menyimpan dokumen dalam format OOXML dengan Aspose.Words untuk Java. Amankan, optimalkan, dan sesuaikan file Anda dengan mudah.
type: docs
weight: 20
url: /id/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Pengantar Menyimpan Dokumen sebagai Format OOXML di Aspose.Words untuk Java

Dalam panduan ini, kita akan mempelajari cara menyimpan dokumen dalam format OOXML menggunakan Aspose.Words untuk Java. OOXML (Office Open XML) adalah format file yang digunakan oleh Microsoft Word dan aplikasi perkantoran lainnya. Kami akan membahas berbagai opsi dan pengaturan untuk menyimpan dokumen dalam format OOXML.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan pustaka Aspose.Words untuk Java di proyek Anda.

## Menyimpan Dokumen dengan Enkripsi Kata Sandi

Anda dapat mengenkripsi dokumen Anda dengan kata sandi sambil menyimpannya dalam format OOXML. Inilah cara Anda melakukannya:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Muat dokumen
Document doc = new Document("Document.docx");

// Buat OoxmlSaveOptions dan atur kata sandi
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Simpan dokumen dengan enkripsi
doc.save("EncryptedDoc.docx", saveOptions);
```

## Mengatur Kepatuhan OOXML

Anda dapat menentukan tingkat kepatuhan OOXML saat menyimpan dokumen. Misalnya, Anda dapat mengaturnya ke ISO 29500:2008 (Ketat). Begini caranya:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Muat dokumen
Document doc = new Document("Document.docx");

// Optimalkan untuk Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Buat OoxmlSaveOptions dan atur tingkat kepatuhan
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Simpan dokumen dengan pengaturan kepatuhan
doc.save("ComplianceDoc.docx", saveOptions);
```

## Memperbarui Properti Waktu Tersimpan Terakhir

Anda dapat memilih untuk memperbarui properti "Waktu Tersimpan Terakhir" pada dokumen saat menyimpannya. Begini caranya:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Muat dokumen
Document doc = new Document("Document.docx");

// Buat OoxmlSaveOptions dan aktifkan pembaruan properti Waktu Tersimpan Terakhir
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Simpan dokumen dengan properti yang diperbarui
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Mempertahankan Karakter Kontrol Warisan

Jika dokumen Anda berisi karakter kontrol lama, Anda dapat memilih untuk menyimpannya saat menyimpannya. Begini caranya:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

// Muat dokumen dengan karakter kontrol lama
Document doc = new Document("LegacyControlChars.doc");

//Buat OoxmlSaveOptions dengan format FLAT_OPC dan aktifkan penyimpanan karakter kontrol lama
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// Simpan dokumen dengan karakter kontrol lama
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Mengatur Tingkat Kompresi

Anda dapat mengatur tingkat kompresi saat menyimpan dokumen. Misalnya, Anda dapat menyetelnya ke SUPER_FAST untuk kompresi minimal. Begini caranya:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Muat dokumen
Document doc = new Document("Document.docx");

// Buat OoxmlSaveOptions dan atur tingkat kompresi
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Simpan dokumen dengan tingkat kompresi yang ditentukan
doc.save("FastCompressionDoc.docx", saveOptions);
```

Ini adalah beberapa opsi dan pengaturan utama yang dapat Anda gunakan saat menyimpan dokumen dalam format OOXML menggunakan Aspose.Words untuk Java. Jangan ragu untuk menjelajahi lebih banyak opsi dan menyesuaikan proses penyimpanan dokumen sesuai kebutuhan.

## Kode Sumber Lengkap Untuk Menyimpan Dokumen sebagai Format OOXML di Aspose.Words untuk Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## Kesimpulan

Dalam panduan komprehensif ini, kami telah mempelajari cara menyimpan dokumen dalam format OOXML menggunakan Aspose.Words untuk Java. Baik Anda perlu mengenkripsi dokumen Anda dengan kata sandi, memastikan kepatuhan terhadap standar OOXML tertentu, memperbarui properti dokumen, mempertahankan karakter kontrol lama, atau menyesuaikan tingkat kompresi, Aspose.Words menyediakan serangkaian alat serbaguna untuk memenuhi kebutuhan Anda.

## FAQ

### Bagaimana cara menghapus proteksi kata sandi dari dokumen yang dilindungi kata sandi?

Untuk menghapus proteksi kata sandi dari dokumen yang dilindungi kata sandi, Anda dapat membuka dokumen dengan kata sandi yang benar lalu menyimpannya tanpa menentukan kata sandi di opsi penyimpanan. Ini akan menyimpan dokumen tanpa proteksi kata sandi.

### Bisakah saya mengatur properti khusus saat menyimpan dokumen dalam format OOXML?

 Ya, Anda dapat mengatur properti khusus untuk dokumen sebelum menyimpannya dalam format OOXML. Menggunakan`BuiltInDocumentProperties` Dan`CustomDocumentProperties` kelas untuk mengatur berbagai properti seperti penulis, judul, kata kunci, dan properti khusus.

### Berapa tingkat kompresi default saat menyimpan dokumen dalam format OOXML?

 Tingkat kompresi default saat menyimpan dokumen dalam format OOXML menggunakan Aspose.Words untuk Java adalah`NORMAL` . Anda dapat mengubah tingkat kompresi menjadi`SUPER_FAST` atau`MAXIMUM` sesuai kebutuhan.