---
title: デジタル署名と真正性の管理
linktitle: デジタル署名と真正性の管理
second_title: Aspose.Words Python ドキュメント管理 API
description: Aspose.Words for Python を使用してデジタル署名を管理し、ドキュメントの信頼性を確保する方法を学びます。ソース コード付きのステップ バイ ステップ ガイド。
type: docs
weight: 17
url: /ja/python-net/document-combining-and-comparison/manage-digital-signatures/
---

## デジタル署名入門

デジタル署名は、手書きの署名の電子版として機能します。デジタル署名は、電子文書の真正性、整合性、および出所を確認する手段を提供します。文書がデジタル署名されると、文書の内容に基づいて暗号化ハッシュが生成されます。次に、このハッシュが署名者の秘密鍵を使用して暗号化され、デジタル署名が作成されます。対応する公開鍵を持つ人なら誰でも、署名を検証して文書の真正性を確認できます。

## Python 用 Aspose.Words の設定

Aspose.Words for Python を使用してデジタル署名の管理を開始するには、次の手順に従います。

1. Aspose.Words をインストールします。次のコマンドで pip を使用して、Aspose.Words for Python をインストールできます。
   
   ```python
   pip install aspose-words
   ```

2. 必要なモジュールをインポートする: Python スクリプトに必要なモジュールをインポートします。
   
   ```python
   import asposewords
   ```

## ドキュメントの読み込みとアクセス

デジタル署名を追加または検証する前に、Aspose.Words を使用してドキュメントを読み込む必要があります。

```python
document = asposewords.Document("document.docx")
```

## 文書にデジタル署名を追加する

ドキュメントにデジタル署名を追加するには、デジタル証明書が必要です。

```python
certificate = asposewords.Certificate("certificate.pfx", "password")
```

次に、文書に署名します。

```python
digital_signature = asposewords.DigitalSignature()
digital_signature.certificate = certificate
document.digital_signatures.add(digital_signature)
document.save("signed_document.docx")
```

## デジタル署名の検証

Aspose.Words を使用して署名されたドキュメントの信頼性を検証します。

```python
for signature in document.digital_signatures:
    if signature.is_valid:
        print("Signature is valid.")
    else:
        print("Signature is invalid.")
```

## デジタル署名の削除

ドキュメントからデジタル署名を削除するには:

```python
document.digital_signatures.clear()
document.save("unsigned_document.docx")
```

## 文書の真正性の確保

デジタル署名は、文書のソースと整合性を確認して文書の真正性を保証します。また、改ざんや不正な変更から保護します。

## デジタル署名の外観をカスタマイズする

デジタル署名の外観をカスタマイズできます。

```python
digital_signature.options.comments = "Approved by John Doe"
digital_signature.options.sign_date_time = datetime.now()
```

## 結論

デジタル署名の管理とドキュメントの信頼性の確保は、今日のデジタル環境では非常に重要です。Aspose.Words for Python は、デジタル署名の追加、検証、カスタマイズのプロセスを簡素化し、開発者がドキュメントのセキュリティと信頼性を強化できるようにします。

## よくある質問

### デジタル署名はどのように機能しますか?

デジタル署名は暗号化を使用して、署名者の秘密鍵で暗号化された文書の内容に基づいて一意のハッシュを生成します。

### デジタル署名された文書は改ざんされる可能性がありますか?

いいえ、デジタル署名された文書を改ざんすると署名が無効になり、不正な変更が行われる可能性が示されます。

### 1 つのドキュメントに複数の署名を追加できますか?

はい、1 つのドキュメントに、それぞれ異なる署名者による複数のデジタル署名を追加できます。

### どのような種類の証明書が互換性がありますか?

Aspose.Words は、デジタル署名によく使用される PFX ファイルを含む X.509 証明書をサポートしています。

### デジタル署名は法的に有効ですか?

はい、デジタル署名は多くの国で法的に有効であり、手書きの署名と同等とみなされることがよくあります。