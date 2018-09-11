--- 
title: "Definir dimensões financeiras"
description: "Este guia de tarefas demonstra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada."
author: aprilolson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 147702c1036c0ada41719c27a033dd646de811f4
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="define-financial-dimensions"></a><span data-ttu-id="fc1b5-103">Definir dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="fc1b5-103">Define financial dimensions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc1b5-104">Este guia de tarefas demonstra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="fc1b5-105">Este guia usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="fc1b5-106">Criar uma dimensão financeira apoiada por entidade</span><span class="sxs-lookup"><span data-stu-id="fc1b5-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="fc1b5-107">Vá para Contabilidade > Plano de contas > Dimensões > Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="fc1b5-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-108">Click New.</span></span>
3. <span data-ttu-id="fc1b5-109">No campo Usar valores de, selecione uma entidade definida pelo sistema para basear a dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-109">In the User values from field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="fc1b5-110">No campo Nome de dimensão, digite um valor para descrever a dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-110">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="fc1b5-111">O nome pode ser diferente da entidade definida pelo sistema, mas não pode conter espaços ou caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>  
5. <span data-ttu-id="fc1b5-112">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-112">Click Activate.</span></span>
    * <span data-ttu-id="fc1b5-113">A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="fc1b5-114">Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="fc1b5-115">Clique em Fechar na mensagem de ativação.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-115">Click Close on the activation message.</span></span>
7. <span data-ttu-id="fc1b5-116">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-116">Click Activate.</span></span>
    * <span data-ttu-id="fc1b5-117">A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="fc1b5-118">Clique em Valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-118">Click Dimension values.</span></span>
    * <span data-ttu-id="fc1b5-119">Alguns valores de dimensão são específicos da companhia.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-119">Some dimension values are company specific.</span></span> <span data-ttu-id="fc1b5-120">Você pode verificar se eles são específicos da companhia se o nome da companhia estiver sendo mostrado na lista de valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="fc1b5-121">Criar uma dimensão financeira personalizada</span><span class="sxs-lookup"><span data-stu-id="fc1b5-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="fc1b5-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-122">Close the page.</span></span>
2. <span data-ttu-id="fc1b5-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-123">Click New.</span></span>
3. <span data-ttu-id="fc1b5-124">No campo Usar valores de, selecione <Custom dimension>.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-124">In the Use values from field, select <Custom dimension>.</span></span>
4. <span data-ttu-id="fc1b5-125">No campo Nome de dimensão, digite um valor para descrever a dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-125">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="fc1b5-126">O nome não pode conter espaços ou caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-126">The name cannot contain spaces or special characters.</span></span>  
    * <span data-ttu-id="fc1b5-127">Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que é possível inserir para valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    * <span data-ttu-id="fc1b5-128">Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="fc1b5-129">Você também pode inserir sinais numéricos (#) e o e comercial (&) como espaços reservados para as letras e números que mudarão sempre que um valor de dimensão for criado.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="fc1b5-130">Use um sinal numérico (#) como um espaço reservado para um número e um e comercial (&) como um espaço reservado para uma letra.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="fc1b5-131">Exemplo: para limitar o valor de dimensão às letras CC e a três números, insira CC-### como a máscara de formato.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="fc1b5-132">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-132">Click Activate.</span></span>
    * <span data-ttu-id="fc1b5-133">A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="fc1b5-134">Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="fc1b5-135">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-135">Click Activate.</span></span>
    * <span data-ttu-id="fc1b5-136">A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
7. <span data-ttu-id="fc1b5-137">Clique em Valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-137">Click Dimension values.</span></span>
8. <span data-ttu-id="fc1b5-138">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-138">Click New.</span></span>
9. <span data-ttu-id="fc1b5-139">No campo Valor da dimensão, digite um nome para descrever o valor da dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-139">In the Dimension value field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="fc1b5-140">No campo Descrição, digite uma descrição que descreva seu valor de dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="fc1b5-140">In the Description field, type a description that describes your financial dimension value.</span></span>


