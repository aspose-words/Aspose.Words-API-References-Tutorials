---
title: 글꼴 이름 확인
linktitle: 글꼴 이름 확인
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 HTML로 변환할 때 누락된 글꼴 이름을 해결하기 위한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/resolve-font-names/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 누락된 글꼴 이름을 해결하기 위한 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서를 HTML로 변환할 때 누락된 글꼴 이름을 자동으로 해결할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 처리할 문서를 로드합니다. 다음 코드를 사용하여 지정된 디렉터리에서 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 이 코드는`Document` 지정된 디렉토리에서 문서를 로드합니다.

## 3단계: HTML 백업 옵션 구성

이제 변환 중에 누락된 글꼴 이름을 해결하기 위해 HTML 저장 옵션을 구성하겠습니다. 다음 코드를 사용하세요.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 이 코드는`HtmlSaveOptions`그리고`ResolveFontNames` 옵션`true`HTML로 변환할 때 누락된 글꼴 이름을 해결합니다. 또한,`PrettyFormat` 옵션이 다음으로 설정되어 있습니다.`true` 형식이 좋은 HTML 코드를 얻으려면

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 앞서 구성한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

이 코드는 누락된 글꼴 이름을 자동으로 확인하여 문서를 HTML로 변환하고 변환된 HTML 파일을 지정된 디렉터리에 저장합니다.

### .NET용 Aspose.Words를 사용하여 글꼴 이름 확인에 대한 예제 소스 코드

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 문서 디렉토리에 대한 올바른 경로를 지정하십시오.`dataDir` 변하기 쉬운.