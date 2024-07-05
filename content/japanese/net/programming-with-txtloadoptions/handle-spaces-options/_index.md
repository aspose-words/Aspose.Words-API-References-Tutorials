---
title: スペース処理オプション
linktitle: スペース処理オプション
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して TXT ドキュメント内のスペースを管理する方法を学びます。不要なスペースを削除して読みやすさを向上させます。
type: docs
weight: 10
url: /ja/net/programming-with-txtloadoptions/handle-spaces-options/
---

このチュートリアルでは、Aspose.Words for .NET の「TXT 読み込みオプションによるスペースの管理」機能用に提供されている C# ソース コードについて説明します。この機能を使用すると、TXT ドキュメントを読み込むときに空白の処理動作を指定できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: テキストドキュメントの作成

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

この手順では、先頭と末尾にスペースがある行を含むテキスト ドキュメントをシミュレートするテキスト文字列を作成します。

## ステップ3: アップロードオプションの設定

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

このステップでは、TXT文書を読み込むためのオプションを設定します。新しい`TxtLoadOptions`オブジェクトを設定し、`LeadingSpacesOptions`そして`TrailingSpacesOptions`プロパティ`TxtLeadingSpacesOptions.Trim`そして`TxtTrailingSpacesOptions.Trim`それぞれ。これにより、Aspose.Words はドキュメントを読み込むときに行の先頭と末尾のスペースを削除します。

## ステップ4: ドキュメントの読み込み

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

このステップでは、`Document`メソッドを実行し、指定されたテキスト文字列とロード オプションを含むメモリ ストリームを渡します。

## ステップ5: ドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

この最後のステップでは、結果の文書を.docx形式で保存します。`Save`メソッドを実行し、出力ファイルへのパスを渡します。

これで、空白処理オプションを指定してソース コードを実行し、テキスト ドキュメントを読み込むことができます。結果のドキュメントは、指定されたディレクトリに「WorkingWithTxtLoadOptions.HandleSpacesOptions.docx」という名前で保存されます。

### Aspose.Words for .NET を使用した TXT 読み込みオプション付きスペース管理機能のサンプル ソース コード*

```csharp

            
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET の TXT 読み込みオプションを使用してスペースを管理する機能について説明しました。TXT ドキュメントを読み込むときに空白の処理動作を指定する方法を学習しました。

この機能は、ドキュメント内の行の左右にある不要なスペースを処理するのに非常に便利です。適切な読み込みオプションを設定することで、これらの不要なスペースを簡単に削除でき、ドキュメントのコンテンツをよりクリーンで読みやすくすることができます。

Aspose.Words for .NET は、ドキュメントの操作と生成のための高度な機能を多数提供します。TXT ドキュメントを読み込むときにスペースを管理する機能は、Aspose.Words for .NET が提供する強力なツールの 1 つです。

特定のシナリオに最適なスペース管理オプションを選択することが重要です。この例では、`Trim`行の先頭と末尾から不要なスペースを削除するオプションがあります。ただし、Aspose.Words には、スペースを保持する、スペースを完全に削除する、またはそのまま保持するオプションもあります。

特定のニーズと TXT ドキュメントの構造に応じて、これらのオプションを調整することを忘れないでください。

Aspose.Words for .NET を使用すると、ドキュメント内の空白を簡単に操作して、レイアウトの品質とコンテンツの読みやすさを向上させることができます。

したがって、Aspose.Words for .NET プロジェクトで空白管理と TXT 読み込みオプションをぜひ統合し、その利点を活用して、適切にフォーマットされた読みやすいドキュメントを作成してください。