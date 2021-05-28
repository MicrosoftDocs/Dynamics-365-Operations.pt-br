---
title: Configurar contas contábeis do TDS
description: Este tópico explica como configurar contas contábeis para o recurso de Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: 93d4cb54488ec0eeee40ca56f3e46f30012f54f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023027"
---
# <a name="set-up-tds-ledger-accounts"></a><span data-ttu-id="9cf80-103">Configurar contas contábeis do TDS</span><span class="sxs-lookup"><span data-stu-id="9cf80-103">Set up TDS ledger accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9cf80-104">Este tópico explica como configurar contas contábeis para o recurso de Imposto Deduzido na Origem (TDS).</span><span class="sxs-lookup"><span data-stu-id="9cf80-104">This topic explains how to set up ledger accounts for the Tax Deducted at Source (TDS) feature.</span></span> <span data-ttu-id="9cf80-105">Use a página **Plano de contas** para configurar contas contábeis para TDS.</span><span class="sxs-lookup"><span data-stu-id="9cf80-105">You use the **Chart of accounts** page to set up ledger accounts for TDS.</span></span>

1. <span data-ttu-id="9cf80-106">Vá para **Contabilidade \> Plano de contas \> Contas \> Contas principais**.</span><span class="sxs-lookup"><span data-stu-id="9cf80-106">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**.</span></span>
2. <span data-ttu-id="9cf80-107">Na guia **Visão geral**, selecione **Alt+N** para criar uma conta contábil de TDS e insira os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="9cf80-107">On the **Overview** tab, select **Alt+N** to create a TDS ledger account, and enter the required details.</span></span>
3. <span data-ttu-id="9cf80-108">Na guia **Configuração**, no campo **Tipo de lançamento**, selecione **Imposto retido na fonte**.</span><span class="sxs-lookup"><span data-stu-id="9cf80-108">On the **Setup** tab, in the **Posting type** field, select **Withholding tax**.</span></span>     

    > [!NOTE]
    > <span data-ttu-id="9cf80-109">As contas contábeis que têm um tipo de lançamento de **Imposto retido na fonte** podem ser definidas somente como contas a receber usadas para lançar o valor de TDS a receber para um código de imposto de TDS.</span><span class="sxs-lookup"><span data-stu-id="9cf80-109">Ledger accounts that have a posting type of **Withholding tax** can be defined only as receivable accounts that are used to post the TDS receivable amount for a TDS tax code.</span></span>

4. <span data-ttu-id="9cf80-110">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9cf80-110">Close the page.</span></span>
