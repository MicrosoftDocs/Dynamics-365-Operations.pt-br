---
title: Cancelar uma nota fiscal de cliente (projeto) (Brasil)
description: É possível cancelar uma fatura de cliente para um projeto.
author: sndray
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa65109aecce60b443a5b35b0c219ed24f701932
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811265"
---
# <a name="cancel-a-customer-fiscal-document-project-brazil"></a>Cancelar uma nota fiscal de cliente (projeto) (Brasil)

[!include [banner](../../includes/banner.md)]

É possível cancelar uma fatura de cliente para um projeto. Ao cancelar uma fatura de projeto, uma fatura de projeto negativa é criada. Ao lançar a fatura de projeto negativa, as faturas de projeto originais e negativas são marcadas como canceladas e todas as transações contábeis e financeiras são revertidas. A transação original é informada como cancelada nos livros fiscais, mas a transação negativa não é informada nos livros fiscais. Não é possível cancelar uma fatura de projeto que está liquidada parcialmente ou completamente. Além de isso, não é possível cancelar uma fatura de projeto, se a data de lançamento da fatura cair em um período fiscal que está fechado. Esta tarefa usa a empresa de demonstração BRMF.

1. Vá para Gerenciamento e contabilidade de projeto > Projetos > Todos os projetos.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique em Diário de faturas.
5. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Fatura com um valor de '04000006'.
6. Clique em Cancelamento de fatura.
7. Clique em Sim.
8. No campo Código de motivo, insira ou selecione um valor.
9. No campo Data de cancelamento da fatura, insira uma data.
10. Clique em Cancelar fatura do projeto.
11. Selecione Não no campo Imprimir fatura.
12. Clique em OK.
13. Clique em OK.
14. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]