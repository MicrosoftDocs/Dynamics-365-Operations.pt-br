---
title: NT 2020.006 – plataforma digital de vendas intermediárias para NF-e
description: Este tópico explica como marcar vendas digitais intermediárias para NF-e.
author: gionoder
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: 8
ms.openlocfilehash: ed509fe35cff5b836e8da01bf80d910190b277ec
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019508"
---
# <a name="nt2020006--intermediary-sales-digital-platform-for-nf-e"></a><span data-ttu-id="17520-103">NT 2020.006 – plataforma digital de vendas intermediárias para NF-e</span><span class="sxs-lookup"><span data-stu-id="17520-103">NT2020.006 – Intermediary sales digital platform for NF-e</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17520-104">Uma venda pode ocorrer mesmo quando o cliente não está fisicamente presente.</span><span class="sxs-lookup"><span data-stu-id="17520-104">A sale can occur even when the customer isn't physically present.</span></span> <span data-ttu-id="17520-105">Em vez disso, uma plataforma ou um mercado digital pode servir como um intermediário para a transação.</span><span class="sxs-lookup"><span data-stu-id="17520-105">Instead, a digital platform or marketplace can serve as an intermediary for the transaction.</span></span> <span data-ttu-id="17520-106">Nessas situações, o XML do modelo de nota fiscal eletrônica 55 (NF-e) que é emitido a partir da venda deve conter uma nova marca para indicar que um intermediário participou da operação.</span><span class="sxs-lookup"><span data-stu-id="17520-106">In these scenarios, the XML of the electronic fiscal document model 55 (NF-e) that is issued from the sale must contain a new tag to indicate that an intermediary participated in the operation.</span></span>

<span data-ttu-id="17520-107">Esse recurso oferece suporte a cenários em que uma plataforma ou um mercado digital são de propriedade ou licenciados pelo emissor da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="17520-107">This feature supports scenarios when a digital platform or marketplace is owned or licensed by the fiscal document issuer.</span></span>

## <a name="enable-the-technical-note-in-dynamics-365-finance-and-dynamics-365-supply-chain-management"></a><span data-ttu-id="17520-108">Habilite a nota técnica no Dynamics 365 Finance e no Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="17520-108">Enable the technical note in Dynamics 365 Finance and Dynamics 365 Supply Chain Management</span></span>

1. <span data-ttu-id="17520-109">Entre na sua instância do Microsoft Dynamics 365 Finance ou do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="17520-109">Sign in to your instance of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>
2. <span data-ttu-id="17520-110">Acesse **Administração da organização** \> **Organizações** \> **Estabelecimentos fiscais** \> **Estabelecimentos fiscais**.</span><span class="sxs-lookup"><span data-stu-id="17520-110">Go to **Organization administration** \> **Organizations** \> **Fiscal establishments** \> **Fiscal establishments**.</span></span>
3. <span data-ttu-id="17520-111">Selecione o estabelecimento fiscal e, depois, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="17520-111">Select the fiscal establishment, and then select **Edit**.</span></span>
4. <span data-ttu-id="17520-112">Na guia **NF-e e NFC-e federal**, no grupo de campos **Notas técnicas da NF-e**, selecione **Habilitar nota técnica de NF-e**.</span><span class="sxs-lookup"><span data-stu-id="17520-112">On the **NF-e and NFC-e federal** FastTab, in the **NF-e technical notes** field group, select **Enable NF-e technical note**.</span></span>
5. <span data-ttu-id="17520-113">No campo **Notas técnicas da NF-e**, selecione **Nota técnica 2020.006 v1.10** para a versão 1.10 da nota técnica.</span><span class="sxs-lookup"><span data-stu-id="17520-113">In the **NF-e technical notes** field, select **2020.006 v1.10 technical note** for version 1.10 of the technical note.</span></span>

## <a name="enable-the-technical-note-in-dynamics-ax-2012-r3"></a><span data-ttu-id="17520-114">Habilite a nota técnica no Dynamics AX 2012 R3</span><span class="sxs-lookup"><span data-stu-id="17520-114">Enable the technical note in Dynamics AX 2012 R3</span></span>

- <span data-ttu-id="17520-115">Aplique KB 4611321 para habilitar a versão 1.10 da nota técnica no Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="17520-115">Apply KB 4611321 to enable version 1.10 of the technical note in Dynamics AX 2012 R3.</span></span>
- <span data-ttu-id="17520-116">Aplique KB 4598546 para habilitar a versão 1.00 da nota técnica no Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="17520-116">Apply KB 4598546 to enable version 1.00 of the technical note in Dynamics AX 2012 R3.</span></span>

## <a name="enter-the-new-nf-e-rejection-codes"></a><span data-ttu-id="17520-117">Insira os códigos de rejeição novos da NF-e</span><span class="sxs-lookup"><span data-stu-id="17520-117">Enter the new NF-e rejection codes</span></span>

