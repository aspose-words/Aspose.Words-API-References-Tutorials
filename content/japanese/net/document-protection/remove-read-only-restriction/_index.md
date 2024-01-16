---
title: 読み取り専用制限を解除する
linktitle: 読み取り専用制限を解除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を削除する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-protection/remove-read-only-restriction/
---
このチュートリアルでは、Aspose.Words for .NET 読み取り専用制限の削除機能を使用する手順を説明します。この機能を使用すると、Word 文書から読み取り専用制限を削除して編集可能にすることができます。以下の手順に従います。

## ステップ 1: ドキュメントの作成と保護の設定

まず、Document クラスのインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

WriteProtection オブジェクトの SetPassword() プロパティを使用して、ドキュメントのパスワードを設定します。

必ず「MyPassword」をドキュメントの保護に使用した実際のパスワードに置き換えてください。

## ステップ 2: 読み取り専用制限を削除する

読み取り専用制限を削除するには、ReadOnlyRecommend プロパティを false に設定します。

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## ステップ 3: 無制限の保護を適用する

最後に、Document オブジェクトの Protect() メソッドを使用して無制限の保護を適用します。

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

読み取り専用の制限なしでドキュメントを保存するには、必ず正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した読み取り専用制限の削除のソース コード例

Aspose.Words for .NET を使用して読み取り専用制限を削除する完全なソース コードは次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

//パスワードを 15 文字以内で入力します。
doc.WriteProtection.SetPassword("MyPassword");

//読み取り専用オプションを削除します。
doc.WriteProtection.ReadOnlyRecommended = false;

//保護を行わずに書き込み保護を適用します。
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

次の手順に従うと、Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を簡単に削除できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を削除する方法を学びました。指定された手順に従うことで、制限を簡単に解除し、ドキュメントを再び編集可能にすることができます。 Aspose.Words for .NET は、ドキュメントの保護と制限を管理するための包括的な機能セットを提供し、Word ドキュメントのセキュリティと編集機能を柔軟に制御できるようにします。

### よくある質問

#### Q: Aspose.Words for .NET の読み取り専用制限は何ですか?

A: Aspose.Words for .NET の読み取り専用制限とは、Word 文書を読み取り専用として設定し、ユーザーがコンテンツや書式を変更できないようにする機能を指します。この制限は、ドキュメントの整合性を保護し、ドキュメントが誤ってまたは悪意を持って変更されることを防ぐのに役立ちます。

#### Q: Aspose.Words for .NET を使用して読み取り専用制限を解除するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書から読み取り専用制限を削除するには、次の手順に従います。
1. のインスタンスを作成します。`Document`クラスを使用し、ドキュメントのパスワードを設定します。`SetPassword`の方法`WriteProtection`物体。
2. をセットする`ReadOnlyRecommended`の財産`WriteProtection`に反対する`false`読み取り専用の推奨を削除します。
3. を使用してドキュメントに無制限の保護を適用します。`Protect`の方法`Document`オブジェクトを使用して`NoProtection`保護タイプ。
4. を使用して、読み取り専用制限なしでドキュメントを保存します。`Save`の方法`Document`物体。

#### Q: パスワードなしで Word 文書の読み取り専用制限を解除できますか?

A: いいえ、正しいパスワードを入力しない限り、Word 文書から読み取り専用制限を解除することはできません。読み取り専用制限はセキュリティ目的で設定されており、パスワードを使用せずにこれを削除すると、ドキュメントの完全性を保護するという目的が損なわれることになります。

#### Q: パスワードが間違っている Word 文書の読み取り専用制限を解除できますか?

A: いいえ、パスワードが間違っている Word 文書の読み取り専用制限を解除することはできません。読み取り専用制限を解除してドキュメントを再度編集可能にするには、正しいパスワードを入力する必要があります。これにより、正しいパスワードを持つ承認されたユーザーのみがドキュメントを変更できるようになります。

#### Q: Aspose.Words for .NET を使用して他の種類のドキュメント保護を削除することはできますか?

A: はい。Aspose.Words for .NET には、パスワード保護、フォーム保護、ドキュメント編集制限など、他の種類のドキュメント保護を削除するためのさまざまな方法が用意されています。ドキュメントに適用されている保護の種類に応じて、Aspose.Words が提供する対応するメソッドとプロパティを使用して、特定の保護を削除し、ドキュメントを編集可能にすることができます。
