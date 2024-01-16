---
title: チェックボックスの現在の状態
linktitle: チェックボックスの現在の状態
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のチェック ボックス コンテンツ コントロールの現在の状態を取得および設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/current-state-of-check-box/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のチェック ボックス コンテンツ コントロールの現在の状態を取得および設定する方法について説明します。現在の状態に基づいて、チェックボックスをオンまたはオフにできます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードし、チェック ボックス コンテンツ コントロールを取得する
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。次に、ドキュメントから目的のチェック ボックス コンテンツ コントロールを取得します。この例では、チェック ボックスがドキュメント内の最初の構造化ドキュメント タグであると仮定します。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ステップ 3: 現在の状態に基づいてチェックボックスをオンまたはオフにします
取得した構造化文書タグが次のタイプであるかどうかを確認します。`SdtType.Checkbox` 。存在する場合は、`Checked`コンテンツ コントロールのプロパティを`true`をクリックしてボックスにチェックを入れます。それ以外の場合は、チェックを外したままにすることができます。

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## ステップ 4: ドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.CurrentStateOfCheckBox.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Aspose.Words for .NET を使用したチェック ボックスの現在の状態のソース コードの例 

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

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内のチェック ボックス コンテンツ コントロールの現在の状態を取得して設定することに成功しました。