---
title: Políticas de consolidação da remessa
description: Este tópico fornece uma visão geral da funcionalidade que fornece uma configuração flexível das políticas de consolidação de remessa.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate, WHSShipConsolidationTemplateApply, WHSShipConsolidationTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: f895b13b2e11d4cb341f80b3cfeb40ed998ccfc4
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654187"
---
# <a name="shipment-consolidation-policies"></a>Políticas de consolidação da remessa

O processo de consolidação de remessa que usa políticas de consolidação de remessa permite a consolidação de remessa automatizada durante a liberação automatizada e manual para o depósito. A consolidação automatizada que estava disponível antes da apresentação deste recurso tinha campos codificados e se baseava no campo **Remessa consolidada em liberação para depósito** que foi definido para um depósito.

As políticas de consolidação de remessa são usadas para a seguinte funcionalidade:

- O trabalho em lotes automatizado de liberação para o depósito
- O comando **Liberar para o depósito** em uma ordem de venda ou ordem de transferência
- A página **Liberar para o depósito** dedicada
- O comando **Liberar para o depósito** na página **Bancada do planejamento de carga**
- A consolidação manual das remessas nas páginas **Consolidar remessas** e **Bancada de consolidação de remessas**

Antes da apresentação de políticas de consolidação de remessa, a função de consolidação existia como uma configuração no nível de depósito. Todas as ordens para todos os clientes de um único depósito eram tratadas como se tivessem os mesmos requisitos de consolidação. As políticas de consolidação de remessa adicionam suporte a cenários em que organizações diferentes têm requisitos diferentes para a consolidação de remessa.

As consultas são usadas para identificar a política de consolidação de remessa que se aplica e, depois, um conjunto editável de campos determina como as linhas de carga são agrupadas no nível de remessa. (Esse padrão é semelhante ao padrão seguidos pelos modelos de onda.) Além disso, uma opção **Consolidar com remessas existentes** foi adicionada a cada política. Quando essa opção está ativada, o procedimento *Liberar para o depósito* localiza remessas para consolidação pesquisando entre as remessas existentes criadas com base na mesma política de consolidação. Nesse caso, o sistema selecionará uma remessa ou um carga existente em vez de criar uma nova. No entanto, o sistema só fará a consolidação com remessas existentes que tenham um status de *Aberto*. As remessas que pertençam a uma liberação da onda com o status *Liberado* ou superior não serão consideradas como destinos para a consolidação.

Quando as políticas de consolidação de remessa são disponibilizadas, a configuração **Remessa consolidada em liberação para depósito** que estava disponível anteriormente na página de configuração de **Depósitos** é ocultada. Para ajudar você a fazer a transição para o novo recurso de consolidação de remessa, uma função na página **Políticas de consolidação de remessa** cria uma política padrão que inclui automaticamente a configuração antiga para os depósitos existentes. Após a criação da política padrão, a configuração **Remessa consolidada em liberação para depósito** na página de configuração de **Depósitos** não será mais considerada.

Você pode usar a página **Liberar para o depósito** para substituir manualmente a política de consolidação aplicável da mesma forma que pode substituir as política de atendimento.

Você pode usar o comando **Liberar \> Liberar para o depósito** na página **Bancada do planejamento de carga** para criar cargas de saída baseadas em ordens de venda e linhas de ordem de transferência antes de fazer a liberação para o depósito. Essas cargas usam a mesma lógica de consolidação que foi apresentada juntamente com a consolidação das políticas de remessa.

Você pode usar a página **Bancada de consolidação de remessas** para consolidar as remessas existentes que ainda não foram confirmadas, mas que já foram liberadas para o depósito. Essa funcionalidade oferece suporte a cenários em que o processo de liberação automatizado, que tem sua própria consolidação de remessa, é executado várias vezes por dia, mas que possíveis consolidações adicionais sejam identificadas manualmente antes que a remessa para as transportadoras seja concluída durante o processo de confirmação. Essa funcionalidade permite que você consolide remessas de saída criadas a partir da ordem de venda ou de linhas de ordem de transferência a qualquer momento depois que as remessas sejam liberadas para o depósito, mas antes que sejam confirmadas.

