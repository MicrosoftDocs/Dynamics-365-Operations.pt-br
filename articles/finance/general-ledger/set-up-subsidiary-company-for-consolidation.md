---
title: Configurar uma entidade legal subsidiária para consolidação
description: Este tópico explica como trabalhar com planos de contas para empresas de consolidação.
author: jinniew
manager: AnnBe
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 4ffe0ac0b11a3f58ca4a893d8786f04b4067b270
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975523"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Configurar uma entidade legal subsidiária para consolidação

[!include [banner](../includes/banner.md)]

O método usado para preparar contas subsidiárias para a consolidação depende, em partes, da extensão para a qual a estrutura do plano de contas na entidade legal subsidiária reflete o plano de contas na entidade legal consolidada.

Antes de iniciar uma consolidação como parte do fechamento do período, execute as atividades preparatórias para o fechamento, mas não feche as contas das subsidiárias até que a consolidação esteja concluída. Para saber mais sobre o fechamento no fim do período, consulte [Fechar a contabilidade no fim do período](close-general-ledger-at-period-end.md) e [Fechar o ano fiscal](tasks/close-fiscal-year.md).

> [!NOTE]
>  É recomendável usar o Management Reporter para Microsoft Dynamics 365 Finance para combinar os resultados financeiros para várias entidades legais em um formato consolidado. O Management Reporter permite criar relatórios financeiros consolidados nas entidades legais, usar o Excel para importar dados de consolidação de outras fontes e traduzir os valores em qualquer número de moedas de relatório sem a necessidade de executar o processo de consolidação no Dynamics 365 Finance.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Mapear as contas principais subsidiárias para as contas principais consolidadas

Se o plano de contas da entidade legal subsidiária não seguir o plano de contas na entidade legal consolidada, você poderá mapear as contas principais na subsidiária para as contas principais na entidade legal consolidada.

1. Na *Entidade legal subsidiária*, vá para **Contabilidade \> Configuração** \> **Plano de contas \> Plano de contas**.
2. Selecione um plano de contas. Na guia rápida **Contas principais**, selecione uma conta principal e então selecione **Editar**.
3. Selecione cada conta principal subsidiária que deve ser mapeada para consolidar uma conta principal. Na guia rápida **Geral**, no campo **Conta de consolidação**, insira a conta da entidade legal consolidada para a qual o saldo ou as transações da conta principal subsidiária selecionada devem ser transferidos. Você pode inserir a mesma conta principal consolidada para várias contas subsidiárias.

    > [!NOTE]
    > Se os tipos de conta principais das contas subsidiárias que estão mapeadas forem diferentes dos tipos de conta principais de contas na entidade legal consolidada, os valores das contas que tem um tipo de conta principal de **Total** serão substituídos durante a consolidação.

4. Prepare relatórios e demonstrativos financeiros para a entidade legal consolidada que se baseiem em dimensões financeiras. Siga estas etapas para mapear as dimensões financeiras usadas nas contas da subsidiária para as dimensões financeiras na entidade legal consolidada:

    1. Na *Entidade legal subsidiária*, vá para **Contabilidade \> Configuração \> Dimensões financeiras \> Dimensões financeiras**, selecione uma dimensão financeira e selecione **Valores da dimensão financeira**.
    2. Selecione o valor da dimensão financeira para mapear para um valor da dimensão financeira na entidade legal consolidada.
    3. Na guia rápida **Geral**, no campo **Dimensão do grupo**, insira a dimensão financeira na entidade legal consolidada. Durante a consolidação, essa dimensão financeira será atribuída a transações e saldos que usem a dimensão financeira selecionada na entidade legal subsidiária. As dimensões financeiras que você inserir aqui devem ser usadas na entidade legal consolidada. Você pode atribuir a dimensão financeira que é usada como a dimensão financeira do grupo em várias dimensões financeiras subsidiárias.

5. Se você estiver fazendo uma consolidação online, siga estas etapas para garantir que as transferências ocorram como pretendidas:

    1. Na *Entidade legal consolidada*, vá para **Contabilidade \> Periódico \> Consolidar \> Consolidar \[Exportar para\]** para abrir a página **Consolidar \[Online\]**.
    2. Na guia **Critérios**, marque a caixa de seleção **Usar conta de consolidação**.
    3. Na guia **Dimensões financeiras**, selecione as dimensões financeiras apropriadas.
    4. Para cada dimensão financeira que você selecionar, insira um número no campo **Ordem dos segmentos** para indicar a ordem em que as dimensões devem ser exibidas

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Manter o mesmo plano de contas da entidade legal subsidiária e consolidada

As contas principais na entidade legal subsidiária podem ter o mesmo números de conta e a mesma estrutura para o plano de conta das contas principais na entidade legal consolidada. Nesse caso, não será necessário mapear manualmente as contas principais das subsidiárias para as contas principais na entidade legal consolidada.

Antes de iniciar a consolidação, siga estas etapas.

1. Na *Entidade legal consolidada*, vá para **Contabilidade \> Periódico \> Consolidar \> Consolidar \[Exportar para\]** para abrir a página **Consolidar \[Online\]**.
2. Marque a caixa de seleção **Usar conta de consolidação**. Durante a consolidação, as transações e os saldos serão transferidos automaticamente para a conta corrente.

> [!NOTE]
> Se as contas não corresponderem, a consolidação será interrompida e você receberá uma mensagem.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Criar um plano de contas para a entidade legal consolidada, com base em um plano de contas existente

Você pode executar uma consolidação mesmo que um plano de contas ainda não tenha sido criado para a entidade legal consolidada.

- Se tiver planejado a estrutura da conta que quer usar na entidade legal consolidada, você poderá mapear as contas subsidiárias a esta estrutura.
- Se você não mapear nenhuma conta subsidiária, as contas na entidade legal consolidada serão automaticamente criadas quando os dados subsidiários forem transferidos para a entidade legal consolidada. Essas contas são baseadas na conta principal. Os dados subsequentes são acumulados nas contas na entidade legal consolidada que tem o mesmo número de conta que as contas subsidiárias.

Independentemente de você ter mapeado contas, desmarque a caixa de seleção **Usar conta de consolidação** na página **Consolidar** na entidade legal consolidada antes de executar esse tipo de consolidação.

> [!NOTE]
> Você pode usar esse método para criar um plano de contas na entidade legal consolidada no plano de contas em uma das entidades legais subsidiárias. (Para obter mais informações, consulte [Grupos de contas de consolidação e contas adicionais de consolidação](../budgeting/consolidation-account-groups-consolidation-accounts.md).) Em seguida, atribua um princípio de conversão de consolidação apropriado a cada conta principal consolidada e execute a consolidação para todas as entidades legais subsidiárias.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]