<span data-ttu-id="17520-118">A nota técnica NT 2020.006 apresentou novos códigos de rejeição de NF-e.</span><span class="sxs-lookup"><span data-stu-id="17520-118">Technical note NT2020.006 introduced new NF-e rejection codes.</span></span> <span data-ttu-id="17520-119">Conclua as etapas a seguir para adicionar os códigos.</span><span class="sxs-lookup"><span data-stu-id="17520-119">Complete the following steps to add the codes.</span></span>

1. <span data-ttu-id="17520-120">Vá para **Administração da organização** \> **Organizações** \> **Documentos eletrônicos** \> **Parâmetros federais de NF-e**.</span><span class="sxs-lookup"><span data-stu-id="17520-120">Go to **Organization administration** \> **Organizations** \> **Electronic documents** \> **NF-e federal parameters**.</span></span>
2. <span data-ttu-id="17520-121">Na guia **Códigos de rejeição**, selecione **Novo** para inserir os novos códigos de rejeição.</span><span class="sxs-lookup"><span data-stu-id="17520-121">On the **Rejection codes** tab, select **New** to enter the new rejection codes.</span></span> <span data-ttu-id="17520-122">Para a lista de novos códigos de rejeição, consulte a documentação da nota técnica NT2020.006 disponível no [Portal da NF-e](http://www.nfe.fazenda.gov.br/portal/principal.aspx).</span><span class="sxs-lookup"><span data-stu-id="17520-122">For the list of new rejection codes, consult the documentation of the NT2020.006 technical note available in the [NF-e Portal](http://www.nfe.fazenda.gov.br/portal/principal.aspx).</span></span>

## <a name="sales-that-are-intermediated-by-the-taxpayers-own-sales-digital-platform"></a><span data-ttu-id="17520-123">Vendas que são intermediárias pela plataforma digital de vendas própria do contribuinte</span><span class="sxs-lookup"><span data-stu-id="17520-123">Sales that are intermediated by the taxpayer's own sales digital platform</span></span>

<span data-ttu-id="17520-124">Quando uma plataforma digital que é de propriedade do contribuinte serve como o intermediário para uma venda, se o tipo de presença for definido como um dos valores a seguir no cabeçalho da ordem de venda criada para a venda, a marca **&lt;indintermed&gt;** será adicionada ao XML da NF-e.</span><span class="sxs-lookup"><span data-stu-id="17520-124">When a digital platform that is owned by the taxpayer serves as the intermediary for a sale, if the presence type is set to one of the following values on the header of the sales order that is created for the sale, the **&lt;indintermed&gt;** tag is added to the XML of the NF-e.</span></span> <span data-ttu-id="17520-125">O valor é definido como **0** (zero).</span><span class="sxs-lookup"><span data-stu-id="17520-125">The value is set to **0** (zero).</span></span>

- <span data-ttu-id="17520-126">Presencial</span><span class="sxs-lookup"><span data-stu-id="17520-126">In person</span></span>
- <span data-ttu-id="17520-127">Internet</span><span class="sxs-lookup"><span data-stu-id="17520-127">Internet</span></span>
- <span data-ttu-id="17520-128">Teleatendimento</span><span class="sxs-lookup"><span data-stu-id="17520-128">Telesales</span></span>
- <span data-ttu-id="17520-129">Diversos</span><span class="sxs-lookup"><span data-stu-id="17520-129">Others</span></span>

<span data-ttu-id="17520-130">Se o tipo de presença for diferente dos listados, a marca **&lt;indintermed&gt;** não será colocada no XML.</span><span class="sxs-lookup"><span data-stu-id="17520-130">If the presence type is different than those listed, the **&lt;indintermed&gt;** tag is not placed in the XML.</span></span>

## <a name="out-of-scope-for-the-feature"></a><span data-ttu-id="17520-131">Fora do escopo do recurso</span><span class="sxs-lookup"><span data-stu-id="17520-131">Out of scope for the feature</span></span>

- <span data-ttu-id="17520-132">Esse recurso não oferece suporte à NF-e emitida de faturas de texto livre que são geradas de vendas em que o cliente não está fisicamente presente e uma plataforma digital de vendas serve como intermediário.</span><span class="sxs-lookup"><span data-stu-id="17520-132">This feature doesn't support NF-e that are issued from free text invoices that are generated from sales where the customer isn't physically present and a sales digital platform serves as an intermediary.</span></span>
- <span data-ttu-id="17520-133">Este recurso não oferece suporte à NF-e emitida de devoluções, ordens de transferência ou cenários de crédito complementares e tributários.</span><span class="sxs-lookup"><span data-stu-id="17520-133">This feature doesn't support NF-e that are issued from returns, transfer orders, or complementary and tax credit scenarios.</span></span>
