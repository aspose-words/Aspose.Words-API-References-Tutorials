---
title: 가져오기 형식 옵션으로 추가
linktitle: 가져오기 형식 옵션으로 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 가져오기 형식 옵션이 있는 문서를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/append-with-import-format-options/
---

이 튜토리얼에서는 가져오기 형식 옵션을 사용하여 .NET용 Aspose.Words를 사용하여 한 문서의 내용을 다른 문서에 추가하는 방법을 설명합니다. 제공된 소스 코드는 소스 및 대상 문서를 열고, 가져오기 형식 옵션을 지정하고, 소스 문서를 대상 문서에 추가하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 원본 및 대상 문서 열기

 다음을 사용하여 원본 및 대상 문서를 엽니다.`Document` 클래스 생성자. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3단계: 가져오기 형식 옵션 지정

 인스턴스를 생성합니다.`ImportFormatOptions` 가져오기 형식 옵션을 지정하는 클래스입니다. 이 예에서는`KeepSourceNumbering` 대상 문서와 충돌이 있는 경우 원본 문서의 번호 매기기가 사용되도록 하는 속성입니다.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 4단계: 원본 문서를 대상 문서에 추가

 사용`AppendDocument` 소스 문서를 추가하는 대상 문서의 메서드입니다. 통과하다`ImportFormatMode.UseDestinationStyles` 대상 문서의 스타일과 서식을 사용하기 위한 두 번째 매개변수입니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 5단계: 대상 문서 저장

마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 가져오기 형식 옵션이 있는 문서 추가 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 가져오기 형식 옵션으로 추가에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// 원본 문서와 대상 문서의 번호 매기기가 충돌하는 경우 다음을 지정합니다.
	// 그런 다음 원본 문서의 번호 매기기가 사용됩니다.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```