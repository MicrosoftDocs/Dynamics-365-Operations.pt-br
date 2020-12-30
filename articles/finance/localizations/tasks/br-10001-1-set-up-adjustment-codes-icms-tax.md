---
title: Configurar códigos de ajuste para imposto ICMS (Brasil)
description: No arquivo de texto fiscal do Sistema Público de Escrituração Digital (SPED), o registro C197 inclui informações sobre ajustes do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) em notas fiscais.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6875fc935a2b724cdeb1e1fc965a55c7497e08a7
ms.sourcegitcommit: 0e60df840688932795b9c8f8fd45d98f5ab6ba8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668962"
---
# <a name="set-up-adjustment-codes-for-icms-tax-brazil"></a><span data-ttu-id="12d92-103">Configurar códigos de ajuste para imposto ICMS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="12d92-103">Set up adjustment codes for ICMS tax (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12d92-104">No arquivo de texto fiscal do Sistema Público de Escrituração Digital (SPED), o registro C197 inclui informações sobre ajustes do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) em notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="12d92-104">In the Sistema Publico de Escrituração Digital (SPED) fiscal text file, record C197 includes information about any adjustments of Imposto sobre Circulação de Mercadorias e Serviços (ICMS) information on fiscal documents.</span></span> <span data-ttu-id="12d92-105">Esses ajustes pode ocorrer devidos a um adiamento, suspensão, diferencial de alíquotas, antecipação, e outras situações de exceção do imposto ICMS.</span><span class="sxs-lookup"><span data-stu-id="12d92-105">These adjustments can occur because of deferral, suspension, differential of tax rates, anticipation, and other situations of exception in the ICMS tax.</span></span> <span data-ttu-id="12d92-106">Os ajustes exigem um código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="12d92-106">The adjustments require an adjustment code.</span></span> <span data-ttu-id="12d92-107">Utilize esse procedimento para configurar códigos de ajuste.</span><span class="sxs-lookup"><span data-stu-id="12d92-107">Use this procedure to set up adjustment codes.</span></span> <span data-ttu-id="12d92-108">Este tópico usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="12d92-108">This topic uses the BRMF demo company.</span></span>

1. <span data-ttu-id="12d92-109">Vá para **Livros fiscais** > **Configuração** > **Códigos de ajuste de imposto** > **Códigos de ajuste de ICMS, ICMS-ST e ICMS-DIF**.</span><span class="sxs-lookup"><span data-stu-id="12d92-109">Go to **Fiscal books** > **Setup** > **Tax adjustment codes** > **ICMS, ICMS-ST, and ICMS-DIF adjustment codes**.</span></span>
2. <span data-ttu-id="12d92-110">Selecione **Novo** e no campo **Identificação**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-110">Select **New**, and in the **Identification** field, type a value.</span></span>
3. <span data-ttu-id="12d92-111">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-111">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="12d92-112">No campo **Estado**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-112">In the **State** field, enter or select a value.</span></span>
5. <span data-ttu-id="12d92-113">No campo **Código de ocorrência**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-113">In the **Occurrence code** field, type a value.</span></span>
6. <span data-ttu-id="12d92-114">No campo **Código de ocorrência**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-114">In the **Occurrence code** field, type a value.</span></span>
7. <span data-ttu-id="12d92-115">No campo **Válido a Partir da Data**, informe uma data.</span><span class="sxs-lookup"><span data-stu-id="12d92-115">In the **Valid From Date** field, enter a date.</span></span>
8. <span data-ttu-id="12d92-116">Expanda a seção **Pagamento**, expanda a seção **Lançamento** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="12d92-116">Expand the **Payment** section, expand the **Posting** section, and then select **New**.</span></span>
9. <span data-ttu-id="12d92-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="12d92-117">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="12d92-118">No campo **Contas da empresa**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-118">In the **Company accounts** field, enter or select a value.</span></span>
11. <span data-ttu-id="12d92-119">No campo **Código do imposto** informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="12d92-119">In the **Sales tax code** field, enter or select a value.</span></span>
12. <span data-ttu-id="12d92-120">No campo **Conta principal**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="12d92-120">In the **Main account** field, specify the desired values.</span></span>
13. <span data-ttu-id="12d92-121">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="12d92-121">Select **Save** and then close the page.</span></span>

