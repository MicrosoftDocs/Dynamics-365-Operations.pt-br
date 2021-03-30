---
title: Criar um conhecimento de embarque
description: Este tópico descreve como criar um conhecimento de embarque ao usar processos de gerenciamento de depósito.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31e6ce3fd65263d6df248322ca149afa5f750cb7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206886"
---
# <a name="create-a-bill-of-lading"></a><span data-ttu-id="c712f-103">Criar um conhecimento de embarque</span><span class="sxs-lookup"><span data-stu-id="c712f-103">Create a bill of lading</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c712f-104">Este tópico descreve como criar um conhecimento de embarque ao usar processos de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="c712f-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="c712f-105">Um conhecimento de embarque é um documento legal entre a empresa que envia os itens e a transportadora.</span><span class="sxs-lookup"><span data-stu-id="c712f-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="c712f-106">O documento acompanha os itens enviados, e serve como um recibo de remessa quando os itens são entregues no destino.</span><span class="sxs-lookup"><span data-stu-id="c712f-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="c712f-107">Se você estiver usando o gerenciamento de depósito, há duas maneiras de gerar um conhecimento de embarque:</span><span class="sxs-lookup"><span data-stu-id="c712f-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="c712f-108">Crie o relatório manualmente usando a página **Conhecimento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="c712f-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="c712f-109">Gere o relatório na **Bancada do planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="c712f-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="c712f-110">Se você gerar o conhecimento de embarque na **Bancada de planejamento de carga**, o status da carga deverá ser **Enviada**.</span><span class="sxs-lookup"><span data-stu-id="c712f-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="c712f-111">Se houver mais de uma remessa na carga, um conhecimento de embarque será criado para cada remessa.</span><span class="sxs-lookup"><span data-stu-id="c712f-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="c712f-112">Depois que um conhecimento de embarque for criado, você poderá alterá-lo na página **Conhecimento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="c712f-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="c712f-113">Conhecimento de embarque mestre</span><span class="sxs-lookup"><span data-stu-id="c712f-113">Master bill of lading</span></span>
<span data-ttu-id="c712f-114">Se houver mais de uma remessa na carga, você poderá gerar um conhecimento de embarque mestre.</span><span class="sxs-lookup"><span data-stu-id="c712f-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="c712f-115">O resultado será o mesmo layout e informações de um conhecimento de embarque, mas com conteúdo resumido de todas as remessas.</span><span class="sxs-lookup"><span data-stu-id="c712f-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="c712f-116">Se a opção **Criar um conhecimento de embarque mestre quando houver mais de uma remessa em uma carga** for definida como **Sim** na página **Parâmetros de gerenciamento de transporte**, um conhecimento de embarque mestre será gerado automaticamente se você criar um conhecimento de embarque na **Bancada de planejamento de carga** e houver mais de uma remessa.</span><span class="sxs-lookup"><span data-stu-id="c712f-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="c712f-117">Você também pode obter uma lista dos conhecimentos de embarque clicando em **Informações relacionadas** &gt; **Conhecimento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="c712f-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="c712f-118">Se você criar conhecimentos de embarque manualmente, poderá criar um conhecimento de embarque mestre na página **Conhecimento de embarque**.</span><span class="sxs-lookup"><span data-stu-id="c712f-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]