A página **Bancada de consolidação de remessas** funciona como a bancada de criação de carga, no qual é possível avaliar várias remessas ao mesmo tempo e atribuir uma ordem não consolidada a uma remessa específica. Você pode aplicar modelos de consolidação de remessa para avaliar as consolidações propostas várias vezes e confirmá-las. Algumas regras são implementadas para evitar a consolidação não autorizada e para avisar sobre possíveis erros.

## <a name="overview-of-new-functionality"></a>Visão geral da nova funcionalidade

Esta seção descreve as páginas, os comandos e os recursos que foram alterados ou adicionados quando você ativa e usa o recurso *Políticas de consolidação de remessa*.

### <a name="shipment-consolidation-policies-page"></a>Página de políticas de consolidação da remessa

As políticas são diferenciadas por tipo de ordem de serviço. O tipo **Ordens de venda** representa as remessas de _Ordem de venda_ e o tipo **Ordens de transferência** representa as remessas de _Saída de transferência_.

Cada política de consolidação de remessa tem uma consulta que define quando ela é aplicada e um número de sequência que determina a ordem de execução. A consolidação é aplicada a cada combinação exclusiva dos campos selecionados. Um parâmetro adicional fornecido é usado para a consolidação com remessas existentes (abertas). As políticas são avaliadas e aplicadas toda vez que uma nova remessa é criada (antes do processamento da onda).

Se um algum campo obrigatório estiver ausente na política ou se ela incluir algum campo proibido, a política será marcada como inválida na seção **Selecionada**. As listas de campos obrigatórios e proibidos são codificadas e podem ser estendidas.

A lista a seguir mostra os campos obrigatórios. Como as remessas são sempre divididas com base nesses campos, não é possível agrupar várias remessas com valores diferentes para esses campos.

- Em ordens de venda:

    - **Número da conta:** _WHSShipmentTable.AccountNum_
    - **Destinatário da entrega:** _WHSShipmentTable.DeliveryName_
    - **Endereço postal (RecId):** _WHSShipmentTable.DeliveryPostalAddress_
    - **Depósito:** _WHSShipmentTable.InventLocationId_

- Para ordens de transferência:

    - **Do depósito:** _InventTransferTable.InventLocationIdFrom_
    - **Para o depósito:** _InventTransferTable.InventLocationIdTo_

Os campos a seguir não estão disponíveis para todos os tipos de documento. Esses campos não são visíveis na interface do usuário (IU) e não podem ser usados para a consolidação.

- **ID da Remessa:** _WHSShipmentTable.ShipmentId_
- **Status:** _WHSShipmentTable.ShipmentStatus_
- **Política de consolidação de remessa:** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Tipo de transação de trabalho:** _WHSShipmentTable.WorkTransType_
- **ID da Onda:** _WHSShipmentTable.WaveId_
- **ID da Carga:** _WHSShipmentTable.LoadId_
- **ID da Remessa:** _WHSLoadLine.ShipmentId_
- **ID da Carga:** _WHSLoadLine.LoadId_

Por padrão, ao criar uma política, o conjunto de campos obrigatórios é usado como campos de consolidação. No entanto, você pode modificar a lista usando os botões de seta para a esquerda e seta para a direita. (O processo lembra o processo de seleção de métodos em modelos de onda.)

Os valores selecionados pelos usuários para esses campos serão usados para todas as remessas recém-criadas ou serão adicionados a remessas existentes durante a consolidação com essas remessas. Quando duas remessas têm o mesmo valor para um campo selecionado para a consolidação dessas remessas, as remessas são consolidadas. O mesmo princípio se aplica a todos os campos de consolidação subsequentes selecionados. Se os valores forem diferentes, a segunda remessa será descartada e será selecionada para uma nova remessa. O processo de consolidação automatizada consiste na criação de todas as combinações exclusivas de valores para os campos de consolidação de remessa e depois na atribuição de uma remessa à combinação relevante.

Os campos não selecionados são ignorados durante o processo de consolidação. Se duas remessas tiverem valores diferentes para um campo não selecionado, o campo será limpo (ou seja, será definido como em branco). Se ambas as remessas tiverem o mesmo valor para um campo não selecionado, o campo será preenchido.

