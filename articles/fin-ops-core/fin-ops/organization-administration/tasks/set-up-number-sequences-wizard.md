---
title: ​Configurar sequências numéricas usando um assistente​
description: Este tópico explica como configurar todas as sequências numéricas necessárias ao mesmo tempo usando um assistente.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ca8174444d5a84f7efb402d6efc787e693801e82
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694730"
---
# <a name="set-up-number-sequences-using-a-wizard"></a><span data-ttu-id="b99f0-103">​Configurar sequências numéricas usando um assistente​</span><span class="sxs-lookup"><span data-stu-id="b99f0-103">Set up number sequences using a wizard</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b99f0-104">Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem.</span><span class="sxs-lookup"><span data-stu-id="b99f0-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="b99f0-105">Um registro de transação ou de dados mestres que exige um identificador é conhecido como referência.</span><span class="sxs-lookup"><span data-stu-id="b99f0-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="b99f0-106">Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência.</span><span class="sxs-lookup"><span data-stu-id="b99f0-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="b99f0-107">Este tópico explica como configurar todas as sequências numéricas necessárias ao mesmo tempo usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="b99f0-107">This topic explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="b99f0-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="b99f0-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="b99f0-109">Vá para **Navegação > Módulos > Administração da organização > Sequências numéricas > Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-109">Go to **Navigation > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="b99f0-110">Selecione **Gerar**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-110">Select **Generate**.</span></span>
3. <span data-ttu-id="b99f0-111">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-111">Select **Next**.</span></span>

   - <span data-ttu-id="b99f0-112">Nessa página, é possível alterar o código de identificação, o valor mais baixo e o valor mais alto.</span><span class="sxs-lookup"><span data-stu-id="b99f0-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="b99f0-113">Além disso, é possível indicar se a sequência numérica deverá ser contínua.</span><span class="sxs-lookup"><span data-stu-id="b99f0-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
   - <span data-ttu-id="b99f0-114">Não selecione a opção **Contínuo** se for necessário alocar antecipadamente os números para a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="b99f0-114">Do not select the **Continuous** option if you must preallocate numbers for the number sequence.</span></span> <span data-ttu-id="b99f0-115">Para adicionar um segmento de escopo ao formato de uma sequência numérica, selecione o formato na lista, e então selecione **Incluir escopo ao formato**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-115">To add a scope segment to the format of a number sequence, select the format in the list, and then select **Include scope in format**.</span></span> <span data-ttu-id="b99f0-116">Para remover um segmento de escopo do formato de uma sequência numérica, selecione o formato na lista, e então selecione **Remover escopo do formato**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then select **Remove scope from format**.</span></span> <span data-ttu-id="b99f0-117">Para excluir uma sequência numérica da geração automática, selecione a sequência numérica na lista, e então selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then select **Delete**.</span></span>  

4. <span data-ttu-id="b99f0-118">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-118">Select **Next**.</span></span>
5. <span data-ttu-id="b99f0-119">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b99f0-119">Select **Finish**.</span></span>

