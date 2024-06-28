---
title: 소스 형식 유지
linktitle: 소스 형식 유지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 원래 형식을 유지하면서 소스 문서를 대상 문서에 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/keep-source-formatting/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 소스 문서의 원래 형식을 유지하면서 소스 문서를 대상 문서에 추가하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 저장될 문서 디렉터리 경로입니다.

## 2단계: 대상 및 원본 문서 만들기

 인스턴스 생성`Document` 대상 및 원본 문서의 경우.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 3단계: 원본 문서를 대상 문서에 추가

 사용`AppendDocument` 소스 문서를 추가하는 대상 문서의 메서드입니다. 통과하다`ImportFormatMode.KeepSourceFormatting` 원본 문서의 원래 형식을 유지하기 위해 가져오기 형식 모드로 사용됩니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 4단계: 수정된 문서 저장

 다음을 사용하여 수정된 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 원래 형식을 유지하면서 소스 문서를 대상 문서에 추가하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 소스 서식 유지에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// 원본 문서를 대상 문서에 추가합니다.
	// 원본 문서를 가져올 때 원본 형식을 유지하려면 형식 모드를 전달하세요.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```