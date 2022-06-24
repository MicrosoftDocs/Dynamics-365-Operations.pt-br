---
title: Funcionários de manutenção responsáveis
description: Este artigo explica como configurar funcionários de manutenção responsáveis no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9535be3161253e88083b5add7ac55c12364aa383
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875582"
---
# <a name="responsible-maintenance-workers"></a>Funcionários de manutenção responsáveis

[!include [banner](../../includes/banner.md)]

 

Os funcionários de manutenção responsáveis podem ser relacionados a tipos de ativo, ativos, locais funcionais, categorias de tipo de trabalho de manutenção, tipos de trabalho de manutenção, variações de tipo de trabalho de manutenção e comércios. Eles podem ser usados em ordens de trabalho e em solicitações de manutenção para indicar uma preferência sobre os funcionários de manutenção que devem ser responsáveis por uma ordem de serviço. (No entanto, esses funcionários de manutenção não são necessariamente os mesmos funcionários agendados para a realização da ordem de serviço). O uso dessa funcionalidade é opcional. Por exemplo, pode ser usado para selecionar funcionários ou grupos de responsáveis para tipos de trabalho ou áreas de trabalho específicos.

Durante o ciclo de vida da ordem de serviço ou um ciclo de vida de solicitação de manutenção, os funcionários de manutenção responsáveis podem ser alterados ou atualizados. Essa alteração ou atualização pode ser relacionada a, por exemplo, uma alteração no estado de ciclo de vida de solicitação de manutenção ou o estado de ciclo de vida da ordem de serviço.

A configuração na página **Funcionários de manutenção responsáveis** *não* é usada durante o agendamento da ordem de serviço.

> [!NOTE]
> No Asset Management, você também pode configurar os funcionários de manutenção *preferidos* que podem ser alocados a ordens de serviço durante o agendamento de ordens de serviço.

Antes de configurar funcionários de manutenção responsáveis, você deverá configurar os funcionários e grupos de funcionários de manutenção que devem estar disponíveis para seleção. Para obter informações sobre como configurar funcionários e grupos de funcionários de manutenção, consulte [Funcionários de manutenção e grupos de funcionários](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Configurar funcionários de manutenção responsáveis

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhadores** \> **Funcionários de manutenção responsáveis**.
2. Selecione **Novo** para criar um registro.
3. Primeiro, crie uma configuração de funcionário de manutenção responsável ou grupo de funcionários de manutenção responsáveis, onde você definirá somente o campo **Grupo de funcionários de manutenção responsáveis** e/ou o campo **Funcionário responsável**. Deixe os demais campos em branco. Essa configuração padrão será usada durante o agendamento da ordem de serviço caso nenhuma outra combinação mais específica corresponda ao conteúdo da ordem de serviço.

    > [!NOTE]
    > Durante a criação de uma solicitação de manutenção, quando um funcionário de manutenção responsável ou grupo de funcionários de manutenção responsáveis for disponibilizado para seleção na página **Todas as solicitações de manutenção**, o Asset Management examina todos os registros de funcionário de manutenção responsável para verificar se há uma correspondência possível. Ele sempre verifica a combinação mais específica primeiro. Ou seja, o Asset Management primeiro verifica a existência uma correspondência para o campo **Comércio**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho de manutenção**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho de manutenção** e assim em diante. Como você pode perceber no layout da página, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência (primeiro **Comércio**, então **Variação de tipo de trabalho de manutenção**, **Tipo de trabalho de manutenção**, **Categoria de tipo de trabalho de manutenção**, **Local funcional**, **Ativo** e, por fim, **Tipo de ativo**). Se nenhuma correspondência for encontrada, o registro padrão que não possui nenhuma seleção nos sete campos é usado.

A ilustração a seguir mostra um exemplo da página **Funcionários de manutenção responsáveis**.

![Página de funcionários de manutenção responsáveis.](media/08-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]