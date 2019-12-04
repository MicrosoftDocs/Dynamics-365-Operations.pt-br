---
title: Visão geral de modelos de registro
description: Este artigo introduz o conceito de modelos de registro e explica como podem ser usados para criar registros que compartilham informações.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a8f924a5c2dad45d2006240230b85592d56e676
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176501"
---
# <a name="record-templates-overview"></a><span data-ttu-id="a9a5b-103">Visão geral de modelos de registro</span><span class="sxs-lookup"><span data-stu-id="a9a5b-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9a5b-104">Este artigo introduz o conceito de modelos de registro e explica como podem ser usados para criar registros que compartilham informações.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="a9a5b-105">Os modelos de registro podem ajudar a criar registros mais rapidamente. No entanto, é possível criar apenas modelos de registro para alguns tipos de registro.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="a9a5b-106">Por exemplo, digamos que você esteja inserindo informações de aluguel para uma empresa de aluguel de carros localizada em San Francisco.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="a9a5b-107">Como é provável que a maioria dos clientes sejam da área de San Francisco, seria interessante já preencher automaticamente os valores dos campos **Estado**, **País** e **Cidade** no formulário de aluguel.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="a9a5b-108">Você pode aplicar modelos apenas nas áreas às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="a9a5b-109">No entanto, todos os títulos de modelo são visíveis para você ao criar um novo registro, e também para outros usuários, se você está criando modelos que serão disponibilizados para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="a9a5b-110">Considere isso ao nomear modelos.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="a9a5b-111">Por exemplo, evite o uso de nomes que incluam palavras como "comissão" se for confidencial que alguns funcionários da empresa recebem salários com base em comissões.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="a9a5b-112">Quando um ou mais modelos aos quais você tem acesso existem para um formulário específico, e você tenta criar um novo registro no formulário, a página **Selecione um modelo para** é exibida.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="a9a5b-113">Quando você seleciona um modelo da lista, o novo registro é criado e contém as informações padrão baseadas no modelo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="a9a5b-114">Se você não deseja usar modelos ao criar novos registros, marque a caixa de seleção **Não perguntar novamente** na página **Selecionar um modelo para**.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="a9a5b-115">Para exibir a caixa de diálogo de seleção de modelos novamente, clique em um registro com o botão direito do mouse, clique em **Informações sobre registro** e em **Mostrar seleção de modelo**.</span><span class="sxs-lookup"><span data-stu-id="a9a5b-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>