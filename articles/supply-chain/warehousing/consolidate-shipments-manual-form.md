---
title: Consolide as remessas manualmente usando a página Consolidar remessas
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas posteriormente usando a página Consolidar remessas.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: ac60bef797d8e0bbe0d20f1585d5c3c0163f8788
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986783"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Consolide as remessas manualmente usando a página Consolidar remessas

[!include [banner](../includes/banner.md)]

Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas posteriormente usando a página **Consolidar remessas**.

## <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configure políticas de consolidação de remessa e filtros de produtos

O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali. Lembre-se de fazer os exercícios antes de continuar este cenário.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crie as ordens de venda para este cenário

Comece criando uma coleção de ordens de venda com as quais possa trabalhar. Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS). A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.

Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.

### <a name="create-sales-orders-1-and-2"></a>Criar as ordens de venda 1 e 2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-007*
    - **Grupo:** *ShipCons*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

### <a name="create-sales-orders-3-and-4"></a>Criar as ordens de venda 3 e 4

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-007*
    - **Grupo:** Deixe esse campo em branco.

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

## <a name="release-the-orders-to-the-warehouse"></a>Libere as ordens para o depósito

Siga estas etapas para liberar cada ordem de venda criada para esse cenário para o depósito.

1. Vá para **Contas a receber \> Ordens \> Todas as ordens de venda**.
1. Encontre e selecione a ordem de venda a ser liberada.
1. No Painel de Ações, na guia **Depósito**, selecione **Ações \> Liberar para depósito** para liberar a ordem de venda selecionada.
1. Repita este procedimento para todas as outras ordens de venda criadas para esse cenário.

## <a name="consolidate-shipments"></a>Consolidar remessas

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Localize e selecione uma remessa que foi criada quando a ordem de venda 1 foi liberada para o depósito. (o campo **Política de consolidação de remessa** deve ser definido como *Grupo de ordens*.)
1. No Painel de Ações, na guia **Remessas**, selecione **Remessas \> Consolidar remessas**.
1. Verifique as remessas sugeridas para consolidação. Somente uma remessa com a mesma política deve ser sugerida para consolidação.
1. Feche a página **Consolidação de remessa**.
1. Localize e selecione uma remessa que foi criada quando a ordem de venda 3 foi liberada para o depósito. (o campo **Política de consolidação de remessa** deve ser definido como *Padrão*.)
1. No Painel de Ações, na guia **Remessas**, selecione **Remessas \> Consolidar remessas**.
1. Verifique se não há remessas sugeridas para consolidação.
1. Selecione **Mostrar filtros**.
1. No painel **Filtros**, remova o filtro **Número da ordem** e selecione **Aplicar**.
1. Verifique as remessas sugeridas para consolidação. Somente uma remessa com a mesma política deve ser sugerida para consolidação.

## <a name="additional-resources"></a>Recursos adicionais

- [Políticas de consolidação da remessa](about-shipment-consolidation-policies.md)
- [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md)