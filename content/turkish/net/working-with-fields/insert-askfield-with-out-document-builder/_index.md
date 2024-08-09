---
title: Belge Oluşturucu Olmadan ASKField'ı Ekle
linktitle: Belge Oluşturucu Olmadan ASKField'ı Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te Document Builder'ı kullanmadan ASK alanını nasıl ekleyeceğinizi öğrenin. Word belgelerinizi dinamik olarak geliştirmek için bu kılavuzu izleyin.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-askfield-with-out-document-builder/
---
## giriiş

Aspose.Words for .NET ile belge otomasyonunda uzmanlaşmak mı istiyorsunuz? Doğru yere geldiniz! Bugün size Belge Oluşturucu kullanmadan ASK alanını nasıl ekleyeceğinizi anlatacağız. Bu, belgenizin kullanıcılardan belirli bir giriş yapmasını istediğinizde kullanışlı bir özelliktir ve Word belgelerinizi daha etkileşimli ve dinamik hale getirir. O halde hemen konuya dalalım ve belgelerinizi daha akıllı hale getirelim!

## Önkoşullar

Bazı kodlarla elimizi kirletmeden önce her şeyin ayarlandığından emin olalım:

1.  Aspose.Words for .NET: Bu kütüphanenin kurulu olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir IDE.
3. .NET Framework: .NET Framework'ün yüklü olduğundan emin olun.

Harika! Artık hazır olduğumuza göre gerekli ad alanlarını içe aktararak başlayalım.

## Ad Alanlarını İçe Aktar

Aspose.Words for .NET'in tüm özelliklerine erişmek için öncelikle Aspose.Words ad alanını içe aktarmamız gerekiyor. İşte bunu nasıl yapacağınız:

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

## 1. Adım: Yeni Bir Belge Oluşturun

ASK alanını eklemeden önce üzerinde çalışacağımız bir belgeye ihtiyacımız var. Yeni bir belgenin nasıl oluşturulacağı aşağıda açıklanmıştır:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belge oluşturma.
Document doc = new Document();
```

Bu kod parçacığı, ASK alanımızı ekleyeceğimiz yeni bir Word belgesi oluşturur.

## Adım 2: Paragraf Düğümüne Erişin

Bir Word belgesinde içerik düğümler halinde düzenlenir. ASK alanımızı ekleyeceğimiz ilk paragraf düğümüne erişmemiz gerekiyor:

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

Bu kod satırı, belgedeki ASK alanı eklemeye hazır ilk paragrafı alır.

## 3. Adım: ASK Alanını Ekleyin

Şimdi ana olaya geçelim – ASK alanını ekleme. Bu alan, belge açıldığında kullanıcıdan giriş yapmasını isteyecektir.

```csharp
// ASK alanını ekleyin.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Burada paragrafa bir ASK alanı ekliyoruz. Basit, değil mi?

## Adım 4: ASK Alanını Yapılandırın

ASK alanının nasıl davranacağını tanımlamak için bazı özellikleri ayarlamamız gerekiyor. Yer işareti adını, bilgi istemi metnini, varsayılan yanıtı ve adres-mektup birleştirme davranışını yapılandıralım:

```csharp
field.BookmarkName = "Test1";
field.PromptText = "Please enter your response:";
field.DefaultResponse = "Default response";
field.PromptOnceOnMailMerge = true;
```

- BookmarkName: ASK alanı için benzersiz bir tanımlayıcı.
- PromptText: Kullanıcıdan giriş yapmasını isteyen metin.
- DefaultResponse: Kullanıcının değiştirebileceği önceden doldurulmuş yanıt.
- PromptOnceOnMailMerge: Adres-mektup birleştirme sırasında istemin yalnızca bir kez görünüp görünmeyeceğini belirler.

## 5. Adım: Alanı Güncelleyin

ASK alanını yapılandırdıktan sonra tüm ayarların doğru şekilde uygulandığından emin olmak için alanı güncellememiz gerekiyor:

```csharp
field.Update();
```

Bu komut, ASK alanımızın hazır olmasını ve belgede doğru şekilde ayarlanmasını sağlar.

## Adım 6: Belgeyi Kaydedin

Son olarak belgeyi belirttiğimiz dizine kaydedelim:

```csharp
doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Bu satır, belgeyi ASK alanı eklenmiş olarak kaydeder. Ve işte karşınızda; belgeniz artık dinamik bir ASK alanıyla donatıldı!

## Çözüm

Tebrikler! Aspose.Words for .NET kullanarak, Document Builder olmadan bir Word belgesine bir ASK alanı eklediniz. Bu özellik, belgelerinizle kullanıcı etkileşimini önemli ölçüde geliştirerek belgelerinizi daha esnek ve kullanıcı dostu hale getirebilir. Aspose.Words'ün tüm potansiyelini ortaya çıkarmak için farklı alanlar ve özelliklerle denemeler yapmaya devam edin. Mutlu kodlama!

## SSS'ler

### Aspose.Words'te ASK alanı nedir?
Aspose.Words'teki ASK alanı, belge açıldığında kullanıcıdan belirli bir giriş yapmasını isteyen ve dinamik veri girişine izin veren bir alandır.

### Tek bir belgede birden fazla ASK alanını kullanabilir miyim?
Evet, bir belgeye her biri benzersiz bilgi istemleri ve yanıtları olan birden fazla ASK alanı ekleyebilirsiniz.

###  Amacı nedir?`PromptOnceOnMailMerge` property?
`PromptOnceOnMailMerge` özelliği, ASK isteminin adres-mektup birleştirme işlemi sırasında yalnızca bir kez mi, yoksa her seferinde mi görüntüleneceğini belirler.

### Özelliklerini ayarladıktan sonra ASK alanını güncellemem gerekir mi?
Evet, ASK alanının güncellenmesi tüm özelliklerin doğru şekilde uygulanmasını ve alanın beklendiği gibi çalışmasını sağlar.

### Bilgi istemi metnini ve varsayılan yanıtı özelleştirebilir miyim?
Kesinlikle! ASK alanını özel ihtiyaçlarınıza göre uyarlamak için özel bilgi istemi metnini ve varsayılan yanıtları ayarlayabilirsiniz.