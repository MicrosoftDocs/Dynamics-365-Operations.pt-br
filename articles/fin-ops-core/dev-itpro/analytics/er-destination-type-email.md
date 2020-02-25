---
title: Tipo de destino de ER do email
description: Este tópico fornece informações sobre como configurar um destino de email para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019626"
---
# <span data-ttu-id="710ae-103"><a name="EmailDestinationType">Destino de email</a></span><span class="sxs-lookup"><span data-stu-id="710ae-103"><a name="EmailDestinationType">Email destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="710ae-104">Você pode configurar um destino de email para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.</span><span class="sxs-lookup"><span data-stu-id="710ae-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="710ae-105">Com base na configuração de destino, um documento gerado é entregue como um anexo de uma mensagem eletrônica.</span><span class="sxs-lookup"><span data-stu-id="710ae-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="710ae-106">Definir **Habilitado** para **Sim** para enviar um arquivo de saída por e-mail.</span><span class="sxs-lookup"><span data-stu-id="710ae-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="710ae-107">Depois que essa opção é ativada, você pode especificar os destinatários do email, bem como editar o assunto e o corpo da mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="710ae-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="710ae-108">Você pode configurar textos constantes para o assunto e corpo de email, ou pode usar [fórmulas](er-formula-language.md) de ER para criar textos de email dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="710ae-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="710ae-109">Você pode configurar endereços de email para o ER de duas formas.</span><span class="sxs-lookup"><span data-stu-id="710ae-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="710ae-110">A configuração pode ser concluída da mesma forma que o recurso Gerenciamento de impressão a conclui, ou você pode resolver um endereço de email usando uma referência direta à configuração de ER por meio de uma fórmula.</span><span class="sxs-lookup"><span data-stu-id="710ae-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="710ae-111">[![Habilitar destino de email](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="710ae-112">Tipos de endereço de email</span><span class="sxs-lookup"><span data-stu-id="710ae-112">Email address types</span></span>

<span data-ttu-id="710ae-113">Quando você seleciona **Editar** nos campos **Para** ou **Cc**, a caixa de diálogo **Email para** é exibida.</span><span class="sxs-lookup"><span data-stu-id="710ae-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="710ae-114">Você pode selecionar o tipo de endereço de email para uso.</span><span class="sxs-lookup"><span data-stu-id="710ae-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="710ae-115">Atualmente, são aceitos os tipos de email **Email de configuração** e **Gerenciamento de impressão**.</span><span class="sxs-lookup"><span data-stu-id="710ae-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="710ae-116">[![Selecionar tipo de email](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="710ae-117">Gerenciamento de impressão</span><span class="sxs-lookup"><span data-stu-id="710ae-117">Print management</span></span>

<span data-ttu-id="710ae-118">Se selecionar o tipo de email **Gerenciamento de impressão**, você poderá inserir os endereços de email fixos no campo **Para**.</span><span class="sxs-lookup"><span data-stu-id="710ae-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="710ae-119">[![Configurar endereços de email fixos](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="710ae-120">Para usar os endereços de e-mail não fixos, você deve selecionar o tipo de origem de e-mails para um destino de arquivo.</span><span class="sxs-lookup"><span data-stu-id="710ae-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="710ae-121">Os valores a seguir são suportados: **Cliente**, **Fornecedor**, **Cliente potencial**, **Contato**, **Concorrente**, **Trabalhador**, **Candidato**, **Fornecedor potencial** e **Fornecedor não permitido**.</span><span class="sxs-lookup"><span data-stu-id="710ae-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="710ae-122">Após selecionar um tipo de origem de email, use o botão ao lado do campo **Conta de origem do email** para abrir o formulário **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="710ae-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="710ae-123">Você pode usar este formulário para anexar uma fórmula que retorne, no tempo de execução, a **conta do participante** do tipo de origem selecionado no documento processado para o destino do email.</span><span class="sxs-lookup"><span data-stu-id="710ae-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="710ae-124">[![Configurar conta de origem de email](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="710ae-125">Fórmulas são específicas à configuração de ER.</span><span class="sxs-lookup"><span data-stu-id="710ae-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="710ae-126">Em **Fórmula**, digite uma referência específica a um tipo da parte do cliente ou fornecedor.</span><span class="sxs-lookup"><span data-stu-id="710ae-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="710ae-127">Em vez de digitar, você pode encontrar um nó da fonte de dados que represente a conta de cliente ou fornecedor e selecionar **Adicionar fonte de dados** para atualizar a fórmula.</span><span class="sxs-lookup"><span data-stu-id="710ae-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="710ae-128">Por exemplo, se você usar a configuração **Transferência de Crédito ISO 20022**, o nó que representa uma conta de fornecedor será `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span><span class="sxs-lookup"><span data-stu-id="710ae-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="710ae-129">Se você inserir um valor de sequência de caracteres, como `"DE-001"`, e salvar uma fórmula, um email será enviado à pessoa de contato do fornecedor, **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="710ae-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="710ae-130">[![Página Designer de fórmula de ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="710ae-131">[![Configurar conta de origem de email](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-131">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="710ae-132">Email de configuração</span><span class="sxs-lookup"><span data-stu-id="710ae-132">Configuration email</span></span>

<span data-ttu-id="710ae-133">Use esse tipo de email se a configuração que você usar tiver um nó nas fontes de dados que retorna um **endereço de email**.</span><span class="sxs-lookup"><span data-stu-id="710ae-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="710ae-134">Você pode usar fontes de dados e as funções no designer de fórmulas para obter um endereço de email corretamente formatado.</span><span class="sxs-lookup"><span data-stu-id="710ae-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="710ae-135">Por exemplo, se você usar a configuração **Transferência de Crédito ISO 20022**, o nó que representa um endereço de email da pessoa de contato de um fornecedor será `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="710ae-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="710ae-136">[![Configurar origem do endereço de email](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="710ae-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="710ae-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="710ae-137">Additional resources</span></span>

- [<span data-ttu-id="710ae-138">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="710ae-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="710ae-139">Destinos de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="710ae-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="710ae-140">Designer de fórmulas no relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="710ae-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
