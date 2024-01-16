---
title: 소스를 함께 유지
linktitle: 소스를 함께 유지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 소스 콘텐츠를 대상 문서와 함께 유지하면서 Word 문서를 결합하고 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/keep-source-together/
---

이 튜토리얼은 Aspose.Words for .NET의 Keep Source Together 기능을 사용하는 과정을 안내합니다. 이 기능을 사용하면 원본 문서의 내용을 대상 문서의 내용과 함께 유지하면서 여러 Word 문서를 결합하고 추가할 수 있습니다. 

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.Words가 설치되었습니다. Aspose 웹사이트에서 다운로드하거나 NuGet을 통해 설치할 수 있습니다.
2. Visual Studio 또는 기타 C# 개발 환경.

## 1단계: 문서 디렉터리 초기화

 먼저 문서 디렉터리의 경로를 설정해야 합니다. 값을 수정합니다.`dataDir` 문서가 있는 경로에 대한 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 및 대상 문서 로드

 다음으로 Aspose.Words를 사용하여 소스 및 대상 문서를 로드해야 합니다.`Document` 수업. 다음에서 파일 이름을 업데이트합니다.`Document` 문서 이름에 따른 생성자.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3단계: 대상 문서의 내용 뒤에 소스 문서가 나타나도록 설정

 소스 문서가 대상 문서의 내용 바로 뒤에 나타나도록 하려면`SectionStart` 소스 문서의 첫 번째 섹션 속성을`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4단계: 소스 문서에 대한 "다음 항목에 유지" 단락 서식 설정

소스 문서의 단락을 함께 유지하려면 문서의 각 단락을 반복하고`KeepWithNext`재산`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 5단계: 원본 문서를 대상 문서에 추가

 이제 다음을 사용하여 소스 문서를 대상 문서에 추가할 수 있습니다.`AppendDocument` 의 방법`Document` 수업. 그만큼`ImportFormatMode.KeepSourceFormatting` 매개변수를 사용하면 추가 작업 중에 소스 형식이 유지됩니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6단계: 최종 문서 저장

 마지막으로 다음을 사용하여 "소스를 함께 유지" 기능을 활성화한 상태로 병합된 문서를 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### .NET용 Aspose.Words를 사용하여 소스를 함께 유지하기 위한 예제 소스 코드 

다음은 .NET용 Aspose.Words를 사용하는 C#의 "소스 함께 유지" 기능에 대한 전체 소스 코드입니다.


```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// 대상 문서의 내용 바로 뒤에 나타나도록 소스 문서를 설정합니다.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Keep Source Together 기능을 성공적으로 구현했습니다. 최종 문서에는 소스 문서의 단락과 함께 병합된 내용이 포함됩니다.