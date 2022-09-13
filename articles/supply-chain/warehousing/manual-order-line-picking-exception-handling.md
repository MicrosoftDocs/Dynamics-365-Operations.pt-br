---
title: Tratar manualmente vendas e transferir exceções de separação de linhas
description: Este artigo descreve como administradores podem separar manualmente (ou desfazer separação) transações de estoque para corrigir problemas causados por dados corrompidos em ordens de venda e de transferência.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403639"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Tratar manualmente vendas e transferir exceções de separação de linhas

[!include [banner](../includes/banner.md)]

A manipulação manual de exceções de separação de linhas de venda e de transferência permite que os administradores corrijam problemas causados por dados corrompidos de ordens de venda e de transferência. Ela permite a usuários confiáveis separar manualmente (ou desfazer a separação) de transações de estoque relacionadas a linhas de ordens de transferência e de venda enquanto os processos de depósito já estão em andamento.

A funcionalidade descrita aqui deve ser usada somente nos casos em que o sistema não pode concluir o processamento da pilha de processos de depósito da maneira usual. Por padrão, somente os usuários com uma função de administrador do sistema têm permissão para usá-la. No entanto, você pode conceder acesso a ela atribuindo o privilégio *Separar linhas de vendas manualmente* a outras funções conforme necessário.

## <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Para poder usar os recursos descritos neste artigo, eles devem estar ativados no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status dos recursos e ativá-los. No espaço de trabalho **Gerenciamento de recursos**, os recursos são listados usando os seguintes nomes:

- *Serviço de separação manual de linha de venda para administrador ou usuários confiáveis semelhantes*<br>(A partir do Supply Chain Management versão 10.0.25, este recurso é obrigatório e não pode ser desativado.)
- *Serviço de separação manual de linha de transferência para administradores ou usuários confiáveis semelhantes*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Corrigir transações relacionadas a linhas de ordem de venda ou de transferência

Use o procedimento a seguir para corrigir transações relacionadas a linhas de ordem de venda ou de transferência.

1. Siga uma destas etapas, dependendo do tipo de ordem a ser corrigida:

    - Para corrigir uma transação relacionada a uma ordem de venda, acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Separar linhas de vendas manualmente**.
    - Para corrigir uma transação relacionada a uma ordem de transferência, acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Separar linhas de transferência manualmente**.

1. Na página **Separar linhas de vendas manualmente** ou **Separar linhas de transferência manualmente**, use os filtros na parte superior da grade para localizar a linha que você está procurando e, depois, selecione a linha da ordem de destino na grade superior.
1. Use as guias **Transações de estoque**, **Linhas de carga**, **Linhas de trabalho** e **Linhas de contêiner** na seção inferior para exibir mais informações sobre a linha selecionada. As informações nessas guias fornecem uma visão geral básica dos processos de depósito relacionados e seus status.
1. No Painel de Ações, selecione **Separar** para abrir a linha de ordem selecionada na página **Separar** para transações de estoque. Você pode concluir essa etapa mesmo para linhas de ordem que já foram liberadas para o depósito. (Em geral, as linhas de ordem que foram liberadas para o depósito não podem ser abertas na página **Separar**.)

    > [!NOTE]
    > Você pode receber vários avisos ao abrir a página **Separar**. Execute qualquer ação que esses avisos recomendem. Por exemplo, você pode receber um aviso sobre linhas de ordem que estão vinculadas ao trabalho de depósito. Nesse caso, faz sentido tentar cancelar o trabalho usando a funcionalidade padrão [Cancelar trabalho](cancel-warehouse-work.md) antes de fazer a correção manualmente.

1. Selecione a linha na grade **Transações** e, depois, selecione **Adicionar linha de separação** na barra de ferramentas **Transações**.
1. A linha selecionada é movida para a grade **Separação**. Defina os valores apropriados para as colunas sem as informações necessárias. (Por exemplo, especifique o local e a placa de licença para os quais o item deve ser separado/removido.)
1. Selecione **Confirmar seleção de todos** na barra de ferramentas **Linhas de separação**.

## <a name="correct-load-line-quantities"></a>Corrigir as quantidades de linhas de carga

Use o procedimento a seguir para corrigir uma quantidade da linha de carga.

1. Siga uma destas etapas, dependendo do tipo de ordem a ser corrigida:

    - Para corrigir uma transação relacionada a uma ordem de venda, acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Separar linhas de vendas manualmente**.
    - Para corrigir uma transação relacionada a uma ordem de transferência, acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Separar linhas de transferência manualmente**.

1. Na página **Separar linhas de vendas manualmente** ou **Separar linhas de transferência manualmente**, use os filtros na parte superior da grade para localizar a linha que você está procurando e, depois, selecione a linha da ordem de destino na grade superior.
1. Na guia **Carregar linhas** da seção inferior, selecione **Corrigir linhas de carga manualmente** na barra de ferramentas.
1. Na página **Corrigir linhas de carga manualmente**, na grade **Transações de estoque**, examine as transações de estoque relacionadas à linha de carga selecionada.
1. Na grade superior, corrija as quantidades de linha de carga nas seguintes colunas, conforme necessário:

    - **Quantidade de trabalho criado**
    - **Quantidade separada**
    - **Quantidade planejada de distribuição integrada**

    O sistema validará todas as alterações feitas nessas colunas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
