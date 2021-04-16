---
title: " Cancelar notas fiscais do fornecedor"
description: Este tópico fornece informações sobre como cancelar uma nota fiscal do fornecedor para o Brasil.
author: ShylaThompson
ms.date: 06/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 69c88e1b27fa985cd66916e1b72dfb309c4911d9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832580"
---
# <a name="cancel-vendor-fiscal-documents"></a><span data-ttu-id="19d21-103"> Cancelar notas fiscais do fornecedor</span><span class="sxs-lookup"><span data-stu-id="19d21-103">Cancel vendor fiscal documents</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="19d21-104">Você pode cancelar as notas fiscais incorretas de fornecedor que uma entidade legal gera e emite para fornecedores que não são contribuintes.</span><span class="sxs-lookup"><span data-stu-id="19d21-104">You can cancel incorrect vendor fiscal documents that a legal entity generates and issues for vendors that aren't taxpayers.</span></span> <span data-ttu-id="19d21-105">Ao cancelar uma nova fiscal incorreta de fornecedor, uma ordem de compra negativa é criada.</span><span class="sxs-lookup"><span data-stu-id="19d21-105">When you cancel an incorrect vendor fiscal document, a negative purchase order is created.</span></span> <span data-ttu-id="19d21-106">Quando você lança uma ordem de compra negativa e executa o processo de integração do livro fiscal, todas as transações financeiras, contábeis e de imposto relacionadas à ordem de compra são revertidas nos livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="19d21-106">When you post a negative purchase order and run the fiscal book integration process, all the tax, ledger, and financial transactions that are related to the purchase order are reversed in the fiscal books.</span></span>

1. <span data-ttu-id="19d21-107">Selecione **Contas a pagar** \> **Comum** \> **Ordens de compra** \> **Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="19d21-107">Select **Accounts payable** \> **Common** \> **Purchase orders** \> **All purchase orders**.</span></span>
2. <span data-ttu-id="19d21-108">Selecione uma ordem de compra que tenha um tipo de compra de **Ordem devolvida** e um status de aprovação **Aprovado** ou **Confirmado**.</span><span class="sxs-lookup"><span data-stu-id="19d21-108">Select a purchase order that has a purchase type of **Returned order** and an approval status of **Approved** or **Confirmed**.</span></span>
3. <span data-ttu-id="19d21-109">No Painel Ação, na guia **Compra**, selecione **Cancelar nota fiscal** para abrir a página **Cancelar nota fiscal**.</span><span class="sxs-lookup"><span data-stu-id="19d21-109">On the Action Pane, on the **Purchase** tab, select **Cancel fiscal document** to open the **Cancel fiscal document** page.</span></span>
4. <span data-ttu-id="19d21-110">No Microsoft Dynamics AX 2012 R3 e na atualização cumulativa 6 ou posterior para Microsoft Dynamics AX 2012 R2: no campo **Código de motivo**, selecione o código de identificação do motivo para cancelar a nota fiscal de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="19d21-110">In Microsoft Dynamics AX 2012 R3, and in cumulative update 6 or later for Microsoft Dynamics AX 2012 R2: In the **Reason code** field, select the identification code of your reason for canceling the vendor fiscal document.</span></span>
5. <span data-ttu-id="19d21-111">No AX 2012 R3 e na atualização cumulativa 6 ou posterior do AX 2012 R2: no campo **Comentário do motivo**, insira ou atualize o motivo para cancelar a nota fiscal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="19d21-111">In AX 2012 R3, and in cumulative update 6 or later for AX 2012 R2: In the **Reason comment** field, enter or update your reason for canceling the vendor fiscal document.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19d21-112">O motivo para o cancelamento deve ter no mínimo 15 caracteres.</span><span class="sxs-lookup"><span data-stu-id="19d21-112">The reason for the cancellation must have a minimum of 15 characters.</span></span>

6. <span data-ttu-id="19d21-113">Selecionar as faturas do fornecedor a serem canceladas.</span><span class="sxs-lookup"><span data-stu-id="19d21-113">Select the vendor invoices to cancel.</span></span>
7. <span data-ttu-id="19d21-114">Selecione **OK** para criar ordens de compra negativas para as faturas de fornecedor selecionadas.</span><span class="sxs-lookup"><span data-stu-id="19d21-114">Select **OK** to create negative purchase orders for the selected vendor invoices.</span></span>
8. <span data-ttu-id="19d21-115">No **Painel de Ação**, selecione **Fatura** \> **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="19d21-115">On the **Action Pane**, select **Invoice** \> **Invoice**.</span></span>
9. <span data-ttu-id="19d21-116">Na página **Fatura de fornecedor**, selecione **Lançar** \> **Lançar** para lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="19d21-116">On the **Vendor invoice** page, select **Post** \> **Post** to post the invoice.</span></span>

## <a name="see-also"></a><span data-ttu-id="19d21-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="19d21-117">See also</span></span>

[<span data-ttu-id="19d21-118">Cancelar uma nota fiscal complementar de compra</span><span class="sxs-lookup"><span data-stu-id="19d21-118">Cancel a purchase complementary fiscal document</span></span>](https://github.com/MicrosoftDocs/DynamicsAX2012-technet/blob/master/dynamicsax2012-technet/bra-cancel-a-purchase-complementary-fiscal-document.md)

[<span data-ttu-id="19d21-119">Cancelar uma nota fiscal de cliente</span><span class="sxs-lookup"><span data-stu-id="19d21-119">Cancel a customer fiscal document</span></span>](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/bra-cancel-cus-fis-doc/articles/financials/localizations/latam-bra-cancel-customer-fiscal-documents.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]