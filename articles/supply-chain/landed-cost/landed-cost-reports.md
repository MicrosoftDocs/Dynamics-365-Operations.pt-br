---
title: Relatórios de custo de entrega
description: Este tópico descreve como localizar e usar os vários tipos de relatórios que estão disponíveis para o módulo de custo de entrega.
author: sherry-zheng
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 565303a4f51d1726c62a85faaf8c4d8692c110fc
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500637"
---
# <a name="landed-cost-reports"></a>Relatórios de custo de entrega

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="outstanding-invoices"></a>Faturas pendentes

O relatório de faturas pendentes contém uma lista de todas as faturas pendentes dos vários níveis de custo associados a cada viagem. Ele é usado para reconciliar a viagem e os custos da viagem junto com a lista de transações do razão regularmente. Após o faturamento dos custos gerais indiretos, eles serão removidos do relatório.

Para gerar um relatório de faturas pendentes, siga estas etapas.

1. Acesse **Custo de entrega \> Relatórios \> Acompanhamento \> Faturas pendentes**.
1. Na caixa de diálogo **Faturas pendentes**, no campo **Por data**, especifique uma data. Qualquer fatura pendente em ou antes dessa data será incluída na saída.
1. Em **Mostrar**, selecione uma das seguintes opções:

    - **Custo não faturado** – inclui custos para remessas faturadas que têm um valor de custo estimado, mas sem custo real.
    - **Estoque não faturado** – inclui custos que foram faturados, mas para os quais a ordem de compra ainda não foi recebida.
    - **Tudo não faturado** – inclua os resultados das opções **Custo não faturado** e **Estoque não faturado**.

1. Defina a opção **Incluir novos custos** como *Sim* para incluir custos que ainda não têm um custo real e para os quais o estoque não foi recebido. Se você defini-la como *Não*, o relatório incluirá somente os custos que foram faturados.
1. Na seção **Exibir**, habilite cada tipo de detalhe que você deseja incluir no relatório.
1. Assim como faz com outros tipos de relatórios no Microsoft Dynamics 365 Supply Chain Management, use a FastTab **Destino** para selecionar o formato de saída do relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management, use a FastTab **Registros a serem incluídos** para limitar ainda mais os registros que serão incluídos no relatório.
1. Selecione **OK** para gerar o relatório.

## <a name="activityprovider-analysis-reports"></a>Relatórios de análise de atividade/provedor

Os relatórios de análise de atividade/provedor permitem que você revise a precisão das estimativas de tempo de cada fornecedor.

Para gerar um relatório de análise de atividade/provedor, siga estas etapas.

1. Dependendo do tipo de relatório que você deseja criar, siga uma destas etapas:

    - Acesse **Custo de entrega \> Relatórios \> Análise de atividade/provedor por atividade**. Nesse caso, as estimativas de tempo serão agrupadas por atividade.
    - Acesse **Custo de entrega \> Relatórios \> Análise de atividade/provedor por provedor**. Nesse caso, as estimativas de tempo serão agrupadas por provedor.

    A caixa de diálogo **Análise de atividade/provedor por atividade** ou a caixa de diálogo **Análise de atividade/provedor por provedor** é exibida. As duas caixas de diálogo fornecem as mesmas opções.

1. Assim como faz com outros tipos de relatórios no Supply Chain Management , use a FastTab **Destino** para selecionar o formato de saída do relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management, use a FastTab **Registros a serem incluídos** para limitar ainda mais os registros que serão incluídos no relatório.
1. Selecione **OK** para gerar o relatório.

## <a name="voyage-costing-reports"></a>Relatórios de custos de viagem

Os relatórios de custos de viagem mostram o custo dos itens e os custos de importação por fólio, contêiner de remessa ou viagem, dependendo das opções que você seleciona ao gerar o relatório. Cada relatório de custos de viagem permite que você exiba o custo estimado de uma viagem versus o custo real e pode ser dividido pelos vários fatores de identificação.

Para gerar um relatório de custos de viagem, siga estas etapas.

