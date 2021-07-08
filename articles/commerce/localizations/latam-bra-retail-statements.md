---
title: Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce
description: Este tópico descreve como lançar documentos fiscais brasileiros por meio de demonstrativos de varejo no Microsoft Dynamics 365 Commerce.
author: v-ankvik
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: v-ankvik
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4839280a8b1c07804b9373a77f8dfd4c3375d4a8
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303526"
---
# <a name="post-brazilian-fiscal-documents-via-retail-statements-in-commerce-headquarters"></a><span data-ttu-id="0b512-103">Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="0b512-103">Post Brazilian fiscal documents via retail statements in Commerce headquarters</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0b512-104">Este tópico descreve como lançar documentos fiscais brasileiros por meio de demonstrativos de varejo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0b512-104">This topic describes how to post Brazilian fiscal documents via retail statements in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0b512-105">Depois de executar o P-jobs e lançar um demonstrativo de varejo, os documentos fiscais NFC-e (Nota Fiscal do Consumidor eletrônico) que foram emitidos através dos terminais do Ponto de Venda (PDV) do Commerce podem ser visualizados na página **Visualizar mensagem XML** na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="0b512-105">After you run P-jobs and post a retail statement, NFC-e (Nota Fiscal do Consumidor eletrônica) fiscal documents that were issued through Commerce point of sale (POS) terminals can be viewed on the **View XML message** page in Commerce headquarters.</span></span>

## <a name="post-retail-statements"></a><span data-ttu-id="0b512-106">Lançar demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="0b512-106">Post retail statements</span></span>

<span data-ttu-id="0b512-107">Os documentos NFC-e que são emitidos em PDV são publicados na sede do Commerce quando as declarações de varejo abertas são publicadas no módulo **Varejo e Commerce**.</span><span class="sxs-lookup"><span data-stu-id="0b512-107">NFC-e documents that are issued in POS are posted in Commerce headquarters when open retail statements are posted in the **Retail and Commerce** module.</span></span> <span data-ttu-id="0b512-108">Os demonstrativos de varejo podem conter transações NFC-e e NF-e (Nota Fiscal eletrônica) para devoluções.</span><span class="sxs-lookup"><span data-stu-id="0b512-108">Retail statements can contain both NFC-e and NF-e (Nota Fiscal eletrônica) transactions for returns.</span></span>

<span data-ttu-id="0b512-109">Para lançar um documento NFC-e que foi emitido em PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0b512-109">To post an NFC-e document that was issued in POS, follow these steps.</span></span>

1. <span data-ttu-id="0b512-110">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="0b512-110">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="0b512-111">Execute o **P-job** para o banco de dados do canal.</span><span class="sxs-lookup"><span data-stu-id="0b512-111">Run the **P-job** for the channel database.</span></span>
1. <span data-ttu-id="0b512-112">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Lançamento do PDV**.</span><span class="sxs-lookup"><span data-stu-id="0b512-112">Go to **Retail and Commerce \> Retail and Commerce IT \> POS posting**.</span></span>
1. <span data-ttu-id="0b512-113">Execute o trabalho em lote de **Validar transações da loja**.</span><span class="sxs-lookup"><span data-stu-id="0b512-113">Run the **Validate store transactions** batch job.</span></span>
1. <span data-ttu-id="0b512-114">Execute o trabalho em lote **Calcular demonstrativos transacionais em lote**.</span><span class="sxs-lookup"><span data-stu-id="0b512-114">Run the **Calculate transactional statements in batch** batch job.</span></span>
1. <span data-ttu-id="0b512-115">Execute o trabalho em lote **Lançar demonstrativos transacionais em lote**.</span><span class="sxs-lookup"><span data-stu-id="0b512-115">Run the **Post transactional statements in batch** job.</span></span>
1. <span data-ttu-id="0b512-116">Vá para **Varejo e Comércio \> Consultas e relatórios \> demonstrativos lançados** e verifique se o demonstrativo foi lançado.</span><span class="sxs-lookup"><span data-stu-id="0b512-116">Go to **Retail and Commerce \> Inquiries and reports \> Posted statements**, and verify that the statement has been posted.</span></span>

> [!NOTE]
> <span data-ttu-id="0b512-117">Esse procedimento faz um lançamento baseado em feed, conforme descrito em [Criação de ordens baseadas em feeds do Trickle para transações de lojas de varejo](../trickle-feed.md).</span><span class="sxs-lookup"><span data-stu-id="0b512-117">This procedure does trickle feed–based posting, as described in [Trickle feed-based order creation for retail store transactions](../trickle-feed.md).</span></span> <span data-ttu-id="0b512-118">Para obter mais informações, consulte [Demonstrativos de varejo](../retail-statements.md).</span><span class="sxs-lookup"><span data-stu-id="0b512-118">For more information, see [Retail statements](../retail-statements.md).</span></span>

## <a name="view-fiscal-document-details-in-commerce-headquarters"></a><span data-ttu-id="0b512-119">Veja detalhes do documento fiscal na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="0b512-119">View fiscal document details in Commerce headquarters</span></span>

