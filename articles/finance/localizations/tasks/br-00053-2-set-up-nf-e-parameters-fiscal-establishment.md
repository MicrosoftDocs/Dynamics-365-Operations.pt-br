---
title: Configurar parâmetros de NF-e para um estabelecimento fiscal (Brasil)
description: Use o procedimento a seguir para configurar os parâmetros para uma Nota Fiscal eletrônica (NF-e) e para um estabelecimento fiscal.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7008122636af0dddb72d6d7ba13416de8bc43cc0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975297"
---
# <a name="set-up-nf-e-parameters-for-a-fiscal-establishment-brazil"></a><span data-ttu-id="f6a59-103">Configurar parâmetros de NF-e para um estabelecimento fiscal (Brasil)</span><span class="sxs-lookup"><span data-stu-id="f6a59-103">Set up NF-e parameters for a fiscal establishment (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f6a59-104">Use o procedimento a seguir para configurar os parâmetros para uma Nota Fiscal eletrônica (NF-e) e para um estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-104">Use the following procedure to set up the parameters for a Nota Fiscal eletrônica (NF-e) for a fiscal establishment.</span></span> <span data-ttu-id="f6a59-105">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="f6a59-105">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="f6a59-106">Vá para Administração da organização > Organizações > Estabelecimentos fiscais > Estabelecimentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="f6a59-106">Go to Organization administration > Organizations > Fiscal establishments > Fiscal establishments.</span></span>
2. <span data-ttu-id="f6a59-107">Selecione um estabelecimento fiscal para o qual será configurada a NF-e.</span><span class="sxs-lookup"><span data-stu-id="f6a59-107">Select a fiscal establishment to set up NF-e for.</span></span>
3. <span data-ttu-id="f6a59-108">Expanda a seção NF-e e NFC-e federal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-108">Expand the NF-e and NFC-e federal section.</span></span>
4. <span data-ttu-id="f6a59-109">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f6a59-109">Click Edit.</span></span>
5. <span data-ttu-id="f6a59-110">Insira o certificado digital que autentica os documentos eletrônicos fiscais que são emitidos pelo estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-110">Enter the digital certificate that authenticates the electronic fiscal documents that are issued by the fiscal establishment.</span></span>
6. <span data-ttu-id="f6a59-111">Selecione o tipo do ambiente da NF-e.</span><span class="sxs-lookup"><span data-stu-id="f6a59-111">Select the NF-e environment type.</span></span>
    * <span data-ttu-id="f6a59-112">Selecione Testes para emitir NF-e para um ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="f6a59-112">Select Testing to issue an NF-e to the testing environment.</span></span> <span data-ttu-id="f6a59-113">Selecione Produção para emitir uma NF-e válida para o ambiente de produção da autoridade do imposto.</span><span class="sxs-lookup"><span data-stu-id="f6a59-113">Select Production to issue a valid NF-e to the tax authority's production environment.</span></span>  
7. <span data-ttu-id="f6a59-114">Selecione a versão do esquema XML da NF-e.</span><span class="sxs-lookup"><span data-stu-id="f6a59-114">Select the version of the NF-e XML schema.</span></span>
8. <span data-ttu-id="f6a59-115">Selecione a autoridade da UF da NF-e.</span><span class="sxs-lookup"><span data-stu-id="f6a59-115">Select the state tax authority for NF-e.</span></span>
9. <span data-ttu-id="f6a59-116">Selecione o modelo de email padrão que deve ser usado para notificar o cliente quando a NF-e for autorizada pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-116">Select the default email template that should be used to notify the customer when the NF-e is authorized by the tax authority.</span></span>
10. <span data-ttu-id="f6a59-117">Selecione o modelo de email padrão que deve ser usado para notificar o cliente quando a NF-e for cancelada pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-117">Select the default email template that should be used to notify the customer when the NF-e is canceled by the tax authority.</span></span>
11. <span data-ttu-id="f6a59-118">Selecione o modelo de email padrão que deve ser usado para notificar o cliente quando a NF-e for atualizada por uma carta de correção eletrônica.</span><span class="sxs-lookup"><span data-stu-id="f6a59-118">Select the default email template that should be used to notify the customer when the NF-e is updated by an electronic correction letter.</span></span>
12. <span data-ttu-id="f6a59-119">Selecionar Sim no campo do formulário pré-impresso de segurança.</span><span class="sxs-lookup"><span data-stu-id="f6a59-119">Select Yes in the Preprinted security form field.</span></span>
    * <span data-ttu-id="f6a59-120">Selecione esta opção quando o estabelecimento fiscal usar o formulário pré-impresso de segurança para imprimir o DANFE em modo de contingência de formulário de segurança.</span><span class="sxs-lookup"><span data-stu-id="f6a59-120">Select this option when the fiscal establishment uses a preprinted security form to print DANFE in the security form contingency mode.</span></span>  
