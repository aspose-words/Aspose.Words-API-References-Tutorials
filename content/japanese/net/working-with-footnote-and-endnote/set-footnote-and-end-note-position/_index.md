---
title: 脚注と終了注の位置を設定する
linktitle: 脚注と終了注の位置を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の脚注と文末脚注の位置を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の脚注と文末脚注の位置を設定する方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、Aspose.Words for .NET が開発環境にインストールされ、セットアップされていることを確認してください。まだ行っていない場合は、からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ドキュメント オブジェクトの初期化

まず、初期化します`Document`ソースドキュメントへのパスを指定してオブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## ステップ 2: 脚注と文末脚注の位置を設定する

次に、`FootnoteOptions`そして`EndnoteOptions`文書のプロパティを使用して、脚注と文末脚注の位置を設定します。この例では、脚注の位置がテキストの下に設定され、文末脚注の位置がセクションの最後に設定されます。

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## ステップ 3: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内の脚注と文末脚注の位置を正常に設定できました。

### Aspose.Words for .NET を使用して脚注と文末脚注の位置を設定するソース コードの例

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

このコードを独自のプロジェクトで自由に使用し、特定の要件に応じて変更してください。

### よくある質問

#### Q: Aspose.Words で脚注と文末脚注を配置するにはどうすればよいですか?

 A: Aspose.Words で脚注と文末脚注を配置するには、`FootnoteOptions`クラスと`Position`財産。このプロパティは、次のような任意の値に設定できます。`BottomOfPage` (ページの下部) または`EndOfSection`（セクションの最後にあります）。

#### Q: 文書の各ページまたはセクションの脚注と文末脚注の位置をカスタマイズすることはできますか?

A: はい、文書の各ページまたはセクションの脚注と文末脚注の位置をカスタマイズできます。 Aspose.Words セクションおよびページ操作メソッドを使用して、脚注と文末脚注の特定の位置を定義できます。

#### Q: 文書から脚注や文末脚注を削除するにはどうすればよいですか?

 A: Aspose.Words の文書から脚注または文末脚注を削除するには、次のような適切な方法を使用できます。`RemoveAllFootnotes`すべての脚注を削除するには、または`RemoveAllEndnotes`すべての文末脚注を削除します。これらの操作を行った後は、必ず文書を保存してください。

#### Q: 脚注と文末脚注をページ余白の外側に配置できますか?

いいえ、デフォルトでは、脚注と文末脚注は Aspose.Words のページ余白の外側に配置できません。ただし、必要に応じて文書の余白を調整して、脚注と文末脚注のためのスペースを増やすことができます。

#### Q: 脚注と文末脚注を特定のフォントや書式スタイルでカスタマイズできますか?

A: はい、Aspose.Words の特定のフォントまたは書式スタイルを使用して脚注と文末脚注をカスタマイズできます。利用可能なメソッドとプロパティを使用して、フォント スタイル、色、フォント サイズなどを脚注と文末脚注に適用できます。