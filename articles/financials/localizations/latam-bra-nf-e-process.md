---
title: Visão geral do processo de NF-e para o Brasil
description: Este tópico fornece uma visão geral do processo para configurar e enviar uma Nota fiscal eletrônica de (NF-e) para registrar a movimentação de itens e de serviço entre duas partes.
author: sndray
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EFDocContingencyMode_BR, EFDocContingencyModeHistory_BR, EFDocCorrectionLetter_BR, EFDocEmailAccountConfiguration_BR, EFDocEmailStatus_BR, EFDocHist_BR, EFDocParameters_BR, EFDocServiceInquire_BR, FiscalDocument_BR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 269114
ms.assetid: 7cb522a4-2f84-4399-a60d-8692df6e08f3
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 81e24220cce58cf40fc6d5d8d0b96d93df2c557e
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849376"
---
# <a name="nf-e-process-overview-for-brazil"></a><span data-ttu-id="751e8-103">Visão geral do processo de NF-e para o Brasil</span><span class="sxs-lookup"><span data-stu-id="751e8-103">NF-e process overview for Brazil</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="751e8-104">Este tópico fornece uma visão geral do processo para configurar e enviar uma Nota fiscal eletrônica de (NF-e) para registrar a movimentação de itens e de serviço entre duas partes.</span><span class="sxs-lookup"><span data-stu-id="751e8-104">This topic provides an overview of the process for setting up and submitting a Nota fiscal eletrônica (NF-e) to register the movement of items and services between two parties.</span></span>

<span data-ttu-id="751e8-105">Você pode usar uma Nota Fiscal eletrônica (NF-e) para registrar a movimentação de itens e serviços entre dois participantes.</span><span class="sxs-lookup"><span data-stu-id="751e8-105">You can use a Nota fiscal eletrônica (NF-e) to register the movement of items and services between two parties.</span></span> <span data-ttu-id="751e8-106">Você pode gerar uma NF-e de qualquer uma das seguintes notas fiscais:</span><span class="sxs-lookup"><span data-stu-id="751e8-106">You can generate an NF-e from any of the following fiscal documents:</span></span>

-   <span data-ttu-id="751e8-107">Ordens de venda</span><span class="sxs-lookup"><span data-stu-id="751e8-107">Sales orders</span></span>
-   <span data-ttu-id="751e8-108">Ordens de compra para fornecedores não contribuinte</span><span class="sxs-lookup"><span data-stu-id="751e8-108">Purchase orders for non-taxpayer vendors</span></span>
-   <span data-ttu-id="751e8-109">Faturas de projeto</span><span class="sxs-lookup"><span data-stu-id="751e8-109">Project invoices</span></span>
-   <span data-ttu-id="751e8-110">Notas fiscais de transferência ou apropriação de imposto</span><span class="sxs-lookup"><span data-stu-id="751e8-110">Tax fiscal documents</span></span>
-   <span data-ttu-id="751e8-111">Faturas de texto livre</span><span class="sxs-lookup"><span data-stu-id="751e8-111">Free text invoices</span></span>

<span data-ttu-id="751e8-112">Antes de gerar uma NF-e, você deve concluir as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="751e8-112">Before you can generate an NF-e, you must complete the following tasks:</span></span>

-   <span data-ttu-id="751e8-113">Configure serviços da Web, códigos de rejeição e esquemas para um domínio.</span><span class="sxs-lookup"><span data-stu-id="751e8-113">Set up web services, rejection codes, and schemas for a domain.</span></span>
-   <span data-ttu-id="751e8-114">Para cada estabelecimento fiscal configure um ambiente, uma versão de NF-e, uma autoridade, um modelo, validação de esquema e um modo de contingência para NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-114">For each fiscal establishment, set up a certificate, an environment, an NF-e version, an authority, a template, schema validation, and a contingency mode for NF-e.</span></span> <span data-ttu-id="751e8-115">Além disso, configure a impressão automática do Documento auxiliar da Nota fiscal eletrônica (DANFE), de forma que o DANFE seja impresso automaticamente após a aprovação da NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-115">Additionally, set up automatic printing of the Documento auxiliar da Nota fiscal eletrônica (DANFE), so that the DANFE is automatically printed after NF-e approval.</span></span>
-   <span data-ttu-id="751e8-116">Configure os serviços da Web relacionados a uma autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="751e8-116">Set up web services that are related to a fiscal authority.</span></span>
-   <span data-ttu-id="751e8-117">Configure um tipo de documento fiscal para uma NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-117">Set up a fiscal document type for an NF-e.</span></span>

