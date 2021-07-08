---
title: Registro adiado de documentos NFC-e emitidos no modo de contingência offline
description: Este tópico dá uma visão geral da funcionalidade para o registro adiado de documentos NFC-e que são emitidos no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce no modo de contingência.
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
ms.openlocfilehash: 8f62d06bf97a92bdb4b0531d23cf20fdb0220d57
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303523"
---
# <a name="postponed-registration-of-nfc-e-documents-issued-in-offline-contingency-mode"></a><span data-ttu-id="0c3ca-103">Registro adiado de documentos NFC-e emitidos no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="0c3ca-103">Postponed registration of NFC-e documents issued in offline contingency mode</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0c3ca-104">Este tópico dá uma visão geral da funcionalidade para o registro adiado de documentos NFC-e (Nota Fiscal do Consumidor eletrônica) que são emitidos no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce no modo de contingência.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-104">This topic gives an overview of the functionality for postponed registration of NFC-e (Nota Fiscal do Consumidor eletrônica) documents that are issued in Microsoft Dynamics 365 Commerce point of sale (POS) in contingency mode.</span></span>

<span data-ttu-id="0c3ca-105">O modo de contingência offline NFC-e deve ser usado quando a conexão à Internet de uma loja não estiver disponível, ou quando o serviço de autorização da SEFAZ (Secretaria de Estado de Fazenda) estiver desativado.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-105">The NFC-e offline contingency mode must be used when a store's internet connection isn't available, or when the SEFAZ (Secretaria de Estado de Fazenda) authorization service is down.</span></span> <span data-ttu-id="0c3ca-106">No modo de contingência offline, o PDV gera documentos NFC-e localmente.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-106">In offline contingency mode, POS locally generates NFC-e documents.</span></span> <span data-ttu-id="0c3ca-107">Esses documentos são encaminhados à SEFAZ posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-107">Those documents are then transmitted to SEFAZ later.</span></span>

<span data-ttu-id="0c3ca-108">Todos os documentos NFC-e que são emitidos por meio de terminais PDV podem ser vistos na página **Visualizar mensagem XML** na sede do Commerce após a execução dos P-jobs e a publicação da declaração de varejo.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-108">All NFC-e documents that are issued through POS terminals can be viewed on the **View XML message** page in Commerce headquarters after P-jobs are run and the retail statement is posted.</span></span> <span data-ttu-id="0c3ca-109">Depois disso, os documentos NFC-e que foram emitidos no PDV no modo de contingência offline podem ser enviados para autorização por meio da sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-109">The NFC-e documents that were issued in POS in offline contingency mode can then be submitted for authorization through Commerce headquarters.</span></span>

## <a name="view-fiscal-document-details"></a><span data-ttu-id="0c3ca-110">Veja os detalhes do documento fiscal</span><span class="sxs-lookup"><span data-stu-id="0c3ca-110">View fiscal document details</span></span>

<span data-ttu-id="0c3ca-111">Para ver um documento NFC-e na sede do Commerce, acesse **Varejo e Comércio \> Consultas e relatórios \> Todos os documentos fiscais**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-111">To view an NFC-e document in Commerce headquarters, go to **Retail and Commerce \> Inquiries and reports \> All fiscal documents**.</span></span> <span data-ttu-id="0c3ca-112">A página **Todos os documentos fiscais** mostra o mesmo formato que é mostrado quando você visualiza um documento fiscal NF-e modelo 55.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-112">The **All fiscal documents** page shows the same format that is shown when you view an NF-e model 55 fiscal document.</span></span> <span data-ttu-id="0c3ca-113">Isso inclui o cabeçalho, linhas e todos os atributos.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-113">It includes the header, lines, and all attributes.</span></span> <span data-ttu-id="0c3ca-114">Para obter mais informações, consulte [Documentos fiscais e estrutura de documentos fiscais para o Brasil](../../finance/localizations/latam-bra-fiscal-documents-fiscal-document-framework.md).</span><span class="sxs-lookup"><span data-stu-id="0c3ca-114">For more information, see [Fiscal documents and fiscal document framework for Brazil](../../finance/localizations/latam-bra-fiscal-documents-fiscal-document-framework.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="0c3ca-115">Por padrão, se você abrir a página **Todos os documentos fiscais** na sede do Commerce, ele lista apenas os documentos fiscais NFC-e modelo 65.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-115">By default, if you open the **All fiscal documents** page in Commerce headquarters, it lists only NFC-e model 65 fiscal documents.</span></span> <span data-ttu-id="0c3ca-116">Para visualizar os retornos que possuem documentos fiscais NFC-e modelo 55, você deve alterar os critérios do filtro.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-116">To view returns that have NFC-e model 55 fiscal documents, you must change the filter criteria.</span></span> <span data-ttu-id="0c3ca-117">No entanto, se você abrir a página **Todos os documentos fiscais** no módulo **Contabilidade**, ele listará todos os modelos de documentos fiscais de entrada e saída, incluindo o modelo 55 e o modelo 65.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-117">However, if you open the **All fiscal documents** page in the **General ledger** module, it lists all incoming and outgoing fiscal document models, including model 55 and model 65.</span></span>
> - <span data-ttu-id="0c3ca-118">Se o documento NFC-e tiver sido emitido e autorizado no PDV, seu status será mostrado como **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-118">If the NFC-e document was issued and authorized in POS, its status is shown as **Approved**.</span></span> <span data-ttu-id="0c3ca-119">Se o documento NFC-e for emitido no modo de contingência offline, seu status será mostrado como **Criado**, **Rejeitado** ou **RejectedNoFix**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-119">If the NFC-e document was issued in offline contingency mode, its status is shown as **Created**, **Rejected**, or **RejectedNoFix**.</span></span>

