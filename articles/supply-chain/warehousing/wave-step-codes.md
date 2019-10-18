---
title: Códigos da etapa da onda
description: Este tópico fornece uma visão geral dos códigos da etapa da onda e como são usados.
author: josaw1
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0f89c6098db9e2e3a9aa4ee3666e4b9ae608f054
ms.sourcegitcommit: d8f1135cdbc2deca70bc4b2805a0519253c9a31f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "1992348"
---
# <a name="wave-step-codes"></a><span data-ttu-id="3a188-103">Códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3a188-103">Wave step codes</span></span>

[!include [banner](../includes/preview-banner.md)]
[!include [banner](../includes/banner.md)]

## <a name="about-wave-step-codes"></a><span data-ttu-id="3a188-104">Sobre códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3a188-104">About wave step codes</span></span>

<span data-ttu-id="3a188-105">Os códigos da etapa da onda são códigos que os usuários podem configurar e usar para vincular instâncias específicas de métodos da onda a um modelo correspondente.</span><span class="sxs-lookup"><span data-stu-id="3a188-105">Wave step codes are codes that users can set up and use to link specific instances of wave methods to a corresponding template.</span></span> <span data-ttu-id="3a188-106">Os modelos incluem modelos para reabastecimento, transporte em contêineres, impressão de etiquetas, criação de carga e classificação.</span><span class="sxs-lookup"><span data-stu-id="3a188-106">The templates include templates for replenishment, containerization, label printing, load building, and sorting.</span></span>

<span data-ttu-id="3a188-107">Quando os códigos da etapa da onda não forem usados, os usuários deverão inserir texto livre para fazer referência a um modelo específico da instância de método da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-107">When wave step codes aren't used, users must enter free text to reference a specific template from the wave method instance.</span></span> <span data-ttu-id="3a188-108">O texto livre é propenso a erros, pois os usuários devem verificar se o texto da etapa da onda adicionado para um método específico da etapa da onda em um modelo da onda corresponde exatamente ao texto da etapa da onda em modelo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a188-108">Free text is prone to error, because users must make sure that the wave step text that they add for a specific wave step method in a wave template exactly matches the wave step text in the target template.</span></span>

<span data-ttu-id="3a188-109">Os códigos da etapa da onda para um tipo específico da etapa da onda são configurados em uma página separada.</span><span class="sxs-lookup"><span data-stu-id="3a188-109">Wave step codes for a specific wave step type are set up on a separate page.</span></span> <span data-ttu-id="3a188-110">Para cada instância de método da etapa da onda em um modelo da onda que requer um código da etapa da onda, o código da etapa da onda deve ser selecionado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="3a188-110">For every wave step method instance in a wave template that requires a wave step code, the wave step code must be selected in a drop-down list.</span></span> <span data-ttu-id="3a188-111">A seleção na lista suspensa substitui a entrada de texto livre e ajuda a reduzir o risco e o impacto de erros humanos.</span><span class="sxs-lookup"><span data-stu-id="3a188-111">Selection in a drop-down list replaces free text entry and helps reduce the risk and impact of human error.</span></span> <span data-ttu-id="3a188-112">Códigos de configuração são usados para vincular um método da etapa da onda a um modelo de destino da onda para o método.</span><span class="sxs-lookup"><span data-stu-id="3a188-112">Setup codes are used to link a wave step method in a wave template to a target template for the method.</span></span>

> [!NOTE]
> <span data-ttu-id="3a188-113">O uso do recurso de códigos da etapa da onda é opcional, e a aceitação é por entidade legal.</span><span class="sxs-lookup"><span data-stu-id="3a188-113">Use of the wave step codes feature is optional, and uptake is per legal entity.</span></span> <span data-ttu-id="3a188-114">Portanto, se uma pessoa jurídica específica usar o recurso, todos os códigos existentes de etapa da onda na entidade legal serão atualizados para a nova estrutura.</span><span class="sxs-lookup"><span data-stu-id="3a188-114">Therefore, if a specific legal entity uses the feature, all existing wave step codes in that legal entity are upgraded to the new structure.</span></span>

## <a name="setup-demo"></a><span data-ttu-id="3a188-115">Demonstração de instalação</span><span class="sxs-lookup"><span data-stu-id="3a188-115">Setup demo</span></span> 

