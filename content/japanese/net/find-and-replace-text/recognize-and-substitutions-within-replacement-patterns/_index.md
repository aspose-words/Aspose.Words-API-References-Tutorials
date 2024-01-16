---
title: 置換パターン内の認識と置換
linktitle: 置換パターン内の認識と置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の認識と置換による置換パターンを使用して Word ドキュメントを操作する方法を学びます。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

この記事では、Aspose.Words for .NET ライブラリの Recognize And Substitutions Within Replacement Patterns 関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能は、複雑な検索パターンを認識し、文書操作中に取得されたグループに基づいて置換を実行するのに役立ちます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

置換パターンで一致と置換の使用を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ 2: 文書にテキストを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。この例では、`Write` 「ジェイソンはポールにお金をあげます」というフレーズを挿入するメソッド。 :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## ステップ 3: 置換パターンの認識と置換

ここで使用するのは、`Range.Replace`正規表現を使用してテキストの検索と置換を実行し、特定のパターンを認識する関数。この例では、正規表現を使用します。`([A-z]+) gives money to ([A-z]+)`誰かが他の人にお金を与える文を認識する。置換パターンを使用します`$2 takes money from $1`役割を逆にして置換を実行します。の用法`$1`そして`$2`正規表現で取得されたグループを指します。

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Aspose.Words for .NET を使用した置換パターン内の認識と置換のソース コード例

Aspose.Words for .NET を使用した置換パターンでの一致と置換の使用を示す完全なソース コード例を次に示します。

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の置換パターン内の認識と置換機能の使用方法を理解しました。ステップバイステップのガイドに従って、ドキュメントの作成、テキストの挿入、正規表現とキャプチャされたグループに基づく置換パターンを使用した検索と置換の実行、ドキュメントの操作を行いました。

### よくある質問

#### Q: Aspose.Words for .NET の「置換パターン内の認識と置換」機能とは何ですか?

A: Aspose.Words for .NET の「置換パターン内の認識と置換」機能を使用すると、正規表現を使用して複雑な検索パターンを認識し、ドキュメント操作中にキャプチャされたグループに基づいて置換を実行できます。置換パターンでキャプチャされたグループを参照することにより、一致したテキストを動的に変換できます。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して新しいドキュメントを作成するには、`Document`物体。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。たとえば、「ジェイソンはポールにお金をあげます。」というフレーズを挿入するには、`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### Q: Aspose.Words for .NET で正規表現を使用してテキスト検索と置換を実行するにはどうすればよいですか?

 A: Aspose.Words for .NET で正規表現を使用してテキスト検索と置換を実行するには、`Range.Replace`関数を正規表現パターンとともに使用します。作成できます`Regex`目的のパターンを持つオブジェクトを作成し、それを`Replace`方法：

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: Aspose.Words for .NET でのテキスト検索および置換中に、置換パターンでキャプチャされたグループを使用するにはどうすればよいですか?

 A: Aspose.Words for .NET でのテキスト検索および置換中に、置換パターンでキャプチャされたグループを使用するには、`UseSubstitutions`の財産`FindReplaceOptions`物体。これにより、キャプチャされたグループを次を使用して参照できるようになります。`$1`, `$2`、などの置換パターン:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: サンプル ソース コードは、Aspose.Words for .NET の「置換パターン内の認識と置換」機能について何を示していますか?

A: サンプル ソース コードは、Aspose.Words for .NET の「置換パターン内の認識と置換」機能の使用を示しています。ドキュメントの作成、テキストの挿入、正規表現を使用したテキスト検索と置換の実行、置換パターンでキャプチャされたグループを使用して一致したテキストを動的に変換する方法を示します。

#### Q: Aspose.Words for .NET での正規表現の使用に関する詳細情報と例はどこで入手できますか?

A: Aspose.Words for .NET での正規表現の使用に関する詳細と例については、以下を参照してください。[Aspose.Words for .NET API リファレンス](https://reference.aspose.com/words/net/)。このドキュメントには、Aspose.Words for .NET での正規表現とテキスト操作を含むさまざまなシナリオの詳細な説明とコード例が記載されています。

#### Q: テキストの検索と置換中に、キャプチャされたグループに基づいてドキュメントの他の側面を操作できますか?

A: はい、テキストの検索と置換中に、キャプチャされたグループに基づいてドキュメントの他の側面を操作できます。テキスト置換の実行に加えて、Aspose.Words for .NET が提供するさまざまな API を使用して、キャプチャされたグループに基づいて書式設定、スタイル、ドキュメント構造、およびその他の要素を変更できます。

#### Q: Aspose.Words for .NET で正規表現やキャプチャされたグループを使用する場合、制限や考慮事項はありますか?

A: 正規表現とキャプチャされたグループは、Aspose.Words for .NET でテキストの検索と置換のための強力な機能を提供しますが、複雑さとパフォーマンスへの影響を考慮することが重要です。非常に複雑な正規表現やキャプチャされたグループの数が多いと、パフォーマンスに影響を与える可能性があります。効率的なドキュメント操作を保証するために、特定の使用例に合わせて正規表現をテストして最適化することをお勧めします。

#### Q: 英語以外の言語でも「置換パターン内の認識と置換」機能を使用できますか?

A: はい、Aspose.Words for .NET の「置換パターン内の認識と置換」機能は英語以外の言語でも使用できます。正規表現は言語に依存せず、どの言語でも特定のパターンに一致するように作成できます。正規表現パターンを調整して、目的の言語や、認識して置換したい特定のテキスト パターンに合わせて調整できます。