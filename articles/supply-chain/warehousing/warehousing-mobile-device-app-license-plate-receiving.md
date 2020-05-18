---
title: Recebimento da placa de licença por meio do aplicativo do depósito
description: Este tópico explica como configurar o aplicativo de depósito para oferecer suporte ao uso de um processo de recebimento de placa de licença para receber um estoque físico.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346367"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a><span data-ttu-id="ca464-103">Recebimento da placa de licença por meio do aplicativo do depósito</span><span class="sxs-lookup"><span data-stu-id="ca464-103">License plate receiving via the warehousing app</span></span>

<span data-ttu-id="ca464-104">Este tópico explica como configurar o aplicativo de depósito para oferecer suporte ao uso de um processo de recebimento de placa de licença para receber um estoque físico.</span><span class="sxs-lookup"><span data-stu-id="ca464-104">This topic explains how to set up the warehousing app so that it supports using a license plate receiving process to receive physical inventory.</span></span>

<span data-ttu-id="ca464-105">Você pode usar esta funcionalidade para registrar rapidamente o recebimento de um estoque de entrada relacionado a um aviso de embarque (ASN).</span><span class="sxs-lookup"><span data-stu-id="ca464-105">You can use this functionality to quickly record the receipt of inbound inventory that is related to an advance ship notice (ASN).</span></span> <span data-ttu-id="ca464-106">O sistema automaticamente cria um ASN quando os processos de gerenciamento do depósito forem usados para remeter uma ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="ca464-106">The system automatically creates an ASN when warehouse management processes are used to ship a transfer order.</span></span> <span data-ttu-id="ca464-107">Para o processo da ordem de compra, um ASN pode ser registrado manualmente ou importado automaticamente usando um processo de entidade de dados do ASN de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca464-107">For the purchase order process, an ASN can be manually recorded, or it can be automatically imported by using an inbound ASN data entity process.</span></span>

<span data-ttu-id="ca464-108">Os dados do ASN são vinculados a cargas e remessas por meio de *estruturas de embalagem*, nas quais os paletes (placas de licença pai) podem conter caixas (placas de licença aninhadas).</span><span class="sxs-lookup"><span data-stu-id="ca464-108">The ASN data is linked to loads and shipments via the *packing structures*, where pallets (parent license plates) can contain cases (nested license plates).</span></span>

> [!NOTE]
> <span data-ttu-id="ca464-109">Para reduzir o número de transações de estoque quando estruturas de embalagem com placas de licença aninhadas forem usadas, o sistema registra o estoque físico disponível na placa de licença pai.</span><span class="sxs-lookup"><span data-stu-id="ca464-109">To reduce the number of inventory transactions when packing structures that have nested license plates are used, the system records the physical on-hand inventory on the parent license plate.</span></span> <span data-ttu-id="ca464-110">Para acionar a movimentação do estoque físico disponível da placa de licença pai para as placas de licença aninhadas, com base nos dados de estrutura de embalagem, o dispositivo móvel deve fornecer um item de menu baseado no processo de criação de trabalho *Empacotar em placas de licença aninhadas*.</span><span class="sxs-lookup"><span data-stu-id="ca464-110">To trigger the movement of the physical on-hand inventory from the parent license plate to the nested license plates, based on the packing structure data, the mobile device must provide a menu item that is based on the *Pack to nested license plates* work creation process.</span></span>

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a><span data-ttu-id="ca464-111">Mostrar ou ignorar a página de resumo do recebimento</span><span class="sxs-lookup"><span data-stu-id="ca464-111">Show or skip the receiving summary page</span></span>

<span data-ttu-id="ca464-112">Você pode usar o recurso *Controlar a exibição de uma página de resumo do recebimento em dispositivos móveis* para usar um fluxo de aplicativo adicional detalhado do depósito como parte do processo de recebimento da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="ca464-112">You can use the *Control whether to display a receiving summary page on mobile devices* feature to take advantage of an additional detailed warehousing app flow as part of the license plate receiving process.</span></span>

<span data-ttu-id="ca464-113">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="ca464-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="ca464-114">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="ca464-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="ca464-115">No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="ca464-115">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="ca464-116">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="ca464-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ca464-117">**Nome do recurso:** *Controlar a exibição de uma página de resumo do recebimento em dispositivos móveis*</span><span class="sxs-lookup"><span data-stu-id="ca464-117">**Feature name:** *Control whether to display a receiving summary page on mobile devices*</span></span>

<span data-ttu-id="ca464-118">Quando este recurso estiver ativado, os itens do menu do dispositivo móvel do recebimento da placa de licença ou do recebimento e armazenamento da placa de licença fornecerão uma configuração para **Exibir página de resumo do recebimento**.</span><span class="sxs-lookup"><span data-stu-id="ca464-118">When this feature is turned on, mobile device menu items for license plate receiving or license plate receiving and put-away will provide a **Display receiving summary page** setting.</span></span> <span data-ttu-id="ca464-119">Essa configuração tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ca464-119">This setting has the following options:</span></span>

