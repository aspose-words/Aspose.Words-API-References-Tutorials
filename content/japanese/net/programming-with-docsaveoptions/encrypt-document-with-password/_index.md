---
title: パスワードで文書を暗号化
linktitle: パスワードで文書を暗号化
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをパスワードで暗号化する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
C# アプリケーションでファイルを使用して文書処理を行う場合、ドキュメントのセキュリティは不可欠です。 .NET 用の Aspose.Words ライブラリを使用すると、ドキュメントをパスワードで暗号化して簡単に保護できます。このステップバイステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、DocSaveOptions 保存オプションを使用してドキュメントを暗号化する方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## ステップ 1: ドキュメント ディレクトリの定義

最初のステップは、暗号化されたドキュメントを保存するディレクトリを設定することです。完全なディレクトリ パスを指定する必要があります。例えば ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 2: ドキュメントの作成と編集

次に、ドキュメントを作成し、それにコンテンツを追加できます。 Aspose.Words が提供する DocumentBuilder クラスを使用して、ドキュメントのコンテンツを構築します。例えば ：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

この例では、新しい空のドキュメントを作成し、DocumentBuilder を使用してテキスト「Hello World!」を書き込みます。

## ステップ 3: 録音オプションを構成する

次に、ドキュメントの保存オプションを設定しましょう。 DocSaveOptions クラスを使用して保存設定を指定します。例えば ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

この例では、新しい DocSaveOptions オブジェクトを作成し、Password プロパティを「password」に設定して、このパスワードでドキュメントを暗号化します。

## ステップ 4: 「パスワードを使用してドキュメントを暗号化」機能を有効にする

すでにオプションを設定しています

指定したパスワードを使用して登録すると、「パスワードによる文書の暗号化」機能が自動的に有効になります。これにより、文書は保存時に指定されたパスワードで暗号化されます。

## ステップ 5: ドキュメントを保存する

最後に、Document クラスの Save メソッドを使用してドキュメントを保存できます。ファイルへのフルパスと任意のファイル名を指定します。例えば ：

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

必ず「dataDir」をドキュメントへのディレクトリ パスに置き換えてください。

### Aspose.Words for .NET を使用した「パスワードによるドキュメントの暗号化」機能を備えた DocSaveOptions 保存オプションのソース コード例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントの作成と編集
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

//「パスワードを使用してドキュメントを暗号化」機能を使用して保存オプションを構成する
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

//指定したオプションを使用してドキュメントを保存します
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、DocSaveOptions 保存オプションを使用してパスワードでドキュメントを暗号化する方法を説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。パスワードを使用して文書を暗号化すると、文書を扱う際の機密性と安全性が保証されます。