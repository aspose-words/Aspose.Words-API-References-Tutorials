---
title: CSS 클래스 이름 접두사 추가
linktitle: CSS 클래스 이름 접두사 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 HTML로 변환할 때 CSS 클래스 이름 접두사를 추가하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 CSS 클래스 이름 접두사를 추가하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서를 HTML로 변환할 때 생성된 CSS 클래스 이름에 사용자 정의 접두사를 추가할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 HTML로 변환하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
//문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: HTML 저장 옵션 설정

이제 CSS 스타일시트 유형 및 CSS 클래스 이름 접두사를 포함한 HTML 저장 옵션을 설정해 보겠습니다. 다음 코드를 사용하세요.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 이 코드는`HtmlSaveOptions` 그리고 세트`CssStyleSheetType` 에게`CssStyleSheetType.External` 외부 CSS 스타일 시트를 생성하고`CssClassNamePrefix` 에게`"pfx_"` 접두사로`"pfx_"` CSS 클래스의 이름을 지정합니다.

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 앞서 정의한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

이 코드는 문서를 HTML로 변환하고 CSS 클래스 이름 접두사가 추가된 파일에 저장합니다.

### .NET용 Aspose.Words를 사용하여 CSS 클래스 이름 접두사 추가에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 .NET용 Aspose.Words를 사용하여 문서를 HTML로 변환할 때 CSS 클래스 이름 접두사를 추가하는 방법을 배웠습니다. 이 튜토리얼에서 제공하는 단계별 안내 단계에 따라 변환된 HTML 문서에서 CSS 클래스 이름을 사용자 정의할 수 있습니다.