---
title: ハイパーリンクを置換する
linktitle: ハイパーリンクを置換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のハイパーリンクを置き換えます。ハイパーリンクを置き換える手順を段階的に説明します。
type: docs
weight: 10
url: /ja/net/working-with-fields/replace-hyperlinks/
---

ここでは、Aspose.Words for .NET 機能を使用してハイパーリンクを置き換える次の C# ソース コードを説明するステップバイステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ 1: ドキュメント ディレクトリ パスを設定する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

必ず、ファイルを含むドキュメント ディレクトリへの正しいパスを指定してください。`Hyperlinks.docx`ファイル。

## ステップ 2: ハイパーリンクを含むドキュメントをロードする

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

ここでは、`Document`指定されたファイルからクラスを取得します。

## ステップ 3: フィールドを参照してハイパーリンクを見つける

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         //一部のハイパーリンクはローカル (ドキュメント内のブックマークへのリンク) である可能性がありますが、それらは無視されます。
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com」;
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

このループは、ドキュメント内のすべてのフィールドを調べて、次のタイプのフィールドを探します。`FieldType.FieldHyperlink` 。このタイプのフィールドが見つかったら、それがローカル リンクであるかどうかをチェックします。`SubAddress`財産。そうでない場合は、リンク アドレスを次のように置き換えます。`"http://www.aspose.com"`そして結果は`"Aspose - The .NET & Java Component Editor"`.

## ステップ 4: 変更したドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

最後に、変更したドキュメントを、置換されたハイパーリンクとともに指定したファイルに保存します。

### ハイパーリンクを Aspose.Words for .NET に置き換えるソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         //一部のハイパーリンクはローカル (ドキュメント内のブックマークへのリンク) である可能性がありますが、それらは無視されます。
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com」;
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

これは、Aspose.Words for .NET を使用してドキュメント内のハイパーリンクを置き換えるサンプル ソース コードです。

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書内のハイパーリンクを置き換えるにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書内のハイパーリンクを置き換えるには、`Document.Range.Replace`検索するテキストと置換テキストを指定するメソッド。検索パラメータと置換パラメータを設定するには、必ず適切なオプションを使用してください。

#### Q: Word 文書内の特定のハイパーリンクのみを Aspose.Words for .NET で置き換えることはできますか?

A: はい、Word 文書内の特定のハイパーリンクのみを Aspose.Words for .NET に置き換えることができます。リンク URL、リンク テキスト、その他の関連プロパティなどの特定の基準を使用して、置換するハイパーリンクをフィルタリングできます。その後、一致するハイパーリンクにのみ置換を適用できます。

#### Q: Aspose.Words for .NET に置き換えるときに、ヘッダー、フッター、または脚注のハイパーリンクを無視するにはどうすればよいですか?

A: Aspose.Words for .NET に置き換えるときにヘッダー、フッター、または脚注のハイパーリンクを無視するには、詳細検索オプションを使用し、適切な検索制限を指定できます。たとえば、検索をドキュメントの主要なセクションに限定し、ヘッダー、フッター、または脚注を除外できます。

#### Q: ハイパーリンクをドキュメントの他の部分への内部リンクに置き換えることはできますか?

 A: はい、Aspose.Words for .NET を使用して、ハイパーリンクをドキュメントの他の部分への内部リンクに置き換えることができます。アンカーまたはテキスト ID を使用して内部リンクを作成し、それらを`Document.Range.Replace`メソッドに適切なオプションを付けます。

#### Q: ハイパーリンクを Aspose.Words for .NET に置き換えると、色やスタイルなどのリンク プロパティは保持されますか?

A: はい、ハイパーリンクを Aspose.Words for .NET に置き換える場合、色やスタイルなどのリンク プロパティは保持されます。置換テキストに同じ書式設定プロパティを指定すると、一貫した結果が得られます。