---
title: Configurar códigos de relatórios de imposto retido na fonte para o tipo de imposto de TDS
description: Os códigos de relatório de imposto retido na fonte são usados para gerar instruções do Formulário 26Q e do Formulário 27Q para Imposto Deduzido na Origem (TDS). Este tópico explica como configurar as etapas de códigos de relatório de imposto retido na fonte para que você possa configurar códigos de relatório de TDS.
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
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023038"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a><span data-ttu-id="3fa56-104">Configurar códigos de relatórios de imposto retido na fonte para o tipo de imposto de TDS</span><span class="sxs-lookup"><span data-stu-id="3fa56-104">Set up withholding tax reporting codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3fa56-105">Os códigos de relatório de imposto retido na fonte são usados para gerar instruções do Formulário 26Q e do Formulário 27Q para Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="3fa56-105">Withholding tax reporting codes are used to generate Form 26Q and Form 27Q statements for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="3fa56-106">Este tópico explica como configurar as etapas de códigos de relatório de imposto retido na fonte para que você possa configurar códigos de relatório de TDS.</span><span class="sxs-lookup"><span data-stu-id="3fa56-106">This topic explains how to set up withholding tax reporting codes steps so that you can set up TDS reporting codes.</span></span>

1. <span data-ttu-id="3fa56-107">Vá para **Imposto \> Configuração \> Imposto retido na fonte \> Códigos de relatório de imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="3fa56-107">Go to **Tax \> Setup \> Withholding tax \> Withholding tax reporting codes**.</span></span>

    <span data-ttu-id="3fa56-108">[![Página códigos de relatório de imposto retido na fonte](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span><span class="sxs-lookup"><span data-stu-id="3fa56-108">[![Withholding tax reporting codes page](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span></span>

2. <span data-ttu-id="3fa56-109">No campo **Tipo de imposto**, selecione **TDS** para definir códigos de relatórios de imposto retido na fonte para o tipo de imposto de TDS.</span><span class="sxs-lookup"><span data-stu-id="3fa56-109">In the **Tax type** field, select **TDS** to define withholding tax reporting codes for the TDS tax type.</span></span>
3. <span data-ttu-id="3fa56-110">No campo **Componente de imposto retido na fonte**, selecione o componente de TDS para o qual você está definindo o código de relatório de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="3fa56-110">In the **Withholding tax component** field, select the TDS component to that you're defining the withholding tax reporting code for.</span></span> <span data-ttu-id="3fa56-111">O campo **Grupo de componentes do imposto retido na fonte** mostra o grupo de componentes de TDS definido para o componente de TDS que você está definindo.</span><span class="sxs-lookup"><span data-stu-id="3fa56-111">The **Withholding tax component group** field shows the TDS component group that was defined for the TDS component that you're defining.</span></span>

    <span data-ttu-id="3fa56-112">O campo **Código de seção** na FastTab **Geral** mostra o código de seção anexado ao grupo de componentes de TDS.</span><span class="sxs-lookup"><span data-stu-id="3fa56-112">The **Section code** field on the **General** FastTab shows the section code that is attached to the TDS component group.</span></span>

4. <span data-ttu-id="3fa56-113">Na FastTab **Geral**, no campo **Código do relatório**, selecione o códigos de relatório de TDS:</span><span class="sxs-lookup"><span data-stu-id="3fa56-113">On the **General** FastTab, in the **Reporting code** field, select the TDS reporting code:</span></span>

    - <span data-ttu-id="3fa56-114">TDS</span><span class="sxs-lookup"><span data-stu-id="3fa56-114">TDS</span></span>
    - <span data-ttu-id="3fa56-115">TCS</span><span class="sxs-lookup"><span data-stu-id="3fa56-115">TCS</span></span>
    - <span data-ttu-id="3fa56-116">Sobretaxa</span><span class="sxs-lookup"><span data-stu-id="3fa56-116">Surcharge</span></span>
    - <span data-ttu-id="3fa56-117">PE\_Cess</span><span class="sxs-lookup"><span data-stu-id="3fa56-117">PE\_Cess</span></span>
    - <span data-ttu-id="3fa56-118">SHE\_Cess</span><span class="sxs-lookup"><span data-stu-id="3fa56-118">SHE\_Cess</span></span>

5. <span data-ttu-id="3fa56-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3fa56-119">Close the page.</span></span>
