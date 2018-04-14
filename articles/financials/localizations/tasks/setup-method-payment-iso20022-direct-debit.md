--- 
title: "Configurar método de pagamento do débito direto ISO20022"
description: "Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo."
author: mrolecki
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: aa159fdf8a8ef543c338546a389d37e1644676a3
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="3d0a4-103">Configurar método de pagamento do débito direto ISO20022</span><span class="sxs-lookup"><span data-stu-id="3d0a4-103">Set up method of payment for ISO20022 direct debit</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3d0a4-104">Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="3d0a4-105">Antes de concluir esta tarefa, você deve definir as configurações do formato de exportação e as contas de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="3d0a4-106">Este procedimento foi criado usando a empresa de dados de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="3d0a4-107">Este é o terceiro dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="3d0a4-108">Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="3d0a4-109">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="3d0a4-110">Por exemplo, filtre o campo Método de pagamento com um valor de 'ELECTRONIC'.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="3d0a4-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-111">Click Edit.</span></span>
4. <span data-ttu-id="3d0a4-112">No campo Conta de pagamento, especifique os valores 'DEMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="3d0a4-113">Expanda a seção Formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="3d0a4-114">Selecione Sim no campo eletrônico Genérico do relatório.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="3d0a4-115">No campo Exportar configuração de formato, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="3d0a4-116">Na lista, selecione Débito direto ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="3d0a4-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="3d0a4-117">Se a lista estiver vazia, a configuração de formato de exportação do pagamento do cliente não foi importada e não está ativa.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="3d0a4-118">Selecione Sim no campo de Solicitação obrigatório.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="3d0a4-119">Selecione o parâmetro Exigir carta de ordem para os formatos de pagamento de cliente, o qual exige a inclusão das informações da carta de ordem na mensagem de pagamento, como Débito direto SEPA.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="3d0a4-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3d0a4-120">Click Save.</span></span>


