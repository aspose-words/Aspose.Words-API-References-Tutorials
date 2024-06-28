---
title: Opsi Penyimpanan Dokumen HTML Tingkat Lanjut dengan Aspose.Words Java
linktitle: Menyimpan Dokumen HTML dengan
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Dalam tutorial ini, kami telah membahas berbagai opsi penyimpanan dokumen HTML tingkat lanjut dengan Aspose.Words untuk Java. Opsi ini memberdayakan Anda untuk membuat HTML berkualitas tinggi.
type: docs
weight: 16
url: /id/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Dalam tutorial ini, kita akan menjelajahi opsi penyimpanan dokumen HTML tingkat lanjut yang disediakan oleh Aspose.Words untuk Java. Aspose.Words adalah Java API yang kuat untuk bekerja dengan dokumen Word, dan menawarkan berbagai fitur untuk manipulasi dan konversi dokumen.

## 1. Perkenalan
Aspose.Words untuk Java memungkinkan Anda bekerja dengan dokumen Word secara terprogram. Dalam tutorial ini, kami akan fokus pada opsi penyimpanan dokumen HTML tingkat lanjut, yang memungkinkan Anda mengontrol bagaimana dokumen Word dikonversi ke HTML.

## 2. Ekspor Informasi Pulang Pergi
 Itu`exportRoundtripInformation` metode ini memungkinkan Anda mengekspor dokumen Word ke HTML sambil menyimpan informasi bolak-balik. Informasi ini dapat berguna ketika Anda ingin mengonversi HTML kembali ke format Word tanpa kehilangan detail spesifik dokumen apa pun.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Ekspor Font sebagai Base64
 Dengan`exportFontsAsBase64` metode ini, Anda dapat mengekspor font yang digunakan dalam dokumen sebagai data berkode Base64 dalam HTML. Hal ini memastikan bahwa representasi HTML mempertahankan gaya font yang sama seperti dokumen Word asli.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Ekspor Sumber Daya
 Itu`exportResources` Metode ini memungkinkan Anda menentukan jenis stylesheet CSS dan mengekspor sumber daya font. Anda juga dapat mengatur folder sumber daya dan alias sumber daya dalam HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://contoh.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Konversikan Metafile ke EMF atau WMF
 Itu`convertMetafilesToEmfOrWmf`Metode ini memungkinkan Anda mengonversi metafile dalam dokumen ke format EMF atau WMF, memastikan kompatibilitas dan rendering yang lancar dalam HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Cuplikan kode tidak ditampilkan agar singkatnya.
}
```

## 6. Konversikan Metafile ke SVG
 Menggunakan`convertMetafilesToSvg` metode untuk mengonversi metafile ke format SVG. Format ini ideal untuk menampilkan grafik vektor dalam dokumen HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Cuplikan kode tidak ditampilkan agar singkatnya.
}
```

## 7. Tambahkan Awalan Nama Kelas CSS
 Dengan`addCssClassNamePrefix` metode, Anda dapat menambahkan awalan ke nama kelas CSS di HTML yang diekspor. Ini membantu mencegah konflik dengan gaya yang ada.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Ekspor URL CID untuk Sumber Daya MHTML
 Itu`exportCidUrlsForMhtmlResources` metode ini digunakan saat menyimpan dokumen dalam format MHTML. Ini memungkinkan ekspor URL Content-ID untuk sumber daya.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Cuplikan kode tidak ditampilkan agar singkatnya.
}
```

## 9. Selesaikan Nama Font
 Itu`resolveFontNames` Metode ini membantu menyelesaikan nama font saat menyimpan dokumen dalam format HTML, memastikan rendering yang konsisten di berbagai platform.

```java
@Test
public void resolveFontNames() throws Exception {
    // Cuplikan kode tidak ditampilkan agar singkatnya.
}
```

## 10. Ekspor Bidang Formulir Input Teks sebagai Teks
 Itu`exportTextInputFormFieldAsText` metode mengekspor bidang formulir sebagai teks biasa dalam HTML, membuatnya mudah dibaca dan diedit.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Cuplikan kode tidak ditampilkan agar singkatnya.
}
```

## 11. Kesimpulan
Dalam tutorial ini, kita menjelajahi opsi penyimpanan dokumen HTML tingkat lanjut yang disediakan oleh Aspose.Words untuk Java. Opsi ini memberi Anda kendali penuh atas proses konversi, memungkinkan Anda membuat dokumen HTML yang sangat mirip dengan dokumen Word asli.

## 12.FAQ
Berikut adalah beberapa pertanyaan umum tentang bekerja dengan opsi penyimpanan dokumen Aspose.Words untuk Java dan HTML:

### Q1: Bagaimana cara mengonversi HTML kembali ke format Word menggunakan Aspose.Words untuk Java?
 Untuk mengonversi HTML kembali ke format Word, Anda dapat menggunakan Aspose.Words API`load` metode untuk memuat dokumen HTML dan kemudian menyimpannya dalam format Word.

### Q2: Dapatkah saya menyesuaikan gaya CSS saat mengekspor ke HTML?
 Ya, Anda dapat menyesuaikan gaya CSS dengan memodifikasi stylesheet yang digunakan dalam HTML atau dengan menggunakan`addCssClassNamePrefix` metode untuk menambahkan awalan ke nama kelas CSS.

### Q3: Apakah ada cara untuk mengoptimalkan keluaran HTML untuk tampilan web?
Ya, Anda dapat mengoptimalkan keluaran HTML untuk tampilan web dengan mengonfigurasi opsi seperti mengekspor font sebagai Base64 dan mengonversi metafile ke SVG.

### Q4: Apakah ada batasan saat mengonversi dokumen Word yang rumit ke HTML?
Meskipun Aspose.Words untuk Java memberikan kemampuan konversi yang kuat, dokumen Word yang kompleks dengan tata letak yang rumit mungkin memerlukan pasca-pemrosesan tambahan untuk mencapai keluaran HTML yang diinginkan.
