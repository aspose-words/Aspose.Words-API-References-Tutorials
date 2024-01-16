---
title: 使用されていないスタイルとリストをクリーンアップする
linktitle: 使用されていないスタイルとリストをクリーンアップする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の未使用のスタイルとリストをクリーンアップするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

このチュートリアルでは、Aspose.Words for .NET を使用して未使用のスタイルとリストをクリーンアップするための C# ソース コードを説明します。この機能を使用すると、ドキュメントで使用されていないスタイルとリストを削除できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

この手順では、クリーンアップする未使用のスタイルとリストを含む Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: クリーニング前にスタイルとリストを数える

クリーニングの前に、ドキュメント内に存在するスタイルとリストの数を数えます。カウンターを表示するには、次のコードを使用します。

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

これらの手順では、クリーニング前のドキュメント内に存在するスタイルとリストの数を示します。

## ステップ 4: 使用されていないスタイルとリストをクリーンアップする

次に、ドキュメントから未使用のスタイルとリストをクリーンアップしましょう。クリーンアップを実行するには、次のコードを使用します。

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

このコードは、指定されたオプションを使用して、ドキュメントから未使用のスタイルとリストをクリーンアップします。この例では、`UnusedStyles`未使用のスタイルを削除するオプションを無効にし、`UnusedLists`使用されない場合でもリストを保持するオプション。

## ステップ 5: クリーニング後にスタイルとリストを数える

クリーンアップを実行した後、スタイルとリストを再度数えて、折りたたまれているかどうかを確認します。新しいカウンターを表示するには、次のコードを使用します。

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

これらの手順は、クリーニング後に残っているスタイルとリストの数を示しています。

### Aspose.Words for .NET を使用して未使用のスタイルとリストをクリーンアップするソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	//組み込みスタイルと組み合わせると、ドキュメントには 8 つのスタイルが含まれます。
	//ドキュメント内にテキストが存在する場合、カスタム スタイルは「使用済み」としてマークされます。
	//そのスタイルでフォーマットされています。これは、追加した 4 つのスタイルが現在使用されていないことを意味します。
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//指定された CleanupOptions に応じて、ドキュメントから未使用のスタイルとリストを削除します。
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

必ず正しいドキュメント パスを指定してください。`dataDir`変数。

Aspose.Words for .NET を使用してドキュメントから未使用のスタイルとリストをクリーンアップする方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、この機能を独自のドキュメントに簡単に適用できます。

