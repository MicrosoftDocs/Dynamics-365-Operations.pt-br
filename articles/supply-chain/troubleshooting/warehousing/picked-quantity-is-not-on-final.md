---
title: Não é possível confirmar uma remessa porque os itens não foram separados
description: Não é possível confirmar uma remessa porque os itens não foram separados
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b57d3151852c9a2880185b7d9414e4246b7efb6429fcfce04c7cdae4ee00e37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760915"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Não é possível confirmar uma remessa porque os itens não foram separados

Código de erro: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Sintomas

Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:

> Alguns dos itens necessários para carregar %1 ainda não foram separados e movidos para a localização de remessa final.

Portanto, não é possível confirmar a remessa da carga.

## <a name="cause"></a>Causa

A carga ou a remessa não pode ser confirmada no estado atual porque pode existir uma das seguintes condições:

- O trabalho relacionado ainda não foi separado e movido para o local de remessa final.
- A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.
- A diretiva de localização foi configurada com o local de embalagem como o local final de envio enquanto usa o modelo de conteinerização em ciclo.

## <a name="resolution"></a>Resolução

A carga ou a remessa estão em um estado no qual a confirmação de remessa falha. Para corrigir esse problema, execute uma das seguintes tarefas:

- Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.
- Cancele os IDs de trabalho que foram criados com a localização de embalagem como o local final de envio, reconfigure a diretiva de localização e libere a carga novamente.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem

Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Selecione a carga para a qual a remessa não pode ser confirmada.
1. Na FastTab **Linhas de carga**, selecione a linha de carga.
1. Anote o valor do campo **Quantidade de trabalho criado**.
1. No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.
1. Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.
1. Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Cancele os IDs de trabalho que foram criados com a localização de embalagem como o local final de envio, reconfigure a diretiva de localização e libere a carga novamente

Use o procedimento a seguir para cancelar os IDs de trabalho que possuem o local de embalagem como o local final de colocação com contêiner automatizado no local.

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.
1. A caixa de diálogo **cancelar trabalho** é aberta. No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar. O ID de trabalho selecionado deve ter um valor **Status de trabalho** de *Aberto*, *Em andamento* *Cancelado*, *Combinado* ou *Fechado*.
1. Selecione **OK**.
1. Selecione **Sim** para confirmar que você deseja cancelar o trabalho.
1. Repita este procedimento para as outras IDs de trabalho conforme necessário.

Para obter mais informações, consulte [Cancelar trabalho de depósito para tratamento de exceções](../../warehousing/cancel-warehouse-work.md).

Use o procedimento a seguir para reconfigurar a diretiva de localização para que ela não use o local de embalagem como local final de envio quando a conteinerização automatizada for configurada para o modelo de ciclo.

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.
1. Selecione a diretiva de localização que você está usando para a conteinerização automatizada.
1. Na barra de ferramentas da FastTab **Ações de diretiva de localização**, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consulta, na guia **Intervalo**, encontre a linha em que **Campo** esteja definida para o *Perfil de localização* e verifique se o campo **Critérios** para essa linha não está definido como um perfil de localização que tenha um **Tipo de localização** de *Embalagem*. Ajuste o campo **Critérios** para corrigir o local final da colocação.

Use o procedimento a seguir para relançar a carga e criar IDs de trabalho com o local de envio final correto.

1. Acesse **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. Na seção **Cargas**, encontre a carga que precisa ser liberada.
1. Na barra de ferramentas da seção **Cargas**, selecione **Liberar \> Liberar para depósito** para liberar a carga selecionada para o depósito.
1. Repita este procedimento para as outras cargas conforme necessário.
