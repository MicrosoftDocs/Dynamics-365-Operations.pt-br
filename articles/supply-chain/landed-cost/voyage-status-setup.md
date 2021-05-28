---
title: Configuração de status de viagem
description: Este tópico descreve como estabelecer os valores de status que os usuários podem atribuir a viagens.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e19a54fc9de166c93fd68408ca8c8c692dc96cab
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022099"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="43710-103">Configuração de status de viagem</span><span class="sxs-lookup"><span data-stu-id="43710-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="43710-104">Na página **Status de viagem**, você estabelece o conjunto de valores de status que os usuários podem atribuir a viagens.</span><span class="sxs-lookup"><span data-stu-id="43710-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="43710-105">Os usuários podem atribuir valores de status de viagem a todos os níveis de uma viagem: viagem, contêiner de remessa, fólio, ordem de compra e item (linhas de compra e linhas de ordem de transferência).</span><span class="sxs-lookup"><span data-stu-id="43710-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="43710-106">Eles são usados para duas finalidades:</span><span class="sxs-lookup"><span data-stu-id="43710-106">They are used for two purposes:</span></span>

- <span data-ttu-id="43710-107">Informar o usuário sobre o status da viagem, o contêiner de remessa, o fólio, a ordem de compra ou o item (linhas de compra e linhas de ordem de transferência).</span><span class="sxs-lookup"><span data-stu-id="43710-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="43710-108">Limitar o uso da área de custo impedindo a modificação ou a exclusão.</span><span class="sxs-lookup"><span data-stu-id="43710-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="43710-109">Para configurar seus status de viagem, vá para **Custo de entrega \> Configuração \> Status de viagem**.</span><span class="sxs-lookup"><span data-stu-id="43710-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="43710-110">Lá, você pode adicionar, remover e editar os status usando os botões no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="43710-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="43710-111">Cada área de custo tem seu próprio conjunto e hierarquia de status de viagem.</span><span class="sxs-lookup"><span data-stu-id="43710-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="43710-112">Portanto, na página **Status de viagem**, no campo **Área de custo**, você deve primeiro selecionar a área de custo que deseja exibir ou para a qual deseja criar status de viagem.</span><span class="sxs-lookup"><span data-stu-id="43710-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="43710-113">Em seguida, para cada status de viagem, defina os campos descritos na tabela a seguir, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="43710-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="43710-114">Observe que o status de uma viagem também pode ser alterado automaticamente por eventos do sistema, como as regras que foram estabelecidas usando o centro de controle de acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="43710-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="43710-115">Campo</span><span class="sxs-lookup"><span data-stu-id="43710-115">Field</span></span> | <span data-ttu-id="43710-116">descrição</span><span class="sxs-lookup"><span data-stu-id="43710-116">Description</span></span> |
|---|---|
| <span data-ttu-id="43710-117">Status da viagem</span><span class="sxs-lookup"><span data-stu-id="43710-117">Voyage status</span></span> | <span data-ttu-id="43710-118">Insira o nome do status de viagem.</span><span class="sxs-lookup"><span data-stu-id="43710-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="43710-119">descrição</span><span class="sxs-lookup"><span data-stu-id="43710-119">Description</span></span> | <span data-ttu-id="43710-120">Insira uma descrição do status de viagem.</span><span class="sxs-lookup"><span data-stu-id="43710-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="43710-121">Modificar</span><span class="sxs-lookup"><span data-stu-id="43710-121">Modify</span></span> | <span data-ttu-id="43710-122">Marque esta caixa de seleção se os usuários tiverem permissão para modificar viagens com este status.</span><span class="sxs-lookup"><span data-stu-id="43710-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="43710-123">Delete</span><span class="sxs-lookup"><span data-stu-id="43710-123">Delete</span></span> | <span data-ttu-id="43710-124">Marque esta caixa de seleção se os usuários tiverem permissão para excluir viagens com este status.</span><span class="sxs-lookup"><span data-stu-id="43710-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="43710-125">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="43710-125">Mandatory</span></span> | <span data-ttu-id="43710-126">Marque esta caixa de seleção para tornar o status de viagem obrigatório, para que ele não possa ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="43710-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="43710-127">Item pai</span><span class="sxs-lookup"><span data-stu-id="43710-127">Parent</span></span> | <span data-ttu-id="43710-128">Use este campo para estabelecer uma hierarquia entre os valores de status.</span><span class="sxs-lookup"><span data-stu-id="43710-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="43710-129">Os status de viagem podem ser alterados (de forma manual ou automática) somente para baixo na hierarquia, do status pai para um de seus status filho.</span><span class="sxs-lookup"><span data-stu-id="43710-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="43710-130">Você deve configurar somente os status de viagem específicos que sua organização usa.</span><span class="sxs-lookup"><span data-stu-id="43710-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="43710-131">Os status de viagem comuns incluem *Confirmado*, *Mercadorias em trânsito*, *Recebido*, *Pronto para avaliação de custo* e *Orçado*.</span><span class="sxs-lookup"><span data-stu-id="43710-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="43710-132">No entanto, outros status podem estar presentes.</span><span class="sxs-lookup"><span data-stu-id="43710-132">However, other statuses might be present.</span></span>
