---
title: Criar cheques que tenham status Em Branco
description: Este tópico explica como criar cheques em branco para uma conta bancária na página Cheques.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 47d54524f87cf718b9b41462b5133df267d5dd9e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4458475"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="e1ea6-103">Criar cheques que tenham status Em Branco</span><span class="sxs-lookup"><span data-stu-id="e1ea6-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1ea6-104">Este tópico explica como criar cheques em branco.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="e1ea6-105">Por exemplo, pode criar um cheque em branco para registrar que um cheque foi danificado e não pode ser usado para pagamento.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="e1ea6-106">Na página **Cheques**, você executa tarefas de manutenção para os cheques.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="e1ea6-107">Por exemplo, você pode criar novos números de cheque e excluir cheques.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="e1ea6-108">Você também pode criar cheques com o status **Em Branco**.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="e1ea6-109">Depois que os cheques em branco forem criados, eles não poderão ser excluídos ou reutilizadas no sistema.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="e1ea6-110">Esse recurso estará disponível na página **Cheques** somente se você ativar o recurso **Criar cheques com um status em branco na página Cheques** na página **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="e1ea6-111">Se o recurso não estiver ativado, os cheques com o status **Em Branco** poderão ser criados somente a partir da caixa de diálogo **Pagamento por cheque** durante o processo de geração de pagamento em Contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="e1ea6-112">Para abrir a página **Cheques**, acesse **Gerenciamento de caixa e bancos \> Contas bancárias \> Contas bancárias** e, no Painel de Ação, na guia **Gerenciar pagamentos**, no grupo **Informações relacionadas**, selecione **Cheques**.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="e1ea6-113">Alternativamente, acesse **Gerenciamento de caixa e bancos \> Consultas e relatórios \> Cheques**.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="e1ea6-114">Em seguida, para criar cheques com o status **Em Branco**, no Painel de Ação, selecione **Criar cheques em branco**.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="e1ea6-115">Enquanto o sistema estiver criando cheques em branco, a conta bancária associada ficará desativada temporariamente.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="e1ea6-116">Esse comportamento reduz o risco de pagamentos serem gerados ao mesmo tempo em que os cheques em branco são criados.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="e1ea6-117">Quando o processamento for concluído, a conta bancária associada será reativada.</span><span class="sxs-lookup"><span data-stu-id="e1ea6-117">When the processing is completed, the associated bank account is reactivated.</span></span>