## <a name="authorize-nfc-e-documents-that-were-issued-in-offline-contingency-mode"></a><span data-ttu-id="0c3ca-120">Autorizar documentos NFC-e que foram emitidos no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="0c3ca-120">Authorize NFC-e documents that were issued in offline contingency mode</span></span>

<span data-ttu-id="0c3ca-121">Para autorizar um documento NFC-e que foi emitido no modo de contingência offline, siga estas etapas na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-121">To authorize an NFC-e document that was issued in offline contingency mode, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="0c3ca-122">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="0c3ca-122">Follow one of these steps:</span></span>

    - <span data-ttu-id="0c3ca-123">Vá para **Contas a receber \> Documentos fiscais \> Documentos fiscais eletrônicos \> Processo de exportação/importação de NF-e**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-123">Go to **Accounts receivable \> Fiscal documents \> Electronic fiscal documents \> Export/import NF-e process**.</span></span>
    - <span data-ttu-id="0c3ca-124">Se você estiver usando o [Complemento de faturamento eletrônico para o Brasil](../../finance/localizations/e-invoicing-bra-get-started.md), vá para **Varejo e Commerce \> Varejo e IT do Commerce \> Publicação no PDV \> Exportar documentos NFC-e**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-124">If you're using the [Electronic invoicing add-on for Brazil](../../finance/localizations/e-invoicing-bra-get-started.md), go to **Retail and Commerce \> Retail and Commerce IT \> POS posting \> Export NFC-e documents**.</span></span>

1. <span data-ttu-id="0c3ca-125">Após a conclusão do processo de exportação, revise o status de autorização da NFC-e acessando **Varejo e Commerce \> Consultas e relatórios \> Todos os documentos fiscais**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-125">After the export process is completed, review the NFC-e authorization status by going to **Retail and Commerce \> Inquiries and reports \> All fiscal documents**.</span></span> <span data-ttu-id="0c3ca-126">Para as vendas autorizadas pela autoridade fiscal do estado, o campo **Status** será definido como **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="0c3ca-126">For sales that have been authorized by the state's tax authority, the **Status** field will be set to **Approved**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c3ca-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0c3ca-127">Additional resources</span></span>

[<span data-ttu-id="0c3ca-128">Configurar e implantar a localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0c3ca-128">Set up and deploy Commerce localization for Brazil</span></span>](latam-bra-deployment.md)

[<span data-ttu-id="0c3ca-129">Localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0c3ca-129">Commerce localization for Brazil</span></span>](latam-bra-commerce-localization.md)

[<span data-ttu-id="0c3ca-130">Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0c3ca-130">NFC-e fiscal document functionality in Commerce POS for Brazil</span></span>](latam-bra-nfce.md)

[<span data-ttu-id="0c3ca-131">Gerenciar informações do cliente no PDV para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0c3ca-131">Manage customer information in POS for Brazil</span></span>](latam-bra-customer-information.md)

[<span data-ttu-id="0c3ca-132">Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="0c3ca-132">Cancellation and return of NFC-e documents in Commerce POS for Brazil</span></span>](latam-bra-nfce-cancel-return.md)

[<span data-ttu-id="0c3ca-133">Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="0c3ca-133">Post Brazilian fiscal documents via retail statements in Commerce headquarters</span></span>](latam-bra-retail-statements.md)
