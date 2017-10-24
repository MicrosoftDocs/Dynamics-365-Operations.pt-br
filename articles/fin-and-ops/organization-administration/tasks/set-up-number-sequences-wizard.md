--- 
title: "Configurar sequências numéricas usando um assistente"
description: "Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 96c1bc711350b447611977c3f2070fbc08fbae0f
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="57448-103">Configurar sequências numéricas usando um assistente</span><span class="sxs-lookup"><span data-stu-id="57448-103">Set up number sequences by using a wizard</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57448-104">Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem.</span><span class="sxs-lookup"><span data-stu-id="57448-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="57448-105">Um registro de transação ou de dados mestres que exige um identificador é conhecido como referência.</span><span class="sxs-lookup"><span data-stu-id="57448-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="57448-106">Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência.</span><span class="sxs-lookup"><span data-stu-id="57448-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="57448-107">Este processo explica como configurar todas as sequências numéricas necessárias ao mesmo tempo usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="57448-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="57448-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="57448-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="57448-109">Vá para Administração da organização > Sequências numéricas > Sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="57448-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="57448-110">Clique em Gerar.</span><span class="sxs-lookup"><span data-stu-id="57448-110">Click Generate.</span></span>
3. <span data-ttu-id="57448-111">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="57448-111">Click Next.</span></span>
    * <span data-ttu-id="57448-112">Nessa página, é possível alterar o código de identificação, o valor mais baixo e o valor mais alto.</span><span class="sxs-lookup"><span data-stu-id="57448-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="57448-113">Além disso, é possível indicar se a sequência numérica deverá ser contínua.</span><span class="sxs-lookup"><span data-stu-id="57448-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="57448-114">Não selecione a opção Contínuo se for necessário alocar antecipadamente os números para a sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="57448-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="57448-115">Para adicionar um segmento de escopo ao formato de uma sequência numérica, selecione o formato na lista, e então clique em Incluir escopo ao formato.</span><span class="sxs-lookup"><span data-stu-id="57448-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="57448-116">Para remover um segmento de escopo do formato de uma sequência numérica, selecione o formato na lista, e então clique em Remover escopo do formato.</span><span class="sxs-lookup"><span data-stu-id="57448-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="57448-117">Para excluir uma sequência numérica da geração automática, selecione a sequência numérica na lista, e então clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="57448-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="57448-118">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="57448-118">Click Next.</span></span>
5. <span data-ttu-id="57448-119">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="57448-119">Click Finish.</span></span>


