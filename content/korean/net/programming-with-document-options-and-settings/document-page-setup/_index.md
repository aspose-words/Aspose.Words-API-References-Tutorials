---
title: 문서 페이지 설정
linktitle: 문서 페이지 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서 레이아웃을 설정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/document-page-setup/
---

이 튜토리얼에서는 Aspose.Words for .NET으로 문서 레이아웃을 구성하기 위한 C# 소스 코드를 안내합니다. 이 기능을 사용하면 레이아웃 모드, 줄당 문자 수, 페이지당 줄 수를 설정할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 구성하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 레이아웃 설정

이제 문서 레이아웃을 구성해 보겠습니다. 다음 코드를 사용하여 레이아웃 모드, 줄당 문자 수 및 페이지당 줄 수를 설정합니다.

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

이 코드는 레이아웃 모드를 "Grid"로 설정한 다음 줄당 문자 수와 페이지당 줄 수를 지정합니다.

### .NET용 Aspose.Words를 사용한 문서 페이지 설정의 예제 소스 코드


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// 문서 그리드 동작을 정의할 수 있는 섹션의 레이아웃 모드를 설정합니다.
	// 문서 격자선 탭은 MS Word의 페이지 설정 대화 상자에 표시됩니다.
	// 아시아 언어가 편집 언어로 정의된 경우.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서의 레이아웃을 구성하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 자신의 문서 레이아웃을 쉽게 사용자 정의할 수 있습니다.