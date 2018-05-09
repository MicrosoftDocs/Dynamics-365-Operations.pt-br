--- 
title: "Configurar códigos de ajuste para imposto ICMS (Brasil)"
description: "No arquivo de texto fiscal do Sistema Público de Escrituração Digital (SPED), o registro C197 inclui informações sobre ajustes do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) em notas fiscais."
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0604616b923e7dd47fe09e955101f692f0442441
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-adjustment-codes-for-icms-tax-brazil"></a><span data-ttu-id="b79c3-103">Configurar códigos de ajuste para imposto ICMS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="b79c3-103">Set up adjustment codes for ICMS tax (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b79c3-104">No arquivo de texto fiscal do Sistema Público de Escrituração Digital (SPED), o registro C197 inclui informações sobre ajustes do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) em notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="b79c3-104">In the Sistema Publico de Escrituração Digital (SPED) fiscal text file, record C197 includes information about adjustments of Imposto sobre Circulação de Mercadorias e Serviços (ICMS) information on fiscal documents.</span></span> <span data-ttu-id="b79c3-105">Esses ajustes podem ocorrer devido ao diferimento, à suspensão diferencial de taxas de impostos, à antecipação, e a outras situações de exceção em impostos ICMS, e isso requer um código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="b79c3-105">These adjustments can occur due to deferral, suspension, differential of tax rates, anticipation, and other situations of exception in the ICMS tax, and thus they require an adjustment code.</span></span> <span data-ttu-id="b79c3-106">Utilize esse procedimento para configurar códigos de ajuste.</span><span class="sxs-lookup"><span data-stu-id="b79c3-106">Use this procedure to set up an adjustment codes.</span></span> <span data-ttu-id="b79c3-107">Este registro usa a empresa de dados de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="b79c3-107">This recording uses the BRMF demo company.</span></span>

1. <span data-ttu-id="b79c3-108">Vá para Livros fiscais > Configuração > Códigos de ajuste de imposto > Tabela de códigos de ajuste de ICMS, ICMS-ST e ICMS-DIF.</span><span class="sxs-lookup"><span data-stu-id="b79c3-108">Go to Fiscal books > Setup > Tax adjustment codes > ICMS , ICMS-ST and ICMS-DIF adjustment codes table.</span></span>
2. <span data-ttu-id="b79c3-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b79c3-109">Click New.</span></span>
3. <span data-ttu-id="b79c3-110">No campo Identificação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-110">In the Identification field, type a value.</span></span>
4. <span data-ttu-id="b79c3-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b79c3-112">No campo Estado, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-112">In the State field, enter or select a value.</span></span>
6. <span data-ttu-id="b79c3-113">No campo Código de ocorrência, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-113">In the Occurrence code field, type a value.</span></span>
7. <span data-ttu-id="b79c3-114">No campo Código de ocorrência, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-114">In the Occurrence code field, type a value.</span></span>
8. <span data-ttu-id="b79c3-115">No campo Válido a Partir da Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b79c3-115">In the Valid From Date field, enter a date.</span></span>
9. <span data-ttu-id="b79c3-116">Expandir a seção Pagamento.</span><span class="sxs-lookup"><span data-stu-id="b79c3-116">Expand the Payment section.</span></span>
10. <span data-ttu-id="b79c3-117">Expanda a seção Lançamento.</span><span class="sxs-lookup"><span data-stu-id="b79c3-117">Expand the Posting section.</span></span>
11. <span data-ttu-id="b79c3-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b79c3-118">Click New.</span></span>
12. <span data-ttu-id="b79c3-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b79c3-119">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="b79c3-120">No campo Contas da empresa, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-120">In the Company accounts field, enter or select a value.</span></span>
14. <span data-ttu-id="b79c3-121">No campo Código de impostos sobre vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b79c3-121">In the Sales tax code field, enter or select a value.</span></span>
15. <span data-ttu-id="b79c3-122">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="b79c3-122">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="b79c3-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b79c3-123">Click Save.</span></span>
17. <span data-ttu-id="b79c3-124">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b79c3-124">Close the page.</span></span>


