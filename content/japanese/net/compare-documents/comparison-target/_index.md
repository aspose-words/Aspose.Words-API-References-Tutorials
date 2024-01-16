---
title: Word文書内の比較対象
linktitle: Word文書内の比較対象
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Word ドキュメントのターゲット比較機能について説明します。この機能を使用すると、ドキュメントを比較し、加えられた変更を含む新しいドキュメントを生成できます。
type: docs
weight: 10
url: /ja/net/compare-documents/comparison-target/
---
ここでは、Aspose.Words for .NET の Word ドキュメント機能の比較ターゲットを使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。

## ステップ 1: はじめに

Aspose.Words for .NET のターゲット比較機能を使用すると、2 つのドキュメントを比較し、ターゲット ドキュメントに加えられた変更を含む新しいドキュメントを生成できます。これは、ドキュメントの異なるバージョン間で行われた変更を追跡するのに役立ちます。

## ステップ 2: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用できるように開発環境をセットアップする必要があります。 Aspose.Words ライブラリがインストールされていること、およびコードを埋め込むための適切な C# プロジェクトがあることを確認してください。

## ステップ 3: 必要なアセンブリを追加する

Aspose.Words for .NET の比較ターゲット機能を使用するには、必要なアセンブリをプロジェクトに追加する必要があります。プロジェクト内に Aspose.Words への適切な参照があることを確認してください。

```csharp
using Aspose.Words;
```

## ステップ 4: ドキュメントの初期化

このステップでは、比較のために 2 つのドキュメントを初期化します。ドキュメントが配置されているディレクトリ パスとソース ドキュメントの名前を指定する必要があります。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//比較するドキュメント A の初期化。
Document docA = new Document(dataDir + "DocumentA.docx");

//ドキュメント A のクローンを作成して、ドキュメント B の同一のコピーを作成します。
Document docB = docA.Clone();
```

## ステップ 5: 比較オプションの構成

このステップでは、比較オプションを構成して比較の動作を指定します。オプションには、書式設定を無視する機能や、Microsoft Word の [ドキュメントの比較] ダイアログ ボックスの [変更箇所を表示] オプションである比較対象が含まれます。

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## ステップ 6: 文書の比較

次に、ドキュメントを比較し、結果を新しいドキュメントに生成します。

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

の`Compare`このメソッドは、ドキュメント A とドキュメント B を比較し、変更をドキュメント A に保存します。参照用にユーザー名と比較の日付を指定できます。

### Aspose.Words for .NET を使用した比較ターゲットのサンプル ソース コード


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

//Microsoft Wordの「ドキュメントの比較」ダイアログボックスの「変更箇所を表示」オプションに関連します。
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## 結論

この記事では、Aspose.Words for .NET の差分ターゲット機能について説明しました。この機能を使用すると、2 つのドキュメントを比較し、加えられた変更を含む新しいドキュメントを生成できます。この知識を使用して、ドキュメントの異なるバージョン間の変更を追跡できます。

### よくある質問

#### Q: Aspose.Words for .NET で比較ターゲットを使用する目的は何ですか?

A: Aspose.Words for .NET の比較ターゲットを使用すると、2 つのドキュメントを比較し、ターゲット ドキュメントに加えられた変更を含む新しいドキュメントを生成できます。この機能は、ドキュメントの異なるバージョン間で行われた変更を追跡し、別のドキュメントの違いを視覚化するのに役立ちます。

#### Q: Aspose.Words for .NET で比較ターゲットを使用するにはどうすればよいですか?

A: Aspose.Words for .NET で比較ターゲットを使用するには、次の手順に従います。
1. Aspose.Words ライブラリを使用して開発環境をセットアップします。
2. Aspose.Words を参照して、必要なアセンブリをプロジェクトに追加します。
3. を使用して、比較するドキュメントを初期化します。`Document`クラスまたは`DocumentBuilder`クラス。
4. を作成して比較オプションを構成します。`CompareOptions`オブジェクトと設定プロパティなど`IgnoreFormatting`そして`Target`（例えば、`ComparisonTargetType.New`比較対象用）。
5. 使用`Compare`一方のドキュメントのメソッドを、もう一方のドキュメントと`CompareOptions`オブジェクトをパラメータとして指定します。このメソッドはドキュメントを比較し、最初のドキュメントの変更を保存します。

####  Q: その目的は何ですか?`Target` property in the `CompareOptions` class?

 A:`Target`のプロパティ`CompareOptions`クラスを使用すると、比較対象を指定できます。これは、Microsoft Word の [ドキュメントの比較] ダイアログ ボックスの [変更箇所を表示] オプションに似ています。ターゲットを設定できるのは、`ComparisonTargetType.New`新しいドキュメントの変更を表示するには、`ComparisonTargetType.Current`現在のドキュメントの変更を表示する、または`ComparisonTargetType.Formatting`書式の変更のみを表示します。