---
title: Belge Oluşturucu Olmadan TOA Alanını Ekle
linktitle: Belge Oluşturucu Olmadan TOA Alanını Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te belge oluşturucu kullanmadan TOA alanını nasıl ekleyeceğinizi öğrenin. Yasal alıntıları verimli bir şekilde yönetmek için adım adım kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-toafield-without-document-builder/
---
## giriiş

Bir Word belgesinde Yetki Tablosu (TOA) alanı oluşturmak, karmaşık bir bulmacanın parçalarını bir araya getirmek gibi gelebilir. Ancak Aspose.Words for .NET'in yardımıyla süreç sorunsuz ve anlaşılır hale geliyor. Bu makalede, bir belge oluşturucu kullanmadan TOA alanı ekleme adımlarında size yol göstererek, Word belgelerinizdeki alıntılarınızı ve yasal referanslarınızı yönetmenizi kolaylaştıracağız.

## Önkoşullar

Eğiticiye dalmadan önce ihtiyacınız olacak temel bilgileri ele alalım:

-  Aspose.Words for .NET: En son sürümün kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/words/net/).
- Geliştirme Ortamı: Visual Studio gibi .NET uyumlu bir IDE.
- Temel C# Bilgisi: Temel C# sözdizimini ve kavramlarını anlamak faydalı olacaktır.
- Örnek Word Belgesi: TOA alanını eklemek istediğiniz yere örnek bir belge oluşturun veya hazır bulundurun.

## Ad Alanlarını İçe Aktar

Başlamak için gerekli ad alanlarını Aspose.Words kütüphanesinden içe aktarmanız gerekir. Bu kurulum, belge işleme için gereken tüm sınıflara ve yöntemlere erişmenizi sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Süreci basit, takip edilmesi kolay adımlara ayıralım. Her kod parçasının ne yaptığını ve TOA alanının oluşturulmasına nasıl katkıda bulunduğunu açıklayarak her aşamada size rehberlik edeceğiz.

## 1. Adım: Belgeyi Başlatın

 İlk önce bir örneğini oluşturmanız gerekir.`Document` sınıf. Bu nesne üzerinde çalıştığınız Word belgesini temsil eder.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Bu kod yeni bir Word belgesini başlatır. Bunu, içeriğinizi ekleyeceğiniz boş bir tuval oluşturmak olarak düşünebilirsiniz.

## 2. Adım: TA Alanını Oluşturun ve Yapılandırın

Daha sonra TA (Yetki Tablosu) alanını ekleyeceğiz. Bu alan TOA'da görünecek girişleri işaretler.

```csharp
Paragraph para = new Paragraph(doc);

// TA ve TOA alanlarını şu şekilde eklemek istiyoruz:
// { TA \c 1 \l "Değer 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

İşte bir döküm:
- Paragraf para = yeni Paragraf(doc);: Belge içinde yeni bir paragraf oluşturur.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Paragrafa bir TA alanı ekler.`FieldType.FieldTOAEntry` bunun bir TOA giriş alanı olduğunu belirtir.
- fieldTA.EntryCategory = "1";: Giriş kategorisini ayarlar. Bu, farklı giriş türlerini kategorize etmek için kullanışlıdır.
- fieldTA.LongCitation = "Değer 0";: Uzun alıntı metnini belirtir. Bu TOA'da görünecek metindir.
- doc.FirstSection.Body.AppendChild(para);: TA alanını içeren paragrafı belgenin gövdesine ekler.

## 3. Adım: TOA Alanını Ekleyin

Şimdi, tüm TA girişlerini bir tabloya derleyen gerçek TOA alanını ekleyeceğiz.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

Bu adımda:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Paragrafa bir TOA alanı ekler.
- fieldToa.EntryCategory = "1";: Girişleri yalnızca "1" kategorisiyle işaretlenenleri içerecek şekilde filtreler.

## 4. Adım: TOA Alanını Güncelleyin

TOA alanını ekledikten sonra, en son girişleri yansıttığından emin olmak için alanı güncellemeniz gerekir.

```csharp
fieldToa.Update();
```

Bu komut TOA alanını yenileyerek tüm işaretli girişlerin tabloda doğru şekilde görüntülenmesini sağlar.

## Adım 5: Belgeyi Kaydedin

Son olarak yeni eklenen TOA alanıyla belgenizi kaydedin.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Bu kod satırı belgeyi belirtilen dizine kaydeder. Değiştirdiğinizden emin olun`"YOUR DOCUMENT DIRECTORY"` dosyanızı kaydetmek istediğiniz gerçek yolla.

## Çözüm

Ve işte karşınızda! Bir belge oluşturucuyu kullanmadan bir Word belgesine başarıyla bir TOA alanı eklediniz. Bu adımları izleyerek alıntıları verimli bir şekilde yönetebilir ve yasal belgelerinizde kapsamlı yetki tabloları oluşturabilirsiniz. Aspose.Words for .NET bu süreci sorunsuz ve verimli hale getirerek karmaşık belge görevlerini kolaylıkla halletmeniz için gerekli araçları sağlar.

## SSS'ler

### Farklı kategorilere sahip birden fazla TA alanı ekleyebilir miyim?
 Evet, farklı kategorilerdeki birden fazla TA alanını ayarlayarak ekleyebilirsiniz.`EntryCategory`buna göre mülk.

### TOA'nın görünümünü nasıl özelleştirebilirim?
TOA alanının giriş biçimlendirmesi ve kategori etiketleri gibi özelliklerini değiştirerek TOA'nın görünümünü özelleştirebilirsiniz.

### TOA alanını otomatik olarak güncellemek mümkün mü?
 TOA alanını kullanarak manuel olarak güncelleyebilirsiniz.`Update` Aspose.Words şu anda belge değişikliklerinde otomatik güncellemeleri desteklememektedir.

### Belgenin belirli bölümlerine TA alanlarını programlı olarak ekleyebilir miyim?
Evet, TA alanlarını istediğiniz paragraf veya bölümlere ekleyerek belirli konumlara ekleyebilirsiniz.

### Tek bir belgede birden fazla TOA alanını nasıl yönetirim?
 Farklı TOA alanlarını atayarak birden fazla TOA alanını yönetebilirsiniz.`EntryCategory` değerler ve her TOA alanının girdileri kategorisine göre filtrelemesini sağlamak.