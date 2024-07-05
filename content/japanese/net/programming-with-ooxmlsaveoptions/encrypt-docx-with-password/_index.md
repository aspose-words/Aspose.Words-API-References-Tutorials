---
title: Docx をパスワードで暗号化する
linktitle: Docx をパスワードで暗号化する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して DOCX ファイルをパスワードで暗号化する方法を学びます。ドキュメント セキュリティに関する完全なチュートリアルです。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
このチュートリアルでは、Aspose.Words for .NET を使用して DOCX ファイルをパスワードで暗号化するための C# ソース コードについて説明します。この機能を使用すると、指定したパスワードでのみアクセスできるようにすることで、ドキュメントを保護できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: ドキュメントの読み込み

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

このステップでは、`Document`メソッドを呼び出して、読み込む DOCX ファイルへのパスを渡します。

## ステップ3: OOXMLバックアップオプションの設定

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

このステップでは、新しいOOXMLファイルを作成して、OOXML保存オプションを設定します。`OoxmlSaveOptions`オブジェクト。文書を暗号化するためのパスワードを指定するには、`Password`プロパティをカスタム パスワードに追加します。

## ステップ4: パスワードで文書を暗号化する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを`.docx`拡張子と指定された保存オプションを指定します。

これで、ソース コードを実行して、DOCX ドキュメントをパスワードで暗号化できます。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx」という名前で保存されます。暗号化されたドキュメントを開くにはパスワードが必要になるため、パスワードは必ず安全に保管してください。

### Aspose.Words for .NET を使用して Docx をパスワードで暗号化するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して DOCX ファイルをパスワードで暗号化する機能について説明しました。指定したパスワードでのみアクセスできるようにすることでドキュメントを保護する方法を学習しました。

ドキュメントの暗号化は、機密情報を保護するための重要なセキュリティ対策です。Aspose.Words for .NET を使用すると、この機能をアプリケーションに簡単に追加できます。

提供されている手順に従うことで、Aspose.Words for .NET プロジェクトにパスワード暗号化を統合し、ドキュメントの機密性を確保できます。

Aspose.Words for .NET が提供する他の機能を自由に試して、高度なドキュメント操作機能でアプリケーションを充実させてください。
