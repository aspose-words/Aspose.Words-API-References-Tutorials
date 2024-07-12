---
title: 메타파일을 SVG로 변환
linktitle: 메타파일을 SVG로 변환
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 HTML로 변환할 때 메타파일을 SVG 형식으로 변환하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 메타파일을 SVG 형식으로 변환하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서를 HTML로 변환할 때 메타파일을 SVG 형식으로 변환할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서에 SVG 이미지 삽입

이 단계에서는 변환할 문서에 SVG 이미지를 삽입합니다. HTML 태그를 사용하여 SVG 이미지를 삽입하려면 다음 코드를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 이 코드는`Document`그리고`DocumentBuilder` 문서를 작성합니다. 이는`<svg>` 다음을 포함하는 태그`<polygon>` SVG 이미지의 모양과 스타일을 정의하는 속성이 있는 요소입니다.

## 3단계: HTML 저장 옵션 설정

이제 메타파일을 SVG 형식으로 변환하도록 지정하여 HTML 저장 옵션을 설정하겠습니다. 다음 코드를 사용하세요.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 이 코드는`HtmlSaveOptions` 그리고 세트`MetafileFormat` 에게`HtmlMetafileFormat.Svg` HTML로 변환할 때 메타파일을 SVG 형식으로 변환해야 함을 지정합니다.

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 앞서 정의한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

이 코드는 문서를 HTML로 변환하고 SVG로 변환된 메타파일과 함께 파일에 저장합니다.

### .NET용 Aspose.Words를 사용하여 메타파일을 Svg로 변환하기 위한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
