---
title: Restrições de tabela definidas pelo sistema e pelo usuário
description: 'Este artigo explica os dois tipos de restrições de tabela definidas pelo usuário e pelo sistema para os componentes de um modelo de configuração de produto: definido pelo usuário e definido pelo sistema. As restrições de tabela representam matrizes das combinações de atributos permitidos, onde cada linha define um conjunto de possíveis valores de atributo.'
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fac49cde1a6098b99e6373bf9221d3357a053a2
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814504"
---
# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="f4f62-104">Restrições de tabela definidas pelo sistema e pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4f62-104">System-defined and user-defined table constraints</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4f62-105">Este artigo explica os dois tipos de restrições de tabela definidas pelo usuário e pelo sistema para os componentes de um modelo de configuração de produto: definido pelo usuário e definido pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="f4f62-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="f4f62-106">As restrições de tabela representam matrizes das combinações de atributos permitidos, onde cada linha define um conjunto de possíveis valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="f4f62-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="f4f62-107">As restrições de tabela representam matrizes de combinações de atributos que são permitidas para componentes de um modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="f4f62-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="f4f62-108">Cada linha na tabela define um conjunto de valores de atributo possíveis.</span><span class="sxs-lookup"><span data-stu-id="f4f62-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="f4f62-109">É possível declarar dois tipos de restrições em um modelo de configuração de produto:</span><span class="sxs-lookup"><span data-stu-id="f4f62-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="f4f62-110">**Restrição de expressão** – Cria uma expressão que define relações entre os atributos para garantir que somente os valores compatíveis possam ser selecionados durante a configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="f4f62-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="f4f62-111">**Restrição de tabela** – Cria uma tabela que define todas as combinações que são permitidas para um conjunto específico de atributos.</span><span class="sxs-lookup"><span data-stu-id="f4f62-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="f4f62-112">Dois tipos de restrições de tabela estão disponíveis: restrições de tabela definidas pelo usuário e restrições de tabela definidas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="f4f62-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="f4f62-113">Este artigo descreve as restrições de tabela definidas pelo usuário e pelo sistema para os componentes de um modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="f4f62-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="f4f62-114">Restrições de tabela definidas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4f62-114">User-defined table constraints</span></span>
<span data-ttu-id="f4f62-115">Uma restrição de tabela definida pelo usuário é um tipo de matriz que é usada para descrever as combinações de valores de atributo que são definidas pelos tipos de atributos.</span><span class="sxs-lookup"><span data-stu-id="f4f62-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="f4f62-116">Por exemplo, se você produz alto-falantes, pode incluir as colunas para o acabamento do gabinete e a grade frontal na restrição de tabela definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f4f62-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="f4f62-117">O tipo de atributo para o acabamento do gabinete possui quatro valores, e o tipo de atributo para a grade frontal tem três valores.</span><span class="sxs-lookup"><span data-stu-id="f4f62-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="f4f62-118">Consequentemente, se as restrições não são usadas, haverá as combinações possíveis de 4 × 3 = 12.</span><span class="sxs-lookup"><span data-stu-id="f4f62-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="f4f62-119">No entanto, neste exemplo, apenas seis combinações são permitidas, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4f62-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="f4f62-120">Estas informações são exibidas na guia **Combinações permitidas** na página **Editar restrição de tabela**.</span><span class="sxs-lookup"><span data-stu-id="f4f62-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="f4f62-121">Acabamento do gabinete</span><span class="sxs-lookup"><span data-stu-id="f4f62-121">Cabinet finish</span></span> | <span data-ttu-id="f4f62-122">Grade frontal</span><span class="sxs-lookup"><span data-stu-id="f4f62-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="f4f62-123">Preto</span><span class="sxs-lookup"><span data-stu-id="f4f62-123">Black</span></span>          | <span data-ttu-id="f4f62-124">Preto</span><span class="sxs-lookup"><span data-stu-id="f4f62-124">Black</span></span>       |
| <span data-ttu-id="f4f62-125">Preto</span><span class="sxs-lookup"><span data-stu-id="f4f62-125">Black</span></span>          | <span data-ttu-id="f4f62-126">Metal</span><span class="sxs-lookup"><span data-stu-id="f4f62-126">Metal</span></span>       |
| <span data-ttu-id="f4f62-127">Carvalho</span><span class="sxs-lookup"><span data-stu-id="f4f62-127">Oak</span></span>            | <span data-ttu-id="f4f62-128">Preto</span><span class="sxs-lookup"><span data-stu-id="f4f62-128">Black</span></span>       |
| <span data-ttu-id="f4f62-129">Jacarandá</span><span class="sxs-lookup"><span data-stu-id="f4f62-129">Rosewood</span></span>       | <span data-ttu-id="f4f62-130">Branco</span><span class="sxs-lookup"><span data-stu-id="f4f62-130">White</span></span>       |
| <span data-ttu-id="f4f62-131">Branco</span><span class="sxs-lookup"><span data-stu-id="f4f62-131">White</span></span>          | <span data-ttu-id="f4f62-132">Preto</span><span class="sxs-lookup"><span data-stu-id="f4f62-132">Black</span></span>       |
| <span data-ttu-id="f4f62-133">Branco</span><span class="sxs-lookup"><span data-stu-id="f4f62-133">White</span></span>          | <span data-ttu-id="f4f62-134">Branco</span><span class="sxs-lookup"><span data-stu-id="f4f62-134">White</span></span>       |

