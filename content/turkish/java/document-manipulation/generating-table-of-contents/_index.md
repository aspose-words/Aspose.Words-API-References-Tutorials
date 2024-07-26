---
title: Aspose.Words for Java'da İçindekiler Oluşturma
linktitle: İçindekiler Oluşturuluyor
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'yı kullanarak İçindekiler Tablosunu (TOC) nasıl oluşturacağınızı ve özelleştireceğinizi öğrenin. Düzenli ve profesyonel belgeleri zahmetsizce oluşturun.
type: docs
weight: 21
url: /tr/java/document-manipulation/generating-table-of-contents/
---

## Aspose.Words for Java'da İçindekiler Oluşturmaya Giriş

Bu eğitimde, Aspose.Words for Java'yı kullanarak İçindekiler Tablosu (TOC) oluşturma sürecinde size yol göstereceğiz. TOC, organize belgeler oluşturmak için çok önemli bir özelliktir. İçindekiler Tablosunun görünümünü ve düzenini nasıl özelleştireceğimizi ele alacağız.

## Önkoşullar

Başlamadan önce Java projenizde Aspose.Words for Java'nın kurulu ve kurulu olduğundan emin olun.

## 1. Adım: Yeni Bir Belge Oluşturun

Öncelikle üzerinde çalışacağımız yeni bir belge oluşturalım.

```java
Document doc = new Document();
```

## Adım 2: İçindekiler Stillerini Özelleştirin

İçindekiler Tablonuzun görünümünü özelleştirmek için onunla ilişkili stilleri değiştirebilirsiniz. Bu örnekte birinci düzey TOC girişlerini kalın yapacağız.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## 3. Adım: Belgenize İçerik Ekleyin

İçeriğinizi belgeye ekleyebilirsiniz. Bu içerik TOC'yi oluşturmak için kullanılacaktır.

## Adım 4: TOC'yi oluşturun

İçindekiler oluşturmak için belgenizde istediğiniz konuma bir TOC alanı ekleyin. Bu alan, belgenizdeki başlıklara ve stillere göre otomatik olarak doldurulacaktır.

```java
// Belgenizde istediğiniz konuma bir TOC alanı ekleyin.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Adım 5: Belgeyi Kaydedin

Son olarak belgeyi TOC ile kaydedin.

```java
doc.save("your_output_path_here");
```

## İçindekiler Tablosunda Sekme Duraklarını Özelleştirme

Sayfa numaralarının düzenini kontrol etmek için İçindekilerinizdeki sekme duraklarını da özelleştirebilirsiniz. Sekme duraklarını şu şekilde değiştirebilirsiniz:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Bu paragrafta kullanılan, sayfa numaralarını hizalayan ilk sekmeyi alın.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Eski sekmeyi kaldırın.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Değiştirilmiş bir konuma (örneğin, 50 birim sola) yeni bir sekme ekleyin.
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Artık belgenizde, sayfa numarası hizalaması için ayarlanmış sekme duraklarıyla özelleştirilmiş bir İçindekiler Tablosu var.


## Çözüm

Bu eğitimde, Word belgeleriyle çalışmak için güçlü bir kütüphane olan Aspose.Words for Java'yı kullanarak bir İçindekiler Tablosunun (TOC) nasıl oluşturulacağını araştırdık. İyi yapılandırılmış bir TOC, uzun belgeleri düzenlemek ve gezinmek için gereklidir ve Aspose.Words, TOC'leri zahmetsizce oluşturup özelleştirmek için gerekli araçları sağlar.

## SSS'ler

### İçindekiler girişlerinin formatını nasıl değiştiririm?

 TOC düzeyleriyle ilişkili stilleri aşağıdakileri kullanarak değiştirebilirsiniz:`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`burada X, TOC seviyesidir.

### İçindekiler Tablosu'na nasıl daha fazla seviye ekleyebilirim?

İçindekiler'inize daha fazla düzey eklemek için TOC alanını değiştirebilir ve istediğiniz düzey sayısını belirleyebilirsiniz.

### Belirli İçindekiler girdileri için sekme durağı konumlarını değiştirebilir miyim?

Evet, yukarıdaki kod örneğinde gösterildiği gibi, paragraflar arasında yineleyerek ve sekme duraklarını buna göre değiştirerek belirli TOC girişleri için sekme durağı konumlarını değiştirebilirsiniz.