---
title: ドキュメントファイル形式の検出
linktitle: ドキュメントファイル形式の検出
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント ファイル形式を検出するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-fileformat/detect-file-format/
---

この記事では、Aspose.Words for .NET でドキュメント ファイル形式検出機能を使用する方法をステップごとに説明します。コードの各部分について詳しく説明します。このチュートリアルを終えると、さまざまなドキュメント ファイルの形式を検出する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ディレクトリを定義する

まず、ファイルの形式に従ってファイルを保存するディレクトリを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。 「Supported」、「Unknown」、「Encrypted」、および「Pre97」ディレクトリがまだ存在しない場合は、これらのディレクトリを作成します。

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

## ステップ 2: ファイルを参照する

次に、`GetFiles`の方法`Directory`クラスを使用して、指定されたディレクトリ内のファイルのリストを取得します。また、`Where`「Corrupted document.docx」という名前の特定のファイルを除外する句。

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## ステップ 3: 各ファイルの形式を検出する

リスト内の各ファイルをループして、`DetectFileFormat`の方法`FileFormatUtil`ファイルの形式を検出するクラス。検出されたドキュメントの種類も表示されます。

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

//文書の種類を表示する
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
// ... サポートされている他のドキュメント形式のケースを追加
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

それだけです ！ Aspose.Words for .NET を使用して、さまざまなドキュメント ファイルの形式を正常に検出できました。

### Aspose.Words for .NET を使用したファイル形式検出のソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	//ディレクトリが存在しない場合は作成します。
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

		//文書の種類を表示する
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

### 文書ファイル形式の検出に関する FAQ

#### Aspose.Words for .NET を使用してドキュメント ファイルの形式を検出するにはどうすればよいですか?

 Aspose.Words for .NET を使用してドキュメント ファイルの形式を検出するには、チュートリアルに記載されている手順に従います。の使用`DetectFileFormat`の方法`FileFormatUtil`クラスを使用すると、ドキュメント ファイルの形式を検出できます。これにより、それが Microsoft Word 97-2003 ドキュメント、テンプレート、Office Open XML WordprocessingML ドキュメント、またはその他のサポートされている形式であるかどうかを判断できます。チュートリアルで提供されているコードを使用して、この機能を実装する手順を説明します。

#### Aspose.Words for .NET はどのようなドキュメント形式をサポートしていますか?

Aspose.Words for .NET は、Microsoft Word 97-2003 ドキュメント (DOC)、テンプレート (DOT)、Office Open XML WordprocessingML ドキュメント (DOCX)、マクロを含む Office Open XML WordprocessingML ドキュメント (DOCM)、Office Open などのさまざまなドキュメント形式をサポートしています。マクロなしの XML WordprocessingML テンプレート (DOTX)、マクロ付きの Office Open XML WordprocessingML テンプレート (DOTM)、フラット OPC ドキュメント、RTF ドキュメント、Microsoft Word 2003 WordprocessingML ドキュメント、HTML ドキュメント、MHTML (Web アーカイブ) ドキュメント、OpenDocument Text (ODT) ドキュメント、 OpenDocument Text (OTT) テンプレート、MS Word 6 または Word 95 ドキュメント、および不明なドキュメント形式。

#### フォーマット検出中に暗号化されたドキュメント ファイルを処理するにはどうすればよいですか?

文書ファイルの形式を検出する場合は、`IsEncrypted`の財産`FileFormatInfo`オブジェクトを使用して、ファイルが暗号化されているかどうかを確認します。ファイルが暗号化されている場合は、暗号化されたドキュメント専用のディレクトリにファイルをコピーするなど、この特定のケースに対処するための追加の手順を実行できます。使用できます`File.Copy`これを行うための方法。

#### 文書の形式が不明な場合はどのような対応をとるべきですか?

ドキュメントの形式が不明な場合は、アプリケーションに固有の方法でドキュメントを処理するかどうかを決定できます。チュートリアルで提供される例では、ドキュメントは、未知の形式のドキュメント専用の特定のディレクトリにコピーされます。このアクションは、特定のニーズに合わせてカスタマイズできます。

#### ドキュメント形式の検出と組み合わせて使用できる Aspose.Words for .NET の機能は他にもありますか?

はい、Aspose.Words for .NET は、Word ドキュメントを処理および操作するための他の多くの機能を提供します。たとえば、ライブラリを使用して、ドキュメントからテキスト、画像、またはメタデータを抽出したり、書式設定の変更を適用したり、ドキュメントを結合したり、ドキュメントを別の形式に変換したりすることができます。