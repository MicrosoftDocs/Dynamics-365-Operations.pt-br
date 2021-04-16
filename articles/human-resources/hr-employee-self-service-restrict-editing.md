---
title: Restringir a edição de informações pessoais
description: Restringir a edição de detalhes de contato por funcionários no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 727e0d4dbc5b330045bc9f91abab4d43b09e4382
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794796"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="4d1a6-103">Restringir a edição de informações pessoais</span><span class="sxs-lookup"><span data-stu-id="4d1a6-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="4d1a6-104">Este tópico descreve como restringir a edição de detalhes do contato por funcionários no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="4d1a6-105">Talvez você queira evitar que os funcionários editem certos detalhes do contato, como local de negócios ou endereço de email.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="4d1a6-106">Para usar esse recurso, você deve primeiro habilitar **(Versão preliminar) Restringir a adição ou edição de informações de endereço e contato por funcionários para fins de seleção** no Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="4d1a6-107">Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="4d1a6-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="4d1a6-108">![Habilitar recursos de visualização](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="4d1a6-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="4d1a6-109">Escolher as informações que um funcionário pode adicionar ou editar</span><span class="sxs-lookup"><span data-stu-id="4d1a6-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="4d1a6-110">No Human Resources, selecione **Gerenciamento de pessoal**, **Links** e **Parâmetros do Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Acesse Parâmetros de recursos humanos](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="4d1a6-112">Na página **Parâmetros de recursos humanos**, selecione a guia **autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Selecione Autoatendimento para funcionários](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="4d1a6-114">Na guia **Autoatendimento para funcionários**, desmarque todas as informações na seção **Informações de endereço e contato** que você não deseja que funcionários adicionem ou editem.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="4d1a6-115">Neste exemplo, desmarcamos informações de contato **comercial**.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Restringir edição para informações de contato comercial](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="4d1a6-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-117">Select **Save**.</span></span>

   ![Salvar alterações](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="4d1a6-119">Experiência do funcionário</span><span class="sxs-lookup"><span data-stu-id="4d1a6-119">Employee experience</span></span>

<span data-ttu-id="4d1a6-120">Após você restringir a adição ou edição de detalhes de contato por funcionários, eles poderão ver as informações, mas não alterá-las.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="4d1a6-121">Neste exemplo, em que os funcionários são impedidos de editar detalhes de contato **comercial**, eles ainda podem ver as informações em Autoatendimento para funcionários:</span><span class="sxs-lookup"><span data-stu-id="4d1a6-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Exibir detalhes do contato comercial](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="4d1a6-123">No entanto, quando eles selecionam os detalhes do contato comercial, o painel **Editar endereço** aparece como somente leitura e eles não podem alterar os campos.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Detalhes do contato comercial são exibidos como somente leitura](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="4d1a6-125">Além disso, se selecionarem **Adicionar** para adicionar um novo endereço, eles não poderão selecionar **Comercial** na caixa suspensa **Finalidade**.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![O funcionário não pode adicionar um endereço comercial](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="4d1a6-127">Os funcionários obtêm a mesma experiência quando selecionam **Detalhes do contato** na página **Informações pessoais** e adicionam um novo endereço.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="4d1a6-128">A caixa suspensa **Finalidade** só exibe os tipos de informações que podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![O funcionário não pode selecionar Comercial na lista suspensa Finalidade](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="4d1a6-130">**Detalhes do contato** agora mostram **Finalidade** na grade.</span><span class="sxs-lookup"><span data-stu-id="4d1a6-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![Finalidade é exibido na grade de detalhes Contato](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="4d1a6-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4d1a6-132">See also</span></span>

[<span data-ttu-id="4d1a6-133">Visão geral de Autoatendimento para funcionários e gerentes</span><span class="sxs-lookup"><span data-stu-id="4d1a6-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="4d1a6-134">Configurar parâmetros de recursos do Human Resources</span><span class="sxs-lookup"><span data-stu-id="4d1a6-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="4d1a6-135">Editar informações pessoais</span><span class="sxs-lookup"><span data-stu-id="4d1a6-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)