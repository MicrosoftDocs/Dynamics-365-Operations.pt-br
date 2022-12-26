---
title: Problemas com a reconciliação de dados de uma redução Z
description: Este artigo descreve problemas que os usuários podem enfrentar com a reconciliação de dados de um relatório Z no Commerce headquarters. Ele também descreve possíveis causas e soluções que podem ajudar a prevenir ocorrências futuras.
author: Shajain
ms.date: 12/06/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 9803134c4c77233e565525e96fd82af293d4c829
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832116"
---
# <a name="issues-with-the-data-reconciliation-of-a-z-report"></a>Problemas com a reconciliação de dados de uma redução Z

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar se você tiver problemas com a reconciliação de dados de um relatório Z no Microsoft Dynamics 365 Commerce headquarters. Ele descreve problemas que os usuários podem enfrentar com a reconciliação de dados, possíveis causas e soluções que podem ajudar a prevenir ocorrências futuras.

## <a name="description"></a>descrição

- Há uma incompatibilidade entre os valores mostrados no relatório Z e os totais mostrados no demonstrativo calculado.
- A transação na sede tem um número incorreto de itens de linha ou há uma incompatibilidade entre o total da linha e o total da transação.
- O número de transações que são mostradas em um turno na matriz é menor do que o número de transações no relatório Z.
- Falha no lançamento do demonstrativo para uma das razões acima.

### <a name="root-cause"></a>Causa raiz

A causa mais comum dos sinais descritos anteriormente é a geração de IDs de transação duplicadas no banco de dados do canal. IDs de transação duplicadas podem ser gerados pelos seguintes motivos:

- O armazenamento de banco de dados local do Ponto de Venda Moderno (MPOS) está corrompido.
- Os MPOS têm algumas transações no modo offline e são reativados usando uma conta que não tem acesso ao banco de dados offline.
- Há um problema com a personalização relacionada à geração de IDs de transação.

## <a name="resolution"></a>Resolução

Normalmente, o Commerce conta com uma sequência numérica para gerar IDs de transação sequenciais. Se o sistema não puder determinar que uma sequência numérica foi usada por algum motivo, uma ID de transação será duplicada. 

Para corrigir o problema de ID de transação duplicada, crie um tíquete de suporte para verificar se os dados da transação podem ser fixos. Em alguns casos, por exemplo, quando não há perda de dados na sede, nenhuma correção de dados é possível ou necessária.

Para ajudar a evitar esse problema no futuro, você deve habilitar o recurso **Habilitar nova ID de transação para evitar IDs duplicadas** no headquarters. Esse recurso foi adicionado ao Commerce versão 10.0.19. Isso ajuda a impedir a criação de IDs de transação sequenciais, garantindo a criação de uma ID exclusiva para cada transação. Para ver mais informações sobre esse recurso, consulte [Evitar IDs de transação duplicadas](../channel-setup-retail.md#ensure-unique-transaction-ids).
