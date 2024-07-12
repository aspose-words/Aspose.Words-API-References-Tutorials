---
title: 未使用のスタイルとリストをクリーンアップする
linktitle: 未使用のスタイルとリストをクリーンアップする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の未使用のスタイルとリストをクリーンアップするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

このチュートリアルでは、C# ソース コードを使用して、Aspose.Words for .NET で未使用のスタイルとリストをクリーンアップする方法を説明します。この機能を使用すると、ドキュメントで使用されていないスタイルとリストを削除できます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

この手順では、クリーンアップする未使用のスタイルとリストを含む Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: クリーンアップの前にスタイルとリストを数える

クリーンアップする前に、ドキュメント内に存在するスタイルとリストの数をカウントします。カウンターを表示するには、次のコードを使用します。

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

これらの手順では、クリーンアップ前のドキュメント内に存在するスタイルとリストの数が表示されます。

## ステップ4: 使用されていないスタイルとリストをクリーンアップする

次に、ドキュメントから未使用のスタイルとリストをクリーンアップします。クリーンアップを実行するには、次のコードを使用します。

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

このコードは、指定されたオプションを使用して、ドキュメントから未使用のスタイルとリストを削除します。この例では、`UnusedStyles`未使用のスタイルを削除し、`UnusedLists`使用されていない場合でもリストを保持するオプション。

## ステップ5: クリーニング後のスタイルとリストを数える

クリーンアップを行った後、スタイルとリストを再度カウントして、折りたたまれているかどうかを確認します。新しいカウンターを表示するには、次のコードを使用します。

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

これらの手順では、クリーニング後に残っているスタイルとリストの数を示します。

### Aspose.Words for .NET を使用して未使用のスタイルとリストをクリーンアップするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	//組み込みスタイルと組み合わせると、ドキュメントには 8 つのスタイルが含まれるようになります。
	//ドキュメント内にテキストがある場合、カスタムスタイルは「使用済み」としてマークされます。
	//そのスタイルでフォーマットされています。つまり、追加した 4 つのスタイルは現在使用されていません。
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//指定された CleanupOptions に応じて、ドキュメントから未使用のスタイルとリストをクリーンアップします。
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

必ず正しいドキュメントパスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用して、ドキュメントから未使用のスタイルとリストをクリーンアップする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、この機能を自分のドキュメントに簡単に適用できます。

