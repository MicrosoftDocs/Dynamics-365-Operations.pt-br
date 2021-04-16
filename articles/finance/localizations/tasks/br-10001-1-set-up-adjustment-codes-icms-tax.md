---
title: Configurar códigos de ajuste para imposto ICMS (Brasil)
description: No arquivo de texto fiscal do Sistema Público de Escrituração Digital (SPED), o registro C197 inclui informações sobre ajustes do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) em notas fiscais.
author: sndray
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a001b60f8921629f75ad9b138b0d1ad1ff8c5138
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842287"
---
# <a name="set-up-adjustment-codes-for-icms-tax-brazil"></a><span data-ttu-id="c0f6c-103">Configurar códigos de ajuste para imposto ICMS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="c0f6c-103">Set up adjustment codes for ICMS tax (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0f6c-104">No arquivo de texto fiscal do Sistema Público de Escrituração Digital (SPED), o registro C197 inclui informações sobre ajustes do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) em notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-104">In the Sistema Publico de Escrituração Digital (SPED) fiscal text file, record C197 includes information about any adjustments of Imposto sobre Circulação de Mercadorias e Serviços (ICMS) information on fiscal documents.</span></span> <span data-ttu-id="c0f6c-105">Esses ajustes pode ocorrer devidos a um adiamento, suspensão, diferencial de alíquotas, antecipação, e outras situações de exceção do imposto ICMS.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-105">These adjustments can occur because of deferral, suspension, differential of tax rates, anticipation, and other situations of exception in the ICMS tax.</span></span> <span data-ttu-id="c0f6c-106">Os ajustes exigem um código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-106">The adjustments require an adjustment code.</span></span> <span data-ttu-id="c0f6c-107">Utilize esse procedimento para configurar códigos de ajuste.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-107">Use this procedure to set up adjustment codes.</span></span> <span data-ttu-id="c0f6c-108">Este tópico usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-108">This topic uses the BRMF demo company.</span></span>

1. <span data-ttu-id="c0f6c-109">Vá para **Livros fiscais** > **Configuração** > **Códigos de ajuste de imposto** > **Códigos de ajuste de ICMS, ICMS-ST e ICMS-DIF**.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-109">Go to **Fiscal books** > **Setup** > **Tax adjustment codes** > **ICMS, ICMS-ST, and ICMS-DIF adjustment codes**.</span></span>
2. <span data-ttu-id="c0f6c-110">Selecione **Novo** e no campo **Identificação**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-110">Select **New**, and in the **Identification** field, type a value.</span></span>
3. <span data-ttu-id="c0f6c-111">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-111">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="c0f6c-112">No campo **Estado**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-112">In the **State** field, enter or select a value.</span></span>
5. <span data-ttu-id="c0f6c-113">No campo **Código de ocorrência**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-113">In the **Occurrence code** field, type a value.</span></span>
6. <span data-ttu-id="c0f6c-114">No campo **Código de ocorrência**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-114">In the **Occurrence code** field, type a value.</span></span>
7. <span data-ttu-id="c0f6c-115">No campo **Válido a Partir da Data**, informe uma data.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-115">In the **Valid From Date** field, enter a date.</span></span>
8. <span data-ttu-id="c0f6c-116">Expanda a seção **Pagamento**, expanda a seção **Lançamento** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-116">Expand the **Payment** section, expand the **Posting** section, and then select **New**.</span></span>
9. <span data-ttu-id="c0f6c-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-117">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="c0f6c-118">No campo **Contas da empresa**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-118">In the **Company accounts** field, enter or select a value.</span></span>
11. <span data-ttu-id="c0f6c-119">No campo **Código do imposto** informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-119">In the **Sales tax code** field, enter or select a value.</span></span>
12. <span data-ttu-id="c0f6c-120">No campo **Conta principal**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-120">In the **Main account** field, specify the desired values.</span></span>
13. <span data-ttu-id="c0f6c-121">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c0f6c-121">Select **Save** and then close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]