---
title: 다른 페이지 설정
linktitle: 다른 페이지 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 다양한 페이지 설정 설정으로 문서를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/different-page-setup/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 다른 페이지 설정 설정이 있는 문서를 다른 문서에 추가하는 방법을 설명합니다. 제공된 소스 코드는 소스 및 대상 문서에 대해 서로 다른 페이지 설정을 지정하고 적절한 연속성과 번호 매기기를 보장하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 원본 및 대상 문서 열기

 다음을 사용하여 원본 및 대상 문서를 엽니다.`Document` 클래스 생성자. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 원본 문서의 페이지 설정 지정

 적절한 연속성과 번호 매기기를 보장하려면 소스 문서의 페이지 설정 설정을 조정하십시오. 이 예에서는 섹션 시작을 다음으로 설정했습니다.`SectionStart.Continuous` 페이지 번호 매기기를 다시 시작하세요. 또한 페이지 너비, 높이 및 방향이 대상 문서의 마지막 섹션과 일치하는지 확인합니다.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 4단계: 단락 서식 수정

 적절한 서식을 유지하려면 소스 문서의 모든 단락을 반복하고`KeepWithNext`재산`true`이렇게 하면 추가 프로세스 중에 단락이 함께 유지됩니다.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 5단계: 원본 문서를 대상 문서에 추가

 사용`AppendDocument` 소스 형식을 유지하면서 수정된 소스 문서를 대상 문서에 추가하는 대상 문서의 메서드입니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6단계: 대상 문서 저장

 마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 다양한 페이지 설정 설정으로 문서를 추가하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 다른 페이지 설정을 위한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// 대상 문서가 끝난 후 바로 계속되도록 소스 문서를 설정합니다.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// 원본 문서 시작 부분에서 페이지 번호 매기기를 다시 시작합니다.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// 원본 문서의 페이지 설정이 다를 때 이런 일이 발생하지 않도록 하려면 다음을 확인하십시오.
	// 설정은 대상 문서의 마지막 섹션 간에 동일합니다.
	// 원본 문서에 이어지는 연속 섹션이 더 있는 경우
	//해당 섹션에 대해 이 작업을 반복해야 합니다.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// 소스 문서의 모든 섹션을 반복합니다.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```