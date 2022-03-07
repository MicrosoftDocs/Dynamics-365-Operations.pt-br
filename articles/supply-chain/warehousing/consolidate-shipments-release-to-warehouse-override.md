---
title: Consolidar remessas quando a política de consolidação de remessa for substituída
description: Este tópico apresenta um cenário em que uma ou mais linhas de venda devem ser liberadas manualmente para o depósito da página Liberar para depósito e a política de consolidação de remessa definida pelo sistema deve ser substituída antes da liberação.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 606f370277b67a65612d81916f4fcc93ca47224e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574176"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden"></a>Consolidar remessas quando a política de consolidação de remessa for substituída

[!include [banner](../includes/banner.md)]

Este tópico apresenta um cenário em que uma ou mais linhas de venda devem ser liberadas manualmente para o depósito da página **Liberar para depósito** e a política de consolidação de remessa definida pelo sistema deve ser substituída antes da liberação. Uma substituição da política de consolidação de remessa poderá ser necessária se, por exemplo, uma ordem que não costume ser consolidada com remessas abertas precise ser consolidada com remessas abertas.

Durante o cenário, você criará um conjunto de ordens de venda e, em seguida, substituirá a política de consolidação de remessa padrão antes de liberar as ordens para o depósito.

## <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configure políticas de consolidação de remessa e filtros de produtos

O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali. Lembre-se de fazer os exercícios antes de continuar este cenário.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crie as ordens de venda para este cenário

1. Acesse **Contas a receber \> Ordens \> Todas as ordens de venda** e crie três ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-002*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Libere as ordens de venda da página Liberar para depósito

Siga estas etapas para substituir a política de consolidação de remessa durante a liberação para o depósito.

1. Acesse **Gerenciamento de depósito \> Liberar para depósito \> Liberar para depósito**.
1. No painel superior, selecione a primeira ordem de venda criada para esse cenário.
1. Selecione **Adicionar** para adicionar a linha à liberação para o depósito. Observe que a política de consolidação de remessa *padrão* é aplicada no painel inferior.
1. No painel inferior, selecione **Selecionar nova política de consolidação de remessa**.
1. Selecione uma política que permita a consolidação com outras remessas abertas da mesma política. Por exemplo, selecione a política *CustomerOrderNo*.
1. Selecione **Liberar para depósito**.
1. Selecione a segunda e a terceira ordens de venda criadas para esse cenário.
1. Selecione **Adicionar** para adicionar as linhas à liberação para o depósito. Observe que a política *padrão* é aplicada no painel inferior.
1. Selecione a segunda linha e, em seguida, no campo **Selecionar nova política de consolidação de remessa**, selecione a política *CustomerOrderNo*.
1. Selecione **Liberar para depósito** para as duas linhas.

## <a name="verify-the-shipments"></a>Verifique as remessas

Duas remessas devem ter sido criadas:

- A primeira remessa contém duas linhas e foi criada usando a política de consolidação de remessa *CustomerOrderNo*.
- A segunda remessa contém uma linha e foi criada usando a política de consolidação de remessa *padrão*.

Siga estas etapas para revisar as remessas que foram criadas.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Localize e selecione a remessa necessária.
1. No campo **Política de consolidação de remessa**, revise a política de consolidação usada quando a remessa foi criada.

## <a name="additional-resources"></a>Recursos adicionais

- [Políticas de consolidação da remessa](about-shipment-consolidation-policies.md)
- [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]