---
title: Marca de estoque com a Otimização de Planejamento
description: Este artigo fornece informações sobre as opções disponíveis para marcar estoque em ordens confirmadas ao usar a Otimização de Planejamento.
author: t-benebo
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 55c83cdbc144f194fe80e8281a35ec7ff43d551e
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219927"
---
# <a name="inventory-marking-with-planning-optimization"></a>Marca de estoque com a Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Este artigo fornece informações sobre as opções disponíveis para marcar estoque em ordens confirmadas ao usar a Otimização de Planejamento.

A *marcação* é usada para vincular fornecimento e demanda. Ela é semelhante à *vinculação*, que indica como o planejamento mestre espera cobrir a demanda. Do ponto de vista de planejamento, a principal diferença é que a marcação é mais permanente do que a vinculação.

A marcação foi introduzida para oferecer suporte a cenários de avaliação de custo especiais para PEPS (primeiro a entrar, primeiro a sair) e UEPS (último a entrar, primeiro a sair). No entanto, agora também é usada para alguns cenários não relacionados à avaliação de custo. A marcação entre fornecimento e demanda é opcional e quase permanente. Ela pode ser removida manualmente por um usuário ou pode ser removida executando um detalhamento de linha da ordem de venda em que a opção **Remover marcação** está selecionada.

A vinculação é controlada pelo planejamento mestre durante a cobertura para vincular a demanda ao fornecimento necessário. Ela pode ser atualizada para cada execução de planejamento a fim de otimizar o fornecimento necessário para cobrir a demanda. Quando o planejamento mestre atualiza as informações de vinculação, ele respeita todas as marcações existentes.

A vinculação começa incluindo marcação relevante, reservas disponíveis e reservas sob encomenda, na seguinte sequência:

1. Marcação entre demanda e fornecimento
1. Reservas disponíveis
1. Reservas sob encomenda

Quando você confirma uma ordem planejada, a caixa de diálogo **Confirmação** fornece um campo **Atualizar marcação** que é usado para definir as opções de marcação para as ordens criadas durante a confirmação. Selecione um dos seguintes valores:

- *Não* – Nenhuma marcação de estoque é aplicada.
- *Padrão* – A marcação de estoque é atualizada de acordo com a vinculação. Uma ordem de necessidade (demanda) é marcada em relação a uma ordem de atendimento (fornecimento). Se alguma quantidade permanecer na ordem de atendimento, ela não será marcada, e as informações de referência serão deixadas em branco. Por exemplo, se uma ordem de venda para 100 ea for vinculada a uma ordem de compra para 150 ea, as informações de referência serão atribuídas somente à ordem de venda.
- *Estendido* – Tanto a ordem de necessidade (demanda) quanto a de atendimento (fornecimento) são marcadas, independentemente de qualquer quantidade restante na ordem de atendimento. Por exemplo, se uma ordem de venda para 100 ea for vinculada a uma ordem de compra para 150 ea, as informações de referência serão atribuídas à ordem de venda e à ordem de compra.
- *Padrão de nível único* – a marcação de nível único é usada. A marcação de nível único marca somente o item principal, não os componentes da lista de materiais (BOM). Portanto, você pode manter flexível a atribuição de componentes para ordens de produção após a confirmação. A marcação de nível único permite que o sistema otimize as alterações de demanda de última hora. Na marcação de nível único *padrão*, as ordens de requisito são marcadas em relação às ordens de processamento, mas estas não serão marcadas se tiverem quantidade pendente.
- *Nível único estendido* – a marcação de nível único é usada. Na marcação de nível único *estendido*, as ordens de requisito são marcadas em relação às ordens de processamento, e estas serão sempre marcadas, tenham ou não quantidade pendente.

Para definir a opção de marcação padrão para o sistema, acesse **Planejamento mestre \> Configuração \> Parâmetros do planejamento mestre**. Em seguida, na guia **Atualização padrão**, defina o campo **Atualizar marcação** como sua opção preferencial.

> [!NOTE]
> As opções *Padrão de nível único* e *Nível único estendido* só estarão disponíveis se o recurso *Automação de fornecimento sob encomenda* for ativado no sistema. Para obter mais informações sobre esse recurso e sobre como ativá-lo, consulte [Automação de fornecimento sob encomenda](../make-to-order-supply-automation.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
