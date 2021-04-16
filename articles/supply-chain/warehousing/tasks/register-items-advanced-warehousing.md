---
title: Registrar itens para um item habilitado de depósito avançado usando um diário de entrada de item
description: Este tópico apresenta um cenário que mostra como registrar itens usando o diário de entrada de itens quando você estiver usando processos de gerenciamento de depósito avançado.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830825"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="6f9c2-103">Registrar itens para um item habilitado de depósito avançado usando um diário de entrada de item</span><span class="sxs-lookup"><span data-stu-id="6f9c2-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6f9c2-104">Este tópico apresenta um cenário que mostra como registrar itens usando o diário de entrada de itens quando você estiver usando processos de gerenciamento de depósito avançado.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-104">This topic presents a scenario that shows how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="6f9c2-105">Normalmente isso é feito por um vendedor de remessa.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-105">This would usually be done by a receiving clerk.</span></span>

## <a name="enable-sample-data"></a><span data-ttu-id="6f9c2-106">Habilitar dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="6f9c2-106">Enable sample data</span></span>

<span data-ttu-id="6f9c2-107">Para trabalhar neste cenário usando os exemplos de registros e valores especificados neste tópico, você deve usar um sistema em que os dados de demonstração padrão são instalados e deve selecionar a entidade legal *USMF* antes de começar.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-107">To work through this scenario using the sample records and values specified in this topic, you must be using a system where the standard demo data is installed, and you must select the *USMF* legal entity before you begin.</span></span>

<span data-ttu-id="6f9c2-108">Você pode trabalhar por meio desse cenário substituindo valores de seus próprios dados desde que tenha os seguintes dados disponíveis:</span><span class="sxs-lookup"><span data-stu-id="6f9c2-108">You can instead work through this scenario by substituting values from your own data provided that you have the following data available:</span></span>

- <span data-ttu-id="6f9c2-109">Você deve ter uma ordem de compra confirmada com uma linha de ordem de compra aberta.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-109">You must have a confirmed purchase order with an open purchase order line.</span></span>
- <span data-ttu-id="6f9c2-110">O item na linha deve ser estocado.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-110">The item on the line must be stocked.</span></span> <span data-ttu-id="6f9c2-111">Ele não deve usar grades de produto e não deve ter dimensões de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-111">It must not use product variants, and must not have tracking dimensions.</span></span>
- <span data-ttu-id="6f9c2-112">O item deve estar associado a um grupo de dimensões de armazenamento com um processo de gerenciamento de depósito habilitado.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-112">The item must be associated with a storage dimension group that has warehouse management process enabled.</span></span>
- <span data-ttu-id="6f9c2-113">O depósito usado deve ser habilitado para processos de gerenciamento de depósito, e a localização usada para recebimento deve ser controlada por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-113">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span>

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a><span data-ttu-id="6f9c2-114">Criar um cabeçalho do diário de entrada de item que use o gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="6f9c2-114">Create an item arrival journal header that uses warehouse management</span></span>

<span data-ttu-id="6f9c2-115">O seguinte cenário mostra como criar um cabeçalho do diário de entrada de item que usa o gerenciamento de depósito:</span><span class="sxs-lookup"><span data-stu-id="6f9c2-115">The following scenario shows how to create an item arrival journal header that uses warehouse management:</span></span>

1. <span data-ttu-id="6f9c2-116">Verifique se o sistema contém uma ordem de compra confirmada que atende aos requisitos descritos na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-116">Make sure your system contains a confirmed purchase order that fulfils the requirements outlined in the previous section.</span></span> <span data-ttu-id="6f9c2-117">Este cenário usa uma ordem de compra para a empresa *USMF*, conta de fornecedor *1001*, depósito *51*, com uma linha de ordem para *10 PL* (10 paletes) do número de item *M9200*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-117">This scenario uses a purchase order for company *USMF*, vendor account *1001*, warehouse *51*, with an order line for *10 PL* (10 pallets) of item number *M9200*.</span></span>
1. <span data-ttu-id="6f9c2-118">Anote o número da ordem de compra que você usará.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-118">Make a note of the purchase order number that you will use.</span></span>
1. <span data-ttu-id="6f9c2-119">Acesse **Gerenciamento de estoque \> Entradas de diário \> Entrada de item \> Entrada de item**.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-119">Go to **Inventory management \> Journal entries \> Item arrival \> Item arrival**.</span></span>
1. <span data-ttu-id="6f9c2-120">Selecione **Novo** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-120">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="6f9c2-121">A caixa de diálogo **Criar diário de gerenciamento de depósito** é aberta.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-121">The **Create warehouse management journal** dialog box opens.</span></span> <span data-ttu-id="6f9c2-122">Selecione um nome de diário no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-122">Select a journal name in the **Name** field.</span></span>
    - <span data-ttu-id="6f9c2-123">Se estiver usando dados de exemplo *USMF*, selecione *WHS*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-123">If you are using *USMF* sample data, select *WHS*.</span></span>
    - <span data-ttu-id="6f9c2-124">Se você estiver usando seus próprios dados, o diário escolhido deverá ter **Verificar local de separação** definido como *Não* e **Gerenciamento de quarentena** definido como *Não*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-124">If you're using your own data, the journal you choose must have **Check picking location** set to *No* and **Quarantine management** set to *No*.</span></span>
