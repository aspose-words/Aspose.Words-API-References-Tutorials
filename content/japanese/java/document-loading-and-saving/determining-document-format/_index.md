---
title: Aspose.Words for Java でのドキュメント形式の決定
linktitle: ドキュメント形式の決定
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words を使用して Java でドキュメント形式を検出する方法を学びます。 DOC、DOCXなどを特定します。ファイルを効率的に整理します。
type: docs
weight: 25
url: /ja/java/document-loading-and-saving/determining-document-format/
---

## Aspose.Words for Java でのドキュメント形式の決定の概要

Java でドキュメント処理を行う場合、扱うファイルの形式を決定することが重要です。 Aspose.Words for Java は、ドキュメント形式を識別するための強力な機能を提供します。そのプロセスについて説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- [Aspose.Words for Java](https://releases.aspose.com/words/java/)
- システムにインストールされている Java Development Kit (JDK)
- Java プログラミングの基本的な知識

## ステップ 1: ディレクトリのセットアップ

まず、ファイルを効果的に整理するために必要なディレクトリを設定する必要があります。さまざまな種類のドキュメント用のディレクトリを作成します。

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

//ディレクトリが存在しない場合は作成します。
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

サポートされているドキュメント タイプ、不明なドキュメント タイプ、暗号化されたドキュメント タイプ、および 97 より前のドキュメント タイプ用のディレクトリを作成しました。

## ステップ 2: ドキュメント形式の検出

次に、ディレクトリ内のドキュメントの形式を検出してみましょう。これを実現するには、Aspose.Words for Java を使用します。

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    //文書の種類を表示する
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        //必要に応じて、他のドキュメント形式のケースを追加します
    }

    //暗号化されたドキュメントを処理する
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        //他の種類のドキュメントを処理する
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

このコード スニペットでは、ファイルを反復処理し、その形式を検出し、ファイルをそれぞれのディレクトリに整理します。

## Aspose.Words for Java でドキュメント形式を決定するための完全なソース コード

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        //ディレクトリが存在しない場合は作成します。
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            //文書の種類を表示する
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## 結論

Aspose.Words for Java でドキュメント形式を決定することは、ドキュメントを効率的に処理するために不可欠です。このガイドで概説されている手順を使用すると、ドキュメント タイプを識別し、それに応じて Java アプリケーションで処理できます。

## よくある質問

### Aspose.Words for Java をインストールするにはどうすればよいですか?

 Aspose.Words for Java は、次の場所からダウンロードできます。[ここ](https://releases.aspose.com/words/java/)提供されるインストール手順に従ってください。

### サポートされているドキュメント形式は何ですか?

Aspose.Words for Java は、DOC、DOCX、RTF、HTML などを含むさまざまなドキュメント形式をサポートしています。完全なリストについてはドキュメントを参照してください。

### Aspose.Words for Java を使用して暗号化されたドキュメントを検出するにはどうすればよいですか?

使用できます`FileFormatUtil.detectFileFormat()`このガイドで説明するように、暗号化されたドキュメントを検出する方法。

### 古いドキュメント形式を使用する場合に制限はありますか?

MS Word 6 や Word 95 などの古い文書形式には、機能や最新のアプリケーションとの互換性の点で制限がある場合があります。必要に応じて、これらのドキュメントのアップグレードまたは変換を検討してください。

### Java アプリケーションでドキュメント形式の検出を自動化できますか?

はい、提供されたコードを Java アプリケーションに統合することで、ドキュメント形式の検出を自動化できます。これにより、検出された形式に基づいてドキュメントを処理できるようになります。