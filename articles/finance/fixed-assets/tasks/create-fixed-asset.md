---
title: Criar um ativo fixo
description: Este tópico explica como criar um novo registro de ativo fixo na página de listagem Ativo fixo.
author: moaamer
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab330c604b2485687544a7d8b3eef3a652fa2069
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985128"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="eac6b-103">Criar um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="eac6b-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eac6b-104">Este tópico explica como criar um novo registro de ativo fixo na página de listagem **Ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="eac6b-105">O sistema atribui o número do ativo, com base na sequência numérica atribuída ao grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="eac6b-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="eac6b-106">Se você usar o modelo de ativo fixo para importar ativos por meio do suplemento do Microsoft Excel ou se usar outro trabalho de importação, o sistema criará automaticamente registros de ativo fixo e incrementará o número do ativo.</span><span class="sxs-lookup"><span data-stu-id="eac6b-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="eac6b-107">Para criar manualmente um registro de ativo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="eac6b-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="eac6b-108">Vá para **Painel de Navegação \> Módulos \> Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="eac6b-109">No **Painel de ação**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-109">On the **Action pane**, select **New**.</span></span>
3. <span data-ttu-id="eac6b-110">No campo **Grupo de ativo fixo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="eac6b-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="eac6b-111">O campo **Número** será padrão se você tiver habilitado a **funcionalidade de ativos fixos Autonumber** nos **parâmetros de ativos fixos** e no **grupo de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="eac6b-112">Se não, você deve inserir um número exclusivo para identificar o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="eac6b-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="eac6b-113">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="eac6b-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="eac6b-114">Insira informações adicionais que sua empresa precisa para este ativo.</span><span class="sxs-lookup"><span data-stu-id="eac6b-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="eac6b-115">No **Painel de ação**, selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-115">On the **Action pane**, select **Books**.</span></span>
6. <span data-ttu-id="eac6b-116">No campo **Data de aquisição**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="eac6b-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="eac6b-117">No campo **Preço de aquisição**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="eac6b-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="eac6b-118">Insira informações adicionais que sua empresa precisa para este registro.</span><span class="sxs-lookup"><span data-stu-id="eac6b-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="eac6b-119">Insira informações adicionais que sua empresa precisa para os registros restantes.</span><span class="sxs-lookup"><span data-stu-id="eac6b-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="eac6b-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eac6b-120">Close the page.</span></span>

<span data-ttu-id="eac6b-121">Também é possível importar ativos fixos usando o suplemento do Excel ou executando um trabalho de importação do espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="eac6b-122">Antes de executar a importação, insira os valores dos campos obrigatórios no modelo.</span><span class="sxs-lookup"><span data-stu-id="eac6b-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="eac6b-123">Se você não tiver definido o número do ativo fixo no modelo do suplemento do Excel ou no Gerenciamento de dados, o sistema cria um número de ativo fixo para cada ativo importado e incrementa automaticamente a sequência numérica para cada um.</span><span class="sxs-lookup"><span data-stu-id="eac6b-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="eac6b-124">No entanto, se você importar ativos e definir números de ativos no modelo, o sistema **não** incrementará automaticamente a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="eac6b-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="eac6b-125">Nesse caso, um administrador pode ter que atualizar manualmente a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="eac6b-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="eac6b-126">Se você tiver definido o número do ativo fixo no modelo do suplemento do Excel, o sistema usará o número do ativo fixo definido e incrementará a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="eac6b-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="eac6b-127">Depois de lançar a depreciação, os campos **Colocado em serviço** e **Data de execução da depreciação** ficarão bloqueados na página **Registro**.</span><span class="sxs-lookup"><span data-stu-id="eac6b-127">After posting the depreciation, the **Placed in service** and **Depreciation run date** fields will be locked on the **Book** page.</span></span> <span data-ttu-id="eac6b-128">Além disso, nenhum campo será atualizado a partir da entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="eac6b-128">Also, both neither field will be updated from the data entity.</span></span>

> [!WARNING]
> <span data-ttu-id="eac6b-129">O registro de ativo fixo não será excluído se as transações forem lançadas no registro associado ou se o ativo fixo recém-criado for inserido em uma linha do diário, mas não lançado.</span><span class="sxs-lookup"><span data-stu-id="eac6b-129">The fixed asset record won't be deleted if transactions were posted to the associated book, or if the newly created fixed asset is entered on a journal line but not posted.</span></span> 
