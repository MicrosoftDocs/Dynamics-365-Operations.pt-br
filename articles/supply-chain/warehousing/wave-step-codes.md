---
title: Códigos da etapa da onda
description: Este tópico fornece uma visão geral dos códigos da etapa da onda e como são usados.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 08b40c076e288592f6a4cd628b9acd8a2eaedb7e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998394"
---
# <a name="wave-step-codes"></a><span data-ttu-id="3b913-103">Códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3b913-103">Wave step codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b913-104">Os códigos da etapa da onda são códigos que os usuários podem configurar e usar para vincular instâncias específicas de métodos da onda a um modelo correspondente.</span><span class="sxs-lookup"><span data-stu-id="3b913-104">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="3b913-105">Os modelos incluem modelos para reabastecimento, transporte em contêineres, impressão de etiquetas, criação de carga e classificação.</span><span class="sxs-lookup"><span data-stu-id="3b913-105">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="3b913-106">Quando os códigos da etapa da onda não forem usados, os usuários deverão inserir texto livre para fazer referência a um modelo específico da instância de método da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-106">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="3b913-107">O texto livre é propenso a erros, pois os usuários devem verificar se o texto da etapa da onda adicionado para um método específico da etapa da onda em um modelo da onda corresponde exatamente ao texto da etapa da onda em modelo de destino.</span><span class="sxs-lookup"><span data-stu-id="3b913-107">Free text is prone to errors because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="3b913-108">Os códigos da etapa da onda para um tipo específico da etapa da onda são configurados em uma página separada.</span><span class="sxs-lookup"><span data-stu-id="3b913-108">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="3b913-109">Para cada instância de método da etapa da onda em um modelo da onda que requer um código da etapa da onda, o código da etapa da onda deve ser selecionado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="3b913-109">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="3b913-110">A seleção na lista suspensa substitui a entrada de texto livre e ajuda a reduzir o risco e o impacto de erros humanos.</span><span class="sxs-lookup"><span data-stu-id="3b913-110">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="3b913-111">Códigos de configuração são usados para vincular um método da etapa da onda a um modelo de destino da onda para o método.</span><span class="sxs-lookup"><span data-stu-id="3b913-111">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="3b913-112">O uso do recurso códigos de etapa da onda é opcional.</span><span class="sxs-lookup"><span data-stu-id="3b913-112">Use of the wave step codes feature is optional.</span></span> <span data-ttu-id="3b913-113">Ela é habilitada em toda a organização para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="3b913-113">It is enabled organization-wide for all legal entities.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="3b913-114">Demonstração de instalação</span><span class="sxs-lookup"><span data-stu-id="3b913-114">Setup demo</span></span> 

<span data-ttu-id="3b913-115">Para esta demonstração, os dados de demonstração devem ser instalados, e você deve usar a empresa de dados de demonstração **USMF** .</span><span class="sxs-lookup"><span data-stu-id="3b913-115">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="3b913-116">Habilitar códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3b913-116">Enable wave step codes</span></span>

<span data-ttu-id="3b913-117">Siga estas etapas para ativar o recurso de códigos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-117">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="3b913-118">Vá para **Gerenciamento de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="3b913-118">Go to **Feature Management**.</span></span>
2. <span data-ttu-id="3b913-119">Selecione para habilitar o recurso chamado **Código de Etapa de Onda para Toda a Organização**.</span><span class="sxs-lookup"><span data-stu-id="3b913-119">Select to enable the feature called **Organization-wide Wave Step Code**.</span></span>

<span data-ttu-id="3b913-120">Todos os textos livres da etapa da onda existentes em todas as entidades legais são atualizados para a nova estrutura.</span><span class="sxs-lookup"><span data-stu-id="3b913-120">All existing wave step free texts in all legal entities are upgraded to the new structure.</span></span> <span data-ttu-id="3b913-121">Depois que essa atualização for concluída para todas as entidades legais, o recurso será habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b913-121">After this upgrade is completed for all legal entities, then the feature is enabled.</span></span> <span data-ttu-id="3b913-122">Se o recurso não puder ser habilitado para uma ou mais entidades legais, o recurso não estará habilitado para nenhuma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="3b913-122">If the feature cannot be enabled for one or more legal entities, then the feature is not enabled for any legal entities.</span></span>

