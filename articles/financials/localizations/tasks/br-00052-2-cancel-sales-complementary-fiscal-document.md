---
title: Cancelar uma nota fiscal complementar de venda (Brasil)
description: É possível cancelar uma nota fiscal complementar de vendas incorreta e fornecer um motivo para o cancelamento.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dae1bc09b31032f9823912712428342d09cf297c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538294"
---
# <a name="cancel-a-sales-complementary-fiscal-document-brazil"></a><span data-ttu-id="7b23f-103">Cancelar uma nota fiscal complementar de venda (Brasil)</span><span class="sxs-lookup"><span data-stu-id="7b23f-103">Cancel a sales complementary fiscal document (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7b23f-104">É possível cancelar uma nota fiscal complementar de vendas incorreta e fornecer um motivo para o cancelamento.</span><span class="sxs-lookup"><span data-stu-id="7b23f-104">You can cancel an incorrect sales complementary fiscal document and provide a reason for the cancellation.</span></span> <span data-ttu-id="7b23f-105">Ao cancelar uma nota fiscal complementar de vendas, é criada uma nota fiscal complementar de vendas com os preços ou valores negativos de ICMS (Imposto Sobre Circulação de Mercadorias e Serviços), ou de IPI (Imposto Sobre Produtos Industrializados).</span><span class="sxs-lookup"><span data-stu-id="7b23f-105">When you cancel a sales complementary fiscal document, a sales complementary fiscal document is created that has a negative price amount, an Imposto Sobre Circulação de Mercadorias e Serviços (ICMS) amount, or an Imposto Sobre Produtos Industrializados (IPI) amount.</span></span> <span data-ttu-id="7b23f-106">Ao lançar a nota fiscal complementar de venda negativa, a nota fiscal complementar original é marcada como cancelada, e todas as transações do razão e as transações financeiras são revertidas.</span><span class="sxs-lookup"><span data-stu-id="7b23f-106">When you post the negative sales complementary fiscal document, the original complementary fiscal document is marked as canceled, and all the ledger transactions and financial transactions are reversed.</span></span> <span data-ttu-id="7b23f-107">A nota fiscal complementar de venda original é relatada em livros fiscais como cancelada.</span><span class="sxs-lookup"><span data-stu-id="7b23f-107">The original sales complementary fiscal document is reported in the fiscal books as canceled.</span></span> <span data-ttu-id="7b23f-108">A nota fiscal complementar de venda negativa não é relatada em livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="7b23f-108">The negative sales complementary fiscal document isn't reported in the fiscal books.</span></span> <span data-ttu-id="7b23f-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="7b23f-109">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="7b23f-110">Vá para Contas a receber > Notas fiscais > Todas as notas fiscais complementares de vendas.</span><span class="sxs-lookup"><span data-stu-id="7b23f-110">Go to Accounts receivable > Fiscal documents > All sales complementary fiscal documents.</span></span>
2. <span data-ttu-id="7b23f-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7b23f-111">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="7b23f-112">Clique em Cancelar nota fiscal para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7b23f-112">Click Cancel fiscal document to open the drop dialog.</span></span>
4. <span data-ttu-id="7b23f-113">No campo Código de motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7b23f-113">In the Reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="7b23f-114">Insira ou atualize seu motivo do cancelamento da nota fiscal complementar de vendas.</span><span class="sxs-lookup"><span data-stu-id="7b23f-114">Enter or update your reason for canceling the sales complementary fiscal document.</span></span>  
5. <span data-ttu-id="7b23f-115">Clique em Criar fatura corrigida.</span><span class="sxs-lookup"><span data-stu-id="7b23f-115">Click Create corrected invoice.</span></span>
    * <span data-ttu-id="7b23f-116">Uma nota fiscal complementar de venda negativa é criada.</span><span class="sxs-lookup"><span data-stu-id="7b23f-116">A negative sales complementary fiscal document is created.</span></span>  
6. <span data-ttu-id="7b23f-117">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="7b23f-117">Click Post.</span></span>
    * <span data-ttu-id="7b23f-118">Ao lançar a nota fiscal complementar de venda negativa, a nota fiscal complementar de venda original é marcada como cancelada.</span><span class="sxs-lookup"><span data-stu-id="7b23f-118">When you post the negative sales complementary fiscal document, the original sales complementary fiscal document is marked as canceled.</span></span>  
7. <span data-ttu-id="7b23f-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7b23f-119">Close the page.</span></span>
8. <span data-ttu-id="7b23f-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7b23f-120">Close the page.</span></span>

