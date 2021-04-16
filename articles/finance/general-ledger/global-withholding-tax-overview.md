---
title: Imposto retido na fonte global
description: Este tópico fornece informações sobre a funcionalidade de imposto retido na fonte global e sobre como configurá-la. A funcionalidade de imposto retido na fonte global é aprimorada para transações de fornecedor e de cliente, de forma que o imposto retido na fonte seja calculado no nível do item.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 9a73d34fb4fbf007cbb5a996cfa6e9719532869c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826657"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="fd803-104">Imposto retido na fonte global</span><span class="sxs-lookup"><span data-stu-id="fd803-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd803-105">Este tópico fornece informações sobre a funcionalidade de imposto retido na fonte global e explica como configurá-la.</span><span class="sxs-lookup"><span data-stu-id="fd803-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="fd803-106">A nova funcionalidade está disponível na versão 10.0.17 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="fd803-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="fd803-107">A funcionalidade de imposto retido na fonte global é aprimorada para transações de fornecedor e de cliente, de forma que o imposto retido na fonte seja calculado no nível do item.</span><span class="sxs-lookup"><span data-stu-id="fd803-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="fd803-108">O saldo na conta de imposto retido na fonte das transações de compra pode ser liquidado com a execução do trabalho de pagamento de imposto retido na fonte na conta de liquidação de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="fd803-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="fd803-109">O imposto retido na fonte global não dá suporte à função **Manter encargos** nas páginas ordem de compra, fatura de fornecedor e ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="fd803-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="fd803-110">Ativar imposto retido na fonte global</span><span class="sxs-lookup"><span data-stu-id="fd803-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="fd803-111">No espaço de trabalho **Gerenciamento de recursos**, selecione **Imposto retido na fonte global** e selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="fd803-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="fd803-112">Acesse **Imposto \> Configuração \> Parâmetros \> Parâmetros de contabilidade**. Depois, na guia **Imposto retido na fonte**, defina a opção **Habilitar imposto retido na fonte global** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fd803-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="fd803-113">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd803-113">Select **Save**.</span></span>
4. <span data-ttu-id="fd803-114">Atualize a página no navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="fd803-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="fd803-115">A funcionalidade de imposto retido na fonte global não pode ser ativada para países/regiões em que já existem soluções localizadas de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="fd803-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="fd803-116">Essas áreas incluem, mas não estão restritas à Índia, Brasil, Tailândia, Arábia Saudita, Irlanda, Grã-Bretanha e Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="fd803-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]