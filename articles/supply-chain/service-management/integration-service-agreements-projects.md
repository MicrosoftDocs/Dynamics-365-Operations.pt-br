---
title: Integração dos contratos de serviço e projetos
description: Quando você trabalha com contratos de serviço e linhas de contrato de serviço, usa os dados configurados nas áreas em Gerenciamento e contabilidade do projeto.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd0a7de17e8ff098220fd183b714b77225cc217f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247301"
---
# <a name="integration-for-service-agreements-and-projects"></a><span data-ttu-id="718f8-103">Integração dos contratos de serviço e projetos</span><span class="sxs-lookup"><span data-stu-id="718f8-103">Integration for service agreements and projects</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="718f8-104">Quando você trabalha com contratos de serviço e linhas de contrato de serviço, usa os dados configurados nas seguintes áreas em **Gerenciamento e contabilidade do projeto**.</span><span class="sxs-lookup"><span data-stu-id="718f8-104">When you work with service agreements and service agreement lines, you use data that is set up in the following areas in **Project management and accounting**.</span></span>

## <a name="project-prices"></a><span data-ttu-id="718f8-105">Preços do projeto</span><span class="sxs-lookup"><span data-stu-id="718f8-105">Project prices</span></span>

<span data-ttu-id="718f8-106">O preço de custo e de venda de uma transação de contrato de serviço derivam da configuração de preço de custo que se aplica ao projeto associado ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="718f8-106">The cost and the sales price for a service agreement transaction are derived from the cost price setup that applies to the project that is attached to the service agreement.</span></span> <span data-ttu-id="718f8-107">Os preços de custo e de venda podem ser configurador por projeto, funcionário e categoria.</span><span class="sxs-lookup"><span data-stu-id="718f8-107">Cost and sales prices can be set up by project, employee, and category.</span></span> 

## <a name="project-validation"></a><span data-ttu-id="718f8-108">Validação de projeto</span><span class="sxs-lookup"><span data-stu-id="718f8-108">Project validation</span></span>

<span data-ttu-id="718f8-109">Os projetos, os funcionários e as categorias disponíveis para seleção em uma linha de contrato de serviço podem ser limitados pela configuração de validação em **Gerenciamento e contabilidade do projeto**.</span><span class="sxs-lookup"><span data-stu-id="718f8-109">The projects, employees, and categories that are available for selection on a service agreement line can be limited by the validation setup in **Project management and accounting**.</span></span> <span data-ttu-id="718f8-110">Usando a configuração de validação, você pode combinar funcionários, projetos e categorias para acesso controlado.</span><span class="sxs-lookup"><span data-stu-id="718f8-110">By using the validation setup, you can combine employees, projects, and categories for control access.</span></span> 

## <a name="project-line-properties"></a><span data-ttu-id="718f8-111">Propriedades da linha de projeto</span><span class="sxs-lookup"><span data-stu-id="718f8-111">Project line properties</span></span>

<span data-ttu-id="718f8-112">Uma propriedade de linha é inserida automaticamente para uma linha de contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="718f8-112">A line property is entered automatically for a service agreement line.</span></span>

<span data-ttu-id="718f8-113">As propriedades de linha são criadas no formulário **Propriedades de linha** em **Gerenciamento e contabilidade de projeto**.</span><span class="sxs-lookup"><span data-stu-id="718f8-113">Line properties are created in the **Line properties** form in **Project management and accounting**.</span></span> <span data-ttu-id="718f8-114">A propriedade da linha inserida em um contrato de serviço é anexada ao projeto selecionado para o contrato e, subsequentemente, herdada subsequentemente pela linha do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="718f8-114">The line property that is entered on a service agreement is attached to the project that is selected for the service agreement and inherited subsequently by the service agreement line.</span></span> 

## <a name="default-offset-accounts"></a><span data-ttu-id="718f8-115">Contrapartidas padrão</span><span class="sxs-lookup"><span data-stu-id="718f8-115">Default offset accounts</span></span>

<span data-ttu-id="718f8-116">Se você inserir uma transação de despesa, uma contrapartida de despesa padrão será selecionada automaticamente para a transação.</span><span class="sxs-lookup"><span data-stu-id="718f8-116">If you enter an expense transaction, a default expense offset account is selected automatically for the transaction.</span></span> <span data-ttu-id="718f8-117">A conta de despesa padrão é configurada para o projeto associado ao contrato de serviço atual.</span><span class="sxs-lookup"><span data-stu-id="718f8-117">The default expense account is set up for the project that is attached to the current service agreement.</span></span>