<span data-ttu-id="0b512-120">Para ver detalhes do documento fiscal na sede do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0b512-120">To view fiscal document details in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="0b512-121">Para ver um documento NFC-e na sede do Commerce, acesse **Varejo e Comércio \> Consultas e relatórios \> Todos os documentos fiscais**.</span><span class="sxs-lookup"><span data-stu-id="0b512-121">To view an NFC-e document in Commerce headquarters, go to **Retail and Commerce \> Inquiries and reports \> All fiscal documents**.</span></span> <span data-ttu-id="0b512-122">A página **Todos os documentos fiscais** mostra o mesmo formato que é mostrado quando você visualiza um documento fiscal NF-e modelo 55.</span><span class="sxs-lookup"><span data-stu-id="0b512-122">The **All fiscal documents** page shows the same format that is shown when you view an NF-e model 55 fiscal document.</span></span> <span data-ttu-id="0b512-123">Isso inclui o cabeçalho, linhas e todos os atributos.</span><span class="sxs-lookup"><span data-stu-id="0b512-123">It includes the header, lines, and all attributes.</span></span> <span data-ttu-id="0b512-124">Para obter mais informações, consulte [Documentos fiscais e estrutura de documentos fiscais para o Brasil](../../finance/localizations/latam-bra-fiscal-documents-fiscal-document-framework.md).</span><span class="sxs-lookup"><span data-stu-id="0b512-124">For more information, see [Fiscal documents and fiscal document framework for Brazil](../../finance/localizations/latam-bra-fiscal-documents-fiscal-document-framework.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b512-125">Por padrão, se você abrir a página **Todos os documentos fiscais** na sede do Commerce, ele lista apenas os documentos fiscais NFC-e modelo 65.</span><span class="sxs-lookup"><span data-stu-id="0b512-125">By default, if you open the **All fiscal documents** page in Commerce headquarters, it lists only NFC-e model 65 fiscal documents.</span></span> <span data-ttu-id="0b512-126">Para visualizar os retornos que possuem documentos fiscais NFC-e modelo 55, você deve alterar os critérios do filtro.</span><span class="sxs-lookup"><span data-stu-id="0b512-126">To view returns that have NFC-e model 55 fiscal documents, you must change the filter criteria.</span></span> <span data-ttu-id="0b512-127">No entanto, se você abrir a página **Todos os documentos fiscais** no módulo **Contabilidade**, ele listará todos os modelos de documentos fiscais de entrada e saída, incluindo o modelo 55 e o modelo 65.</span><span class="sxs-lookup"><span data-stu-id="0b512-127">However, if you open the **All fiscal documents** page in the **General ledger** module, it lists all incoming and outgoing fiscal document models, including model 55 and model 65.</span></span>

1. <span data-ttu-id="0b512-128">Na página **Todos os documentos fiscais**, revise o campo **Status** para os documentos fiscais que deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="0b512-128">On the **All fiscal documents** page, review the **Status** field for the fiscal documents that you want to view.</span></span> <span data-ttu-id="0b512-129">Para as vendas autorizadas pela autoridade fiscal do estado, o campo **Status** será definido como **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="0b512-129">For sales that have been authorized by the state's tax authority, the **Status** field will be set to **Approved**.</span></span>
1. <span data-ttu-id="0b512-130">Selecione os documentos fiscais necessários e, em seguida, na guia **NF-e federal**, selecione **Documento XML**.</span><span class="sxs-lookup"><span data-stu-id="0b512-130">Select the required fiscal documents, and then, on the **NF-e federal** tab, select **XML document**.</span></span>
1. <span data-ttu-id="0b512-131">Na página **Visualizar mensagem XML**, nas guias **NF-e** e **Devolução de NF-e**, valide as solicitações e respostas XML disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0b512-131">On the **View XML message** page, on the **NF-e** and **NF-e return** tabs, validate the XML requests and responses that are available.</span></span>
1. <span data-ttu-id="0b512-132">Na guia **Cancelar**, valide qualquer solicitação e resposta XML cancelada que estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="0b512-132">On the **Cancel** tab, validate any canceled XML requests and responses that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0b512-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0b512-133">Additional resources</span></span>

[<span data-ttu-id="0b512-134">Configurar e implantar a localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0b512-134">Set up and deploy Commerce localization for Brazil</span></span>](latam-bra-deployment.md)

[<span data-ttu-id="0b512-135">Localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0b512-135">Commerce localization for Brazil</span></span>](latam-bra-commerce-localization.md)

[<span data-ttu-id="0b512-136">Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0b512-136">NFC-e fiscal document functionality in Commerce POS for Brazil</span></span>](latam-bra-nfce.md)

[<span data-ttu-id="0b512-137">Gerenciar informações do cliente no PDV para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0b512-137">Manage customer information in POS for Brazil</span></span>](latam-bra-customer-information.md)

[<span data-ttu-id="0b512-138">Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0b512-138">Cancellation and return of NFC-e documents in Commerce POS for Brazil</span></span>](latam-bra-nfce-cancel-return.md)

[<span data-ttu-id="0b512-139">Registro adiado de documentos NFC-e emitidos no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="0b512-139">Postponed registration of NFC-e documents issued in offline contingency mode</span></span>](latam-bra-nfce-contingency-mode.md)