<span data-ttu-id="751e8-118">Depois que você gera uma NF-e, pode enviar a NF-e assinada digitalmente para a Secretaria da Fazenda (SEFAZ) em uma mensagem XML.</span><span class="sxs-lookup"><span data-stu-id="751e8-118">After you generate an NF-e, you can submit the digitally signed NF-e to the Secretaria da Fazenda (SEFAZ) in an XML message.</span></span> <span data-ttu-id="751e8-119">Os itens poderão ser entregues depois que a NF-e for aprovada eletronicamente pela SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="751e8-119">The items can be delivered after the NF-e is electronically approved by SEFAZ.</span></span> <span data-ttu-id="751e8-120">O processo da NF-e inclui as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="751e8-120">The NF-e process includes the following steps:</span></span>

1.  <span data-ttu-id="751e8-121">O estabelecimento fiscal lança uma nota fiscal usando um tipo de nota fiscal que é configurado para o modelo de nota fiscal 55 para gerar uma NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-121">The fiscal establishment posts a fiscal document by using a fiscal document type that is set up for fiscal document model 55 to generate an NF-e.</span></span>
2.  <span data-ttu-id="751e8-122">O processo de exportação ou de importação detecta a nota fiscal lançada para o modelo de nota fiscal 55 e gera uma mensagem XML no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="751e8-122">The NF-e export or import process detects the posted fiscal document for the fiscal document model 55 and generates an XML message in the specified format.</span></span> <span data-ttu-id="751e8-123">Uma mensagem XML separada é gerada para cada NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-123">A separate XML message is generated for each NF-e.</span></span> <span data-ttu-id="751e8-124">A mensagem XML é transmitida à SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="751e8-124">The XML message is transmitted to SEFAZ.</span></span>
3.  <span data-ttu-id="751e8-125">A SEFAZ processa a mensagem XML e retorna um protocolo e um status para cada NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-125">SEFAZ processes the XML message and returns a protocol and status for each NF-e.</span></span> <span data-ttu-id="751e8-126">O status da NF-e e o protocolo são então atribuídos à NF-e que é usada no processo de exportação ou importação de NF-e.</span><span class="sxs-lookup"><span data-stu-id="751e8-126">The NF-e status and protocol are then assigned to the NF-e that is used in the NF-e export or import process.</span></span> <span data-ttu-id="751e8-127">O status que é retornado pode ser **Aprovado**, **Negado**, **Rejeitado**, **Cancelado**, **Rejeitado sem correção** ou **Rejeitado**.</span><span class="sxs-lookup"><span data-stu-id="751e8-127">The status that is returned can be **Approved**, **Denied**, **Discarded**, **Canceled**, **Rejected non fixable**, or **Rejected**.</span></span> <span data-ttu-id="751e8-128">Essas informações são usadas para atualizar o status da nota fiscal no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="751e8-128">This information is used to update the fiscal document status in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="751e8-129">Depois que o status da NF-e for recebido da SEFAZ, você poderá executar as seguintes tarefas, dependendo do status:</span><span class="sxs-lookup"><span data-stu-id="751e8-129">After the status of the NF-e is received from SEFAZ, you can perform the following tasks, depending on the status:</span></span>