A lista de campos de consolidação (ou seja, os campos que serão limpos se tiverem valores diferentes) é codificada. A lista contém todos os campos inicializados a partir de uma ordem de venda ou linha de ordem de transferência quando uma nova remessa é criada. Em outras palavras, se um campo não for inicializado a partir de uma ordem de venda ou de linha de ordem de transferência, ele será ignorado quando novos dados forem adicionados a uma remessa existente.

### <a name="release-to-warehouse-page"></a>Página Liberar para o depósito

- Um novo campo na grade inferior mostra a política de consolidação aplicada.
- Um novo botão permite selecionar e/ou substituir manualmente a política de consolidação.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>O comando Liberar para o depósito na página Bancada do planejamento de carga

- A lógica foi ajustada para usar as políticas de consolidação aplicadas.
- As remessas agora estão consolidadas em somente uma única carga.

### <a name="consolidate-shipments-page"></a>Página Consolidar remessas

- A pesquisa por remessas semelhantes (ou seja, candidatas à consolidação) foi alterada para usar os campos selecionados na política de consolidação de remessa.
- Os campos que tenham valores diferentes em remessas diferentes são agora definidos como em branco. (Anteriormente, eram usados os valores da remessa "base" selecionada.)

### <a name="shipment-consolidation-workbench-page"></a>Página Bancada de consolidação de remessas

- A nova funcionalidade replica o processo de consolidação manual em uma escala maior.
- Agora você pode abrir esta página no menu **Liberar para o depósito** no módulo **Gerenciamento de depósito**.
- O algoritmo analisa as remessas existentes que ainda não foram enviadas. Em seguida, ele propõe consolidação com base nos campos selecionados nas políticas de consolidação.

## <a name="comparison-of-functionality"></a>Comparação de funcionalidades

A tabela a seguir resume como a consolidação de remessa funciona quando você não usa políticas de consolidação de remessa e quando usa.

