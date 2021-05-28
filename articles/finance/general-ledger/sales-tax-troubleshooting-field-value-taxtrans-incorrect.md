---
title: Valor de campo incorreto em TaxTrans
description: Este tópico fornece informações sobre como solucionar problemas de valores de campo incorretos em TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020154"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="90c77-103">Valor de campo incorreto em TaxTrans</span><span class="sxs-lookup"><span data-stu-id="90c77-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90c77-104">Se um valor de campo em **TaxTrans** estiver incorreto, use as informações deste tópico para tentar resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="90c77-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="90c77-105">Visão geral de valores</span><span class="sxs-lookup"><span data-stu-id="90c77-105">Overview of values</span></span>
<span data-ttu-id="90c77-106">A lista a seguir mostra como **TaxTrans**, **TaxUncommitted** e **TmpTaxWorkTrans** são conjuntos de dados semelhantes, mas trabalham de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="90c77-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="90c77-107">**TaxTrans** é o resultado da transação de imposto lançado final persistente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="90c77-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="90c77-108">**TaxUncommitted** é o resultado do imposto calculado intermediário persistente no banco de dados (se aplicável), que será usado posteriormente no lançamento.</span><span class="sxs-lookup"><span data-stu-id="90c77-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="90c77-109">**TmpTaxWorkTrans** é o resultado do imposto calculado temporário da tabela na memória (Tipo de Tabela = InMemory).</span><span class="sxs-lookup"><span data-stu-id="90c77-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="90c77-110">Se você encontrar a causa raiz de uma coluna **TaxTrans** incorreta, também encontrará a causa raiz de uma coluna **TaxUncommitted** ou **TmpTaxWorkTrans** incorreta.</span><span class="sxs-lookup"><span data-stu-id="90c77-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="90c77-111">Isso ocorre porque as três colunas são copiadas uma da outra.</span><span class="sxs-lookup"><span data-stu-id="90c77-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="90c77-112">Normalmente, durante o cálculo de impostos, **TmpTaxWorkTrans** é gerado e, em seguida, se aplicável, **TaxUncommitted** é gerado.</span><span class="sxs-lookup"><span data-stu-id="90c77-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="90c77-113">Durante o lançamento de impostos, **TaxTrans** é gerado.</span><span class="sxs-lookup"><span data-stu-id="90c77-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="90c77-114">Adicionar pontos de interrupção</span><span class="sxs-lookup"><span data-stu-id="90c77-114">Add breakpoints</span></span>
<span data-ttu-id="90c77-115">Para adicionar pontos de interrupção, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="90c77-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="90c77-116">Adicione extensões e pontos de interrupção em *insert()* e *update()* nas extensões, conforme mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="90c77-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="90c77-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="90c77-117">**TaxTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="90c77-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="90c77-118">**TaxUncommitted**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="90c77-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="90c77-119">**TmpTaxWorkTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. <span data-ttu-id="90c77-120">Como alternativa, você pode adicionar pontos de interrupção diretamente quando **TaxUncommitted** não estiver incluído.</span><span class="sxs-lookup"><span data-stu-id="90c77-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="90c77-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="90c77-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="90c77-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="90c77-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="90c77-123">Reproduzir e depurar</span><span class="sxs-lookup"><span data-stu-id="90c77-123">Reproduce and debug</span></span>

<span data-ttu-id="90c77-124">Depois que os pontos de interrupção são definidos, todas as alterações de persistência de dados ficam visíveis durante a depuração.</span><span class="sxs-lookup"><span data-stu-id="90c77-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="90c77-125">Para encontrar a causa raiz de uma coluna incorreta de **TaxTrans**, **TaxUncommitted** ou **TmpTaxWorkTrans**, revise e anote os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="90c77-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="90c77-126">O último ponto de interrupção no qual a coluna está correta.</span><span class="sxs-lookup"><span data-stu-id="90c77-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="90c77-127">O primeiro ponto de interrupção no qual a coluna está incorreta.</span><span class="sxs-lookup"><span data-stu-id="90c77-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="90c77-128">O que acontece entre esses dois pontos.</span><span class="sxs-lookup"><span data-stu-id="90c77-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="90c77-129">Determinar se há personalização</span><span class="sxs-lookup"><span data-stu-id="90c77-129">Determine whether customization exists</span></span>
<span data-ttu-id="90c77-130">Se você concluiu as etapas nas seções anteriores, mas não conseguiu resolver o problema, determine se há personalização.</span><span class="sxs-lookup"><span data-stu-id="90c77-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="90c77-131">Se não houver personalização, contate o Suporte da Microsoft para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="90c77-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

