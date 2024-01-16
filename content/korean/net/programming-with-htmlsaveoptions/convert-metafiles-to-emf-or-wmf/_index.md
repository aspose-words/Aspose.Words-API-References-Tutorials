---
title: 메타파일을 Emf 또는 Wmf로 변환
linktitle: 메타파일을 Emf 또는 Wmf로 변환
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 HTML로 변환할 때 메타파일을 EMF 또는 WMF 형식으로 변환하는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 메타파일을 EMF 또는 WMF 형식으로 변환하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서를 HTML로 변환할 때 메타파일 형식의 이미지를 EMF 또는 WMF와 같은 보다 호환되는 형식으로 변환할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서에 이미지 삽입

이 단계에서는 변환할 문서에 이미지를 삽입합니다. HTML 태그를 사용하여 데이터 소스의 이미지를 삽입하려면 다음 코드를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 이 코드는`Document` 그리고`DocumentBuilder` 문서를 작성합니다. 삽입합니다`<img>` base64로 인코딩된 이미지로 문서에 태그를 추가하세요.

## 3단계: HTML 저장 옵션 설정

이제 이미지에 사용할 메타파일 형식을 포함하여 HTML 저장 옵션을 설정하겠습니다. 다음 코드를 사용하세요.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 이 코드는`HtmlSaveOptions` 그리고 세트`MetafileFormat` 에게`HtmlMetafileFormat.EmfOrWmf` HTML로 변환할 때 메타파일을 EMF 또는 WMF 형식으로 변환해야 함을 지정합니다.

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 이전에 정의한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

이 코드는 문서를 HTML로 변환하고 설정된 저장 옵션에 따라 EMF 또는 WMF 형식의 변환된 메타파일이 포함된 파일에 저장합니다.

### .NET용 Aspose.Words를 사용하여 메타파일을 Emf 또는 Wmf로 변환하기 위한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 문서 디렉토리에 대한 올바른 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 문서를 HTML로 변환할 때 메타파일을 EMF 또는 WMF 형식으로 변환하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 변환된 HTML 문서의 메타파일을 쉽게 관리할 수 있습니다.