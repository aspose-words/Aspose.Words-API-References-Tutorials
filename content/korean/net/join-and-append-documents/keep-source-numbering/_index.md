---
title: 소스 번호 유지
linktitle: 소스 번호 유지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 서식을 유지하면서 문서를 가져오는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/keep-source-numbering/
---
## 소개

 .NET용 Aspose.Words로 작업할 때 형식을 유지하면서 한 소스에서 다른 소스로 문서를 가져오는 작업을 다음을 사용하여 효율적으로 처리할 수 있습니다.`NodeImporter` 수업. 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET용 Aspose.Words가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드하십시오.[여기](https://releases.aspose.com/words/net/).
- C# 및 .NET 프로그래밍에 대한 기본 지식.

## 네임스페이스 가져오기

먼저 프로젝트에 필요한 네임스페이스를 포함합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## 1단계: 프로젝트 설정

Visual Studio에서 새 C# 프로젝트를 생성하고 NuGet 패키지 관리자를 통해 Aspose.Words를 설치하는 것으로 시작합니다.

## 2단계: 문서 초기화
소스의 인스턴스를 생성합니다(`srcDoc`) 및 목적지(`dstDoc`) 문서.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 가져오기 옵션 구성
번호가 매겨진 단락을 포함하여 소스 서식을 유지하도록 가져오기 옵션을 설정합니다.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## 4단계: 단락 가져오기
소스 문서의 단락을 반복하여 대상 문서로 가져옵니다.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## 5단계: 문서 저장
병합된 문서를 원하는 위치에 저장합니다.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## 결론

 결론적으로, Aspose.Words for .NET을 사용하여 형식을 유지하면서 문서를 가져오는 것은 다음과 같이 간단합니다.`NodeImporter` 수업. 이 방법을 사용하면 문서의 원래 모양과 구조가 원활하게 유지됩니다.

## FAQ

### 서식 스타일이 다른 문서를 가져올 수 있나요?
 예,`NodeImporter` 클래스는 다양한 서식 스타일로 문서 가져오기를 지원합니다.

### 내 문서에 복잡한 표와 이미지가 포함되어 있으면 어떻게 되나요?
Aspose.Words for .NET은 가져오기 작업 중에 테이블 및 이미지와 같은 복잡한 구조를 처리합니다.

### Aspose.Words는 모든 버전의 .NET과 호환됩니까?
Aspose.Words는 원활한 통합을 위해 .NET Framework 및 .NET Core 버전을 지원합니다.

### 문서를 가져오는 동안 오류를 처리하려면 어떻게 해야 합니까?
가져오기 프로세스 중에 발생할 수 있는 예외를 처리하려면 try-catch 블록을 사용하십시오.

### .NET용 Aspose.Words에 대한 자세한 문서는 어디서 찾을 수 있나요?
 방문하다[선적 서류 비치](https://reference.aspose.com/words/net/) 포괄적인 가이드 및 API 참조를 확인하세요.
