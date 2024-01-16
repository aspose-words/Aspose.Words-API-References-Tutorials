---
title: 러시아어를 기본 편집 언어로 설정
linktitle: 러시아어를 기본 편집 언어로 설정
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 러시아어를 문서의 기본 편집 언어로 설정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 러시아어를 기본 편집 언어로 설정하는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 문서를 로드할 때 기본 언어를 설정할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 러시아어를 기본 편집 언어로 설정하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

## 3단계: 기본 언어 확인하기

문서 업로드 후 기본 언어가 러시아어로 올바르게 설정되어 있는지 확인하겠습니다. 기본 언어 ID를 얻으려면 다음 코드를 사용하십시오.

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

코드는 언어 ID가 러시아어 ID와 일치하는지 확인합니다. 결과에 따라 해당 메시지가 표시됩니다.

### .NET용 Aspose.Words를 사용하여 러시아어를 기본 편집 언어로 설정하기 위한 예제 소스 코드

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 올바른 문서 경로를 지정하십시오.`dataDir` 변하기 쉬운.

이제 Aspose.Words for .NET을 사용하여 러시아어를 문서의 기본 편집 언어로 설정하는 방법을 배웠습니다. 단계 가이드를 따르면