-   <span data-ttu-id="751e8-130">Se a NF-e for aprovada, você poderá imprimir o DANFE.</span><span class="sxs-lookup"><span data-stu-id="751e8-130">If the NF-e is approved, you can print the DANFE.</span></span> <span data-ttu-id="751e8-131">Como alternativa, se a opção **Imprimir DANFE quando NF-e for aprovada** for selecionada na FastTab **NF-e federal** da página **Estabelecimentos fiscais**, o DANFE será impresso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="751e8-131">Alternatively, if the **Print DANFE when NF-e is approved** option is selected on the **NF-e federal** FastTab of the **Fiscal establishments** page, the DANFE is printed automatically.</span></span>
-   <span data-ttu-id="751e8-132">Se a NF-e for negada, será necessário cancelá-la.</span><span class="sxs-lookup"><span data-stu-id="751e8-132">If the NF-e is denied, you must cancel the NF-e.</span></span>
-   <span data-ttu-id="751e8-133">Se a NF-e for rejeitada e puder ser corrigida, você poderá corrigir as informações incorretas e depois poderá clicar em **Reenviar** na guia **NF-e federal** da página **Documento fiscal** para reenviar a NF-e à SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="751e8-133">If the NF-e is rejected and can be fixed, you can correct the incorrect information, and then click **Resend** on the **NF-e federal** tab of the **Fiscal document** page to resend the NF-e to SEFAZ.</span></span>
-   <span data-ttu-id="751e8-134">Se a NF-e for rejeitada e não puder ser corrigida, você deverá cancelar a NF-e descartada que tem o número descartado.</span><span class="sxs-lookup"><span data-stu-id="751e8-134">If the NF-e is rejected and can't be fixed, you must cancel the discarded NF-e that has discarded number.</span></span> <span data-ttu-id="751e8-135">O processo de exportação ou de importação da NF-e detecta a nota fiscal lançada e marcada para descarte e então gera uma mensagem XML no formato especificado para o número da NF-e descartada.</span><span class="sxs-lookup"><span data-stu-id="751e8-135">The NF-e export or import process detects the fiscal document that is posted and marked for discard, and then generates an XML message in the specified format for the discarded NF-e number.</span></span> <span data-ttu-id="751e8-136">Esta mensagem XML é transmitida à SEFAZ, e o status da nota fiscal é definido é como **Rejeitado**</span><span class="sxs-lookup"><span data-stu-id="751e8-136">This XML message is then transmitted to SEFAZ, and the fiscal document status is set to **Discarded**.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="751e8-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="751e8-137">Additional resources</span></span>

 - [<span data-ttu-id="751e8-138">Certificação de NF-e</span><span class="sxs-lookup"><span data-stu-id="751e8-138">NF-e certification</span></span>](latam-bra-nfe-certs.md)
 - [<span data-ttu-id="751e8-139">Configurar parâmetros federais de NF-e (Brasil)</span><span class="sxs-lookup"><span data-stu-id="751e8-139">Set up NF-e federal parameters (Brazil)</span></span>](tasks/br-00053-1-set-up-nf-e-federal-parameters.md)
 - [<span data-ttu-id="751e8-140">Configurar parâmetros de NF-e para um estabelecimento fiscal (Brasil)</span><span class="sxs-lookup"><span data-stu-id="751e8-140">Set up NF-e parameters for a fiscal establishment (Brazil)</span></span>](tasks/br-00053-2-set-up-nf-e-parameters-fiscal-establishment.md)
 - [<span data-ttu-id="751e8-141">Gerar emails para NF-e aprovada e anexar arquivos PDF do DANFE e arquivos XML da NF-e aos emails (Brasil)</span><span class="sxs-lookup"><span data-stu-id="751e8-141">Generate emails for approved NF-e and attach DANFE PDF files and NF-e XML files to the emails (Brazil)</span></span>](tasks/br-00053-3-generate-emails-approved-nf-e-attach-danfe-pdf-files-nf-e-xml-files-emails.md)
 - [<span data-ttu-id="751e8-142">NF-e 3.10 (Brasil)</span><span class="sxs-lookup"><span data-stu-id="751e8-142">NF-e 3.10 (Brazil)</span></span>](tasks/br-00053-nf-e-3-10.md)
 - [<span data-ttu-id="751e8-143">Transmissão automática de notas fiscais eletrônicas (Brasil)</span><span class="sxs-lookup"><span data-stu-id="751e8-143">Automatic transmission of NF-e fiscal documents (Brazil)</span></span>](tasks/br-00058-automatic-transmission-nf-e-fiscal-documents.md)

