---
title: Configurar livros fiscais
description: Este tópico explica como configurar eventos SPED-Reinf usando Livros fiscais no Microsoft Dynamics 365 Finance para o Brasil.
author: sndray
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: f00cdcdaf33990995f3241b85a46183b37b7c80a
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117023"
---
# <a name="set-up-fiscal-books"></a><span data-ttu-id="4c581-103">Configurar livros fiscais</span><span class="sxs-lookup"><span data-stu-id="4c581-103">Set up fiscal books</span></span>

<span data-ttu-id="4c581-104">Este tópico explica como configurar o módulo **Livros fiscais** para gerar e emitir eventos para as autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="4c581-104">This topic explains how to set up the **Fiscal books** module to generate and issue events to the tax authorities.</span></span> 

## <a name="set-up-service-types"></a><span data-ttu-id="4c581-105">Configurar tipos de serviço</span><span class="sxs-lookup"><span data-stu-id="4c581-105">Set up service types</span></span>

<span data-ttu-id="4c581-106">A tabela de tipo de serviço representa a tabela 06.</span><span class="sxs-lookup"><span data-stu-id="4c581-106">The service type table represents table 06.</span></span> <span data-ttu-id="4c581-107">As autoridades fiscais estabeleceram esta tabela para classificar os serviços que são fornecidos, com base na atribuição de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c581-107">The tax authorities have established this table to classify the services that are provided, based on the assignment of labor.</span></span> <span data-ttu-id="4c581-108">É possível consultar uma lista detalhada dos valores disponíveis no site do sistema de registros digitais públicos (SPED).</span><span class="sxs-lookup"><span data-stu-id="4c581-108">A detailed list of available values is available on the public digital bookkeeping system (SPED) website.</span></span>

1. <span data-ttu-id="4c581-109">Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Tipos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="4c581-109">Go to **Fiscal books** \> **Setup** \> **SPED Reinf** \> **Service types**.</span></span>
2. <span data-ttu-id="4c581-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4c581-110">Select **New**.</span></span>
3. <span data-ttu-id="4c581-111">Insira um código de classificação que foi estabelecido pelas autoridades fiscais e digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="4c581-111">Enter a classification code that has been established by the tax authorities, and then enter a description.</span></span>

    ![Página Tipos de serviço](media/bra-service-type-setup.png)

4. <span data-ttu-id="4c581-113">Depois que a lista de tipos de serviço for criada, eles devem ser atribuídos a códigos de serviço.</span><span class="sxs-lookup"><span data-stu-id="4c581-113">After the list of service types is created, the service types must be assigned to service codes.</span></span> <span data-ttu-id="4c581-114">Acesse **Gerenciamento de inventário** \> **Configuração** \> **Informações fiscais** \> **Código de serviço**, e então, para cada serviço, atribua o tipo de serviço relacionado.</span><span class="sxs-lookup"><span data-stu-id="4c581-114">Go to **Inventory management** \> **Setup** \> **Fiscal information** \> **Service code**, and then, for each service, assign the related service type.</span></span>

## <a name="set-up-tax-classification-codes"></a><span data-ttu-id="4c581-115">Configurar códigos de classificação de imposto</span><span class="sxs-lookup"><span data-stu-id="4c581-115">Set up tax classification codes</span></span>

1. <span data-ttu-id="4c581-116">Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Códigos de classificação fiscal**.</span><span class="sxs-lookup"><span data-stu-id="4c581-116">Go to **Fiscal books** \> **Setup** \> **SPED Reinf** \> **Tax classification codes**.</span></span>
2. <span data-ttu-id="4c581-117">Insira os tipos de classificação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4c581-117">Enter the available classification types.</span></span>

![Página Códigos de classificação fiscal](media/bra-tax-classification-codes.png)

<span data-ttu-id="4c581-119">Essas informações são atribuídas à organização fiscal e podem ser encontradas na FastTab **Geral** da página **Organização fiscal**, (**Livros fiscais \> Configuração \> Organização fiscal**).</span><span class="sxs-lookup"><span data-stu-id="4c581-119">This information is assigned to the fiscal organization and can be found on the **General** FastTab of the **Fiscal organization** page (**Fiscal books \> Setup \> Fiscal organization**).</span></span>

![Página Organização fiscal](media/bra-fiscal-organization-setup.png)

## <a name="set-up-codes-explanation-suspension"></a><span data-ttu-id="4c581-121">Configurar suspensão da explicação de códigos</span><span class="sxs-lookup"><span data-stu-id="4c581-121">Set up codes explanation suspension</span></span>

