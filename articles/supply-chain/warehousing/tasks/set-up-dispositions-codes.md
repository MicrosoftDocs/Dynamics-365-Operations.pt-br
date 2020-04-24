---
title: Configurar códigos de disposições
description: Este procedimento se concentra na configuração de um código de disposição que pode ser usado em um dispositivo móvel para o processo de recebimento da ordem de devolução.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56117445df82a8f8a69287ed1cdfca04de7abf5b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216910"
---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="1de4a-103">Configurar códigos de disposições</span><span class="sxs-lookup"><span data-stu-id="1de4a-103">Set up dispositions codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1de4a-104">Este procedimento se concentra na configuração de um código de disposição que pode ser usado em um dispositivo móvel para o processo de recebimento da ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="1de4a-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="1de4a-105">Códigos de disposição são um conjunto de regras que podem ser usadas quando itens são recebidos.</span><span class="sxs-lookup"><span data-stu-id="1de4a-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="1de4a-106">Por exemplo, quando um usuário de trabalho utiliza um dispositivo móvel para receber itens que foram danificados, o usuário deve escanear um código de disposição para itens danificados.</span><span class="sxs-lookup"><span data-stu-id="1de4a-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="1de4a-107">O status de estoque dos bens recebidos, o modelo de trabalho, e a diretiva de localização podem ser determinados a partir do código de disposição escaneado.</span><span class="sxs-lookup"><span data-stu-id="1de4a-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="1de4a-108">Para os processos de recebimento da ordem de compra e de relatório de ordem de produção como concluída, o uso de um código de disposição é opcional.</span><span class="sxs-lookup"><span data-stu-id="1de4a-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="1de4a-109">Para o processo de recebimento de devolução da ordem de venda, se os itens forem registrados utilizando um dispositivo móvel, o uso do código de disposição é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="1de4a-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="1de4a-110">Esse guia foi criado usando a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="1de4a-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="1de4a-111">Esse procedimento é destinado ao gerente do depósito.</span><span class="sxs-lookup"><span data-stu-id="1de4a-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="1de4a-112">Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Códigos de disposição.</span><span class="sxs-lookup"><span data-stu-id="1de4a-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="1de4a-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1de4a-113">Click New.</span></span>
    * <span data-ttu-id="1de4a-114">Crie um novo código de disposição a ser usado para devoluções de clientes.</span><span class="sxs-lookup"><span data-stu-id="1de4a-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="1de4a-115">No campo Código de descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1de4a-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="1de4a-116">No campo Status do estoque, selecione um status de estoque onde exista bloqueio de estoque.</span><span class="sxs-lookup"><span data-stu-id="1de4a-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="1de4a-117">Se você estiver usando USMF, selecione 'Bloqueio'.</span><span class="sxs-lookup"><span data-stu-id="1de4a-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="1de4a-118">Você pode adicionar um status de estoque ao código de disposição para substituir o status padrão que está nas linhas da ordem.</span><span class="sxs-lookup"><span data-stu-id="1de4a-118">You can add an inventory status to the disposition code to override the default status that's on the order lines.</span></span>  
5. <span data-ttu-id="1de4a-119">No campo Modelo de trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1de4a-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="1de4a-120">Opcional: Selecione um código de modelo de trabalho associado a uma ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="1de4a-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="1de4a-121">Se nenhum valor for fornecido, o modelo de trabalho será resolvido usando as regras padrão configuradas no sistema.</span><span class="sxs-lookup"><span data-stu-id="1de4a-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="1de4a-122">Selecionar um modelo de trabalho irá limitar os processos para os quais este código de disposição pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="1de4a-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="1de4a-123">Por exemplo, se um código de disposição tem um modelo de trabalho com uma ordem de trabalho do tipo ordem de compra, ele não poderá ser usado para registrar os itens que são devolvidos por clientes.</span><span class="sxs-lookup"><span data-stu-id="1de4a-123">For example, if a disposition code has a work template with a work order of type purchase order, it can't be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="1de4a-124">No campo Código de disposição de devolução, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1de4a-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="1de4a-125">O código de disposição de devolução determina o restante do processo da ordem de devolução para os itens registrados.</span><span class="sxs-lookup"><span data-stu-id="1de4a-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="1de4a-126">Neste exemplo, o cliente deve receber uma nota de crédito.</span><span class="sxs-lookup"><span data-stu-id="1de4a-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="1de4a-127">Adicione um código de disposição de devoluções que contenha uma ação de Crédito.</span><span class="sxs-lookup"><span data-stu-id="1de4a-127">Add a returns disposition code that contains an action Credit.</span></span>  