- <span data-ttu-id="ca464-120">**Exibir um resumo detalhado** – Durante o recebimento da placa de licença, os trabalhadores verão uma página extra que mostra as informações completas do ASN.</span><span class="sxs-lookup"><span data-stu-id="ca464-120">**Display a detailed summary** – During license plate receiving, workers will see an extra page that shows the full ASN information.</span></span>
- <span data-ttu-id="ca464-121">**Ignorar o resumo** – Os funcionários não verão as informações completas do ASN.</span><span class="sxs-lookup"><span data-stu-id="ca464-121">**Skip the summary** – Workers won't see the full ASN information.</span></span> <span data-ttu-id="ca464-122">Os trabalhadores de depósito também não poderão definir um código de disposição nem adicionar exceções durante o processo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="ca464-122">Warehouse workers also won't be able to set a disposition code or add exceptions during the receiving process.</span></span>

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a><span data-ttu-id="ca464-123">Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino</span><span class="sxs-lookup"><span data-stu-id="ca464-123">Prevent transfer order–shipped license plates from being used at warehouses other than the destination warehouse</span></span>

<span data-ttu-id="ca464-124">Um processo de recebimento de placa de licença não pode ser usado se o ASN contiver uma ID de placa de licença já existente e dados físicos disponíveis em um local de depósito diferente do local de depósito no qual o registro da placa de licença está sendo realizado.</span><span class="sxs-lookup"><span data-stu-id="ca464-124">A license plate receiving process can't be used if an ASN contains a license plate ID that already exists and has physical on-hand data at a warehouse location other than the warehouse location where the license plate registration is occurring.</span></span>

<span data-ttu-id="ca464-125">Para cenários de ordem de transferência nos quais o depósito de trânsito não rastreia placas de licença (e, portanto, não rastreia o estoque físico disponível por placa de licença), é possível usar o recurso *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino* para impedir atualizações de placas de licença físicas disponíveis que ainda estão em trânsito.</span><span class="sxs-lookup"><span data-stu-id="ca464-125">For transfer order scenarios where the transit warehouse doesn't track license plates (and therefore also doesn't track physical on-hand inventory per license plate), you can use the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature to prevent physical on-hand updates of license plates that are in transit.</span></span>

<span data-ttu-id="ca464-126">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="ca464-126">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="ca464-127">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="ca464-127">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="ca464-128">No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="ca464-128">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="ca464-129">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="ca464-129">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ca464-130">**Nome do recurso:** *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino*</span><span class="sxs-lookup"><span data-stu-id="ca464-130">**Feature name:** *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse*</span></span>

<span data-ttu-id="ca464-131">Para gerenciar a funcionalidade quando esse recurso estiver disponível, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ca464-131">To manage the functionality when this feature is available, follow these steps.</span></span>

1. <span data-ttu-id="ca464-132">Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="ca464-132">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="ca464-133">Na guia **Geral** no FastTab **Placas de licença**, defina o campo **Política da placa de licença do depósito de trânsito** com um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ca464-133">On the **General** tab, on the **License plates** FastTab, set the **Transit warehouse license plate policy** field to one of the following values:</span></span>

    - <span data-ttu-id="ca464-134">**Permitir reutilização de placa de licença não rastreada** – O sistema funciona da mesma forma quando o recurso *Impedir que as placas de licença remetidas da ordem de transferência sejam usadas em depósitos diferentes do depósito de destino* não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ca464-134">**Allow reuse of non-tracked license plate** – The system works the same way that it works when the *Prevent transfer order shipped license plates from being used on other warehouses than the destination warehouse* feature isn't available.</span></span> <span data-ttu-id="ca464-135">Esse valor é a configuração padrão quando você ativa o recurso pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ca464-135">This value is the default setting when you first activate the feature.</span></span>
    - <span data-ttu-id="ca464-136">**Impedir a reutilização de placa de licença não rastreada** – Somente as atualizações disponíveis relacionadas a uma placa de licença remetida serão permitidas no depósito de destino até que a ordem de transferência tenha sido recebida.</span><span class="sxs-lookup"><span data-stu-id="ca464-136">**Prevent reuse of non-tracked license plate** – Only on-hand updates that are related to a shipped license plate will be allowed at the destination warehouse until the transfer order has been received.</span></span>

## <a name="more-information"></a><span data-ttu-id="ca464-137">Mais informações</span><span class="sxs-lookup"><span data-stu-id="ca464-137">More information</span></span>

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

<span data-ttu-id="ca464-138">Para obter mais informações sobre itens do menu do dispositivo móvel, consulte [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="ca464-138">For more information about mobile device menu items, see [Set up mobile devices for warehouse work](configure-mobile-devices-warehouse.md).</span></span>