1. <span data-ttu-id="4c581-122">Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Suspensão de explicação dos códigos**.</span><span class="sxs-lookup"><span data-stu-id="4c581-122">Go to **Fiscal books** \> **Setup** \> **SPED Reinf** \> **Codes explanation suspension**.</span></span>
2. <span data-ttu-id="4c581-123">Configure os códigos que são usados no evento R-1070 quando a suspensão de retenção for aplicável.</span><span class="sxs-lookup"><span data-stu-id="4c581-123">Set up the codes that are used in event R-1070 when suspension of withholding applies.</span></span> <span data-ttu-id="4c581-124">Esses códigos são atribuídos na página **Processo administrativo e judicial** (**Livros fiscais** \> **Periódico** \> **SPED Reinf** \> **Processo administrativo e judicial**).</span><span class="sxs-lookup"><span data-stu-id="4c581-124">These codes are assigned on the **Administrative and judicial process** page (**Fiscal books** \> **Periodic** \> **SPED Reinf** \> **Administrative and judicial process**).</span></span>

![Página Suspensão de explicação dos códigos](media/bra-codes-explanation-suspension.png)

## <a name="set-up-acquisition-type-determination"></a><span data-ttu-id="4c581-126">Configurar a determinação do tipo de aquisição</span><span class="sxs-lookup"><span data-stu-id="4c581-126">Set up acquisition type determination</span></span>

<span data-ttu-id="4c581-127">Esta configuração é usada para determinar o tipo de aquisição agrícola dos documentos fiscais recebidos que são relatados na marca **indAquis** para o evento R-2055.</span><span class="sxs-lookup"><span data-stu-id="4c581-127">This setup is used to determine the agriculture acquisition type of incoming fiscal documents that are reported in the **indAquis** tag for event R-2055.</span></span> 

1. <span data-ttu-id="4c581-128">Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Aquisição de produção rural**.</span><span class="sxs-lookup"><span data-stu-id="4c581-128">Go to **Fiscal books** \> **Setup** \> **SPED Reinf** \> **Acquisition of rural production**.</span></span>
2. <span data-ttu-id="4c581-129">Define a classificação dos documentos fiscais, com base nos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="4c581-129">Define the classification of fiscal documents, based on the following criteria:</span></span>

    - <span data-ttu-id="4c581-130">**Conta do fornecedor:** Todos, grupo ou tabela</span><span class="sxs-lookup"><span data-stu-id="4c581-130">**Vendor account:** All, group, or table</span></span>
    - <span data-ttu-id="4c581-131">**CFOP:** Todos, grupo ou tabela</span><span class="sxs-lookup"><span data-stu-id="4c581-131">**CFOP:** All, group, or table</span></span>
    - <span data-ttu-id="4c581-132">**Classificação fiscal**</span><span class="sxs-lookup"><span data-stu-id="4c581-132">**Fiscal classification**</span></span>

## <a name="set-up-gilrat-and-senar-taxes"></a><span data-ttu-id="4c581-133">Configurar impostos GILRAT e SENAR</span><span class="sxs-lookup"><span data-stu-id="4c581-133">Set up GILRAT and SENAR taxes</span></span>

<span data-ttu-id="4c581-134">**GILRAT**: a contribuição fiscal do grau de incidência de Deficiência de trabalho resultante de riscos ambientas da profissão.</span><span class="sxs-lookup"><span data-stu-id="4c581-134">**GILRAT**: The tax contribution of the degree of incidence of Labor disability resulting from occupational environmental risks.</span></span>
<span data-ttu-id="4c581-135">**SENAR**: a contribuição fiscal relacionada à produção rural.</span><span class="sxs-lookup"><span data-stu-id="4c581-135">**SENAR**: The tax contribution related to rural production.</span></span>

1. <span data-ttu-id="4c581-136">Acesse **Livros fiscais** \> **Configuração** \> **SPED Reinf** \> **Códigos do imposto GILRAT** ou **Códigos do imposto SENAR**.</span><span class="sxs-lookup"><span data-stu-id="4c581-136">Go to **Fiscal books** \> **Setup** \> **SPED Reinf** \> **GILRAT tax codes** or **SENAR tax codes**.</span></span>
2. <span data-ttu-id="4c581-137">Identifique os códigos de imposto de vendas que são usados para representas impostos GILRAT e SENAR.</span><span class="sxs-lookup"><span data-stu-id="4c581-137">Identify the sales tax codes that are used to represent GILRAT and SENAR taxes.</span></span> <span data-ttu-id="4c581-138">Na definição dos códigos de imposto de vendas, o tipo de imposto deve ser definido como **Outro**.</span><span class="sxs-lookup"><span data-stu-id="4c581-138">In the definition of the sales tax codes, the tax type should be set to **Other**.</span></span> <span data-ttu-id="4c581-139">O valor desses impostos é usado nas marcas **vlrRatDescPR** e **vlrSenarDesc** para o evento R-2055.</span><span class="sxs-lookup"><span data-stu-id="4c581-139">The amount of these taxes is used in the **vlrRatDescPR** and **vlrSenarDesc** tags for event R-2055.</span></span>

