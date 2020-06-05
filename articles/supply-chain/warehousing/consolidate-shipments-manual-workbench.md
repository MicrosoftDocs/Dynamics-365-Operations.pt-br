---
title: Consolidar remessas usando a bancada de consolidação de remessa
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas em remessas posteriormente usando a bancada de consolidação de remessas.
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
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383713"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolidar remessas usando a bancada de consolidação de remessa

[!include [banner](../includes/banner.md)]

Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas em remessas posteriormente usando a bancada de consolidação de remessas.

## <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configure políticas de consolidação de remessa e filtros de produtos

O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali. Lembre-se de fazer os exercícios antes de continuar este cenário.

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a>Ative o recurso de consolidação de remessa manual

Para usar o recurso *Consolidação de remessa manual*, você precisa ativá-lo no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Consolidação de remessa manual*

Como foi mencionado em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md), você também deve ativar o recurso *Consolidar remessa* para poder criar políticas. No entanto, você já deve ter concluído essa etapa.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crie as ordens de venda para este cenário

Comece criando uma coleção de ordens de venda com as quais possa trabalhar. Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS). A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.

Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.

### <a name="create-order-set-1"></a>Crie o conjunto de ordens 1

#### <a name="sales-orders-1-1-and-1-2"></a>Ordens de venda 1-1 e 1-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

#### <a name="sales-order-1-3"></a>Ordem de venda 1-3

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Modo de entrega:** *10*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.
1. Adicione uma segunda linha da ordem com as seguintes configurações:

    - **Número do item:** *A0002* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a segunda linha da ordem.

### <a name="create-order-set-2"></a>Crie o conjunto de ordens 2

#### <a name="sales-orders-2-1-and-2-2"></a>Ordens de venda 2-1 e 2-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-002*
    - **Modo de entrega:** *Airwa-Air*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.
1. Adicione uma segunda linha da ordem com as seguintes configurações:

    - **Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)
    - **Quantidade:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a segunda linha da ordem.

### <a name="create-order-set-3"></a>Crie o conjunto de ordens 3

#### <a name="sales-orders-3-1-and-3-2"></a>Ordens de venda 3-1 e 3-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Requisição de cliente:** *1*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

#### <a name="sales-orders-3-3-and-3-4"></a>Ordens de venda 3-3 e 3-4

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Requisição de cliente:** *2*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

### <a name="create-order-set-4"></a>Crie o conjunto de ordens 4

#### <a name="sales-orders-4-1-and-4-2"></a>Ordens de venda 4-1 e 4-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-003*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

#### <a name="sales-orders-4-3-and-4-4"></a>Ordens de venda 4-3 e 4-4

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-004*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

#### <a name="sales-orders-4-5-and-4-6"></a>Ordens de venda 4-5 e 4-6

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-007*
    - **Local:** *6*
    - **Depósito:** *61*
    - **Grupo:** *ShipCons*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

#### <a name="sales-orders-4-7-and-4-8"></a>Ordens de venda 4-7 e 4-8

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-007*
    - **Local:** *6*
    - **Depósito:** *61*
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

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a>Consolidar as remessas usando a bancada de consolidação de remessa

1. Vá para **Gerenciamento de depósito \> Liberar para depósito \> Bancada de consolidação de remessa**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consulta, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:

    - **Tabela:** *Ordens de venda*
    - **Campo:** *Ordem de venda*
    - **Critérios:** Insira uma lista separada por vírgulas dos números de ordem de venda para cada conjunto de ordens criado para esse cenário.

1. Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.
1. No Painel de Ações, selecione **Consolidar remessas**.
1. Selecione todas as remessas e, depois, no Painel de Ações, selecione **Consolidar**.

## <a name="verify-the-shipments"></a>Verifique as remessas

O procedimento a seguir permite verificar as remessas que foram criadas ou atualizadas como resultado da consolidação de remessa. Use-o para revisar cada conjunto de ordens criado para esse cenário e, em seguida, analisar as subseções a seguir para garantir que você obtenha os resultados esperados.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Localize e selecione a remessa necessária.
1. Se uma política de consolidação foi usada quando a remessa foi criada ou atualizada, você verá a mesma no campo **Política de consolidação de remessa**.

### <a name="related-shipments-for-order-set-1"></a>Remessas relacionadas para o conjunto de ordens 1

Duas remessas devem ter sido criadas:

- A primeira remessa contém três linhas e foi criada usando a política de consolidação de remessa *CustomerMode*.
- A segunda remessa, que não usa o modo de entrega *Airways*, foi criada usando a política de consolidação de remessa *CustomerOrderNo*.

### <a name="related-shipments-for-order-set-2"></a>Remessas relacionadas para o conjunto de ordens 2

Três remessas devem ter sido criadas:

- A primeira remessa contém itens *Inflamáveis*.
- Cada uma das outras duas remessas contém uma linha com o item *Explosivo*.

### <a name="related-shipments-for-order-set-3"></a>Remessas relacionadas para o conjunto de ordens 3

Duas remessas devem ter sido criadas:

- A primeira remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *1*.
- A segunda remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *2*.

### <a name="related-shipments-for-order-set-4"></a>Remessas relacionadas para o conjunto de ordens 4

Quatro remessas devem ter sido criadas:

- As linhas de duas ordens de cliente *US-003* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de duas ordens de cliente *US-004* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de ordens de venda 4-5 e 4-6 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de ordens de venda 4-7 e 4-8 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *CrossOrder*.

## <a name="additional-resources"></a>Recursos adicionais

- [Políticas de consolidação da remessa](about-shipment-consolidation-policies.md)
- [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md)
