---
title: 페이지 설정 및 섹션 서식 설정
linktitle: 페이지 설정 및 섹션 서식 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서 레이아웃 및 섹션 형식을 설정하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 레이아웃 및 섹션 서식을 설정하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 페이지 방향, 여백 및 용지 크기를 설정할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 만들기

이 단계에서는 새 문서를 만듭니다. 다음 코드를 사용하여 문서를 만들고 생성자를 초기화합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

## 3단계: 레이아웃 설정 및 문서 저장

이제 문서 레이아웃을 구성해 보겠습니다. 다음 코드를 사용하여 방향, 여백 및 용지 크기를 설정합니다.

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

이 코드는 페이지 방향을 가로로, 왼쪽 여백을 50으로, 용지 크기를 10x14로 설정합니다.

### .NET용 Aspose.Words를 사용하여 페이지 설정 및 섹션 서식 설정에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 문서를 저장할 디렉토리의 올바른 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서의 레이아웃과 섹션 형식을 구성하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 문서의 레이아웃과 서식을 쉽게 사용자 정의할 수 있습니다.