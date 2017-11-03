---
title: Modelos de registro
description: "Este artigo introduz o conceito de modelos de registro e explica como podem ser usados para criar registros que compartilham informações."
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ef5e95d9d6beed10cd6c80aa131c5cbef85c07a8
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="record-templates"></a><span data-ttu-id="50e79-103">Modelos de registro</span><span class="sxs-lookup"><span data-stu-id="50e79-103">Record templates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="50e79-104">Este artigo introduz o conceito de modelos de registro e explica como podem ser usados para criar registros que compartilham informações.</span><span class="sxs-lookup"><span data-stu-id="50e79-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="50e79-105">Os modelos de registro podem ajudá-lo a criar registros mais rápido no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="50e79-105">Record templates can help you to create records more quickly in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="50e79-106">Você pode criar modelos de registro apenas para alguns tipos de registro no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="50e79-106">You can create record templates for only some of the record types in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="50e79-107">Por exemplo, digamos que você esteja inserindo informações de aluguel para uma empresa de aluguel de carros localizada em San Francisco.</span><span class="sxs-lookup"><span data-stu-id="50e79-107">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="50e79-108">Como é provável que a maioria dos clientes sejam da área de San Francisco, seria interessante já preencher automaticamente os valores dos campos **Estado**, **País** e **Cidade** no formulário de aluguel.</span><span class="sxs-lookup"><span data-stu-id="50e79-108">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span> 

> [!Note]
> <span data-ttu-id="50e79-109">Você só pode aplicar modelos nas áreas do Finance and Operations às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="50e79-109">You can apply templates only for the areas of Finance and Operations that you have access to.</span></span> <span data-ttu-id="50e79-110">No entanto, todos os títulos de modelo são visíveis para você ao criar um novo registro, e também para outros usuários, se você está criando modelos que serão disponibilizados para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="50e79-110">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="50e79-111">Considere isso ao nomear modelos.</span><span class="sxs-lookup"><span data-stu-id="50e79-111">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="50e79-112">Por exemplo, evite o uso de nomes que incluam palavras como "comissão" se for confidencial que alguns funcionários da empresa recebem salários com base em comissões.</span><span class="sxs-lookup"><span data-stu-id="50e79-112">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span> 

<span data-ttu-id="50e79-113">Quando um ou mais modelos aos quais você tem acesso existem para um formulário específico, e você tenta criar um novo registro no formulário, a página **Selecione um modelo para** é exibida.</span><span class="sxs-lookup"><span data-stu-id="50e79-113">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="50e79-114">Quando você seleciona um modelo da lista, o novo registro é criado e contém as informações padrão baseadas no modelo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="50e79-114">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="50e79-115">Se você não deseja usar modelos ao criar novos registros, marque a caixa de seleção **Não perguntar novamente** na página **Selecionar um modelo para**.</span><span class="sxs-lookup"><span data-stu-id="50e79-115">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="50e79-116">Para exibir a caixa de diálogo de seleção de modelos novamente, clique em um registro com o botão direito do mouse, clique em **Informações sobre registro** e em **Mostrar seleção de modelo**.</span><span class="sxs-lookup"><span data-stu-id="50e79-116">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>




