---
title: Consolidar remessas quando são liberadas para o depósito usando a liberação automática de ordens de venda
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito no mesmo procedimento periódico automatizado de liberação para o depósito.
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
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 373b6bf6219ef76bacef3c67a816aec4c084c405
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383711"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a>Consolidar remessas quando são liberadas para o depósito usando a liberação automática de ordens de venda

[!include [banner](../includes/banner.md)]

Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito no mesmo procedimento periódico automatizado de liberação para o depósito. As ordens serão automaticamente consolidadas em remessas, com base em regras definidas como políticas de consolidação de remessa.

Durante o cenário, você criará conjuntos de ordens de venda e liberará cada conjunto para o depósito. Em seguida, você verificará as remessas criadas ou atualizadas durante a consolidação da remessa, com base nas políticas configuradas.

## <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Configure políticas de consolidação de remessa e filtros de produtos

O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali. Lembre-se de fazer os exercícios antes de continuar este cenário.

## <a name="create-the-sales-orders-for-this-scenario"></a>Crie as ordens de venda para este cenário

Comece criando uma coleção de ordens de venda com as quais possa trabalhar. Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS). A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.

Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.

### <a name="create-order-set-1"></a>Crie o conjunto de ordens 1

#### <a name="sales-order-1-1"></a>Ordem de venda 1-1

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

#### <a name="sales-order-1-2"></a>Ordem de venda 1-2

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Modo de entrega:** *Airwa-Air*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

#### <a name="sales-order-1-3"></a>Ordem de venda 1-3

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Modo de entrega:** *10*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

1. Adicione uma segunda linha da ordem com as seguintes configurações:

    - **Número do item:** *A0002* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

### <a name="create-order-set-2"></a>Crie o conjunto de ordens 2

#### <a name="sales-orders-2-1-and-2-2"></a>Ordens de venda 2-1 e 2-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-002*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)
    - **Quantidade:** *1.00*

1. Adicione uma segunda linha da ordem com as seguintes configurações:

    - **Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)
    - **Quantidade:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

### <a name="create-order-set-3"></a>Crie o conjunto de ordens 3

#### <a name="sales-order-3-1"></a>Ordem de venda 3-1

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-002*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)
    - **Quantidade:** *1.00*

1. Adicione uma segunda linha da ordem com as seguintes configurações:

    - **Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)
    - **Quantidade:** *1.00*
    - **Modo de entrega:** *Airwa-Air*

> [!NOTE]
> Essa ordem é idêntica às duas ordens criadas para o conjunto de ordens 2. No entanto, ela está listada como seu próprio conjunto de ordens, pois será liberada separadamente mais adiante neste cenário.

### <a name="create-order-set-4"></a>Crie o conjunto de ordens 4

#### <a name="sales-order-4-1"></a>Ordem de venda 4-1

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Requisição de cliente:** *1*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

### <a name="create-order-set-5"></a>Crie o conjunto de ordens 5

#### <a name="sales-orders-5-1-and-5-2"></a>Ordens de venda 5-1 e 5-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Requisição de cliente:** *2*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

#### <a name="sales-order-5-3"></a>Ordem de venda 5-3

1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Requisição de cliente:** *1*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

### <a name="create-order-set-6"></a>Crie o conjunto de ordens 6

#### <a name="sales-orders-6-1-and-6-2"></a>Ordens de venda 6-1 e 6-2

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-003*
    - **Requisição de cliente:** *2*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>Ordens de venda 6-3 e 6-4

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-004*
    - **Requisição de cliente:** *1*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>Ordens de venda 6-5 e 6-6

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-007*
    - **Local:** *6*
    - **Depósito:** *61*
    - **Grupo:** *ShipCons*

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>Ordens de venda 6-7 e 6-8

1. Crie duas ordens de venda idênticas com as seguintes configurações:

    - **Conta de cliente:** *US-007*
    - **Local:** *6*
    - **Depósito:** *61*
    - **Grupo:** Deixe esse campo em branco.

1. Adicione uma linha da ordem com as seguintes configurações:

    - **Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)
    - **Quantidade:** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Liberação automática de ordens de venda para o depósito

