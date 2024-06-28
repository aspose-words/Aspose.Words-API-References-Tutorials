---
title: サフィックスなしで置換を取得
linktitle: サフィックスなしで置換を取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でサフィックスなしのフォント置換を管理する方法を学習します。ステップバイステップのガイドに従って、ドキュメントを常に完璧に見せることができます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/get-substitution-without-suffixes/
---

Aspose.Words for .NET を使用したフォント置換の管理に関するこの包括的なガイドへようこそ。文書内でフォントが正しく表示されないことに悩んだことがあるなら、ここが正しい場所です。このチュートリアルでは、サフィックスのないフォント置換を効率的に処理するための段階的なプロセスを説明します。始めましょう！

## 前提条件

チュートリアルに入る前に、次のものが揃っていることを確認してください。

- C# の基本知識: C# プログラミングを理解すると、手順に従って実装することが容易になります。
-  Aspose.Words for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/words/net/).
- 開発環境: Visual Studio などの開発環境をセットアップして、コードを作成して実行します。
- サンプルドキュメント: サンプルドキュメント (例:`Rendering.docx`) このチュートリアルで使用します。

## 名前空間のインポート

まず、Aspose.Words が提供するクラスとメソッドにアクセスするために必要な名前空間をインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが存在するディレクトリを指定します。これは、作業したいドキュメントを見つけるのに役立ちます。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 置換警告ハンドラーを設定する

次に、ドキュメント処理中にフォントの置換が発生するたびに通知する警告ハンドラーを設定する必要があります。これは、フォントの問題を検出して処理するために非常に重要です。

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## ステップ 3: カスタム フォント ソースを追加する

この手順では、Aspose.Words が正しいフォントを見つけて使用できるようにするために、カスタム フォント ソースを追加します。これは、特定のフォントをカスタム ディレクトリに保存している場合に特に便利です。

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

このコードでは:
- 現在のフォント ソースを取得し、新しいフォント ソースを追加します。`FolderFontSource`カスタム フォント ディレクトリを指します (`C:\\MyFonts\\`）。
- 次に、この新しいリストでフォント ソースを更新します。

## ステップ 4: ドキュメントを保存する

最後に、フォント置換設定を適用した後、ドキュメントを保存します。このチュートリアルでは、PDF として保存します。

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## ステップ 5: 警告ハンドラー クラスを作成する

警告を効果的に処理するには、`IWarningCallback`インターフェース。このクラスは、フォント置換の警告をキャプチャしてログに記録します。

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

このクラスでは:
- の`Warning`このメソッドは、フォントの置換に関連する警告をキャプチャします。
- の`FontWarnings`コレクションには、さらなる検査またはログ記録のためにこれらの警告が保存されます。

## 結論

これで、Aspose.Words for .NET を使用してサフィックスなしのフォント置換を処理するプロセスをマスターできました。この知識により、システムで使用可能なフォントに関係なく、ドキュメントが意図した外観を維持できるようになります。 Aspose.Words の機能を最大限に活用するには、さまざまな設定とソースを試し続けてください。

## よくある質問

### Q1: 複数のカスタム ディレクトリのフォントを使用するにはどうすればよいですか?

複数追加することもできます`FolderFontSource`インスタンスへの`fontSources`フォント ソースをリストし、それに応じて更新します。

### Q2: Aspose.Words for .NET の無料トライアルはどこでダウンロードできますか?

無料トライアル版は次からダウンロードできます。[Asposeの無料トライアルページ](https://releases.aspose.com/).

###  Q3: を使用して複数の種類の警告を処理できますか?`IWarningCallback`?

はい`IWarningCallback`インターフェイスを使用すると、フォントの置換だけでなく、さまざまな種類の警告を処理できます。

### Q4: Aspose.Words のサポートはどこで受けられますか?

サポートについては、次のサイトにアクセスしてください。[Aspose.Words サポート フォーラム](https://forum.aspose.com/c/words/8).

### Q5: 一時ライセンスを購入することはできますか?

はい、次のサイトから一時ライセンスを取得できます。[一時ライセンスのページ](https://purchase.aspose.com/temporary-license/).