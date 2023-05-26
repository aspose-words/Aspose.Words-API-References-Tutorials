---
title: Alanları Sil
linktitle: Alanları Sil
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinizdeki birleştirme alanlarını silmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fields/delete-fields/
---

Aspose'da "Alanları Sil" özelliğinin nasıl kullanılacağını açıklamak. .NET için kelimeler, aşağıda adım adım bir kılavuz oluşturduk. 

İstenen sonuçları elde etmek için her adımı yakından takip etmek önemlidir. 

## 1. Adım: Yeni Belge Oluşturma

Bu kod parçacığında, aşağıdaki satırı kullanarak yeni bir boş belge oluşturarak başlıyoruz: 

```csharp
Document doc = new Document();
```

## 2. Adım: Birleştirme Alanlarını Kaldırın

 Belgede bulunan tüm birleştirme alanlarını kaldırmak için`DeleteFields()` işlev. 

Bu, özellikle yalnızca statik içeriği tutmak ve herhangi bir birleştirme bilgisini kaldırmak istiyorsanız kullanışlıdır. 

### Aspose.Words for .NET ile Alanları Silme Kaynak Kodu Örneği

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Mevcut belgeyi yükleyin.
Document doc = new Document(dataDir + "YourDocument.docx");

// Birleştirme alanlarını kaldırın.
doc.MailMerge.DeleteFields();

// Değiştirilen belgeyi kaydedin.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 Örneğimizde, çağırmadan önce mevcut bir belgeyi yüklüyoruz.`DeleteFields()`. Son olarak değiştirilen belgeyi yeni bir dosya adıyla kaydediyoruz. 

Aspose.Words for .NET'in "Alanları Kaldır" özelliğini kullanarak birleştirme alanlarını bir belgeden etkili bir şekilde kaldırmak için bu örnekten bir ipucu alın. 

"BELGELER DİZİNİNİZİ" kendi dizin yolunuzla değiştirmeyi her zaman unutmayın. 

Aspose.Words for .NET aracılığıyla "Alanları Sil" işlevselliğini uygulamaya yönelik rehberimiz böylece tamamlanmış oldu.