---
title: 画像の箇条書きを保存しないでください
linktitle: 画像の箇条書きを保存しないでください
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の箇条書きイメージの保存を無効にする方法を説明します。
type: docs
weight: 10
url: /ja/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

図付き箇条書きは、Word 文書でカスタムの箇条書きを追加するためによく使用される機能です。ただし、Aspose.Words Library for .NET を使用してドキュメントを操作する場合、場合によっては、イメージの箇条書き登録を無効にする必要がある場合があります。このステップバイステップ ガイドでは、.NET 用の Aspose.Words C# ソース コードを使用して、DocSaveOptions 保存オプションを使用して画像の箇条書き保存を無効にする方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## ステップ 1: ドキュメント ディレクトリの設定

最初のステップは、ドキュメントを配置するディレクトリを定義することです。完全なディレクトリ パスを指定する必要があります。例えば ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: 画像の箇条書きを含むドキュメントをロードする

次に、画像の箇条書きを含むドキュメントをロードする必要があります。 Document クラスを使用して、ファイルからドキュメントを読み込みます。例えば ：

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

この例では、「画像箇条書きポイント.docx」ファイルからドキュメントをロードしています。

  ドキュメントディレクトリにあります。

## ステップ 3: 録音オプションを構成する

次に、ドキュメントの保存オプションを設定しましょう。 DocSaveOptions クラスを使用して保存設定を指定します。例えば ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

この例では、新しい DocSaveOptions オブジェクトを作成し、SavePictureBullet プロパティを false に設定して、図の箇条書きの保存を無効にします。

## ステップ 4: 「画像の箇条書きを保存しない」機能を有効にする

「画像の箇条書きを保存しない」機能を有効にするために、SavePictureBullet を false に設定して保存オプションをすでに構成しています。これにより、画像の箇条書きが最終ドキュメントに保存されなくなります。

## ステップ 5: ドキュメントを保存する

最後に、Document クラスの Save メソッドを使用してドキュメントを保存できます。ファイルへのフルパスと任意のファイル名を指定します。例えば ：

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

必ず「dataDir」をドキュメントへのディレクトリ パスに置き換えてください。

## Aspose.Words for .NET を使用した「画像の箇条書きを保存しない」機能を備えた DocSaveOptions 保存オプションのソース コード例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//画像の箇条書きを含むドキュメントをロードする
Document doc = new Document(dataDir + "Image bullet points.docx");

//「画像の箇条書きを保存しない」機能で保存オプションを構成する
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

//指定したオプションを使用してドキュメントを保存します
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用してドキュメント内の箇条書きイメージの保存を無効にする方法について説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。状況によっては、図の箇条書きの保存を無効にすると、図の箇条書きを保存せずに文書の構造と書式を保持できる場合があります。