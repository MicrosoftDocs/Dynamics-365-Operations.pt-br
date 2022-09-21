---
title: Consolide remessas liberando para o depósito da bancada de planejamento de carga
description: Este artigo apresenta um cenário em que várias ordens são liberadas para o depósito na mesma carga e são consolidadas automaticamente em remessas.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 862b4b4121effa3ed0a2134924b2152c8a982110
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428081"
---
# <a name="consolidate-shipments-by-releasing-to-warehouse-from-the-load-planning-workbench"></a>Consolide remessas liberando para o depósito da bancada de planejamento de carga

[!include [banner](../includes/banner.md)]

Este artigo apresenta um cenário em que várias ordens são liberadas para o depósito na mesma carga e são consolidadas automaticamente em remessas.

## <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

O cenário neste artigo faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configure políticas de consolidação de remessa e filtros de produtos

O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali. Lembre-se de fazer os exercícios antes de continuar este cenário.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crie as ordens de venda para este cenário

Comece criando uma coleção de ordens de venda com as quais possa trabalhar. Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS). A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.

Acesse **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.

### <a name="create-order-set-1"></a>Crie o conjunto de ordens 1

#### <a name="sales-order-1-1"></a>Ordem de venda 1-1

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.

#### <a name="sales-order-1-2"></a>Ordem de venda 1-2

1. Crie uma ordem de venda com as seguintes configurações:

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

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a>Use a bancada de planejamento de carga para criar cargas e liberá-las para o depósito

Siga estas etapas para criar uma carga para cada conjunto de ordens que você criou para esse cenário e, em seguida, liberá-lo para o depósito.

1. Acesse **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. Na guia **Linhas de venda**, localize e selecione todas as linhas da ordem de venda em um dos conjuntos de ordens criados para esse cenário.
1. No Painel de Ações, na guia **Oferta e demanda**, selecione **Adicionar \> Para nova carga** para adicionar as linhas de ordem selecionadas a uma nova carga.
1. Na caixa de diálogo **Atribuição de modelo de carga**, no campo **ID do modelo de carga**, selecione um modelo de carga, como *Modelo de Carga Padrão*.
1. Selecione **OK** para fechar a caixa de diálogo. 
1. Na seção **Cargas**, localize e selecione a carga que você acabou de criar.
1. Selecione **Liberar \> Liberar para depósito** para liberar a carga selecionada para o depósito.
1. Repita este procedimento para os outros três conjuntos de ordens criados para esse cenário.

## <a name="verify-the-shipments"></a>Verifique as remessas

O procedimento a seguir permite verificar as remessas que foram criadas ou atualizadas como resultado da consolidação de remessa. Use-o para revisar cada conjunto de ordens criado para esse cenário e, em seguida, analisar as subseções a seguir para garantir que você obtenha os resultados esperados.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Localize e selecione a remessa necessária.
1. Se uma política de consolidação foi usada quando a remessa foi criada ou atualizada, você verá a mesma no campo **Política de consolidação de remessa**.

### <a name="release-order-set-1-in-one-load"></a>Libere o conjunto de ordens 1 em uma carga

Duas remessas devem ter sido criadas:

- A primeira remessa contém três linhas e foi criada usando a política de consolidação de remessa *CustomerMode*.
- A segunda remessa, que não usa o modo de entrega *Airways*, foi criada usando a política de consolidação de remessa *CustomerOrderNo*.

### <a name="release-order-set-2-in-one-load"></a>Libere o conjunto de ordens 2 em uma carga

Três remessas devem ter sido criadas:

- A primeira remessa contém os itens *inflamáveis*.
- Cada uma das outras duas remessas contém uma linha com o item *Explosivo*.

### <a name="release-order-set-3-in-one-load"></a>Libere o conjunto de ordens 3 em uma carga

Duas remessas devem ter sido criadas:

- A primeira remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *1*.
- A segunda remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *2*.

### <a name="release-order-set-4-in-one-load"></a>Libere o conjunto de ordens 4 em uma carga

Quatro remessas devem ter sido criadas:

- As linhas de duas ordens de conta de cliente *US-003* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de duas ordens de conta de cliente *US-004* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de ordens de venda 4-5 e 4-6 da conta de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de ordens de venda 4-7 e 4-8 da conta de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *CrossOrder*.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de políticas de consolidação de remessa](about-shipment-consolidation-policies.md)
- [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]