<span data-ttu-id="3b913-123">Durante a habilitação, serão feitas validações durante a atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="3b913-123">During the enablement, validations are done during the data upgrade.</span></span> <span data-ttu-id="3b913-124">Se a atualização falhar, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="3b913-124">If the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="3b913-125">Uma atualização pode falhar devido aos seguintes conflitos:</span><span class="sxs-lookup"><span data-stu-id="3b913-125">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="3b913-126">Existem textos livres da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-126">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="3b913-127">Existem Personalizações.</span><span class="sxs-lookup"><span data-stu-id="3b913-127">Customizations exist.</span></span>
- <span data-ttu-id="3b913-128">Um texto livre da etapa da onda que é associado a uma instância de método da etapa da onda não corresponde ao tipo de modelo esperado.</span><span class="sxs-lookup"><span data-stu-id="3b913-128">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="3b913-129">Depois de resolver os conflitos identificados durante validações, você pode tentar habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="3b913-129">After you've resolved any conflicts that are identified during the validations, you can retry to enable the feature.</span></span>

<span data-ttu-id="3b913-130">Quando o recurso for habilitado, a página **Códigos da etapa da onda** (**Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda**) ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="3b913-130">When the feature has been enabled, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="3b913-131">Esta página lista os códigos da etapa da onda que foram atualizados quando o recurso Código de Etapa de Onda para Toda a Organização for habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b913-131">This page lists the wave step codes that were upgraded when the Organization-wide Wave Step Code feature was enabled.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="3b913-132">Criar novos códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3b913-132">Create new wave step codes</span></span>

<span data-ttu-id="3b913-133">Você pode usar a página **Códigos da etapa da onda** para criar e excluir códigos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-133">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="3b913-134">Cada novo código da etapa e sua ID associada devem ser exclusivos em todos os tipos de etapa da onda e devem ser definidos para um tipo específico de etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-134">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="3b913-135">Aplicar códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3b913-135">Apply wave step codes</span></span>

<span data-ttu-id="3b913-136">Depois de definir os códigos da etapa da onda apropriados, eles podem ser aplicados aos métodos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-136">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="3b913-137">Para aplicar códigos da etapa da onda, vá para o modelo apropriado de destino.</span><span class="sxs-lookup"><span data-stu-id="3b913-137">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="3b913-138">Veja a seguir os modelos de destino para os quais os códigos da etapa da onda estão designados para apontar:</span><span class="sxs-lookup"><span data-stu-id="3b913-138">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="3b913-139">**Modelos de reabastecimento:** Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="3b913-139">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="3b913-140">**Modelos de criação de carga:** Gerenciamento de depósito \> Configuração \> Carga \> Modelos de criação de carga</span><span class="sxs-lookup"><span data-stu-id="3b913-140">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="3b913-141">**Modelos de classificação:** Gerenciamento de depósito \> Configuração \> Embalagem \> Modelos de classificação de saída</span><span class="sxs-lookup"><span data-stu-id="3b913-141">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="3b913-142">**Modelos de transporte em contêineres:** Gerenciamento de depósito \> Configuração \> Contêineres \> Modelos de criação de contêiner</span><span class="sxs-lookup"><span data-stu-id="3b913-142">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="3b913-143">**Modelos de impressão de etiquetas:** Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiquetas da onda</span><span class="sxs-lookup"><span data-stu-id="3b913-143">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="3b913-144">Os modelos nesta lista são aplicados quando referidos em um método da etapa da onda que está selecionado em um modelo da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-144">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="3b913-145">Quando o código da etapa da onda de um processo de método da onda em um modelo da onda corresponder ao código da etapa da onda em um dos tipos de modelos, o modelo será aplicado.</span><span class="sxs-lookup"><span data-stu-id="3b913-145">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="3b913-146">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="3b913-146">Sample scenario</span></span>

<span data-ttu-id="3b913-147">O procedimento a seguir ajuda a garantir que o método de reabastecimento criado seja aplicado para o modelo da onda.</span><span class="sxs-lookup"><span data-stu-id="3b913-147">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="3b913-148">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda** e crie um código da etapa da onda para o tipo **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="3b913-148">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="3b913-149">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento** e crie o modelos de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="3b913-149">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="3b913-150">No modelo de reabastecimento, selecione o código da etapa da onda criada para o tipo **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="3b913-150">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="3b913-151">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos da onda** e selecione o modelo da onda que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="3b913-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="3b913-152">No modelo, na guia rápida **Métodos**, selecione o método **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="3b913-152">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="3b913-153">No campo **Código da etapa da onda**, selecione o código da etapa da onda selecionada no modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="3b913-153">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>

<span data-ttu-id="3b913-154">Essas etapas são executadas para cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="3b913-154">You perform these steps for each legal entity.</span></span>
