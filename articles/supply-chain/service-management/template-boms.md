---
title: BOMs de modelo
description: "Uma BOM (lista de materiais) de modelo fornece uma lista padronizada de componentes de objetos de serviço que são atendidos regularmente."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: cdb38790015d8932412b120a82f316dd8b5adcb0
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="template-boms"></a><span data-ttu-id="a17ba-103">BOMs de modelo</span><span class="sxs-lookup"><span data-stu-id="a17ba-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a17ba-104">Uma BOM (lista de materiais) de modelo fornece uma lista padronizada de componentes para objetos de serviço que são atendidos regularmente.</span><span class="sxs-lookup"><span data-stu-id="a17ba-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="a17ba-105">Os componentes listados na BOM de modelo representam os subcomponentes individuais do objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="a17ba-106">Ao aplicar uma BOM de modelo a um objeto de serviço, você pode manter um registro dos subcomponentes que foram substituídos no objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="a17ba-107">Para aplicar uma BOM de modelo a um contrato de serviço ou uma ordem de serviço, anexe-a a uma relação de objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a17ba-108">Você pode aplicar somente uma BOM de modelo a um objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="a17ba-109">Criar uma BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="a17ba-109">Create a template BOM</span></span>

<span data-ttu-id="a17ba-110">A tabela a seguir contém informações sobre os vários métodos que podem ser usados para criar uma BOM de modelo.</span><span class="sxs-lookup"><span data-stu-id="a17ba-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a17ba-111">Método</span><span class="sxs-lookup"><span data-stu-id="a17ba-111">Method</span></span></p></th>
<th><p><span data-ttu-id="a17ba-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="a17ba-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a17ba-113">Produção</span><span class="sxs-lookup"><span data-stu-id="a17ba-113">Production</span></span></p></td>
<td><p><span data-ttu-id="a17ba-114">A BOM de modelo se baseia em uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="a17ba-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="a17ba-115">Essa opção se aplicará somente se você operar em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="a17ba-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="a17ba-116">O benefício é que você tem uma lista detalhada e atualizada dos componentes de um item.</span><span class="sxs-lookup"><span data-stu-id="a17ba-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a17ba-117">BOM de item</span><span class="sxs-lookup"><span data-stu-id="a17ba-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="a17ba-118">A BOM de modelo se baseia na BOM de um item.</span><span class="sxs-lookup"><span data-stu-id="a17ba-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="a17ba-119">A BOM do item, diferentemente da BOM de produção, é uma lista estática dos componentes que compõem um item.</span><span class="sxs-lookup"><span data-stu-id="a17ba-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a17ba-120">Modelo existente</span><span class="sxs-lookup"><span data-stu-id="a17ba-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="a17ba-121">O modelo se baseia na BOM de um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="a17ba-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a17ba-122">Manual</span><span class="sxs-lookup"><span data-stu-id="a17ba-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="a17ba-123">Se você souber quais peças sobressalentes geralmente são substituídas em um objeto de serviço, será possível criar a BOM de modelo manualmente.</span><span class="sxs-lookup"><span data-stu-id="a17ba-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="a17ba-124">Esse modelo ajuda a verificar se os componentes incluídos no modelo refletem os requisitos reais do local de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a17ba-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="a17ba-125">Aplicar a BOM de modelo a um contrato de serviço ou uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="a17ba-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="a17ba-126">Você pode aplicar uma BOM de modelo a um contrato de serviço, a uma ordem de serviço, ou a ambos.</span><span class="sxs-lookup"><span data-stu-id="a17ba-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="a17ba-127">O contrato de serviço normalmente cobre um relacionamento de longo prazo com um cliente.</span><span class="sxs-lookup"><span data-stu-id="a17ba-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="a17ba-128">O histórico de substituições registrado na BOM de serviço contém dados úteis para o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="a17ba-129">Também é possível aplicar uma BOM de modelo a uma ordem de serviço para registrar o histórico do serviço que foi executado em um objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="a17ba-130">Copiar o histórico de uma BOM de serviço</span><span class="sxs-lookup"><span data-stu-id="a17ba-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="a17ba-131">Você pode copiar o histórico de uma linha de BOM de serviço de um contrato de serviço em outro.</span><span class="sxs-lookup"><span data-stu-id="a17ba-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="a17ba-132">Ao copiar o histórico de serviço entre contratos, você pode preservar o registro de substituições de um item.</span><span class="sxs-lookup"><span data-stu-id="a17ba-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="a17ba-133">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="a17ba-133">**Example**</span></span>

