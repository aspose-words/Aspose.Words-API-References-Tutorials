---
title: 従来の制御文字を保持する
linktitle: 従来の制御文字を保持する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに、従来の制御文字を保持する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに従来の制御文字を保持するための C# ソース コードについて説明します。この機能を使用すると、ドキュメントを変換または保存するときに特殊な制御文字を保持できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: ドキュメントの読み込み

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

このステップでは、`Document`メソッドを使用し、継承された制御文字を含むファイルへのパスを渡します。

## ステップ3: OOXMLバックアップオプションの設定

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

このステップでは、新しいOOXMLファイルを作成して、OOXML保存オプションを設定します。`OoxmlSaveOptions`オブジェクト。希望する保存形式を指定します（ここでは、`FlatOpc` ）を有効にして、`KeepLegacyControlChars`従来の制御文字を保持するオプション。

## ステップ4: 従来の制御文字を使用してドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを`.docx`拡張子と指定された保存オプションを指定します。

ドキュメントを保存するときに、ソース コードを実行して従来の制御文字を保持できるようになりました。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx」という名前で保存されます。

### Aspose.Words for .NET を使用して従来の制御文字を保持するサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに、従来の制御文字を保持する機能について説明しました。ドキュメントの適切な書式設定や表示に重要となる可能性のある特殊文字を保持する方法について学習しました。

従来の制御文字の保存は、特殊な制御文字などの古い機能や特定の機能を使用する文書をWords Processingで処理する場合に特に便利です。`KeepLegacyControlChars`ドキュメントを保存するときにオプションを選択すると、これらの文字が保持されます。

Aspose.Words for .NET は、ドキュメント操作のニーズを満たす、柔軟で強力なバックアップ オプションを幅広く提供しています。適切なオプションを使用することで、バックアップ プロセスをカスタマイズし、ドキュメントの特定の特性を保持することができます。

この機能を Aspose.Words for .NET プロジェクトに自由に組み込むことで、ドキュメント内の従来の制御文字の整合性と保持を確保できます。