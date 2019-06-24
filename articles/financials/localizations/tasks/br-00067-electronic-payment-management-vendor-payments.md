---
title: Gerenciamento de pagamento eletrônico para pagamentos de fornecedores (Brasil)
description: É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco.
author: sndray
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a962d50fba3c65c395fc345c3d219839fd01c16
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567194"
---
# <a name="electronic-payment-management-for-vendor-payments-brazil"></a>Gerenciamento de pagamento eletrônico para pagamentos de fornecedores (Brasil)

[!include [task guide banner](../../includes/task-guide-banner.md)]

É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco. É possível gerar e enviar um arquivo de remessa eletrônica para um banco. Nesse caso, o arquivo de exportação contém informações sobre as faturas que devem ser recebidas ou pagas, as solicitações de faturas de devolução, ou as alterações nos endereços de cliente ou de fornecedor. Como alternativa, é possível importar um arquivo de devolução de um banco. Nesse caso, o arquivo de devolução contém informações sobre a aceitação de uma fatura, junto com o número de pagamento fornecido pelo banco, ou informações sobre os pagamentos recebidos de um cliente ou pagos a um fornecedor. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Razão de compra > Pagamentos > Transferências de pagamento.
2. Na lista, marque a linha selecionada.
3. Clique em Arquivo retorno - Fornecedor.
4. No campo Condições de pagamento, insira ou selecione um valor.
5. Clique em OK.
6. Clique em OK.
    * O status dos pagamentos é atualizado no campo Status de pagamento na página Transferências de pagamento. O novo status se baseia no status do pagamento no arquivo de devolução.  
7. Clique em Lançar.
8. No campo Nome do novo diário, digite um valor.
9. Clique em OK.
10. Feche a página.

