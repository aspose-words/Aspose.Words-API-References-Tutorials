---
title: 연속 가입
linktitle: 연속 가입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 서식을 유지하면서 두 문서를 연속적으로 결합하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/join-continuous/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 두 문서를 연속적으로 결합하는 방법을 설명합니다. 제공된 소스 코드는 원래 형식을 유지하면서 다른 문서의 끝에 문서를 추가하는 방법을 보여줍니다.

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

## 3단계: 연속 구간 시작 설정

 소스 문서가 대상 문서의 내용 바로 뒤에 나타나도록 하려면`SectionStart` 소스 문서의 첫 번째 섹션 속성을`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4단계: 소스 문서 추가

 다음을 사용하여 원본 문서를 대상 문서에 추가합니다.`AppendDocument` 의 방법`Document` 수업. 가져오기 형식 모드를 다음으로 설정합니다.`ImportFormatMode.KeepSourceFormatting` 소스 문서의 원래 스타일을 유지합니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5단계: 수정된 문서 저장

 마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

이로써 .NET용 Aspose.Words를 사용하여 두 문서를 지속적으로 결합하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 Join Continuous의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// 문서가 대상 문서 내용 바로 뒤에 나타나도록 합니다.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// 소스 문서에 있는 원래 스타일을 사용하여 소스 문서를 추가합니다.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```