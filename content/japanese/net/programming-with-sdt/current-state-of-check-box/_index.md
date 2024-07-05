---
title: チェックボックスの現在の状態
linktitle: チェックボックスの現在の状態
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のチェック ボックス コンテンツ コントロールの現在の状態を取得および設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/current-state-of-check-box/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内のチェック ボックス コンテンツ コントロールの現在の状態を取得および設定する方法について説明します。チェック ボックスの現在の状態に基づいて、チェック ボックスをオンまたはオフにすることができます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを読み込み、チェックボックス コンテンツ コントロールを取得する
Word文書を読み込むには、`Document`コンストラクターを呼び出して、ドキュメントへのパスをパラメーターとして渡します。次に、ドキュメントから目的のチェック ボックス コンテンツ コントロールを取得します。この例では、チェック ボックスがドキュメント内の最初の構造化ドキュメント タグであると想定しています。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ステップ3: 現在の状態に基づいてチェックボックスをオンまたはオフにする
取得した構造化文書タグのタイプを確認する`SdtType.Checkbox`設定されている場合、`Checked`コンテンツコントロールのプロパティ`true`チェックボックスをオンにします。それ以外の場合は、チェックを外すこともできます。

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## ステップ4: ドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.CurrentStateOfCheckBox.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Aspose.Words for .NET を使用したチェックボックスの現在の状態のサンプルソースコード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	//ドキュメントから最初のコンテンツ コントロールを取得します。
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内のチェック ボックス コンテンツ コントロールの現在の状態を取得して設定できました。