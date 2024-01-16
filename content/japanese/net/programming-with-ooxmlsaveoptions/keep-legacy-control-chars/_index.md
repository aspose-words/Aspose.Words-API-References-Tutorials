---
title: 従来の制御文字を保持する
linktitle: 従来の制御文字を保持する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに従来の制御文字を保持する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに従来の制御文字を保持するために提供されている C# ソース コードを調べます。この機能を使用すると、ドキュメントの変換または保存時に特殊な制御文字を保存できます。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: ドキュメントをロードする

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

このステップでは、`Document`メソッドを使用して、継承された制御文字を含むファイルへのパスを渡します。

## ステップ 3: OOXML バックアップ オプションの構成

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

このステップでは、新しいファイルを作成して OOXML 保存オプションを構成します。`OoxmlSaveOptions`物体。希望の保存形式を指定します (ここでは、`FlatOpc` ) を有効にして、`KeepLegacyControlChars`従来の制御文字を保持するオプション。

## ステップ 4: 従来の制御文字を使用してドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを渡します。`.docx`拡張子と、指定された保存オプションを追加します。

ドキュメントを保存するときに、ソース コードを実行して従来の制御文字を保持できるようになりました。結果のファイルは、「WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx」という名前で指定されたディレクトリに保存されます。

### Aspose.Words for .NET を使用した Keep Legacy Control Chars のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに従来の制御文字を保持する機能について説明しました。私たちは、適切な文書の書式設定や表示に重要な特殊文字を保存する方法を学びました。

従来の制御文字を保持すると、特殊な制御文字など、古い機能や特定の機能を使用する文書を文書処理する場合に特に便利です。を有効にすることで、`KeepLegacyControlChars`ドキュメントを保存するときにオプションを使用すると、これらの文字が確実に保持されます。

Aspose.Words for .NET は、ドキュメント操作のニーズを満たす、柔軟で強力なバックアップ オプションを幅広く提供します。適切なオプションを使用すると、バックアップ プロセスをカスタマイズして、ドキュメントの特定の特性を保存できます。

この機能を自由に Aspose.Words for .NET プロジェクトに組み込んで、ドキュメント内の従来の制御文字の整合性と保持を確保してください。