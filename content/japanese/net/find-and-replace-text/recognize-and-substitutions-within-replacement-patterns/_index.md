---
title: 置換パターン内の認識と置換
linktitle: 置換パターン内の認識と置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で認識と置換による置換パターンを使用して Word 文書を操作する方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Recognize And Substitutions Within Replacement Patterns 関数の使用方法を理解します。この機能は、複雑な検索パターンを認識し、ドキュメント操作中にキャプチャされたグループに基づいて置換を実行するのに役立ちます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

置換パターンで一致と置換を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ2: 文書にテキストを挿入する

文書ができたら、`DocumentBuilder`オブジェクトです。例では、`Write` 「ジェイソンはポールにお金をあげる」というフレーズを挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## ステップ3: 置換パターンの認識と置換

ここで、`Range.Replace`特定のパターンを認識するために正規表現を使用してテキスト検索と置換を実行する関数。この例では、正規表現を使用します。`([A-z]+) gives money to ([A-z]+)`誰かが誰かにお金を渡す文を認識するために、置換パターンを使用します`$2 takes money from $1`役割を逆にすることで代入を実行する。`$1`そして`$2`正規表現によってキャプチャされたグループを参照します。

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Aspose.Words for .NET を使用して置換パターン内の認識と置換を行うためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用した置換パターンでの一致と置換の使用法を示した完全なサンプル ソース コードです。

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の置換パターン内の認識と置換機能の使用方法を理解しました。ドキュメントの作成、テキストの挿入、キャプチャされたグループに基づく正規表現と置換パターンを使用した検索と置換の実行、ドキュメントの操作について、ステップ バイ ステップ ガイドに従いました。

### よくある質問

#### Q: Aspose.Words for .NET の「置換パターン内の認識と置換」機能とは何ですか?

A: Aspose.Words for .NET の「置換パターン内の認識と置換」機能を使用すると、正規表現を使用して複雑な検索パターンを認識し、ドキュメント操作中にキャプチャされたグループに基づいて置換を実行できます。置換パターンでキャプチャされたグループを参照することで、一致したテキストを動的に変換できます。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用して新しいドキュメントを作成するには、`Document`オブジェクト。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: 文書を作成したら、`DocumentBuilder`たとえば、「ジェイソンはポールにお金を与える」というフレーズを挿入するには、`Write`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### Q: Aspose.Words for .NET で正規表現を使用してテキストの検索と置換を実行するにはどうすればよいですか?

 A: Aspose.Words for .NETで正規表現を使用してテキスト検索と置換を実行するには、`Range.Replace`関数と正規表現パターンを組み合わせて作成できます。`Regex`希望するパターンを持つオブジェクトを作成し、それを`Replace`方法：

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: Aspose.Words for .NET でテキストの検索と置換中に、キャプチャされたグループを置換パターンで使用するにはどうすればよいでしょうか?

 A: Aspose.Words for .NETでテキスト検索と置換を行う際に、置換パターンでキャプチャしたグループを使用するには、`UseSubstitutions`の財産`FindReplaceOptions`オブジェクト。これにより、キャプチャしたグループを`$1`, `$2`置換パターン内の、など:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### Q: Aspose.Words for .NET の「置換パターン内の認識と置換」機能のサンプル ソース コードはどのようなことを示していますか?

A: サンプル ソース コードは、Aspose.Words for .NET の「置換パターン内の認識と置換」機能の使用方法を示しています。ドキュメントの作成方法、テキストの挿入方法、正規表現を使用したテキスト検索と置換の実行方法、置換パターンでキャプチャされたグループを使用して一致したテキストを動的に変換する方法を示しています。

#### Q: Aspose.Words for .NET での正規表現の使用に関する詳細情報や例はどこで入手できますか?

A: Aspose.Words for .NETでの正規表現の使用に関する詳細と例については、[Aspose.Words for .NET API リファレンス](https://reference.aspose.com/words/net/)このドキュメントでは、Aspose.Words for .NET での正規表現とテキスト操作に関するさまざまなシナリオの詳細な説明とコード例を示します。

#### Q: テキストの検索と置換中にキャプチャされたグループに基づいてドキュメントの他の側面を操作できますか?

A: はい、テキストの検索と置換中にキャプチャされたグループに基づいて、ドキュメントの他の側面を操作できます。テキストの置換を実行するだけでなく、Aspose.Words for .NET が提供するさまざまな API を使用して、キャプチャされたグループに基づいて書式設定、スタイル、ドキュメント構造、およびその他の要素を変更できます。

#### Q: Aspose.Words for .NET で正規表現やキャプチャされたグループを使用する場合、制限や考慮事項はありますか?

A: 正規表現とキャプチャされたグループは Aspose.Words for .NET でのテキスト検索と置換に強力な機能を提供しますが、複雑さとパフォーマンスへの影響を考慮することが重要です。非常に複雑な正規表現と多数のキャプチャされたグループはパフォーマンスに影響を与える可能性があります。効率的なドキュメント操作を確実に行うために、特定のユースケースで正規表現をテストして最適化することをお勧めします。

#### Q: 「置換パターン内の認識と置換」機能は英語以外の言語でも使用できますか?

A: はい、Aspose.Words for .NET の「置換パターン内の認識と置換」機能は、英語以外の言語でも使用できます。正規表現は言語に依存せず、任意の言語の特定のパターンに一致するように作成できます。正規表現パターンは、目的の言語や認識して置換する特定のテキスト パターンに合わせて調整できます。