## <a name="project-categories"></a><span data-ttu-id="718f8-118">Categorias de projeto</span><span class="sxs-lookup"><span data-stu-id="718f8-118">Project categories</span></span>

<span data-ttu-id="718f8-119">As categorias disponíveis para as linhas do contrato de serviço são configuradas no formulário **Categorias de projeto** na seção **Gerenciamento e contabilidade do projeto**.</span><span class="sxs-lookup"><span data-stu-id="718f8-119">The categories that are available for service agreement lines are set up in the **Project categories** form in **Project management and accounting**.</span></span> 

> [!NOTE]
> <P><span data-ttu-id="718f8-120">As categorias que têm a caixa de seleção <STRONG>Ativo em diários</STRONG> marcada na guia <STRONG>Projeto</STRONG> do formulário <STRONG>Categorias de projeto</STRONG> estão disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="718f8-120">Categories that have the <STRONG>Active in journals</STRONG> check box selected on the <STRONG>Project</STRONG> tab in the <STRONG>Project categories</STRONG> form are available for selection.</span></span> <span data-ttu-id="718f8-121">Porém, se a caixa de seleção <STRONG>Categorias inativas</STRONG> estiver selecionada na guia <STRONG>Diários</STRONG> no formulário <STRONG>Parâmetros de gerenciamento do projeto e a contabilidade</STRONG>, todas as categorias estarão disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="718f8-121">However, if the <STRONG>Inactive categories</STRONG> check box is selected on the <STRONG>Journals</STRONG> tab in the <STRONG>Project management and accounting parameters</STRONG> form, all categories are available for selection.</span></span></P>

## <a name="project-parameters"></a><span data-ttu-id="718f8-122">Parâmetros do projeto</span><span class="sxs-lookup"><span data-stu-id="718f8-122">Project parameters</span></span>

<span data-ttu-id="718f8-123">Se o campo **Trabalhadores demitidos** na guia **Diários** no formulário **Parâmetros de gerenciamento e contabilidade de projetos** for selecionada, você pode selecionar funcionários inativos e ativos nos formulários **Contratos de serviço** e **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="718f8-123">If the **Terminated workers** field on the **Journals** tab in the **Project management and accounting parameters** form is selected, you can select inactive employees and active employees in the **Service agreements** and **Service orders** forms.</span></span>

<span data-ttu-id="718f8-124">Você também poderá habilitar os campos **Hora de início** e **Hora de término** na guia **Projeto** do formulário **Ordens de serviço** para especificar horários de início e término em linhas de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="718f8-124">Also, you can enable the **Start time** and **End time** fields on the **Project** tab in the **Service orders** form to enter starting and ending times on service order lines.</span></span>

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a><span data-ttu-id="718f8-125">Habilitar o recurso de horário de início e término para ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="718f8-125">Enable the starting and ending time feature for service orders</span></span>

1.  <span data-ttu-id="718f8-126">Clique em **Gerenciamento e contabilidade de projetos** \> **Configurar** \> **Parâmetros de gerenciamento e contabilidade de projetos**.</span><span class="sxs-lookup"><span data-stu-id="718f8-126">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="718f8-127">Clique na guia **Diários**, e depois marque a caixa de seleção **Mostrar horas de início/término**.</span><span class="sxs-lookup"><span data-stu-id="718f8-127">Click the **Journals** tab, and then select the **Show start/end times** check box.</span></span>

3.  <span data-ttu-id="718f8-128">Clique em **Gerenciamento e contabilidade de projetos** \> **Configuração** \> **Diários** \> **Nomes de diário**.</span><span class="sxs-lookup"><span data-stu-id="718f8-128">Click **Project management and accounting** \> **Setup** \> **Journals** \> **Journal names**.</span></span>

4.  <span data-ttu-id="718f8-129">Selecione o nome do diário anexado à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="718f8-129">Select the journal name that is attached to the service order.</span></span>

5.  <span data-ttu-id="718f8-130">Clique na guia **Geral**, e depois marque a caixa de seleção **Mostrar horas de início/término**.</span><span class="sxs-lookup"><span data-stu-id="718f8-130">Click the **General** tab, and then select the **Show start/end times** check box.</span></span>


> [!NOTE]
> <P><span data-ttu-id="718f8-131">Selecione o nome do diário para a ordem de serviço no campo <STRONG>Hora</STRONG> na guia <STRONG>Diários</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="718f8-131">Select the journal name for the service order in the <STRONG>Hour</STRONG> field on the <STRONG>Journals</STRONG> tab in the <STRONG>Service management parameters</STRONG> form.</span></span></P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]