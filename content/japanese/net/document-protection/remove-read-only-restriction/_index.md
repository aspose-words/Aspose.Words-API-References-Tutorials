---
title: 読み取り専用制限を解除
linktitle: 読み取り専用制限を解除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/remove-read-only-restriction/
---
このチュートリアルでは、Aspose.Words for .NET の読み取り専用制限解除機能を使用する手順を説明します。この機能を使用すると、Word 文書から読み取り専用制限を解除して編集可能にすることができます。以下の手順に従ってください。

## ステップ1: ドキュメントの作成と保護の設定

まず、Document クラスのインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

WriteProtection オブジェクトの SetPassword() プロパティを使用してドキュメントのパスワードを設定します。

「MyPassword」は、ドキュメントを保護するために使用した実際のパスワードに置き換えてください。

## ステップ2: 読み取り専用制限を解除する

読み取り専用制限を削除するには、ReadOnlyRecommended プロパティを false に設定します。

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## ステップ3: 無制限の保護を適用する

最後に、Document オブジェクトの Protect() メソッドを使用して無制限の保護を適用します。

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

読み取り専用制限なしでドキュメントを保存するには、正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用して読み取り専用制限を削除するためのサンプル ソース コード

Aspose.Words for .NET を使用して読み取り専用制限を削除するための完全なソース コードは次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

//最大 15 文字のパスワードを入力してください。
doc.WriteProtection.SetPassword("MyPassword");

//読み取り専用オプションを削除します。
doc.WriteProtection.ReadOnlyRecommended = false;

//保護なしで書き込み保護を適用します。
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

以下の手順に従うと、Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を簡単に削除できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を削除する方法を学習しました。提供されている手順に従うことで、簡単に制限を削除し、文書を再び編集可能にすることができます。Aspose.Words for .NET は、文書の保護と制限を管理するための包括的な機能セットを提供し、Word 文書のセキュリティと編集機能に対する柔軟性と制御を提供します。

### よくある質問

#### Q: Aspose.Words for .NET の読み取り専用制限とは何ですか?

A: Aspose.Words for .NET の読み取り専用制限とは、Word 文書を読み取り専用に設定して、ユーザーがコンテンツや書式を変更できないようにする機能のことです。この制限により、文書の整合性が保護され、誤ってまたは悪意を持って変更されることがなくなります。

#### Q: Aspose.Words for .NET を使用して読み取り専用制限を解除するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を削除するには、次の手順に従います。
1. インスタンスを作成する`Document`クラスを作成し、`SetPassword`方法の`WriteProtection`物体。
2. をセットする`ReadOnlyRecommended`の財産`WriteProtection`反対する`false`読み取り専用の推奨事項を削除します。
3. 文書に無制限の保護を適用するには、`Protect`方法の`Document`オブジェクト`NoProtection`保護タイプ。
4. 読み取り専用制限なしで文書を保存するには、`Save`方法の`Document`物体。

#### Q: パスワードなしで Word 文書から読み取り専用制限を削除できますか?

A: いいえ、正しいパスワードを入力しないと、Word 文書から読み取り専用制限を解除することはできません。読み取り専用制限はセキュリティ目的で設定されており、パスワードなしで削除すると、文書の整合性を保護する目的が損なわれます。

#### Q: 間違ったパスワードを持つ Word 文書から読み取り専用制限を削除できますか?

A: いいえ、間違ったパスワードでは Word 文書から読み取り専用制限を解除できません。読み取り専用制限を解除して文書を再び編集可能にするには、正しいパスワードを入力する必要があります。これにより、正しいパスワードを持つ承認済みユーザーのみが文書を変更できるようになります。

#### Q: Aspose.Words for .NET を使用して他の種類のドキュメント保護を削除することは可能ですか?

A: はい、Aspose.Words for .NET には、パスワード保護、フォーム保護、ドキュメント編集制限など、他の種類のドキュメント保護を解除するさまざまな方法が用意されています。ドキュメントに適用されている保護の種類に応じて、Aspose.Words が提供する対応するメソッドとプロパティを使用して、特定の保護を解除し、ドキュメントを編集可能にすることができます。
