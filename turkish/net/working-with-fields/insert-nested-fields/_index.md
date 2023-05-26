---
title: İç İçe Alanlar Ekle
linktitle: İç İçe Alanlar Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile iç içe geçmiş alanları Word belgelerinize kolayca nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-nested-fields/
---

Aşağıda, Aspose.Words for .NET'in "İç İçe Alanları Ekle" özelliğini kullanan C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır. İstenen sonuçları elde etmek için her adımı dikkatlice uyguladığınızdan emin olun.

## 1. Adım: Belge Dizini Kurulumu

Sağlanan kodda, belgelerinizin dizinini belirtmeniz gerekir. "BELGE DİZİNİNİZ" değerini belgeler dizininizin uygun yolu ile değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Document ve DocumentBuilder'ı Oluşturma

Yeni bir belge oluşturarak ve bir DocumentBuilder başlatarak başlıyoruz.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Sayfa sonları ekleme

Belgeye birden fazla sayfa sonu eklemek için bir döngü kullanıyoruz.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## 4. Adım: Altbilgiye Taşıyın

 biz kullanıyoruz`MoveToHeaderFooter()` İmleci ana altbilgiye taşımak için DocumentBuilder yöntemi.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Adım 5: İç içe alan ekleme

 DocumentBuilder'ı kullanıyoruz`InsertField()` altbilgiye iç içe geçmiş bir alan ekleme yöntemi.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Son olarak, diyoruz`Update()` alanı güncelleme yöntemi.

```csharp
field. Update();
```

### Aspose.Words for .NET ile iç içe alanlar eklemek için örnek kaynak kodu

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi ve DocumentBuilder'ı oluşturun.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sayfa sonları ekleyin.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Altbilgiye git.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// İç içe alan ekleyin.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Alanı güncelleyin.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

Bu örnekte, yeni bir belge oluşturduk, sayfa sonları ekledik, imleci alt bilgiye taşıdık ve ardından alt bilgiye iç içe bir alan ekledik.