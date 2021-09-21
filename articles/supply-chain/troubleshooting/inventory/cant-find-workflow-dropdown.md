---
title: Não é possível localizar a caixa de diálogo suspensa "Fluxo de trabalho" para diários de estoque
description: Você não consegue localizar a caixa de diálogo suspensa "Fluxo de trabalho" na página do diário ou as operações de fluxo de trabalho relacionadas não estão disponíveis
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8b2772a75c2388f4d78a459f9dfb72ad7c1be4ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475562"
---
# <a name="you-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Não é possível localizar a caixa de diálogo suspensa "Fluxo de trabalho" para diários de estoque

## <a name="symptoms"></a>Sintomas

Você não consegue localizar a caixa de diálogo suspensa **Fluxo de trabalho** na página do diário ou as operações de fluxo de trabalho relacionadas não estão disponíveis.

Esse problema pode ocorrer por três motivos, conforme descrito nas seções a seguir.

## <a name="resolution-1"></a>Resolução 1

Se o problema se aplica a todos os usuários, ele pode estar ocorrendo porque o fluxo de trabalho de aprovação não foi atribuído ao nome de diário. Para corrigir o problema, siga estas etapas.

1. Acesse **Gerenciamento de estoque &gt; Configuração &gt; Nomes de diário &gt; Estoque**.
1. No painel de lista, selecione um nome de diário para abrir suas configurações.
1. Na FastTab **Geral**, defina a opção **Fluxo de trabalho de aprovação** como *Sim*. Se você for solicitado a confirmar a alteração, selecione **Sim**.
1. No campo **Fluxo de trabalho**, selecione o fluxo de trabalho que você deseja usar para o nome de diário selecionado.

## <a name="resolution-2"></a>Resolução 2

Se o seu fluxo de trabalho usa código personalizado, podem ocorrer problemas após a atualização do sistema. Por exemplo, no fluxo de trabalho do diário, o botão **Enviar** pode estar esmaecido, assim, não é possível selecioná-lo para aprovar um envio.

Se o botão **Enviar** estiver esmaecido, seu fluxo de trabalho pode ter sido personalizado, o que significa que o método do fluxo de trabalho, `canSubmitToWorkflow()` em `FormDataUtil`, foi estendido. Para corrigir esse problema, altere a forma como você estende o método do `canSubmitToWorkflow()` para usar a estrutura no exemplo a seguir.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

## <a name="resolution-3"></a>Resolução 3

Se o problema se aplica somente a alguns usuários específicos, esses usuários talvez não tenham os privilégios de segurança necessários para executar operações de fluxo de trabalho em diários de estoque. Verifique se cada usuário afetado tem o privilégio de segurança *Manter fluxo de trabalho do diário de estoque*. Por padrão, esse privilégio é atribuído a um direito que tem o mesmo nome e esse direito é aplicado às funções *Trabalhador de depósito* e *Gerente de depósito*.