Para cada conjunto de ordens de venda criadas anteriormente, você concluirá um procedimento para liberação automática para o depósito. Em cada caso, você trabalhará no [procedimento básico de liberação para depósito](#release-procedure) que é fornecido aqui.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Procedimento básico de liberação para depósito

Para cada conjunto de ordens de venda criadas anteriormente, você concluirá os três procedimentos descritos nas subseções a seguir.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>Atualize o modelo de onda que será usado durante a liberação

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. Defina o campo **Tipo de modelo de onda** como *Remessa*.
1. Localize e selecione o modelo de onda associado ao depósito que você usou nos conjuntos de ordens criados para esse cenário. Por exemplo, se você usou depósito *24*, selecione o modelo de onda **Padrão de 24 remessas**. Se você usou depósito *61*, selecione o modelo de onda **61 remessas**.
1. No Painel de Ações, selecione **Editar**.
1. Defina a opção **Processar onda na liberação para o depósito** como *Não*.

#### <a name="release-to-the-warehouse"></a>Libere para o depósito

1. Vá para **Gerenciamento de depósito \> Liberar para depósito \> Liberação automática de ordens de venda**.
1. Defina o campo **Quantidade para liberação** como *Todos*.
1. Na Guia Rápida **Registros para incluir**, selecione **Filtro** para abrir a caixa de diálogo de consulta.
1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:

    - **Tabela:** *Ordem de venda*
    - **Tabela derivada:** *Ordem de venda*
    - **Campo:** *Ordem de venda*
    - **Critérios:** Insira uma lista separada por vírgulas dos números da ordem de venda no conjunto de ordens desejado.

1. Selecione **OK** para salvar a consulta.
1. Selecione **OK** para iniciar o procedimento *Liberar automaticamente para o depósito*.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>Avalie a remessa criada ou atualizada

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Localize e selecione a remessa necessária.
1. Se uma política de consolidação foi usada quando a remessa foi criada ou atualizada, você verá a mesma no campo **Política de consolidação de remessa**.

### <a name="release-sales-orders-from-order-set-1"></a>Libere ordens de venda do conjunto de ordens 1

Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 1.

Quando terminar, você verá que duas remessas foram criadas:

- A primeira remessa contém três linhas e foi criada usando a política de consolidação de remessa *CustomerMode*.
- A segunda remessa, que não usa o modo de entrega *Airways*, foi criada usando a política de consolidação de remessa *CustomerOrderNo*.

### <a name="release-sales-orders-from-order-set-2"></a>Libere ordens de venda do conjunto de ordens 2

Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 2.

Quando terminar, você verá que três remessas foram criadas:

- A primeira remessa contém itens *Inflamáveis*.
- Cada uma das outras duas remessas contém uma linha com o item *Explosivo*.

### <a name="release-sales-orders-from-order-set-3"></a>Libere ordens de venda do conjunto de ordens 3

Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 3.

Quando terminar, você verá que as seguintes ações ocorreram:

- Uma remessa existente (a remessa que foi criada quando o conjunto de ordens 2 foi liberado para o depósito) foi atualizada. Uma linha com o item *Inflamável* foi adicionada.
- Uma nova remessa foi criada que contém o item *Explosivo*.

### <a name="release-sales-orders-from-order-set-4"></a>Libere ordens de venda do conjunto de ordens 4

Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 4.

Quando terminar, você verá que uma remessa existente (em que o campo **Requisição do cliente** está definido como *1*) foi atualizada. Uma nova linha foi adicionada.

### <a name="release-sales-orders-from-order-set-5"></a>Libere ordens de venda do conjunto de ordens 5

Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 5.

Quando terminar, você verá que as seguintes ações ocorreram:

- Uma remessa existente (em que o campo **Requisição do cliente** é definido como *1*) foi atualizada. Uma linha da ordem de venda 5-3 (em que o campo **Requisição do cliente** está definido como *1*) foi adicionado.
- Uma nova remessa foi criada, na qual as linhas das ordens de venda 5-1 e 5-2 são agrupadas em uma remessa.

### <a name="release-sales-orders-from-order-set-6"></a>Libere ordens de venda do conjunto de ordens 6

Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 6.

Quando terminar, você verá que quatro remessas foram criadas:

- As linhas de duas ordens de cliente *US-003* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de duas ordens de cliente *US-004* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de ordens de venda 6-5 e 6-6 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.
- As linhas de ordens de venda 6-7 e 6-8 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *CrossOrder*.

## <a name="additional-resources"></a>Recursos adicionais

- [Políticas de consolidação da remessa](about-shipment-consolidation-policies.md)
- [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md)