<span data-ttu-id="f4f62-135">As restrições de tabela definidas pelo usuário são definidas pela entrada de tabela estática que funciona da mesma forma que uma restrição de expressão.</span><span class="sxs-lookup"><span data-stu-id="f4f62-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="f4f62-136">Ao usar uma restrição de tabela definida pelo usuário, a vantagem é que as tabelas são frequentemente mais fáceis de serem criadas, compreendidas, e mantidas do que as restrições de expressão extensas.</span><span class="sxs-lookup"><span data-stu-id="f4f62-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="f4f62-137">Restrições de tabela definidas pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4f62-137">System-defined table constraints</span></span>
<span data-ttu-id="f4f62-138">Uma restrição de tabela definida pelo sistema cria um mapeamento dinâmicos entre um tipo de atributo e um campo em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="f4f62-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="f4f62-139">Quando uma restrição de tabela definida pelo sistema for incluída em um modelo de configuração do produto, o mapeamento garante que os dados da tabela serão mostrados em vez dos valores de tipo de atributo.</span><span class="sxs-lookup"><span data-stu-id="f4f62-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="f4f62-140">O resultado é uma restrição dinâmica, pois o conteúdo da tabela pode ser alterado (por exemplo, por outros módulos).</span><span class="sxs-lookup"><span data-stu-id="f4f62-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="f4f62-141">Ao criar uma restrição de tabela definida pelo sistema, selecione uma tabela, se preferir, defina a consulta a ser usada e, em seguida, associe os tipos de atributos aos campos da tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="f4f62-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="f4f62-142">Os tipos dos campos devem corresponder aos tipos dos tipos de atributo.</span><span class="sxs-lookup"><span data-stu-id="f4f62-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="f4f62-143">Antes que uma restrição de tabela possa ter efeito em um modelo de configuração de produto, a restrição de tabela deve ser incluída em uma restrição em um dos componentes do modelo.</span><span class="sxs-lookup"><span data-stu-id="f4f62-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="f4f62-144">O procedimento é criar uma nova restrição, selecionar o tipo de restrição de tabela e, em seguida, selecionar a definição de restrição de tabela a ser usada.</span><span class="sxs-lookup"><span data-stu-id="f4f62-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="f4f62-145">Por fim, todos os campos na tabela de restrição devem ser mapeados para atributos no modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="f4f62-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f4f62-146">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f4f62-146">Additional resources</span></span>
--------

[<span data-ttu-id="f4f62-147">Visão geral dos modelos de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="f4f62-147">Product configuration models overview</span></span>](product-configuration-models.md)



