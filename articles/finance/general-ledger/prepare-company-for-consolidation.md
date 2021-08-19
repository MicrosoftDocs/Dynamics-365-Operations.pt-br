---
title: Preparar uma entidade legal para o processo de consolidação
description: Durante uma consolidação, você reúne transações de vários conjuntos de contas de entidade legal em um único conjunto de contas de entidade legal. Este tópico explica como preparar uma entidade legal para uma consolidação.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: a1ffbf79cdccab457b1aee1bc0f1d963bca49b3e390187c6be5da475f278a3d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720493"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Preparar uma entidade legal para o processo de consolidação

[!include [banner](../includes/banner.md)]

Durante uma consolidação, você reúne transações de vários conjuntos de contas de entidade legal em um único conjunto de contas de entidade legal. Este tópico explica como preparar uma entidade legal para uma consolidação.

> [!NOTE]
> É recomendável usar o Management Reporter para Microsoft Dynamics 365 Finance para combinar os resultados financeiros para várias entidades legais em um formato consolidado. O Management Reporter permite criar relatórios financeiros consolidados nas entidades legais, usar o Excel para importar dados de consolidação de outras fontes e traduzir os valores em qualquer número de moedas de relatório sem a necessidade de executar o processo de consolidação no Dynamics 365 Finance.

É possível imprimir relatórios, como demonstrativos financeiros, da entidade legal consolidada. No entanto, não é possível usar a entidade legal consolidada para transações diárias.

Você pode consolidar dados das entidades legais que usam bancos de dados que não são a entidade legal consolidada. Esse processo de consolidação é conhecido como uma *consolidação de importação*. Como alternativa, as entidades legais podem usar o mesmo banco de dados que a entidade legal consolidada. Esse processo de consolidação é conhecido como uma *consolidação online*.

A entidade legal consolidada coleta os resultados e saldos das subsidiárias. Para preparar uma entidade legal consolidada para uma consolidação, siga estas etapas.

1. Acesse **Contabilidade \> Configuração \> Organização \> Entidades legais**.
2. Selecione **Novo** para criar a entidade legal que será a entidade legal consolidada.
3. Marque a caixa de seleção **Usar para processo de consolidação financeira** e insira informações sobre a entidade legal consolidada. Insira essas informações exatamente como deseja que apareçam nos demonstrativos financeiros da entidade legal consolidada.
4. Feche a página.
5. Selecione a entidade legal consolidada no campo do canto superior direito da página e, depois, selecione **OK**.
6. Acesse **Contabilidade \> Configuração \> Razão**.
7. Selecione o plano de contas, o calendário fiscal, a moeda contábil, uma moeda de relatório opcional e o tipo de taxa de câmbio padrão para a entidade legal consolidada. 
8. Acesse **Contabilidade \> Configuração \> Moedas \> Taxas de câmbio de moedas**.
9. Configure as taxas de câmbio de moedas nos períodos relevantes para as moedas das entidades legais de subsidiárias.
10. Feche a página.
11. Se a entidade legal consolidada tiver subsidiárias que usem moedas estrangeiras, siga estas etapas:

    1. Acesse **Contabilidade \> Configuração \> Lançamento \> Contas para transações automáticas**.
    2. No campo **Tipo de lançamento**, selecione uma conta apropriada:

        - Se a entidade legal tiver subsidiárias estrangeiras que sejam financeira ou operacionalmente interdependentes da entidade legal pai, selecione uma conta apropriada para o tipo de lançamento **Conta de lucros e perdas para diferenças de consolidação**.
        - Se estiver consolidando uma subsidiária que seja financeira ou operacionalmente independente da entidade legal principal, ou uma entidade legal que contenha os resultados de várias subsidiárias que sejam financeira ou operacionalmente independentes da entidade legal principal, e se estiver usando métodos de conversão para consolidar os dados, selecione uma conta apropriada para o tipo de lançamento **Conta de saldo para diferenças de consolidação**.

    3. No campo **Conta principal**, selecione as contas principais que devem ser usadas para ajustes de reavaliação de moeda estrangeira.
    4. Feche a página.

    Ao criar a entidade legal consolidada antecipadamente em um período, você poderá reavaliar os valores de moeda estrangeira à medida que as taxas de câmbio mudarem durante o período de consolidação.

A entidade legal consolidada agora está configurada para o trabalho periódico **Consolidar**. Você pode fazer uma consolidação de importação ou uma consolidação online.

- Para fazer uma consolidação de importação, acesse **Contabilidade \> Periódico \> Consolidar \> Consolidar \[importar de\]**.
- Para fazer uma consolidação online, acesse **Contabilidade \> Periódico \> Consolidar \> Consolidar \[Online\]**.

> [!NOTE]
> Para poder processar a consolidação, prepare as entidades legais subsidiárias para a consolidação. Para obter mais informações, consulte [Configurar uma entidade legal subsidiária para consolidação](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]