<span data-ttu-id="a17ba-134">Você configurou um contrato de serviço de três anos para o carro de um cliente.</span><span class="sxs-lookup"><span data-stu-id="a17ba-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="a17ba-135">Durante esse período, o cliente se acostuma com o bom nível de serviço prestado pela empresa.</span><span class="sxs-lookup"><span data-stu-id="a17ba-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="a17ba-136">Assim, após a expiração do contrato, o cliente quer firmar um novo.</span><span class="sxs-lookup"><span data-stu-id="a17ba-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="a17ba-137">Agora você pode negociar um contrato mais favorável para a empresa.</span><span class="sxs-lookup"><span data-stu-id="a17ba-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="a17ba-138">Como o registro dos componentes substituídos pode ser útil no futuro, você copia o histórico da BOM de serviço no novo contrato.</span><span class="sxs-lookup"><span data-stu-id="a17ba-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="a17ba-139">Modificar a BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="a17ba-139">Modify the template BOM</span></span>

<span data-ttu-id="a17ba-140">Se um BOM de modelo não tiver sido anexada a um objeto de serviço, você poderá modificar ou excluir suas linhas.</span><span class="sxs-lookup"><span data-stu-id="a17ba-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="a17ba-141">Depois de anexar a BOM de modelo a um objeto de serviço, você só poderá modificar a versão local da BOM.</span><span class="sxs-lookup"><span data-stu-id="a17ba-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="a17ba-142">Se quiser duplicar a configuração de uma versão local de uma BOM de modelo, poderá criar uma nova BOM de modelo com base na versão local.</span><span class="sxs-lookup"><span data-stu-id="a17ba-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="a17ba-143">Para obter mais informações, consulte [Modificar uma BOM de Serviço](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="a17ba-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="a17ba-144">Ao substituir um item na BOM, você poderá registrar a substituição na linha de BOM no Designer de BOM.</span><span class="sxs-lookup"><span data-stu-id="a17ba-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="a17ba-145">Se desejar, você poderá criar uma linha de ordem de serviço para o objeto de substituição.</span><span class="sxs-lookup"><span data-stu-id="a17ba-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="a17ba-146">Ao criar uma linha de ordem de serviço, você poderá faturar o item de substituição.</span><span class="sxs-lookup"><span data-stu-id="a17ba-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="a17ba-147">Caso você não crie uma linha de ordem de serviço para uma substituição, o registro da substituição será mantido a fim de rastrear o histórico do objeto de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="a17ba-148">Alterar como as informações na linha da BOM são exibidas</span><span class="sxs-lookup"><span data-stu-id="a17ba-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="a17ba-149">É possível alterar o modo como as informações na linha de BOM são exibidas para todas as BOM de modelo e de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="a17ba-150">As alterações são aplicadas a todas as BOMs de modelo e de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="a17ba-151">Isso inclui aquelas que são anexadas aos objetos de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="a17ba-152">Configurar sequências numéricas para as BOMs de modelo</span><span class="sxs-lookup"><span data-stu-id="a17ba-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="a17ba-153">Para usar BOMs de modelo, você deve configurar duas sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="a17ba-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="a17ba-154">Configure uma sequência numérica para a BOM de modelo e uma para o número da linha do histórico da BOM.</span><span class="sxs-lookup"><span data-stu-id="a17ba-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a17ba-155">As sequências numéricas são usadas em todo o Microsoft Dynamics AX para alocar identificadores para registros que os exigem.</span><span class="sxs-lookup"><span data-stu-id="a17ba-155">Number sequences are used throughout Microsoft Dynamics AX to allocate identifiers to records that require them.</span></span> <span data-ttu-id="a17ba-156">Para poder atribuir uma sequência numérica a uma BOM de modelo ou a um número da linha do histórico da BOM, você deve configurar códigos de sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="a17ba-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="a17ba-157">Configurar sequências numéricas</span><span class="sxs-lookup"><span data-stu-id="a17ba-157">Set up number sequences</span></span>

1.  <span data-ttu-id="a17ba-158">Na página de listagem **Sequências numéricas**, crie sequências numéricas para BOMs de modelo e para o número da linha do histórico da BOM.</span><span class="sxs-lookup"><span data-stu-id="a17ba-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="a17ba-159">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Parâmetros de gerenciamento de serviços**.</span><span class="sxs-lookup"><span data-stu-id="a17ba-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="a17ba-160">Clique em **Sequências numéricas** e selecione um código de sequência numérica para as referências de sequência numérica que você criou no formulário **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="a17ba-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="a17ba-161">Feche o formulário para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a17ba-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a17ba-162">O número da linha do histórico da BOM é usado pelo sistema para associar as transações no histórico da BOM a um contrato de serviço ou a uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="a17ba-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="a17ba-163">O número não é exibido na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="a17ba-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="a17ba-164">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a17ba-164">See also</span></span>

[<span data-ttu-id="a17ba-165">Criar uma BOM de modelo</span><span class="sxs-lookup"><span data-stu-id="a17ba-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="a17ba-166">Gerenciar BOMs de modelo nas relações de objeto</span><span class="sxs-lookup"><span data-stu-id="a17ba-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="a17ba-167">Modificar uma BOM de Serviço</span><span class="sxs-lookup"><span data-stu-id="a17ba-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 