13. <span data-ttu-id="f6a59-121">Selecione Sim no campo Anexar DANFE em PDF ao email.</span><span class="sxs-lookup"><span data-stu-id="f6a59-121">Select Yes in the Attach the DANFE as PDF file to  email field.</span></span>
    * <span data-ttu-id="f6a59-122">Selecione esta opção para anexar automaticamente o DANFE ao email que é enviado ao cliente após a NF-e ser autorizado pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-122">Select this option to automatically attach the DANFE to the email that is sent to the customer after the NF-e has been authorized by the tax authority.</span></span>  
14. <span data-ttu-id="f6a59-123">Selecione Sim no campo Imprimir DANFE quando NF-e for aprovada.</span><span class="sxs-lookup"><span data-stu-id="f6a59-123">Select Yes in the Print DANFE when NF-e is approved field.</span></span>
    * <span data-ttu-id="f6a59-124">Selecione esta opção para imprimir o DANFE automaticamente após a NF-e ser autorizada pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="f6a59-124">Select this option to automatically print the DANFE after the NF-e has been authorized by the tax authority.</span></span>  
15. <span data-ttu-id="f6a59-125">Selecione Sim no campo Validar esquema XML no lançamento.</span><span class="sxs-lookup"><span data-stu-id="f6a59-125">Select Yes in the Validate XML schema on posting field.</span></span>
    * <span data-ttu-id="f6a59-126">Selecione esta opção para validar o XML de NF-e com o esquema XML oficial que é publicado pela autoridade fiscal antes de as notas serem lançadas.</span><span class="sxs-lookup"><span data-stu-id="f6a59-126">Select this option to validate the NF-e XML against the official XML schema that is published by the tax authority before fiscal documents are posted.</span></span>  
16. <span data-ttu-id="f6a59-127">Selecionar Sim no campo Lançar somente NF-e com chave de acesso validada.</span><span class="sxs-lookup"><span data-stu-id="f6a59-127">Select Yes in the Post only NF-e that have valid access keys field.</span></span>
    * <span data-ttu-id="f6a59-128">Selecione esta opção para validar a chave de acesso de NF-e de uma NF-e um que é emitida por um fornecedor antes que as notas fiscais do fornecedor sejam lançadas.</span><span class="sxs-lookup"><span data-stu-id="f6a59-128">Select this option to validate the NF-e access key from an NF-e that is issued by a vendor before vendor fiscal documents are posted.</span></span>  
17. <span data-ttu-id="f6a59-129">Selecione Sim no campo Não postar NF-e se o XML não corresponder com a fatura.</span><span class="sxs-lookup"><span data-stu-id="f6a59-129">Select Yes in the Block NF-e posting if XML does not match field.</span></span>
    * <span data-ttu-id="f6a59-130">Selecione esta opção se uma nota fiscal de fornecedor não tiver que ser lançada se o XML de NF-e de fornecedor não corresponder à ordem.</span><span class="sxs-lookup"><span data-stu-id="f6a59-130">Select this option if a vendor fiscal document should not be posted if the NF-e XML from the vendor doesn't match the order.</span></span>  
18. <span data-ttu-id="f6a59-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f6a59-131">Click Save.</span></span>
19. <span data-ttu-id="f6a59-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f6a59-132">Close the page.</span></span>

