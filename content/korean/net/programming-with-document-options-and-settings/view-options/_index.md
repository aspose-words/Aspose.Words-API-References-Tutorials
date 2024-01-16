---
title: 보기 옵션
linktitle: 보기 옵션
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서 표시 옵션을 구성하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/view-options/
---

이 튜토리얼에서는 Aspose.Words for .NET으로 디스플레이 옵션을 구성하기 위한 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서의 보기 모드와 확대/축소 수준을 사용자 지정할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 표시 옵션을 구성하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 디스플레이 옵션 구성

이제 문서 표시 옵션을 구성하겠습니다. 다음 코드를 사용하여 표시 모드와 확대/축소 수준을 설정합니다.

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

이 코드는 보기 모드를 "PageLayout"으로 설정하고 확대/축소 수준을 50%로 설정합니다.

### .NET용 Aspose.Words를 사용하는 보기 옵션의 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서 표시 옵션을 구성하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 자신의 문서 표시를 쉽게 사용자 정의할 수 있습니다.