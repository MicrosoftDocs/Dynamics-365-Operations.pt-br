---
title: Defina os parâmetros de TDS no Contas a pagar e no Contas a receber
description: Este tópico explica como definir parâmetros no Contas a pagar e no Contas a receber para oferecer suporte a deduções de Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023028"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="51bc9-103">Defina os parâmetros de TDS no Contas a pagar e no Contas a receber</span><span class="sxs-lookup"><span data-stu-id="51bc9-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51bc9-104">Este tópico explica como definir parâmetros no Contas a pagar e no Contas a receber para oferecer suporte a deduções de Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="51bc9-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="51bc9-105">Vá para **Imposto \> Configuração \> Parâmetros \> Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="51bc9-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="51bc9-106">Na guia **Atualizações**, selecione **Atualizar linhas da ordem** para abrir a caixa de diálogo **Atualizar linhas da ordem**.</span><span class="sxs-lookup"><span data-stu-id="51bc9-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="51bc9-107">Na seção **Grupo de TDS**, no campo **Atualizando grupo de TDS**, especifique o método a ser usado para atualizar o grupo de TDS no nível de linha.</span><span class="sxs-lookup"><span data-stu-id="51bc9-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="51bc9-108">Esta configuração é usada quando o grupo de TDS é atualizado em um cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="51bc9-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="51bc9-109">As opções a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="51bc9-109">The following options are available:</span></span>

    - <span data-ttu-id="51bc9-110">**Nunca** – o grupo de TDS não é atualizado nas linhas da ordem quando é atualizado no cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="51bc9-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="51bc9-111">**Sempre** – o grupo de TDS é atualizado automaticamente nas linhas da ordem quando é atualizado no cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="51bc9-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="51bc9-112">**Avisar** – os usuários recebem uma mensagem que solicita que eles atualizem o grupo de TDS nas linhas da ordem.</span><span class="sxs-lookup"><span data-stu-id="51bc9-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="51bc9-113">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="51bc9-113">Select **OK**.</span></span>

    <span data-ttu-id="51bc9-114">[![Caixa de diálogo Atualizar linhas da ordem](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="51bc9-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="51bc9-115">Vá para **Imposto \> Configuração \> Parâmetros \> Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="51bc9-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="51bc9-116">Na guia **Geral**, na FastTab **Divisão com base nas informações de entrega**, defina a opção **Recebimento de produtos** como **Sim** para lançar e dividir um recebimento de um produto com endereços de entrega e números de conta de impostos (TANS) diferentes.</span><span class="sxs-lookup"><span data-stu-id="51bc9-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="51bc9-117">Se esta opção estiver definida como **Não**, não será possível lançar uma guia de remessa de compra que tenha endereços de entrega e TANS diferentes.</span><span class="sxs-lookup"><span data-stu-id="51bc9-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="51bc9-118">Defina a opção **Fatura** como **Sim** para lançar e dividir uma fatura de compra que tenha vários endereços de entrega e TANs.</span><span class="sxs-lookup"><span data-stu-id="51bc9-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="51bc9-119">[![FastTab Divisão baseada nas informações de entrega](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="51bc9-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="51bc9-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="51bc9-120">Close the page.</span></span>
