---
title: 빌더를 사용하여 문서 삽입
linktitle: 빌더를 사용하여 문서 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 다른 문서 끝에 문서를 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/insert-document-with-builder/
---

 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서를 다른 문서에 삽입하는 방법을 설명합니다.`DocumentBuilder` 수업. 제공된 소스 코드는 소스 서식을 유지하면서 다른 문서의 끝에 문서를 삽입하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 원본 및 대상 문서 열기

 다음을 사용하여 원본 및 대상 문서를 엽니다.`Document` 클래스 생성자. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: DocumentBuilder 초기화

 새 인스턴스를 생성합니다.`DocumentBuilder` 클래스를 선택하고 대상 문서를 매개변수로 전달합니다.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## 4단계: DocumentBuilder 배치

이동`DocumentBuilder` 문서 끝까지`MoveToDocumentEnd` 방법. 삽입된 문서에서 기존 콘텐츠를 분리하려면 페이지 나누기를 삽입하세요.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 5단계: 원본 문서 삽입

 사용`InsertDocument` 의 방법`DocumentBuilder` 소스 문서를 대상 문서에 삽입하는 클래스입니다. 가져오기 형식 모드를 다음으로 설정합니다.`ImportFormatMode.KeepSourceFormatting` 소스 형식을 유지합니다.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6단계: 수정된 문서 저장

마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 다른 문서에 문서를 삽입하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 빌더로 문서 삽입에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```