<span data-ttu-id="3a188-116">Para esta demonstração, os dados de demonstração devem ser instalados, e você deve usar a empresa de dados de demonstração **USMF** .</span><span class="sxs-lookup"><span data-stu-id="3a188-116">For this demo, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="enable-wave-step-codes"></a><span data-ttu-id="3a188-117">Habilitar códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3a188-117">Enable wave step codes</span></span>

<span data-ttu-id="3a188-118">Siga estas etapas para ativar o recurso de códigos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-118">Follow these steps to turn on the wave step codes feature.</span></span>

1. <span data-ttu-id="3a188-119">Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="3a188-119">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
2. <span data-ttu-id="3a188-120">Na guia **Geral**, na guia rápida **Processamento da onda** , defina a opção **Habilitar códigos da etapa da onda** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3a188-120">On the **General** tab, on the **Wave processing** FastTab, set the **Enable wave step codes** option to **Yes**.</span></span>

<span data-ttu-id="3a188-121">Todos os textos livres da etapa da onda existentes são atualizados para a nova estrutura.</span><span class="sxs-lookup"><span data-stu-id="3a188-121">All existing wave step free texts are upgraded to the new structure.</span></span> <span data-ttu-id="3a188-122">Depois que essa atualização for executada para uma entidade legal, a opção **Habilitar códigos da etapa da onda** não estará mais disponível na página **Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="3a188-122">After this upgrade is completed for a legal entity, the **Enable wave step codes** option is no longer available on the **Warehouse management parameters** page.</span></span>

<span data-ttu-id="3a188-123">Validações são feitas durante a atualização, e, se a atualização falhar, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="3a188-123">Validations are done during the upgrade, and if the upgrade fails, you receive an error message.</span></span> <span data-ttu-id="3a188-124">Uma atualização pode falhar devido aos seguintes conflitos:</span><span class="sxs-lookup"><span data-stu-id="3a188-124">An upgrade might fail because of the following conflicts:</span></span>

- <span data-ttu-id="3a188-125">Existem textos livres da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-125">Duplicate wave step free texts exist.</span></span>
- <span data-ttu-id="3a188-126">Existem Personalizações.</span><span class="sxs-lookup"><span data-stu-id="3a188-126">Customizations exist.</span></span>
- <span data-ttu-id="3a188-127">Um texto livre da etapa da onda que é associado a uma instância de método da etapa da onda não corresponde ao tipo de modelo esperado.</span><span class="sxs-lookup"><span data-stu-id="3a188-127">A wave step free text that is associated with a wave step method instance doesn't match the expected template type.</span></span>

<span data-ttu-id="3a188-128">Depois de resolver os conflitos identificados durante validações, você pode executar novamente o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="3a188-128">After you've resolved any conflicts that are identified during the validations, you can rerun the upgrade process.</span></span>

<span data-ttu-id="3a188-129">Quando a atualização for bem-sucedida, a página **Códigos da etapa da onda** (**Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda**) será disponibilizada.</span><span class="sxs-lookup"><span data-stu-id="3a188-129">When the upgrade succeeds, the **Wave step codes** page (**Warehouse management \> Setup \> Waves \> Wave step codes**) becomes available.</span></span> <span data-ttu-id="3a188-130">Esta página lista os códigos da etapa da onda que foram atualizados quando o recurso de códigos da etapa da onda foi ativado.</span><span class="sxs-lookup"><span data-stu-id="3a188-130">This page lists the wave step codes that were upgraded when the wave step codes feature was turned on.</span></span>

### <a name="create-new-wave-step-codes"></a><span data-ttu-id="3a188-131">Criar novos códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3a188-131">Create new wave step codes</span></span>

<span data-ttu-id="3a188-132">Você pode usar a página **Códigos da etapa da onda** para criar e excluir códigos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-132">You can use the **Wave step codes** page to create and delete wave step codes.</span></span>

<span data-ttu-id="3a188-133">Cada novo código da etapa e sua ID associada devem ser exclusivos em todos os tipos de etapa da onda e devem ser definidos para um tipo específico de etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-133">Every new wave step code and its associated ID must be unique across all wave step types, and they must be defined for a specific wave step type.</span></span>

### <a name="apply-wave-step-codes"></a><span data-ttu-id="3a188-134">Aplicar códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="3a188-134">Apply wave step codes</span></span>

<span data-ttu-id="3a188-135">Depois de definir os códigos da etapa da onda apropriados, eles podem ser aplicados aos métodos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-135">After you've defined the appropriate wave step codes, they can be applied to the wave process methods.</span></span>

