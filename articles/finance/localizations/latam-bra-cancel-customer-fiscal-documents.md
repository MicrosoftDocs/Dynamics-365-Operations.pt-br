---
title: Cancelar uma nota fiscal do cliente (Brasil)
description: Este tópico fornece informações sobre como cancelar uma nota fiscal do cliente para o Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 06/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 75a5e2b5949479f6fac02822841859da2b141a94
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005777"
---
# <a name="cancel-a-customer-fiscal-document-brazil"></a><span data-ttu-id="bc1b3-103">Cancelar uma nota fiscal do cliente (Brasil)</span><span class="sxs-lookup"><span data-stu-id="bc1b3-103">Cancel a customer fiscal document (Brazil)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bc1b3-104">Você pode cancelar uma nota fiscal de cliente incorreta usando a página **Cancelar nota fiscal** .</span><span class="sxs-lookup"><span data-stu-id="bc1b3-104">You can cancel an incorrect customer fiscal document by using the **Cancel fiscal document** page.</span></span> <span data-ttu-id="bc1b3-105">Ao cancelar uma nota fiscal, ela é marcada como cancelada e todas as transações financeiras e contábeis são revertidas.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-105">When you cancel a fiscal document, the fiscal document is marked as canceled, and all of the ledger transactions and financial transactions are reversed.</span></span>

1.  <span data-ttu-id="bc1b3-106">Clique em **Contas a receber** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-106">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>
    
    <span data-ttu-id="bc1b3-107">–ou–</span><span class="sxs-lookup"><span data-stu-id="bc1b3-107">–or–</span></span>
    
    <span data-ttu-id="bc1b3-108">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-108">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="bc1b3-109">Selecione uma ordem de venda a ser cancelada.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-109">Select a sales order to cancel.</span></span>

3.  <span data-ttu-id="bc1b3-110">No Painel Ação, clique na guia **Vender** e, em seguida, clique em **Cancelar nota fiscal** para abrir a página **Cancelar nota fiscal**.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-110">On the Action Pane, click the **Sell** tab, and then click **Cancel fiscal document** to open the **Cancel fiscal document** page.</span></span> 

4.  <span data-ttu-id="bc1b3-111">No campo **Código de motivo**, selecione o código de identificação do motivo que foi usado para cancelar a nota fiscal do cliente.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-111">In the **Reason code** field, select the identification code of the reason that is used to cancel the customer fiscal document.</span></span>

5.  <span data-ttu-id="bc1b3-112">No campo **Comentário do motivo**, insira ou atualize o motivo para cancelar a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-112">In the **Reason comment** field, enter or update the reason to cancel the fiscal document.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc1b3-113">O motivo para o cancelamento deve conter pelo menos 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-113">The reason for the cancellation must contain a minimum of 15 characters.</span></span>

6.  <span data-ttu-id="bc1b3-114">Na guia **Fatura**, marque as caixas de seleção **Marcar** para selecionar as linhas de ordem de venda individuais.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-114">On the **Invoice** tab, select the **Mark** check boxes to select individual sales order lines.</span></span> <span data-ttu-id="bc1b3-115">Como alternativa, você pode marcar a caixa de seleção **Selecionar tudo** para selecionar todas as linhas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-115">Alternatively, you can select the **Select all** check box to select all of the sales order lines.</span></span>

7.  <span data-ttu-id="bc1b3-116">Clique em **OK** para criar transações que tenham quantidades negativas.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-116">Click **OK** to create transactions that have negative quantities.</span></span>

8.  <span data-ttu-id="bc1b3-117">Na página de listagem **Todas as ordens de venda**, selecione as transações que têm quantidades negativas.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-117">On the **All sales orders** list page, select the transactions that have negative quantities.</span></span>

9.  <span data-ttu-id="bc1b3-118">No **Painel de Ação**, clique na guia **Fatura** e em **Fatura** para abrir a página **Lançando fatura**.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-118">On the **Action Pane**, click the **Invoice** tab, and then click **Invoice** to open the **Posting invoice** page.</span></span>

10. <span data-ttu-id="bc1b3-119">Marque as caixas de seleção **Lançando** e **Imprimir fatura** para lançar e imprimir a fatura.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-119">Select the **Posting** and **Print invoice** check boxes to post and print the invoice.</span></span>

11. <span data-ttu-id="bc1b3-120">Clique em **OK** para cancelar a ordem de venda e para reverter todas as transações contábeis e financeiras.</span><span class="sxs-lookup"><span data-stu-id="bc1b3-120">Click **OK** to cancel the sales order, and to reverse all of the ledger and financial transactions.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc1b3-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bc1b3-121">Additional resources</span></span>

[<span data-ttu-id="bc1b3-122"> Cancelar notas fiscais do fornecedor</span><span class="sxs-lookup"><span data-stu-id="bc1b3-122">Cancel vendor fiscal documents</span></span>](latam-bra-cancel-vendor-fiscal-documents.md)