## <a name="vendor-setup"></a><span data-ttu-id="4c581-140">Configuração do fornecedor</span><span class="sxs-lookup"><span data-stu-id="4c581-140">Vendor setup</span></span>

- <span data-ttu-id="4c581-141">Acesse **Contas a pagar** \> **Fornecedores** \> **Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="4c581-141">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
- <span data-ttu-id="4c581-142">Selecione um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4c581-142">Select a vendor.</span></span>
- <span data-ttu-id="4c581-143">Na guia **Informações fiscais**, configure **Taxação Reinf sobre folha de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="4c581-143">On the **Fiscal information** tab, set up  **Reinf taxation over payroll**.</span></span> <span data-ttu-id="4c581-144">Este novo atributo determina o tipo de taxação, pois essas informações são necessárias na marca **indOpcCP** para o evento R-2055.</span><span class="sxs-lookup"><span data-stu-id="4c581-144">This new attribute determines the type of taxation, because this information is required in the **indOpcCP** tag for event R-2055.</span></span>

## <a name="set-up-fiscal-books-parameters"></a><span data-ttu-id="4c581-145">Configurar parâmetros dos livros fiscais</span><span class="sxs-lookup"><span data-stu-id="4c581-145">Set up Fiscal books parameters</span></span>

1. <span data-ttu-id="4c581-146">Acesse **Livros fiscais** > **Parâmetros das extensões de obrigações fiscais** > **SPED Reinf** > **Parâmetros SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="4c581-146">Go to **Fiscal books** > **Tax statements parameters** > **SPED Reinf** > **SPED Reinf parameters**.</span></span>
2. <span data-ttu-id="4c581-147">Na guia **Geral**, selecione **Versão SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="4c581-147">On the **General** tab, select **SPED Reinf version**.</span></span>
3. <span data-ttu-id="4c581-148">Selecione o tipo de ambiente e o status da organização fiscal.</span><span class="sxs-lookup"><span data-stu-id="4c581-148">Select the environment type and the status of the fiscal organization.</span></span>
4. <span data-ttu-id="4c581-149">Acesse **Livros fiscais** > **Configuração** > **Parâmetros dos livros fiscais**.</span><span class="sxs-lookup"><span data-stu-id="4c581-149">Go to **Fiscal books** > **Setup** > **Fiscal books parameters**.</span></span>
5. <span data-ttu-id="4c581-150">Na guia **Sequências numéricas**, configure a sequência numérica para os eventos R-2010, R-2020 e R-2055.</span><span class="sxs-lookup"><span data-stu-id="4c581-150">On the **Number sequences** tab, set up the number sequence for events R-2010, R-2020, and R-2055.</span></span>

![Guia Sequências numéricas na página Parâmetros dos livros fiscais](media/bra-sped-fiscal-books-parameters.png)

> [!NOTE]
> <span data-ttu-id="4c581-152">Se as sequências numéricas não tiverem sido inicializadas durante a lista de verificação da configuração para a instalação de KB, você poderá gerá-las usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="4c581-152">If the number sequences weren't initialized during the setup checklist for KB installation, you can generate them by using a wizard.</span></span> <span data-ttu-id="4c581-153">Para abrir o assistente, acesse **Administração da organização** \> **Sequências numéricas** \> **Sequências numéricas** e selecione **Gerar**.</span><span class="sxs-lookup"><span data-stu-id="4c581-153">To open the wizard, go to **Organization administration** \> **Number sequences** \> **Number sequences**, and select **Generate**.</span></span> <span data-ttu-id="4c581-154">Você pode configurar a sequência numérica relacionada:</span><span class="sxs-lookup"><span data-stu-id="4c581-154">You can then configure the related number sequence:</span></span>
>
> - <span data-ttu-id="4c581-155">**Área:** Livros fiscais</span><span class="sxs-lookup"><span data-stu-id="4c581-155">**Area:** Fiscal books</span></span>
> - <span data-ttu-id="4c581-156">**Referência**: ID de evento do SPED-Reinf</span><span class="sxs-lookup"><span data-stu-id="4c581-156">**Reference:** SPED-Reinf event ID</span></span>
