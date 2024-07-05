---
title: ドキュメントファイル形式の検出
linktitle: ドキュメントファイル形式の検出
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント ファイル形式を検出するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-fileformat/detect-file-format/
---

この記事では、Aspose.Words for .NET でドキュメント ファイル形式検出機能を使用する方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、さまざまなドキュメント ファイルの形式を検出する方法が理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ディレクトリを定義する

まず、ファイルを保存するディレクトリをフォーマットに応じて定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。「Supported」、「Unknown」、「Encrypted」、および「Pre97」ディレクトリが存在しない場合は作成されます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

//ディレクトリがまだ存在しない場合は作成します。
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## ステップ2: ファイルを参照する

次に、`GetFiles`方法の`Directory`クラスを使用して、指定されたディレクトリ内のファイルのリストを取得します。また、`Where`「Corrupted document.docx」という名前の特定のファイルを除外する句。

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## ステップ3: 各ファイルの形式を検出する

リスト内の各ファイルをループし、`DetectFileFormat`方法の`FileFormatUtil`クラスを使用してファイルの形式を検出します。検出されたドキュメントの種類も表示します。

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

//ドキュメントの種類を表示する
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ...サポートされている他のドキュメント形式のケースを追加する
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
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
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

以上です。Aspose.Words for .NET を使用して、さまざまなドキュメント ファイルの形式を正常に検出できました。

### Aspose.Words for .NET を使用したファイル形式検出のサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	//ディレクトリがまだ存在しない場合は作成します。
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
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

### ドキュメントファイル形式の検出に関するFAQ

#### Aspose.Words for .NET を使用してドキュメント ファイルの形式を検出する方法は?

 Aspose.Words for .NETを使用してドキュメントファイルの形式を検出するには、チュートリアルに記載されている手順に従ってください。`DetectFileFormat`方法の`FileFormatUtil`クラスを使用すると、ドキュメント ファイルの形式を検出できます。これにより、Microsoft Word 97-2003 ドキュメント、テンプレート、Office Open XML WordprocessingML ドキュメント、またはその他のサポートされている形式であるかどうかを判断できます。チュートリアルで提供されるコードでは、この機能の実装手順を説明します。

#### Aspose.Words for .NET はどのようなドキュメント形式をサポートしていますか?

Aspose.Words for .NET は、Microsoft Word 97-2003 ドキュメント (DOC)、テンプレート (DOT)、Office Open XML WordprocessingML ドキュメント (DOCX)、マクロ付き Office Open XML WordprocessingML ドキュメント (DOCM)、マクロなしの Office Open XML WordprocessingML テンプレート (DOTX)、マクロ付き Office Open XML WordprocessingML テンプレート (DOTM)、フラット OPC ドキュメント、RTF ドキュメント、Microsoft Word 2003 WordprocessingML ドキュメント、HTML ドキュメント、MHTML (Web アーカイブ) ドキュメント、OpenDocument テキスト (ODT) ドキュメント、OpenDocument テキスト (OTT) テンプレート、MS Word 6 または Word 95 ドキュメント、および不明なドキュメント形式など、さまざまなドキュメント形式をサポートしています。

#### フォーマット検出中に暗号化されたドキュメント ファイルを処理するにはどうすればよいでしょうか?

文書ファイルの形式を検出するときは、`IsEncrypted`の財産`FileFormatInfo`オブジェクトを使用して、ファイルが暗号化されているかどうかを確認します。ファイルが暗号化されている場合は、ファイルを暗号化されたドキュメント専用のディレクトリにコピーするなど、この特定のケースを処理するための追加の手順を実行できます。`File.Copy`これを行う方法。

#### ドキュメントの形式が不明な場合は、どのようなアクションを実行する必要がありますか?

ドキュメントの形式が不明な場合は、アプリケーション固有の方法で処理することができます。チュートリアルで提供された例では、ドキュメントは不明な形式のドキュメント専用の特定のディレクトリにコピーされます。このアクションは、特定のニーズに合わせてカスタマイズできます。

#### ドキュメント形式の検出と組み合わせて使用できる Aspose.Words for .NET の他の機能はありますか?

はい、Aspose.Words for .NET には、Word 文書を処理および操作するための他の多くの機能が用意されています。たとえば、ライブラリを使用して、文書からテキスト、画像、またはメタデータを抽出したり、書式変更を適用したり、文書を結合したり、文書を別の形式に変換したりすることができます。