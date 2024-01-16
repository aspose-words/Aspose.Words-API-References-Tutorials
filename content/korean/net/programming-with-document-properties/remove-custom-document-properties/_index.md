---
title: 사용자 정의 문서 속성 제거
linktitle: 사용자 정의 문서 속성 제거
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에서 사용자 정의 속성을 제거하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/remove-custom-document-properties/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 문서에서 사용자 정의 속성을 제거하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서에서 특정 사용자 정의 속성을 제거할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 사용자 정의 속성을 제거하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 사용자 정의 속성 삭제

이제 문서에서 특정 사용자 정의 속성을 제거해 보겠습니다. 다음 코드를 사용하세요.

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

이 코드는 문서에서 "승인된 날짜" 사용자 정의 속성을 제거합니다. "승인된 날짜"를 제거하려는 사용자 정의 속성의 이름으로 바꿀 수 있습니다.

### .NET용 Aspose.Words를 사용하여 사용자 정의 문서 속성 제거에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 .NET용 Aspose.Words를 사용하여 문서에서 사용자 정의 속성을 제거하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 자신의 문서에서 사용자 정의 속성을 쉽게 제거할 수 있습니다.