<span data-ttu-id="3a188-136">Para aplicar códigos da etapa da onda, vá para o modelo apropriado de destino.</span><span class="sxs-lookup"><span data-stu-id="3a188-136">To apply wave step codes, go to the appropriate target template.</span></span> <span data-ttu-id="3a188-137">Veja a seguir os modelos de destino para os quais os códigos da etapa da onda estão designados para apontar:</span><span class="sxs-lookup"><span data-stu-id="3a188-137">Here are the target templates that the wave step codes are designated to point to:</span></span>

- <span data-ttu-id="3a188-138">**Modelos de reabastecimento:** Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="3a188-138">**Replenishment templates:** Warehouse management \> Setup \> Replenishment \> Replenishment templates</span></span>
- <span data-ttu-id="3a188-139">**Modelos de criação de carga:** Gerenciamento de depósito \> Configuração \> Carga \> Modelos de criação de carga</span><span class="sxs-lookup"><span data-stu-id="3a188-139">**Load build templates:** Warehouse management \> Setup \> Load \> Load build templates</span></span>
- <span data-ttu-id="3a188-140">**Modelos de classificação:** Gerenciamento de depósito \> Configuração \> Embalagem \> Modelos de classificação de saída</span><span class="sxs-lookup"><span data-stu-id="3a188-140">**Sort templates:** Warehouse management \> Setup \> Packing \> Outbound sorting templates</span></span>
- <span data-ttu-id="3a188-141">**Modelos de transporte em contêineres:** Gerenciamento de depósito \> Configuração \> Contêineres \> Modelos de criação de contêiner</span><span class="sxs-lookup"><span data-stu-id="3a188-141">**Containerization templates:** Warehouse management \> Setup \> Containers \> Container build templates</span></span>
- <span data-ttu-id="3a188-142">**Modelos de impressão de etiquetas:** Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiquetas da onda</span><span class="sxs-lookup"><span data-stu-id="3a188-142">**Label printing templates:** Warehouse management \> Setup \> Document routing \> Wave label templates</span></span>

<span data-ttu-id="3a188-143">Os modelos nesta lista são aplicados quando referidos em um método da etapa da onda que está selecionado em um modelo da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-143">The templates in this list are applied when they are referenced from a wave process method that is selected in a wave template.</span></span> <span data-ttu-id="3a188-144">Quando o código da etapa da onda de um processo de método da onda em um modelo da onda corresponder ao código da etapa da onda em um dos tipos de modelos, o modelo será aplicado.</span><span class="sxs-lookup"><span data-stu-id="3a188-144">When the wave step code on a wave process method in a wave template matches the wave step code in one of the templates types, the template is applied.</span></span>

### <a name="sample-scenario"></a><span data-ttu-id="3a188-145">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="3a188-145">Sample scenario</span></span>

<span data-ttu-id="3a188-146">O procedimento a seguir ajuda a garantir que o método de reabastecimento criado seja aplicado para o modelo da onda.</span><span class="sxs-lookup"><span data-stu-id="3a188-146">The following procedure helps guarantee that the replenishment template that you created will be applied for the wave template.</span></span>

1. <span data-ttu-id="3a188-147">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda** e crie um código da etapa da onda para o tipo **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="3a188-147">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**, and create a wave step code for the **Replenishment** type.</span></span>
2. <span data-ttu-id="3a188-148">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento** e crie o modelos de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="3a188-148">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**, and create a replenishment template.</span></span>
3. <span data-ttu-id="3a188-149">No modelo de reabastecimento, selecione o código da etapa da onda criada para o tipo **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="3a188-149">In the replenishment template, select the wave step code that you created for the **Replenishment** type.</span></span>
4. <span data-ttu-id="3a188-150">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos da onda** e selecione o modelo da onda que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="3a188-150">Go to **Warehouse management \> Setup \> Waves \> Wave templates**, and select the wave template that you intend to use.</span></span>
5. <span data-ttu-id="3a188-151">No modelo, na guia rápida **Métodos**, selecione o método **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="3a188-151">In the template, on the **Methods** FastTab, select the **Replenishment** method.</span></span>
6. <span data-ttu-id="3a188-152">No campo **Código da etapa da onda**, selecione o código da etapa da onda selecionada no modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="3a188-152">In the **Wave step code** field, select the wave step code that you selected in the replenishment template.</span></span>
