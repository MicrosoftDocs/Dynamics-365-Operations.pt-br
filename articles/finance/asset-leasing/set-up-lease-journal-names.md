---
title: Configurar nomes de diário de arrendamento
description: Este tópico explica como definir nomes de diário de arrendamento. Os nomes de diários de arrendamento especificam os diários em que as entradas originadas em Arrendamento de ativo são lançadas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 89c5fc768aafe9e5de9adcde32e7b4d0a084941b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990908"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="00b63-104">Configurar nomes de diário de arrendamento</span><span class="sxs-lookup"><span data-stu-id="00b63-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00b63-105">Os nomes de diários de arrendamento especificam os diários em que transações de Arrendamento de ativo são lançadas.</span><span class="sxs-lookup"><span data-stu-id="00b63-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="00b63-106">Somente os nomes de diário atribuídos ao tipo de diário **Arrendamento de ativo** aparecem nos campos **Reconhecimento Inicial** e **Nome de Diário Mensal** na página **Parâmetros de arrendamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="00b63-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="00b63-107">Somente o tipo de diário de **registro de fatura de fornecedor** pode ser atribuído ao campo **Nome do diário de fatura**.</span><span class="sxs-lookup"><span data-stu-id="00b63-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="00b63-108">Para configurar nomes de diário de arrendamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="00b63-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="00b63-109">Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="00b63-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="00b63-110">Na guia **Geral**, no campo **Nome do diário de reconhecimento inicial**,selecione um diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="00b63-111">Todas as entradas do diário de reconhecimento inicial serão lançadas nesse nome de diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="00b63-112">No campo **Nome de diário de fatura**, selecione um diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="00b63-113">Se a opção **Pagar ao fornecedor** for definida como **Sim** para o registro de arrendamento, as faturas de pagamento de arrendamento e despesa serão lançadas nesse nome de diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="00b63-114">No campo **Nome de diário de arrendamento**, selecione um diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="00b63-115">Todas as entradas de depreciação, juros e reclassificação de curto prazo serão lançadas nesse nome de diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="00b63-116">Se a opção **Pagar ao fornecedor** for definida como **Não** para o registro de arrendamento, as entradas de pagamento do arrendamento e de pagamento da despesa também serão lançadas nesse nome de diário.</span><span class="sxs-lookup"><span data-stu-id="00b63-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>