1. Dependendo do tipo de relatório que você deseja criar, siga uma destas etapas:

    - Acesse **Custo de entrega \> Relatórios \> Avaliação de custo \> Avaliação de custo de viagens por custo individual**. Nesse caso, a opção de custo individual mostrará os custos de importação por área de custo por código de tipo de custo.
    - Acesse **Custo de entrega \> Relatórios \> Avaliação de custo \> Avaliação de custo de viagens por categoria de relatório**. Nesse caso, o custo de importação será dividido nas várias categorias de relatório. Os tipos de custo são agrupados por categorias de relatório.

    A caixa de diálogo **Avaliação de custo de viagens por custo individual** ou a caixa de diálogo **Avaliação de custo de viagens por categoria de relatório** é exibida. Essas caixas de diálogo são semelhantes. As diferenças são observadas no restante deste procedimento.

1. Se você tiver aberto a caixa de diálogo **Avaliação de custo de viagens por categoria de relatório**, no campo **Custo**, selecione um dos seguintes valores:

    - **Valor de custo** – o valor é calculado usando custos automáticos ou criados manualmente na área de custo.
    - **Estimado** – após o recebimento das mercadorias, o custo estimado será definido.
    - **Real** – após o faturamento da ordem, o custo real será definido como o custo na fatura.
    - **Melhor** – o sistema usará a que for mais precisa entre as três opções anteriores. (É recomendável selecionar essa opção.)

1. Defina a opção **Por item** como *Sim* para mostrar o custo de cada item. Defina-a como *Não* para mostrar custos por viagem.
1. Na seção **Exibir**, selecione as categorias para dividir o custo.
1. Na seção **Dimensões**, selecione as dimensões a serem incluídas no relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management , use a FastTab **Destino** para selecionar o formato de saída do relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management, use a FastTab **Registros a serem incluídos** para limitar ainda mais os registros que serão incluídos no relatório.
1. Selecione **OK** para gerar o relatório.

## <a name="shipping-container-receipts-list"></a>Lista de recebimentos de contêiner de remessa

A lista de recebimentos do contêiner de remessa contém todas as quantidades não recebidas que vencem em ou antes de uma data esperada. A equipe de depósito pode usar este relatório para identificar as mercadorias esperadas em um contêiner de remessa. Ele também pode ser usado para validar mercadorias manualmente à medida que elas são recebidas em um contêiner de remessa.

Para gerar uma lista de recebimentos do contêiner de remessa, siga estas etapas.

1. Acesse **Custo de entrega \> Relatórios \> Acompanhamento \> Lista de recebimentos do contêiner de remessa**.
1. Na caixa de diálogo **Lista de recebimentos do contêiner de remessa**, no campo **Data esperada**, especifique uma data. As quantidades não recebidas em ou antes dessa data serão incluídas na saída.
1. Na seção **Dimensões**, selecione as dimensões a serem incluídas no relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management , use a FastTab **Destino** para selecionar o formato de saída do relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management, use a FastTab **Registros a serem incluídos** para limitar ainda mais os registros que serão incluídos no relatório.
1. Selecione **OK** para gerar o relatório.

## <a name="expected-delivery-report"></a>Relatório de entrega esperada

O relatório de entrega esperado contém informações básicas sobre a viagem, o contêiner de remessa, o fólio, os itens e a data de entrega esperada.

Para gerar um relatório de entrega esperada, siga estas etapas.

1. Acesse **Custo de entrega \> Relatórios \> Acompanhamento \> Entrega esperada**.
1. Na caixa de diálogo **Entrega esperada**, no campo **Data esperada**, selecione a data em que a entrega das mercadorias para o depósito de destino final é esperada. Qualquer linha de viagem com uma data esperada em ou antes dessa data, e ainda não recebida, será incluída na saída.
1. Opcional: no campo **Conta de fornecedor**, selecione uma conta de fornecedor para incluir somente as entregas de um fornecedor específico.
1. Na seção **Dimensões**, selecione as dimensões a serem incluídas no relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management , use a FastTab **Destino** para selecionar o formato de saída do relatório.
1. Assim como faz com outros tipos de relatórios no Supply Chain Management, use a FastTab **Registros a serem incluídos** para limitar ainda mais os registros que serão incluídos no relatório.
1. Selecione **OK** para gerar o relatório.
