---
title: Masayı Bir Arada Tutun
linktitle: Masayı Bir Arada Tutun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak tabloların Word belgelerindeki sayfalar arasında bölünmesini nasıl önleyeceğinizi öğrenin. Profesyonel, okunabilir belgelere sahip olmak için kılavuzumuzu izleyin.
type: docs
weight: 10
url: /tr/net/programming-with-tables/keep-table-together/
---
## giriiş

Word belgenizdeki bir tablo iki sayfaya bölündüğünde hiç hayal kırıklığına uğradınız mı? Sanki özenle hazırlanmış bilgileriniz aniden yarı yolda ara vermeye karar vermiş gibi! Tabloların tek sayfada bir arada tutulması okunabilirlik ve sunum açısından çok önemlidir. İster bir rapor, ister bir proje teklifi, ister yalnızca kişisel bir belge için olsun, tabloların bölünmüş olması oldukça sarsıcı olabilir. Şanslıyız ki Aspose.Words for .NET bu sorunu çözmenin şık bir yolunu sunuyor. Bu eğitimde, masalarınızın sağlam ve şık görünmesini sağlayacak adımları izleyeceğiz. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Words for .NET - Henüz yüklemediyseniz şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/net/).
2. Tablolu Bir Word Belgesi - Birden fazla sayfaya yayılan bir tabloya sahip örnek bir belgeyle çalışacağız.
3. Temel C# Bilgisi - Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktaralım. Bu bize Aspose.Words for .NET'ten ihtiyacımız olan sınıflara ve yöntemlere erişmemizi sağlayacak.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Süreci kolay, sindirilebilir adımlara ayıralım. Belgemizi yükleyerek başlayacağız ve güncellenen belgeyi tablonun bir arada kalacağı yere kaydederek bitireceğiz.

## 1. Adım: Belgeyi Yükleyin

 Bir Word belgesiyle çalışmak için önce onu yüklememiz gerekir. biz kullanacağız`Document` Bunun için sınıf.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Adım 2: Tabloya Erişin

Daha sonra bir arada tutmak istediğimiz masayı almamız gerekiyor. Bunun belgedeki ilk tablo olduğunu varsayacağız.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Adım 3: Paragraflar için KeepWithNext'i Ayarlayın

 Tablonun sayfalar arasında bölünmesini önlemek için,`KeepWithNext` Son satırdaki son paragraflar hariç, tablodaki her paragrafın özelliği.

```csharp
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
    cell.EnsureMinimum();
    foreach (Paragraph para in cell.Paragraphs)
    {
        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }
}
```

## Adım 4: Belgeyi Kaydedin

Son olarak güncellenen belgeyi kaydediyoruz. Bu, değişikliklerimizi uygulayacak ve tablonun tek sayfada bir arada kalmasını sağlayacaktır.

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Çözüm

Ve işte karşınızda! Yalnızca birkaç satır kodla, tablolarınızın Word belgelerinizdeki sayfalara bölünmesini önleyebilirsiniz. Bu basit ama etkili çözüm, tablolarınızın düzenli ve profesyonel kalmasını sağlayarak belgelerinizin okunabilirliğini artırır. Aspose.Words for .NET, bu tür biçimlendirme sorunlarının üstesinden gelmeyi kolaylaştırarak harika içerik oluşturmaya odaklanmanıza olanak tanır.

## SSS'ler

### Bu yöntemi kullanarak birden fazla tabloyu bir arada tutabilir miyim?  
Evet, belgenizdeki her tabloyu yineleyerek aynı mantığı birden çok tabloya uygulayabilirsiniz.

### Tablom bir sayfaya sığmayacak kadar büyükse ne olur?  
Bir tablo tek bir sayfaya sığmayacak kadar büyükse yine de sayfalara yayılacaktır. Bu yöntem, daha küçük tabloların bölünmeden sağlam kalmasını sağlar.

### Bunu bir belgedeki tüm tablolar için otomatikleştirmenin bir yolu var mı?  
 Evet, belgenizdeki tüm tablolar arasında geçiş yapabilir ve`KeepWithNext` her paragrafın özelliği.

### Aspose.Words for .NET için ücretli bir lisansa ihtiyacım var mı?  
Ücretsiz deneme sürümüyle şu adresten başlayabilirsiniz:[Burada](https://releases.aspose.com/)ancak tam işlevsellik için ücretli bir lisans önerilir.

### Tabloyu bir arada tutarken tabloya başka biçimlendirme uygulayabilir miyim?  
Kesinlikle! Tablonuzun tek sayfada bir arada kalmasını sağlarken gerektiği gibi biçimlendirebilirsiniz.