| Sem políticas de consolidação de remessa | Com políticas de consolidação de remessa |
|---|----|
| Não Aplicável | As remessas de venda ou transferência selecionadas para consolidação devem ter a mesma política de consolidação que a remessa que está sendo criada ou devem ser atribuídas a uma remessa aberta (quando a opção **Consolidar com remessas existentes** estiver ativada). |
| O procedimento *Liberar para o depósito* não pesquisa entre as remessas existentes para encontrar uma remessa para a consolidação. Somente as remessas criadas por uma instância atual do procedimento *Liberar para o depósito* são usadas para encontrar uma remessa para a consolidação. | Se a opção **Consolidar com remessas existentes** estiver ativada para uma política de consolidação que está sendo usada no momento, o procedimento *Liberar para o depósito* pesquisará entre as remessas existentes que foram criadas com base na mesma política de consolidação para encontrar uma remessa para a consolidação. Portanto, se você tiver duas políticas, uma remessa criada com base na política 2 nunca será consolidada com uma remessa criada com base na política 1. |
| Não Aplicável | Se uma lista de campos de política de consolidação estiver vazia ou se uma política não puder ser encontrada, uma nova remessa será criada para cada ordem de venda ou linha de ordem de transferência. |
| O campo de consolidação a seguir define a combinação exclusiva de valores que é usada para consolidar remessas para uma *linha de transferência*. (Todos os outros campos são ignorados.)<ul><li>Número da ordem (OrderNum)</li></ul> | Os campos de consolidação a seguir definem a combinação exclusiva de valores que é usada para consolidar remessas para uma *linha de transferência*. (Todos os outros campos são ignorados.)<ul><li>Número da ordem (OrderNum)</li><li>Destinatário da entrega (DeliveryName)</li><li>Endereço postal (DeliveryPostalAddress)</li><li>Código ISO do país (CountryRegionISOCode)</li><li>Endereço (Address)</li><li>Site (InventSiteId)</li><li>Depósito (InventLocationId)</li><li>Transportadora (CarrierCode)</li><li>Serviço de transportadora (CarrierServiceCode)</li><li>Modo de entrega (ModeCode)</li><li>Grupo de transportadoras (CarrierGroupCode)</li><li>Condições de entrega (DlvTermId)</li></ul>Esses campos são os únicos campos disponíveis e inicializados quando uma nova remessa é criada. |
| Os campos de consolidação a seguir definem a combinação exclusiva de valores que é usada para consolidar remessas para uma *linha de venda*. (Todos os outros campos são ignorados.)<ul><li>Número da ordem (OrderNum)</li><li>Referência de cliente (CustomerRef)</li><li>Requisição de cliente (CustomerReq)</li><li>Condições de entrega (DlvTermId)</li></ul> | Os campos de consolidação a seguir definem a combinação exclusiva de valores que é usada para consolidar remessas para uma *linha de venda*. (Todos os outros campos são ignorados.)<ul><li>Número da ordem (OrderNum)</li><li>Número da conta (AccountNum)</li><li>Destinatário da entrega (DeliveryName)</li><li>Endereço postal (DeliveryPostalAddress)</li><li>Código ISO do país (CountryRegionISOCode)</li><li>Endereço (Address)</li><li>Site (InventSiteId)</li><li>Depósito (InventLocationId)</li><li>Transportadora (CarrierCode)</li><li>Serviço de transportadora (CarrierServiceCode)</li><li>Modo de entrega (ModeCode)</li><li>Grupo de transportadoras (CarrierGroupCode)</li><li>ID do Agente (BrokerCode)</li><li>Direção (LoadDirection)</li><li>Condições de entrega (DlvTermId)</li><li>Referência de cliente (CustomerRef)</li><li>Requisição de cliente (CustomerReq)</li></ul>Esses campos são os únicos campos disponíveis e inicializados quando uma nova remessa é criada. |
| Não Aplicável | Os seguintes campos de consolidação são obrigatórios para uma *linha de venda* e não podem ser removidos:<ul><li>Número da conta (AccountNum)</li><li>Destinatário da entrega (DeliveryName)</li><li>Endereço postal (DeliveryPostalAddress)</li><li>Depósito (InventLocationId)</li></ul>Por padrão, esses campos serão atribuídos quando uma nova política for criada. Eles não podem ser removidos. |
| O procedimento *Liberação de cargas para o depósito* na página **Bancada de planejamento de carga** usa seu próprio código separado para criar remessas e ondas. | As políticas de consolidação de remessa são aplicadas para determinar quais campos devem ser avaliados para consolidação. As remessas agora são consolidadas em somente uma única carga. |
| Você seleciona manualmente **Consolidar remessas** na página **Todas as remessas** e, em seguida, seleciona a remessa "base" de destino. O filtro sugerirá todas as remessas existentes que tenham valores correspondentes a vários campos-chave. | Você seleciona manualmente **Consolidar remessas** na página **Todas as remessas** e, em seguida, seleciona a remessa "base" de destino. O sistema sugerirá outras remessas existentes fazendo a correspondência dos valores de vários campos-chave configurados para as política de consolidação de remessa relevantes. |
| Você pode usar o comando **Consolidar remessas** na página **Todas as remessas** para uma única remessa. | A página **Bancada de consolidação de remessas** ajuda você a encontrar um conjunto de remessas que ainda não estejam em um estado Enviado. Essas remessas são analisadas com base em vários campos-chave configurados nas políticas de consolidação de remessa. As remessas em que haja correspondência nos valores desses campos serão sugeridas para consolidação.<p>Você pode manter a consolidação manualmente, removendo remessas das consolidações sugeridas e/ou adicionando remessas a elas. Vários tipos de erros podem ocorrer, mas é possível substituir alguns deles.</p> |
| **Observação de design:** o procedimento *Liberação automática de ordens para o depósito* divide as linhas de venda em grupos. Cada grupo tem seu próprio valor exclusivo de **ReleaseToWarehouseId** e é processado separadamente pelo procedimento *Liberar para depósito*. Esse procedimento cria um trabalho independentemente da configuração de intervalo de trabalho. | **Observação de design:** o procedimento *Liberação automática de ordens para o depósito* atribui o mesmo valor de **ReleaseToWarehouseId** a todas as linhas de venda que estão sendo processadas. Todas as linhas de venda são processadas pelo procedimento *Liberar para o depósito* ao mesmo tempo. Para garantir o comportamento anterior, você deve configurar o intervalo de trabalho por ID de remessa. |

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md)
