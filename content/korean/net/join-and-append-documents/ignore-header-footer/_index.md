---
title: 머리글 바닥글 무시
linktitle: 머리글 바닥글 무시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 머리글과 바닥글 내용을 무시하면서 문서를 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/ignore-header-footer/
---

이 튜토리얼에서는 머리글과 바닥글 내용을 무시하면서 문서를 추가하기 위해 .NET용 Aspose.Words를 사용하는 방법을 설명합니다. 제공된 소스 코드는 추가 프로세스 중에 머리글과 바닥글을 제외하도록 가져오기 형식 옵션을 설정하는 방법을 보여줍니다.

## 1단계: 프로젝트 설정

다음 필수 구성 요소가 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Words가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Releases]https://releases.aspose.com/words/net/ 또는 NuGet 패키지 관리자를 사용하여 설치하세요.
- 원본 및 대상 문서가 있는 문서 디렉터리 경로입니다.

## 2단계: 원본 및 대상 문서 열기

 다음을 사용하여 원본 및 대상 문서를 엽니다.`Document` 클래스 생성자. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하세요.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 가져오기 형식 옵션 설정

 인스턴스를 생성합니다.`ImportFormatOptions` 클래스를 설정하고`IgnoreHeaderFooter`재산`false`. 이렇게 하면 추가 프로세스 중에 머리글과 바닥글 내용이 포함됩니다.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## 4단계: 원본 문서를 대상 문서에 추가

 사용`AppendDocument` 소스 문서를 추가하는 대상 문서의 메서드입니다. 통과하다`ImportFormatMode.KeepSourceFormatting` 두 번째 매개변수로 가져오기 형식 옵션을 세 번째 매개변수로 사용합니다.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## 5단계: 대상 문서 저장

 마지막으로 다음을 사용하여 수정된 대상 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

이것으로 Aspose.Words for .NET을 사용하여 머리글과 바닥글 내용을 무시하고 문서를 추가하는 구현이 완료되었습니다.

### .NET용 Aspose.Words를 사용하여 머리글 바닥글 무시에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```