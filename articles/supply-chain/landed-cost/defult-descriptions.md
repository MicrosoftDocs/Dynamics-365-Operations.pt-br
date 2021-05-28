---
title: Descrições padrão da contabilidade
description: As descrições padrão podem ser usadas para atualizar o campo Descrição em lançamentos de comprovantes na contabilidade.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 25dd72c86b22b50eccef22a5d2cbcfcf04280684
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021603"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="3d682-103">Descrições padrão da contabilidade</span><span class="sxs-lookup"><span data-stu-id="3d682-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3d682-104">As descrições padrão podem ser usadas para atualizar o campo **Descrição** em lançamentos de comprovantes na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="3d682-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="3d682-105">Essa funcionalidade foi aprimorada para trabalhar com custo de entrega.</span><span class="sxs-lookup"><span data-stu-id="3d682-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="3d682-106">Para configurar descrições padrão para lançamentos contábeis, acesse **Administração organizacional \> Configuração \> Descrições padrão**.</span><span class="sxs-lookup"><span data-stu-id="3d682-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="3d682-107">A tabela a seguir lista os novos valores que foram adicionados ao campo **Descrição** na página **Descrições padrão** para dar suporte ao custo de entrega.</span><span class="sxs-lookup"><span data-stu-id="3d682-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="3d682-108">Tipo de descrição</span><span class="sxs-lookup"><span data-stu-id="3d682-108">Description type</span></span> | <span data-ttu-id="3d682-109">Observação</span><span class="sxs-lookup"><span data-stu-id="3d682-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="3d682-110">Custos de importação – acumulação de custos</span><span class="sxs-lookup"><span data-stu-id="3d682-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="3d682-111">Quando uma fatura de ordem de compra é lançada, uma acumulação de custo é processada para estimar custos de viagens.</span><span class="sxs-lookup"><span data-stu-id="3d682-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="3d682-112">As descrições padrão podem ser especificadas para adicionar o número da viagem à descrição.</span><span class="sxs-lookup"><span data-stu-id="3d682-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="3d682-113">Use *%4* para o número de remessa.</span><span class="sxs-lookup"><span data-stu-id="3d682-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="3d682-114">Importar avaliação de custo – Ordem de mercadorias em trânsito</span><span class="sxs-lookup"><span data-stu-id="3d682-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="3d682-115">Se você estiver usando o processamento em trânsito, a fatura da ordem de compra será lançada e as mercadorias serão lançadas em uma conta de mercadorias em trânsito.</span><span class="sxs-lookup"><span data-stu-id="3d682-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="3d682-116">As descrições padrão podem ser especificadas para adicionar o número da ordem em trânsito à descrição.</span><span class="sxs-lookup"><span data-stu-id="3d682-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="3d682-117">Use *%4* para o número da ordem em trânsito.</span><span class="sxs-lookup"><span data-stu-id="3d682-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="3d682-118">Estoque - fechar - ajuste</span><span class="sxs-lookup"><span data-stu-id="3d682-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="3d682-119">Quando a fatura de contas a pagar (AP) é processada para um custo de viagem, um ajuste de estoque é processado para estimar os custos de viagens.</span><span class="sxs-lookup"><span data-stu-id="3d682-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="3d682-120">As descrições padrão podem ser especificadas para adicionar o número da viagem à descrição.</span><span class="sxs-lookup"><span data-stu-id="3d682-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="3d682-121">Use *%4* para o número de remessa.</span><span class="sxs-lookup"><span data-stu-id="3d682-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="3d682-122">Para obter mais informações sobre como trabalhar com a página **Descrições padrão**, consulte [Configurar descrições padrão para lançamento automático](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="3d682-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
