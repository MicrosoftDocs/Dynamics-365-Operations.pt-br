---
title: Configurar método de pagamento para débito direto de ISO20022
description: Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d3c6d8157803e0a8d33520a0cd64fb725e8c9a3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174756"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="d1fbe-103">Configurar método de pagamento para débito direto de ISO20022</span><span class="sxs-lookup"><span data-stu-id="d1fbe-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d1fbe-104">Este procedimento mostra como configurar o método de pagamento de cliente do Débito direto ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="d1fbe-105">Antes de concluir esta tarefa, você deve definir as configurações do formato de exportação e as contas de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="d1fbe-106">Este procedimento foi criado usando a empresa de dados de demonstração DEMF.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="d1fbe-107">Este é o terceiro dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="d1fbe-108">Vá para Contas a receber > Configurar pagamentos > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="d1fbe-109">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d1fbe-110">Por exemplo, filtre o campo Método de pagamento com um valor de 'ELECTRONIC'.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="d1fbe-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-111">Click Edit.</span></span>
4. <span data-ttu-id="d1fbe-112">No campo Conta de pagamento, especifique os valores 'DEMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="d1fbe-113">Expanda a seção Formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="d1fbe-114">Selecione Sim no campo eletrônico Genérico do relatório.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="d1fbe-115">No campo Exportar configuração de formato, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="d1fbe-116">Na lista, selecione Débito direto ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="d1fbe-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="d1fbe-117">Se a lista estiver vazia, a configuração de formato de exportação do pagamento do cliente não foi importada e não está ativa.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="d1fbe-118">Selecione Sim no campo de Solicitação obrigatório.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="d1fbe-119">Selecione o parâmetro Exigir carta de ordem para os formatos de pagamento de cliente, o qual exige a inclusão das informações da carta de ordem na mensagem de pagamento, como Débito direto SEPA.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="d1fbe-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d1fbe-120">Click Save.</span></span>
