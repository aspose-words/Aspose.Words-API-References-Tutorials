---
title: Word Belgesinde Yer İşaretli İçeriği Gizle'yi Göster
linktitle: Word Belgesinde Yer İşaretli İçeriği Gizle'yi Göster
second_title: Aspose.Words Belge İşleme API'si
description: Bu ayrıntılı, adım adım kılavuzla Aspose.Words for .NET'i kullanarak Word belgelerinde yer imlerine eklenmiş içeriği nasıl gösterip gizleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## giriiş

Aspose.Words for .NET ile belge işleme dünyasına dalmaya hazır mısınız? İster belge görevlerini otomatikleştirmek isteyen bir geliştirici olun, ister yalnızca Word dosyalarını programlı olarak işlemeyi merak eden biri olun, doğru yerdesiniz. Bugün, Aspose.Words for .NET'i kullanarak bir Word belgesinde yer imlerine eklenmiş içeriğin nasıl gösterileceğini ve gizleneceğini inceleyeceğiz. Bu adım adım kılavuz, yer işaretlerine dayalı olarak içerik görünürlüğünü kontrol etme konusunda sizi profesyonel yapacaktır. Hadi başlayalım!

## Önkoşullar

İşin özüne geçmeden önce ihtiyacınız olacak birkaç şey var:

1. Visual Studio: .NET ile uyumlu herhangi bir sürüm.
2.  Aspose.Words for .NET: İndirin[Burada](https://releases.aspose.com/words/net/).
3. Temel C# Anlayışı: Eğer basit bir "Merhaba Dünya" programı yazabiliyorsanız, hazırsınız.
4. Yer İmleri İçeren Bir Word Belgesi: Bu eğitim için yer imleri içeren örnek bir belge kullanacağız.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu, görevimiz için ihtiyacımız olan tüm araçlara sahip olmamızı sağlar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Bu ad alanları hazır olduğunda hepimiz yolculuğumuza başlamaya hazırız.

## 1. Adım: Projenizi Kurma

Tamam, projemizi Visual Studio'da ayarlayarak işe başlayalım.

### Yeni Bir Proje Oluştur

Visual Studio'yu açın ve yeni bir Konsol Uygulaması (.NET Core) projesi oluşturun. "BookmarkVisibilityManager" gibi akılda kalıcı bir ad verin.

### Aspose.Words for .NET'i ekleyin

Aspose.Words for .NET'i projenize eklemeniz gerekecek. Bunu NuGet Paket Yöneticisi aracılığıyla yapabilirsiniz.

1. Araçlar > NuGet Paket Yöneticisi > Çözüm için NuGet Paketlerini Yönet'e gidin.
2. "Aspose.Words" ifadesini arayın.
3. Paketi yükleyin.

Harika! Artık projemiz oluşturulduğuna göre belgemizi yüklemeye geçebiliriz.

## Adım 2: Belgeyi Yükleme

Yer işaretlerini içeren Word belgesini yüklememiz gerekiyor. Bu eğitim için "Bookmarks.docx" adlı örnek bir belge kullanacağız.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Bu kod parçacığı belge dizininizin yolunu belirler ve belgeyi`doc` nesne.

## 3. Adım: Yer İşaretli İçeriği Göster/Gizle

Şimdi işin eğlenceli kısmı geliyor; yer imlerine göre içeriğin gösterilmesi veya gizlenmesi. adında bir yöntem oluşturacağız.`ShowHideBookmarkedContent` bunu halletmek için.

Yer imlerine eklenen içeriğin görünürlüğünü değiştirecek yöntem aşağıda verilmiştir:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Yöntemin Dağılımı

-  Yer İşareti Alma:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` yer imini getirir.
- Düğüm Geçişi: Yer işaretinin içindeki düğümleri dolaşıyoruz.
-  Görünürlük Geçişi: Düğüm bir`Run` (bitişik bir metin dizisi),`Hidden` mülk.

## Adım 4: Yöntemin Uygulanması

Yöntemimiz uygulandığında, bunu bir yer imine dayalı içeriği göstermek veya gizlemek için uygulayalım.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Bu kod satırı, "MyBookmark1" adlı yer işaretinin içindeki içeriği gizleyecektir.

## Adım 5: Belgeyi Kaydetme

Son olarak değiştirdiğimiz belgemizi kaydedelim.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Bu, belgeyi yaptığımız değişikliklerle birlikte kaydeder.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak bir Word belgesinde yer imlerine eklenmiş içeriği nasıl gösterip gizleyeceğinizi öğrendiniz. Bu güçlü araç, ister raporları otomatikleştiriyor olun, ister şablonlar oluşturuyor olun, ister yalnızca Word dosyalarıyla uğraşıyor olun, belge üzerinde değişiklik yapmayı çocuk oyuncağı haline getirir. Mutlu kodlama!

## SSS'ler

### Aynı anda birden fazla yer imini değiştirebilir miyim?
 Evet, arayabilirsiniz`ShowHideBookmarkedContent` Geçiş yapmak istediğiniz her yer işareti için yöntem.

### İçeriği gizlemek belgenin yapısını etkiler mi?
Hayır, içeriğin gizlenmesi yalnızca görünürlüğünü etkiler. İçerik belgede kalır.

### Bu yöntemi diğer içerik türleri için kullanabilir miyim?
Bu yöntem özellikle metin çalıştırmalarını değiştirir. Diğer içerik türleri için düğüm geçiş mantığını değiştirmeniz gerekecektir.

### Aspose.Words for .NET ücretsiz mi?
 Aspose.Words ücretsiz deneme sunuyor[Burada](https://releases.aspose.com/) ancak üretimde kullanım için tam lisans gereklidir. Satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).

### Sorunla karşılaşırsam nasıl destek alabilirim?
 Aspose topluluğundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/words/8).