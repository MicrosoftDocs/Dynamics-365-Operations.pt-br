---
title: Configurar imposto global retido na fonte
description: Este tópico lista as etapas para configurar o imposto global retido na fonte para vendas e compras.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 00c472e90f4926c52ffe9b19661e68cbfa6bd493
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204824"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="e066e-103">Configurar imposto global retido na fonte</span><span class="sxs-lookup"><span data-stu-id="e066e-103">Set up global withholding tax</span></span>

<span data-ttu-id="e066e-104">Este tópico lista as etapas para configurar o imposto global retido na fonte para vendas e compras.</span><span class="sxs-lookup"><span data-stu-id="e066e-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="e066e-105">Configure as autoridades de imposto retido na fonte na página **Autoridades de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="e066e-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="e066e-106">Configure os períodos de liquidação de retenção na página **Períodos de liquidação de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="e066e-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="e066e-107">Configure o grupo de lançamentos contábeis na página **Imposto retido na fonte > Grupo de lançamentos do razão**.</span><span class="sxs-lookup"><span data-stu-id="e066e-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="e066e-108">**A conta de imposto retido na fonte** será atribuída a uma conta principal com o **Tipo de lançamento** Imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="e066e-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="e066e-109">**A conta de contrapartida de retenção de imposto na fonte** também será atribuída a uma conta principal com o **Tipo de lançamento** Contrapartida de retenção de imposto na fonte.</span><span class="sxs-lookup"><span data-stu-id="e066e-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="e066e-110">Vá para **Contabilidade > Plano de contas > Contas > Contas principais**, configure o **Tipo de lançamento** no subformulário **Validação de lançamento** para as contas principais.</span><span class="sxs-lookup"><span data-stu-id="e066e-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="e066e-111">Configure os códigos de imposto retido na fonte na página **Autoridades imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="e066e-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="e066e-112">Configure os grupos de imposto retido na fonte na página **Grupos de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="e066e-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="e066e-113">Configure os tipos de receita de imposto retido na fonte na página **Tipos** de **Receita de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="e066e-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="e066e-114">Configure os grupos de imposto retido na fonte na página **Grupos de imposto retido na fonte do item** para um item ou serviço.</span><span class="sxs-lookup"><span data-stu-id="e066e-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="e066e-115">Configure o **Valor mínimo da fatura** na página **Parâmetros de contabilidade > Imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="e066e-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]