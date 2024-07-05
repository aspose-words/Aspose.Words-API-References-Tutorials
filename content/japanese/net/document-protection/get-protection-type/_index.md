---
title: Word 文書の保護タイプを取得する
linktitle: Word 文書の保護タイプを取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Word 文書の保護タイプの取得機能を使用して、文書の保護タイプを確認する方法を学習します。
type: docs
weight: 10
url: /ja/net/document-protection/get-protection-type/
---
Aspose.Words for .NET の Get Protection Type 機能の C# ソース コードを説明するステップ バイ ステップ ガイドへようこそ。この記事では、この強力な機能を使用してドキュメントの保護タイプを判断する方法を説明します。ドキュメントの保護は、ファイルの機密性と整合性を確保するために不可欠です。Aspose.Words for .NET を統合し、Get Protection Type 機能を使用するために必要な手順を説明します。

## ステップ1: ドキュメントの読み込み

Get Protection Type 機能を使用するための最初の手順は、作業するドキュメントをアップロードすることです。これは、Aspose.Words for .NET によって提供される Document クラスを使用して実行できます。ファイルからドキュメントを読み込むサンプル コードを次に示します。

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

ドキュメント ファイルへの正しいパスを必ず指定してください。

## ステップ2: 保護タイプの取得

ドキュメントをアップロードした後、Document オブジェクトの ProtectionType プロパティを使用して、ドキュメントに適用されている保護の種類を取得できます。方法は次のとおりです。

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Aspose.Words for .NET を使用して保護タイプを取得するためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用した Get Protection Type 関数の完全なソース コードです。

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## 結論

この記事では、Aspose.Words for .NET の Get Protection Type 関数を使用してドキュメントの保護タイプを判断する方法について説明しました。説明されている手順に従うことで、この機能を独自の C# プロジェクトに簡単に統合し、保護されたドキュメントを効率的に操作できるようになります。Aspose.Words for .NET は優れた柔軟性を提供します。

### よくある質問

#### Q: Aspose.Words for .NET の ProtectionType プロパティとは何ですか?

 A:`ProtectionType` Aspose.Words for .NET のプロパティは、Word 文書に適用される保護の種類を決定できる機能です。コメント、変更、フォーム、その他の種類の制限に対して文書が保護されているかどうかなど、文書の保護レベルに関する情報を提供します。

#### Q: Aspose.Words for .NET を使用してドキュメントの保護タイプを取得するにはどうすればよいですか?

A: Aspose.Words for .NET を使用してドキュメントの保護タイプを取得するには、次の手順に従います。
1. ドキュメントをロードするには、`Document`クラス。
2. アクセス`ProtectionType`の財産`Document`保護タイプを取得するオブジェクト。

#### Q: ProtectionType プロパティを使用して、ドキュメントがフォームまたはフォーム フィールドに対して保護されているかどうかを確認できますか?

 A: はい、フォームまたはフォームフィールドに対して文書が保護されているかどうかは、`ProtectionType` Aspose.Words for .NETのプロパティ。保護タイプが`AllowOnlyFormFields`は、ドキュメントが保護されており、フォーム フィールドのみを編集できることを示します。

#### Q: ProtectionType プロパティは他にどのような保護タイプを返すことができますか?

 A:`ProtectionType` Aspose.Words for .NET のプロパティは、次のようなさまざまな保護タイプを返すことができます。
- `NoProtection`: ドキュメントは保護されていません。
- `AllowOnlyRevisions`: ドキュメントは保護されており、修正のみ行うことができます。
- `AllowOnlyComments`: ドキュメントは保護されており、コメントのみを追加できます。
- `AllowOnlyFormFields`: ドキュメントは保護されており、フォーム フィールドのみ編集できます。
- `ReadOnly`: ドキュメントは保護されており、読み取り専用に設定されています。

#### Q: ProtectionType プロパティを使用してドキュメントの保護タイプを変更できますか?

 A: いいえ、`ProtectionType`Aspose.Words for .NET のプロパティは読み取り専用プロパティです。このプロパティを使用すると、ドキュメントの現在の保護タイプを取得できますが、保護タイプを直接変更することはできません。保護タイプを変更するには、`Document`クラス、例えば`Protect`または`Unprotect`.

#### Q: 複数の保護タイプを同時に使用してドキュメントを保護することは可能ですか?

A: いいえ、Aspose.Words for .NET では、ドキュメントに一度に適用できる保護の種類は 1 つだけです。ただし、保護を有効にし、1 つの種類を設定して保護を無効にし、別の種類で再度有効にすることで、異なる保護の種類を組み合わせることができます。

