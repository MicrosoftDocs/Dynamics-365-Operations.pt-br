---
title: Não é possível alterar a data de efetivação de um fornecedor aprovado
description: A lista de Fornecedores aprovados por entidade de produto não permite que a data de efetivação seja alterada
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475536"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>Não é possível alterar a data de efetivação de um fornecedor aprovado


## <a name="symptoms"></a>Sintomas

Um produto tem um fornecedor aprovado que tem, por exemplo, uma data de efetivação de 11 de janeiro de 2018 (*11/01/2018*) e uma data de vencimento *Nunca*. Se você tentar alterar a data de efetivação para 10 de janeiro de 2018 (*10/01/2018*) ou 12 de janeiro, 2018 (*12/01/2018*), receberá o seguinte erro:

> Não é possível criar um registro na lista de fornecedores Aprovados (PdsApproveVendorList). O valor de 'Vencimento' precisa ser maior ou igual ao valor de 'Efetivo'.

## <a name="resolution"></a>Resolução

Você só pode estender o período para o qual o fornecedor foi aprovado. As seguintes regras são aplicadas:

- Para alterar a data de efetivação de forma que ela seja anterior a qualquer um dos registros existentes (períodos) para o fornecedor do item, a data de vencimento do novo período deve ser anterior a todas as datas de vencimento nos registros existentes.
- Para alterar a data de vencimento para que seja posterior a qualquer um dos períodos existentes, a data de efetivação deve ser posterior à data de vencimento mais recente em qualquer registro existente.
- Para reduzir o período geral para o qual o fornecedor foi aprovado, você deve excluir ou modificar os registros existentes. Como alternativa, você pode usar o alternador **truncar** durante a importação. Esta opção exclui todos os registros existentes na tabela para fornecedores aprovados por item.

Para o cenário de exemplo descrito na descrição do problema, em que um registro tem uma data de efetivação de *11/01/2018* e uma data de expiração *Nunca*, você pode importar um novo registro que tenha uma data de efetivação de *10/01/2018* e uma data de expiração *Nunca*. No entanto, não é possível reduzir o período para que a data de efetivação seja atualizada para *12/01/2018* por meio do gerenciamento de dados. Você deve fazer essa alteração por meio da interface do usuário.
