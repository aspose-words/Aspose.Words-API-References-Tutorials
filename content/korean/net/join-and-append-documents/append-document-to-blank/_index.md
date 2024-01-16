---
title: 공백에 문서 추가
linktitle: 공백에 문서 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words에서 빈 대상 문서에 문서를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/append-document-to-blank/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 한 문서의 내용을 빈 대상 문서에 추가하는 방법을 설명합니다. 제공된 소스 코드는 새 문서를 만들고, 해당 내용을 제거한 다음, 소스 문서를 추가하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 새 대상 문서 만들기

 새로 만들기`Document` 대상 문서의 개체입니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## 3단계: 대상 문서에서 기존 콘텐츠 제거

 깨끗한 대상 문서를 보장하려면 다음을 사용하여 문서에서 기존 내용을 모두 제거하십시오.`RemoveAllChildren` 방법.

```csharp
dstDoc.RemoveAllChildren();
```

## 4단계: 원본 문서를 대상 문서에 추가

 다음을 사용하여 원본 문서의 내용을 대상 문서에 추가합니다.`AppendDocument` 방법`ImportFormatMode.KeepSourceFormatting` 옵션.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5단계: 대상 문서 저장

 마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 빈 대상 문서에 문서를 추가하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 공백에 문서 추가에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// 대상 문서가 비어 있지 않아 종종 추가된 문서 앞에 빈 페이지가 나타납니다.
	// 이는 기본 문서에 빈 섹션이 있고 새 문서가 다음 페이지에서 시작되기 때문입니다.
	// 추가하기 전에 대상 문서에서 모든 콘텐츠를 제거하세요.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```