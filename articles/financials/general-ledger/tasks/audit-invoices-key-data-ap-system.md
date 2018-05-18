--- 
title: Auditar faturas e dados-chave em contas a pagar
description: "Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento."
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5cd9448c95b7ec0c4a82aca3d21d961259dfb109
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Auditar faturas e dados-chave em contas a pagar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento. Antes de começar, verifique se a configuração conciliação de faturas está marcada. 

Na página de parâmetros de contas a pagar, verifique se a opção de validação de conciliação de nota fiscal está selecionada, o campo Lançar nota fiscal com discrepâncias é configurado para exigir aprovação, e o campo da diretiva de conciliação de linha está definido à conciliação tripla.

Este procedimento usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.


## <a name="create-a-purchase-order"></a>Crie uma ordem de compra
1. Ir para Todas as ordens de compra.
2. Clique em Novo.
3. No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.
4. No campo Conta de fornecedor, insira um valor.
5. Clique em OK.
6. Clique em Adicionar linha.
7. No campo Número de item, digite um valor.
8. No Painel de Ação, clique em Compra.
9. Clique em Confirmar.

## <a name="post-a-product-receipt"></a>Lançar um recebimento de produto
1. No Painel de Ação, clique em Receber.
2. Clique em Recebimento de produtos.
3. Na lista, marque a linha selecionada.
4. No campo Recebimento de produtos, digite um valor.
5. Clique em OK.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registre e a concilie uma fatura de fornecedor com um recebimento de produto
1. No Painel de Ação, clique em Fatura.
2. Clique em Fatura.
3. No campo Número, digite um valor.
4. Clique no padrão de: Quantidade encomendada para abrir a caixa de diálogo de descarte.
5. No campo Quantidade padrão para linhas, selecione uma opção.
6. Clique em OK.
7. Clique em Sim.
8. Clique em Conciliar recebimentos de produtos.
9. Clique em OK.
10. No Painel de Ação, clique em Revisar.
11. Clique em Detalhes da conciliação.


