---
title: Configure informações sobre grupo TDS, PANs e TANs para fornecedores e clientes
description: Este tópico explica como configurar informações sobre grupos de Imposto Deduzido na Origem (TDS), número de conta permanente (PAN) e número de conta de imposto (TAN) para fornecedores e clientes.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023029"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="28876-103">Configuração de informações do grupo TDS, PAN e TAN para fornecedores e clientes</span><span class="sxs-lookup"><span data-stu-id="28876-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28876-104">Este tópico explica como configurar informações sobre grupos de Imposto Deduzido na Origem (TDS), número de conta permanente (PAN) e número de conta de imposto (TAN) para fornecedores e clientes.</span><span class="sxs-lookup"><span data-stu-id="28876-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="28876-105">Vá para **Contas a pagar \> Fornecedores \> Todos os fornecedores** ou **Contas a receber \> Clientes \> Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="28876-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="28876-106">[![Página Todos os fornecedores](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="28876-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="28876-107">No Painel de Ações, selecione **Novo** para criar um fornecedor ou cliente e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="28876-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="28876-108">Alternativamente, selecione um fornecedor ou cliente existente.</span><span class="sxs-lookup"><span data-stu-id="28876-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="28876-109">Na FastTab **Fatura e entrega**, na seção **Imposto retido na fonte**, defina a opção **Calcular imposto retido na fonte** como **Sim** para calcular a retenção de imposto, TDS ou Impostos Recolhidos na Fonte (TCS) para o fornecedor ou cliente.</span><span class="sxs-lookup"><span data-stu-id="28876-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="28876-110">O TDS para uma fatura de compra é calculado com base no grupo de TDS padrão definido para o fornecedor ou cliente.</span><span class="sxs-lookup"><span data-stu-id="28876-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="28876-111">No campo **Grupo de TDS**, selecione o grupo de TDS padrão.</span><span class="sxs-lookup"><span data-stu-id="28876-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28876-112">Quando você seleciona um grupo de TDS no campo **Grupo de TDS**, os campos **Grupo de impostos retidos na fonte** e **Grupo de TCS** ficam indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="28876-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="28876-113">Na FastTab **Informações sobre imposto**, na seção **Informações sobre PAN**, no campo **Status**, selecione o status do número da conta permanente para o fornecedor ou cliente:</span><span class="sxs-lookup"><span data-stu-id="28876-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="28876-114">**Não disponível** – o fornecedor ou o cliente não tem um PAN.</span><span class="sxs-lookup"><span data-stu-id="28876-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="28876-115">**Recebido** – O fornecedor ou o cliente tem um PAN.</span><span class="sxs-lookup"><span data-stu-id="28876-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="28876-116">**Aplicado** – o fornecedor ou o cliente se aplicou para um PAN.</span><span class="sxs-lookup"><span data-stu-id="28876-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="28876-117">**Inválido** – o fornecedor ou o cliente tem um PAN, mas ele não é válido.</span><span class="sxs-lookup"><span data-stu-id="28876-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="28876-118">Se você selecionou **Recebido** no campo **Status** para indicar que o fornecedor ou o cliente tem um PAN, insira o PAN no campo **Número**.</span><span class="sxs-lookup"><span data-stu-id="28876-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="28876-119">O PAN deve consistir em cinco caracteres alfabéticos, quatro caracteres numéricos e, depois, um caractere alfabético.</span><span class="sxs-lookup"><span data-stu-id="28876-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="28876-120">Veja aqui um exemplo: **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="28876-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="28876-121">Se você selecionou **Aplicado** no campo **Status** para indicar que o fornecedor ou cliente aplicou PAN, informe o número de referência no campo **Número de referência**.</span><span class="sxs-lookup"><span data-stu-id="28876-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="28876-122">No campo **Natureza do avaliado**, selecione a natureza da categoria do avaliado à qual o fornecedor ou cliente pertence:</span><span class="sxs-lookup"><span data-stu-id="28876-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="28876-123">Empresa</span><span class="sxs-lookup"><span data-stu-id="28876-123">Company</span></span>
    - <span data-ttu-id="28876-124">HUF</span><span class="sxs-lookup"><span data-stu-id="28876-124">HUF</span></span>
    - <span data-ttu-id="28876-125">Confirmar</span><span class="sxs-lookup"><span data-stu-id="28876-125">Firm</span></span>
    - <span data-ttu-id="28876-126">Pessoa física</span><span class="sxs-lookup"><span data-stu-id="28876-126">Individual</span></span>
    - <span data-ttu-id="28876-127">AOP</span><span class="sxs-lookup"><span data-stu-id="28876-127">AOP</span></span>
    - <span data-ttu-id="28876-128">BOI</span><span class="sxs-lookup"><span data-stu-id="28876-128">BOI</span></span>
    - <span data-ttu-id="28876-129">Autoridade local</span><span class="sxs-lookup"><span data-stu-id="28876-129">Local authority</span></span>
    - <span data-ttu-id="28876-130">Diversos</span><span class="sxs-lookup"><span data-stu-id="28876-130">Others</span></span>

    <span data-ttu-id="28876-131">[![FastTab Informações sobre imposto](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="28876-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="28876-132">No Painel de Ações, na guia **Fornecedor**, no grupo **Registro**, selecione **IDs de Registro** para abrir a página **Gerenciar endereços**.</span><span class="sxs-lookup"><span data-stu-id="28876-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="28876-133">Na página **Gerenciar endereços**, na FastTab **Informações sobre imposto**, selecione **Adicionar** ou **Editar** para abrir a página **Gerenciar informações sobre imposto**, na qual é possível manter a entrada do registro de imposto.</span><span class="sxs-lookup"><span data-stu-id="28876-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="28876-134">Na página **Gerenciar informações sobre imposto**, na FastTab **Imposto retido na fonte**, no campo **Número da Conta de Imposto (TAN)**, insira o TAN.</span><span class="sxs-lookup"><span data-stu-id="28876-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="28876-135">O TAN deve consistir em quatro caracteres alfabéticos, cinco caracteres numéricos e, depois, um caractere alfabético.</span><span class="sxs-lookup"><span data-stu-id="28876-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="28876-136">Veja aqui um exemplo: **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="28876-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="28876-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="28876-137">Close the page.</span></span>
