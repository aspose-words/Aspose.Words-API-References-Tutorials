---
title: 자원 수출
linktitle: 자원 수출
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 HTML로 저장할 때 문서 리소스를 내보내는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-resources/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서 리소스를 내보내는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서를 HTML 형식으로 저장할 때 글꼴과 같은 리소스를 외부 파일로 내보낼 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 내보낼 문서를 로드합니다. 다음 코드를 사용하여 지정된 디렉터리에서 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 코드는`Document` 지정된 디렉토리에서 문서를 로드합니다.

## 3단계: HTML 백업 옵션 구성

이제 문서 리소스를 내보내도록 HTML 저장 옵션을 구성하겠습니다. 다음 코드를 사용하세요.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 이 코드는`HtmlSaveOptions` 다음 옵션을 설정합니다.

- `CssStyleSheetType` 로 설정되어 있습니다`CssStyleSheetType.External`CSS 스타일 시트를 외부 파일로 내보냅니다.
- `ExportFontResources` 로 설정되어 있습니다`true` 글꼴 리소스를 내보냅니다.
- `ResourceFolder` 리소스가 저장될 대상 디렉터리를 지정합니다.
- `ResourceFolderAlias` 리소스에 액세스하는 데 사용되는 URL 별칭을 지정합니다.

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 앞서 구성한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

이 코드는 문서를 HTML로 변환하고 지정된 URL 별칭을 사용하여 리소스를 지정된 디렉터리에 저장합니다.

### .NET용 Aspose.Words를 사용하여 리소스 내보내기에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 문서 디렉토리에 대한 올바른 경로를 지정하십시오.`dataDir` 변하기 쉬운.