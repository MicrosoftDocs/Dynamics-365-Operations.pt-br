---
title: Definir dimensões financeiras
description: Este guia de tarefas demonstra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c93a67d0c4a8443eaf40b094770ed6ce29da527b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834443"
---
# <a name="define-financial-dimensions"></a><span data-ttu-id="90dba-103">Definir dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="90dba-103">Define financial dimensions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90dba-104">Este guia de tarefas demonstra como adicionar uma dimensão financeira apoiada por entidade e dimensão financeira personalizada.</span><span class="sxs-lookup"><span data-stu-id="90dba-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="90dba-105">Este guia usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="90dba-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="90dba-106">Criar uma dimensão financeira apoiada por entidade</span><span class="sxs-lookup"><span data-stu-id="90dba-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="90dba-107">Vá para **Painel de navegação > Módulos > Contabilidade > Plano de contas > Dimensões > Dimensões financeiras**.</span><span class="sxs-lookup"><span data-stu-id="90dba-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Dimensions > Financial dimensions**.</span></span>
2. <span data-ttu-id="90dba-108">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="90dba-108">Click **New**.</span></span>
3. <span data-ttu-id="90dba-109">No campo **Usar valores de**, selecione uma entidade definida pelo sistema para basear a dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="90dba-109">In the **User values form** field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="90dba-110">No campo **Nome de dimensão**, digite um valor para descrever a dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="90dba-110">In the **Dimension name** field, type a value to describe the financial dimension.</span></span> <span data-ttu-id="90dba-111">O nome pode ser diferente da entidade definida pelo sistema, mas não pode conter espaços ou caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="90dba-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>
5. <span data-ttu-id="90dba-112">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="90dba-112">Click **Activate**.</span></span> <span data-ttu-id="90dba-113">A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas.</span><span class="sxs-lookup"><span data-stu-id="90dba-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="90dba-114">Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.</span><span class="sxs-lookup"><span data-stu-id="90dba-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="90dba-115">Clique em **Fechar** na mensagem de ativação.</span><span class="sxs-lookup"><span data-stu-id="90dba-115">Click **Close** on the activation message.</span></span>
7. <span data-ttu-id="90dba-116">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="90dba-116">Click **Activate**.</span></span> <span data-ttu-id="90dba-117">A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.</span><span class="sxs-lookup"><span data-stu-id="90dba-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="90dba-118">No **Painel de Ação**, clique em **Valores de dimensão**.</span><span class="sxs-lookup"><span data-stu-id="90dba-118">On **Action pane**, click **Dimension values**.</span></span> <span data-ttu-id="90dba-119">Alguns valores de dimensão são específicos da companhia.</span><span class="sxs-lookup"><span data-stu-id="90dba-119">Some dimension values are company specific.</span></span> <span data-ttu-id="90dba-120">Você pode verificar se eles são específicos da companhia se o nome da companhia estiver sendo mostrado na lista de valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="90dba-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="90dba-121">Criar uma dimensão financeira personalizada</span><span class="sxs-lookup"><span data-stu-id="90dba-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="90dba-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="90dba-122">Close the page.</span></span>
2. <span data-ttu-id="90dba-123">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="90dba-123">Click **New**.</span></span>
3. <span data-ttu-id="90dba-124">No campo **Usar valores de**, selecione **Dimensão personalizada**.</span><span class="sxs-lookup"><span data-stu-id="90dba-124">In the **Use values from** field, select **Custom dimension**.</span></span>
4. <span data-ttu-id="90dba-125">No campo **Nome de dimensão**, digite um valor para descrever a dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="90dba-125">In the **Dimension name** field, type a value to describe the financial dimension.</span></span>
    - <span data-ttu-id="90dba-126">O nome não pode conter espaços ou caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="90dba-126">The name cannot contain spaces or special characters.</span></span>  
    - <span data-ttu-id="90dba-127">Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que é possível inserir para valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="90dba-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    - <span data-ttu-id="90dba-128">Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen.</span><span class="sxs-lookup"><span data-stu-id="90dba-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="90dba-129">Você também pode inserir sinais numéricos (#) e o e comercial (&) como espaços reservados para as letras e números que mudarão sempre que um valor de dimensão for criado.</span><span class="sxs-lookup"><span data-stu-id="90dba-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="90dba-130">Use um sinal numérico (#) como um espaço reservado para um número e um e comercial (&) como um espaço reservado para uma letra.</span><span class="sxs-lookup"><span data-stu-id="90dba-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="90dba-131">Exemplo: para limitar o valor de dimensão às letras CC e a três números, insira CC-### como a máscara de formato.</span><span class="sxs-lookup"><span data-stu-id="90dba-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="90dba-132">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="90dba-132">Click **Activate**.</span></span> <span data-ttu-id="90dba-133">A ativação da dimensão financeira atualiza a tabela com o nome da dimensão financeira e remove as dimensões excluídas.</span><span class="sxs-lookup"><span data-stu-id="90dba-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="90dba-134">Você pode inserir valores de dimensão antes de ativar uma dimensão financeira, mas uma dimensão financeira não pode ser usada até ser ativada.</span><span class="sxs-lookup"><span data-stu-id="90dba-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>     
6. <span data-ttu-id="90dba-135">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="90dba-135">Click **Activate**.</span></span> <span data-ttu-id="90dba-136">A ativação da dimensão pode ser programada para execução por lote em data e horário específicos.</span><span class="sxs-lookup"><span data-stu-id="90dba-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>      
7. <span data-ttu-id="90dba-137">No **Painel de Ação**, clique em **Valores de dimensão**.</span><span class="sxs-lookup"><span data-stu-id="90dba-137">On **Action pane**, click **Dimension values**.</span></span>
8. <span data-ttu-id="90dba-138">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="90dba-138">Click **New**.</span></span>
9. <span data-ttu-id="90dba-139">No campo **Valor da dimensão**, digite um nome para descrever o valor da dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="90dba-139">In the **Dimension value** field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="90dba-140">No campo **Descrição**, digite uma descrição que defina seu valor de dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="90dba-140">In the **Description** field, type a description that describes your financial dimension value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]