1. <span data-ttu-id="6f9c2-125">Defina **Referência** como *Ordem de compra*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-125">Set **Reference** to *Purchase order*.</span></span>
1. <span data-ttu-id="6f9c2-126">Defina **Número da conta** como *1001*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-126">Set **Account number** to *1001*.</span></span>
1. <span data-ttu-id="6f9c2-127">Defina **Número** para o número da ordem de compra que você identificou para este exercício.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-127">Set **Number** to the number of the purchase order that you identified for this exercise.</span></span>

    <span data-ttu-id="6f9c2-128">![Diário de entrada de itens](../media/item-arrival-journal-header.png "Diário de entrada de itens")</span><span class="sxs-lookup"><span data-stu-id="6f9c2-128">![Item arrival journal](../media/item-arrival-journal-header.png "Item arrival journal")</span></span>

1. <span data-ttu-id="6f9c2-129">Selecione **OK** para criar o cabeçalho do diário.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-129">Select the **OK** to create the journal header.</span></span>
1. <span data-ttu-id="6f9c2-130">Na seção **Linhas do diário**, selecione **Adicionar linha** e insira os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="6f9c2-130">In the **Journal lines** section, select **Add line** and enter the following data:</span></span>
    - <span data-ttu-id="6f9c2-131">**Número do item** – Defina como *M9200*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-131">**Item number** – Set to *M9200*.</span></span> <span data-ttu-id="6f9c2-132">O **Local**, o **Depósito** e a **Quantidade** serão definidos com base nos dados da transação de estoque para os 10 paletes (1000 ea.).</span><span class="sxs-lookup"><span data-stu-id="6f9c2-132">The **Site**, **Warehouse**, and **Quantity** will get set based on the inventory transaction data for the 10 pallets (1000 ea.).</span></span>
    - <span data-ttu-id="6f9c2-133">**Local** – definido como *001*.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-133">**Location** – Set to  *001*.</span></span> <span data-ttu-id="6f9c2-134">Este local específico não controla as placas de licença.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-134">This specific location does not track license plates.</span></span>

    <span data-ttu-id="6f9c2-135">![Linha do diário de entrada de itens](../media/item-arrival-journal-line.png "Linha do diário de entrada de itens")</span><span class="sxs-lookup"><span data-stu-id="6f9c2-135">![Item arrival journal line](../media/item-arrival-journal-line.png "Item arrival journal line")</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f9c2-136">O campo **Data** determina a data em que a quantidade disponível desse item será registrada no estoque.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-136">The **Date** field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    >
    > <span data-ttu-id="6f9c2-137">A **ID do lote** será preenchida pelo sistema se puder ser identificada somente a partir das informações fornecidas.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-137">The **Lot ID** will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="6f9c2-138">Caso contrário, você precisará inseri-la manualmente.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-138">Otherwise you will have to enter this manually.</span></span> <span data-ttu-id="6f9c2-139">Este é um campo obrigatório, que vincula esse registro a uma linha de documento de origem específica.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-139">This is a required field, which links this registration to a specific source document line.</span></span>  

1. <span data-ttu-id="6f9c2-140">No Painel de Ações, selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-140">Select **Validate** on the Action Pane.</span></span> <span data-ttu-id="6f9c2-141">Isso verifica se o diário está pronto para ser lançado.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-141">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="6f9c2-142">Se a validação falhar, você precisará corrigir os erros antes de poder lançar o diário.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-142">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
1. <span data-ttu-id="6f9c2-143">A caixa de diálogo **Verificar diário** é aberta.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-143">The **Check journal** dialog box opens.</span></span> <span data-ttu-id="6f9c2-144">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-144">Select **OK**.</span></span>
1. <span data-ttu-id="6f9c2-145">Analise a barra de mensagens.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-145">Review the message bar.</span></span> <span data-ttu-id="6f9c2-146">Deve haver uma mensagem denotando que a operação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-146">There should be a message denoting that the operation was completed.</span></span>  
1. <span data-ttu-id="6f9c2-147">No Painel de Ações, selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-147">Select **Post** on the Action Pane.</span></span>
1. <span data-ttu-id="6f9c2-148">A caixa de diálogo **Lançar diário** é aberta.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-148">The **Post journal** dialog box opens.</span></span> <span data-ttu-id="6f9c2-149">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-149">Select **OK**.</span></span>
1. <span data-ttu-id="6f9c2-150">Analise a barra de mensagens.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-150">Review the message bar.</span></span> <span data-ttu-id="6f9c2-151">Deve haver mensagens denotando que a operação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-151">There should be messages denoting that the operation completed.</span></span>
1. <span data-ttu-id="6f9c2-152">Selecione **Funções > Recebimento de produtos** no Painel de Ações para atualizar a linha da ordem de compra e lançar um recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="6f9c2-152">Select **Functions > Product receipt** on the Action Pane to update the purchase order line and post a product receipt.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
