---
title: 새 서명란 생성 및 공급자 ID 설정
linktitle: 새 서명란 생성 및 공급자 ID 설정
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에서 새 서명란을 만들고 공급자 ID를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
이 자습서에서는 .NET용 Aspose.Words와 함께 새 서명 줄 만들기 및 공급자 ID 설정 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서에 서명란을 삽입하고, 사용자 정의 옵션을 설정하고, 문서에 서명할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 및 생성기 만들기

Document 클래스와 DocumentBuilder 개체의 인스턴스를 만드는 것부터 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 서명란 옵션 설정

SignatureLineOptions 클래스의 인스턴스를 만들고 원하는 옵션을 설정합니다.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 3단계: 서명란 삽입

DocumentBuilder 개체의 InsertSignatureLine() 메서드를 사용하여 문서에 서명란을 삽입합니다.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 4단계: 공급자 ID 설정

ProviderId 속성을 사용하여 서명란에 대한 공급자 ID를 설정합니다.

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

사용 사례에 맞는 올바른 공급자 ID를 지정해야 합니다.

## 5단계: 문서 저장

수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

문서를 저장하려면 올바른 경로와 파일 이름을 지정해야 합니다.

## 6단계: 문서에 서명하기

문서에 서명하려면 서명 옵션을 설정하고 DigitalSignatureUtil 클래스를 사용해야 합니다.

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

문서, 인증서 및 서명된 문서에 대한 올바른 경로를 지정하십시오.

### .NET용 Aspose.Words를 사용하여 새 서명 줄 생성 및 공급자 ID 설정에 대한 예제 소스 코드

다음은 새로운 서명란을 생성하고 .NET용 Aspose.Words를 사용하여 공급자 ID를 설정하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 쉽게 새 서명란을 만들고 Word 문서에 공급자 ID를 설정할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 새 서명란을 만들고 공급자 ID를 설정하는 기능을 살펴보았습니다. 제공된 단계를 따르면 사용자 정의 옵션이 포함된 서명란을 쉽게 삽입하고 제공자 ID를 사용하여 특정 제공자와 연결할 수 있습니다. 서명란을 추가하고 제공자 정보를 사용자 정의하면 문서의 진위성과 신뢰성이 향상됩니다. Aspose.Words for .NET은 Word 문서의 서명란과 디지털 인증서를 사용하여 단어 처리를 위한 강력한 API를 제공하여 서명 프로세스를 자동화하고 문서의 유효성을 보장할 수 있습니다.

### FAQ

#### Q: 서명란에 있는 제공자 ID는 무엇입니까?

A: 서명란의 공급자 ID는 디지털 서명 공급자를 나타내는 고유 식별자입니다. 서명을 담당하는 출처나 조직을 식별하는 데 도움이 됩니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 새 서명란을 어떻게 만들 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서에 새 서명란을 만들려면 다음 단계를 따르세요.
1.  인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 물체.
2.  인스턴스를 생성합니다.`SignatureLineOptions` 클래스를 선택하고 원하는 서명란 옵션을 설정하세요.
3.  사용`InsertSignatureLine` 의 방법`DocumentBuilder` 문서에 서명란을 삽입하는 개체입니다.

#### Q: 서명자 이름, 제목, 지침 등 서명란의 옵션을 사용자 정의할 수 있나요?

 A: 예, 서명란의 옵션을 사용자 정의할 수 있습니다. 그만큼`SignatureLineOptions` 클래스는 다음과 같이 원하는 옵션을 설정하는 속성을 제공합니다.`Signer`, `SignerTitle`, `Instructions`, `AllowComments`등. 서명란을 삽입하기 전에 이러한 속성을 수정할 수 있습니다.

#### Q: 서명란에 공급자 ID를 설정하는 목적은 무엇입니까?

A: 서명란에 공급자 ID를 설정하면 디지털 서명을 담당하는 소스나 조직을 식별하는 데 도움이 됩니다. 이를 통해 서명을 특정 공급자 또는 엔터티와 연결하여 서명의 출처와 신뢰성에 대한 추가 정보를 제공할 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 서명란에 대한 공급자 ID를 어떻게 설정할 수 있습니까?

A: .NET용 Aspose.Words를 사용하여 서명란에 대한 공급자 ID를 설정하려면 다음 단계를 따르세요.
1.  서명란을 삽입한 후 접속하세요.`ProviderId` 의 재산`SignatureLine` 물체.
2.  설정`ProviderId` 다음을 사용하여 원하는 공급자 ID 값에 속성을 추가합니다.`Guid` 데이터 형식.

#### Q: 새로운 서명란을 생성하고 공급자 ID를 설정한 후 문서에 서명할 수 있나요?

 A: 네, 새 서명란을 생성하고 공급자 ID를 설정한 후 문서에 서명할 수 있습니다. 문서에 서명하려면 서명란 ID, 공급자 ID, 설명, 서명 시간 등의 서명 옵션을 설정해야 합니다. 그런 다음`DigitalSignatureUtil.Sign` 디지털 인증서를 사용하여 문서에 서명하는 방법입니다.

#### 질문: Word 문서의 각 서명란에 특정 공급자 ID를 지정할 수 있습니까?

A: 예, Word 문서의 각 서명란에 특정 공급자 ID를 지정할 수 있습니다. 각 서명란을 삽입한 후 다음 페이지에 액세스하여 특정 서명란에 대한 공급자 ID를 설정할 수 있습니다.`ProviderId` 해당 재산의`SignatureLine` 물체.

#### Q: 새로운 서명란을 생성하고 공급자 ID를 설정한 후 수정된 문서를 어떻게 저장합니까?

 A: 새로운 서명란을 생성하고 제공자 ID를 설정한 후 수정된 문서를 저장하려면`Save` 의 방법`Document` 물체. 문서를 저장하려면 올바른 경로와 파일 이름을 지정하세요.

#### Q: Aspose.Words for .NET은 서명란 생성 및 서명을 위해 어떤 파일 형식을 지원합니까?

A: Aspose.Words for .NET은 DOCX 파일 형식으로 서명란을 생성하고 서명하는 것을 지원합니다. 제공된 메서드와 클래스를 사용하여 DOCX 파일에 서명란을 만들고 서명할 수 있습니다.

#### 질문: 서명란에 서명한 후 공급자 ID나 서명란의 기타 옵션을 수정할 수 있습니까?

답변: 서명란에 서명하면 문서 내용의 일부가 되며 별도로 수정할 수 없습니다. 공급자 ID 또는 기타 옵션 변경과 같이 서명란을 수정하려면 기존 서명을 제거하고 새 서명란을 만들어야 합니다.