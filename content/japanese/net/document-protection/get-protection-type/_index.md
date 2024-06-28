---
title: Word 文書の保護タイプを取得
linktitle: Word 文書の保護タイプを取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Word ドキュメント関数で [保護の種類を取得] を使用して、ドキュメントの保護の種類を決定する方法を説明します。
type: docs
weight: 10
url: /ja/net/document-protection/get-protection-type/
---
Aspose.Words for .NET の保護タイプの取得機能の C# ソース コードを説明するこのステップバイステップ ガイドへようこそ。この記事では、この強力な機能を使用してドキュメントの保護の種類を決定する方法を説明します。ファイルの機密性と整合性を確保するには、文書の保護が不可欠です。 Aspose.Words for .NET を統合し、保護の種類の取得機能を使用するために必要な手順を説明します。

## ステップ 1: ドキュメントをロードする

保護タイプの取得機能を使用するための最初のステップは、作業するドキュメントをアップロードすることです。これは、Aspose.Words for .NET によって提供される Document クラスを使用して実行できます。ファイルからドキュメントをロードするサンプル コードを次に示します。

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

必ずドキュメント ファイルへの正しいパスを指定してください。

## ステップ 2: 保護タイプの取得

ドキュメントがアップロードされた後、Document オブジェクトの ProtectionType プロパティを使用して、ドキュメントに適用されている保護の種類を取得できます。その方法は次のとおりです。

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Aspose.Words for .NET を使用した保護タイプの取得のソース コード例

Aspose.Words for .NET を使用した Get Protection Type 関数の完全なソース コードは次のとおりです。

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## 結論

この記事では、Aspose.Words for .NET の Get Protection Type 関数を使用してドキュメントの保護の種類を決定する方法を説明しました。説明されている手順に従うことで、この機能を独自の C# プロジェクトに簡単に統合し、保護されたドキュメントを効率的に操作できるようになります。 Aspose.Words for .NET は優れた柔軟性を提供します

### よくある質問

#### Q: Aspose.Words for .NET の ProtectionType プロパティとは何ですか?

 A:`ProtectionType` Aspose.Words for .NET のプロパティは、Word ドキュメントに適用される保護の種類を決定できる機能です。これは、ドキュメントがコメント、改訂、フォーム、またはその他の種類の制限に対して保護されているかどうかなど、ドキュメントの保護のレベルに関する情報を提供します。

#### Q: Aspose.Words for .NET を使用してドキュメントの保護タイプを取得するにはどうすればよいですか?

A: Aspose.Words for .NET を使用してドキュメントの保護の種類を取得するには、次の手順に従います。
1. を使用してドキュメントをロードします。`Document`クラス。
2. にアクセスしてください`ProtectionType`の財産`Document`オブジェクトを使用して保護タイプを取得します。

#### Q: ProtectionType プロパティを使用して、ドキュメントがフォームまたはフォーム フィールドに対して保護されているかどうかを判断できますか?

 A: はい、ドキュメントがフォームまたはフォーム フィールドに対して保護されているかどうかを確認するには、`ProtectionType` Aspose.Words for .NET のプロパティ。保護タイプが に設定されている場合`AllowOnlyFormFields`、ドキュメントが保護されており、フォーム フィールドのみを編集できることを示します。

#### Q: ProtectionType プロパティは他にどのような保護タイプを返すことができますか?

 A:`ProtectionType` Aspose.Words for .NET のプロパティは、次のようなさまざまな保護タイプを返すことができます。
- `NoProtection`：文書は保護されていません。
- `AllowOnlyRevisions`：文書は保護されており、修正のみ可能です。
- `AllowOnlyComments`：文書は保護されており、コメントのみ追加できます。
- `AllowOnlyFormFields`: 文書は保護されており、フォームフィールドのみを編集できます。
- `ReadOnly`: ドキュメントは保護されており、読み取り専用に設定されています。

#### Q: ProtectionType プロパティを使用してドキュメントの保護の種類を変更できますか?

 A: いいえ、`ProtectionType`Aspose.Words for .NET のプロパティは読み取り専用のプロパティです。これにより、ドキュメントの現在の保護タイプを取得できますが、保護タイプを変更する直接的な手段は提供されません。保護タイプを変更するには、`Document`クラスなど`Protect`または`Unprotect`.

#### Q: 複数の保護タイプでドキュメントを同時に保護することはできますか?

A: いいえ、Aspose.Words for .NET では、ドキュメントに一度に 1 つの保護タイプのみを適用できます。ただし、保護を有効にし、1 つのタイプを設定し、保護を無効にしてから、別のタイプで再度有効にすることで、異なる保護タイプを組み合わせることができます。

