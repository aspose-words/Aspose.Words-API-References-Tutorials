---
title: ドキュメントファイル形式の検出
linktitle: ドキュメントファイル形式の検出
second_title: Aspose.Words ドキュメント処理 API
description: この包括的なステップバイステップ ガイドを使用して、Aspose.Words for .NET を使用してドキュメント ファイル形式を検出する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-fileformat/detect-file-format/
---
## 導入

今日のデジタル世界では、さまざまなドキュメント形式を効率的に管理することが重要です。Word、PDF、HTML、その他の形式を扱う場合でも、これらのファイルを正しく検出して処理できれば、多くの時間と労力を節約できます。このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント ファイル形式を検出する方法について説明します。このガイドでは、前提条件から詳細なステップ バイ ステップ ガイドまで、知っておく必要のあるすべてのことを説明します。

## 前提条件

コードに進む前に、必要なものがすべて揃っていることを確認しましょう。

-  Aspose.Words for .NET: ダウンロードはこちらから[ここ](https://releases.aspose.com/words/net/)有効なライセンスを持っていることを確認してください。そうでない場合は、[一時ライセンス](https://purchase.aspose.com/temporary-license/).
- Visual Studio: 最新バージョンであれば問題なく動作します。
- .NET Framework: 正しいバージョンがインストールされていることを確認してください。

## 名前空間のインポート

開始するには、プロジェクトに必要な名前空間をインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

わかりやすくするために、例を複数のステップに分解してみましょう。

## ステップ1: ディレクトリを設定する

まず、ファイルを形式に基づいて並べ替えるディレクトリを設定する必要があります。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

//ディレクトリがまだ存在しない場合は作成します。
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## ステップ2: ファイルのリストを取得する

次に、破損したドキュメントを除いたディレクトリからファイルのリストを取得します。

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## ステップ3: ファイル形式の検出

ここで、各ファイルを反復処理し、Aspose.Words を使用してその形式を検出します。

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    //ドキュメントの種類を表示する
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## 結論

Aspose.Words for .NET を使用してドキュメント ファイル形式を検出するのは簡単なプロセスです。ディレクトリを設定し、ファイルのリストを取得し、Aspose.Words を使用してファイル形式を検出することで、ドキュメントを効率的に整理および管理できます。このアプローチは時間を節約するだけでなく、さまざまなドキュメント形式を正しく処理することも保証します。

## よくある質問

### Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、Word 文書をプログラムで操作するための強力なライブラリです。開発者は、さまざまな形式で文書を作成、変更、変換できます。

### Aspose.Words は暗号化されたドキュメントを検出できますか?
はい、Aspose.Words はドキュメントが暗号化されているかどうかを検出し、それに応じてドキュメントを処理できます。

### Aspose.Words はどのような形式を検出できますか?
Aspose.Words は、DOC、DOCX、RTF、HTML、MHTML、ODT など、さまざまな形式を検出できます。

### Aspose.Words の一時ライセンスを取得するにはどうすればよいですか?
臨時免許証は[Aspose 購入](https://purchase.aspose.com/temporary-license/)ページ。

### Aspose.Words のドキュメントはどこにありますか?
Aspose.Wordsのドキュメントは以下にあります。[ここ](https://reference.aspose.com/words/net/).
