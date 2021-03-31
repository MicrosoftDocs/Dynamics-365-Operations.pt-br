---
title: Configurar, criar e gerenciar custos de absorção
description: Este tópico fornece informações sobre como configurar, criar e gerenciar custos de absorção para o Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a4c18bd47f6d7a45fce2ca1061b999c67fa77ca1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219867"
---
# <a name="set-up-create-and-manage-absorption-costs"></a>Configurar, criar e gerenciar custos de absorção 

[!include [banner](../includes/banner.md)]

Você pode calcular e lançar os custos diretos e indiretos incorridos nas ordens de produção de um período fiscal. Os custos finais da fabricação são registrados no razão no final do período fiscal. Você pode calcular os custos de absorção alocando os custos totais de fabricação para os produtos fabricados durante um período fiscal.

## <a name="set-up-a-number-sequence-for-absorption-costs"></a>Configurar uma sequência numérica para custos de absorção

Use este procedimento para configurar o código da sequência numérica para diários de absorção de custos.

1.  Clique em **Controle de produção** \> **Configuração** \> **Custos de absorção** \> **Parâmetros**.

2.  No campo **Código da sequência numérica**, selecione o código de sequência numérica a ser usado para o diário de absorção de custo.

## <a name="set-up-a-cost-center-for-absorption-costs"></a>Configurar um centro de custo para custos de absorção

Use este procedimento para configurar um tipo de custo para um centro de custo. Você pode usar a página **Centro de custo** para configurar centros de custos para custos de absorção. 

1.  Clique em **Controle de produção** \> **Configuração** \> **Custos de absorção** \> **Centros de custo**.

2.  Selecione o centro de custo a ser usado para lançar custos de absorção.

3.  No campo **Tipo de custo**, selecione o tipo de custo do centro de custo.

## <a name="set-up-journal-names-for-absorption-costs"></a>Configurar nomes de diário para custos de absorção

Use este procedimento para configurar nomes de diários para custos de absorção.

1.  Clique em **Controle de produção** \> **Configuração** \> **Custos de absorção** \> **Nomes de diário**.

2.  Pressione CTRL+N para criar um registro.

3.  No campo **Nome**, digite um nome para o diário.  

    > [!NOTE]
    > O campo <STRONG>Tipo de diário</STRONG> é atualizado com o tipo de diário padrão que é usado para custos de absorção. O tipo de diário padrão é <STRONG>Custos indiretos</STRONG>.

4.  No campo **Descrição** informe uma breve descrição do diário.

5.  No campo **Série de comprovante**, selecione o código de sequência numérica a ser usado para o diário.

6.  No campo **Seleção por**, indique se um novo comprovante será selecionado durante a entrada ou após o lançamento.

7.  No campo **Nível de detalhe**, selecione o método a ser usado para resumir os detalhes do diário.

## <a name="create-the-cost-absorption-journal"></a>Criar o diário de absorção de custos

Use este procedimento para criar e lançar um diário de absorção de custos.

1.  Clique em **Controle de produção** \> **Periódico** \> **Custos de absorção** \> **Diário de absorção de custo**.

2.  Para criar um diário, pressione CTRL+N.

3.  Na guia **Visão geral**, no campo **Nome**, selecione o nome do diário de absorção de custo.

4.  No campo **Mês/ano de fechamento**, selecione o mês e ano nos quais os custos são lançados.

5.  Clique em **Linhas** para abrir a página **Linhas do diário** e especifique valores nos seguintes campos:
    
      - **Data** – a data na qual a linha do diário será lançada.
      - **Conta contábil** – o número da conta contábil na qual a linha do diário será lançada.
      - **Centro de custo** – O número do centro de custo a ser usado para lançar a linha do diário.
      - **Valor do custo** – O valor do custo da linha do diário.

6.  Clique em **Lançar** \> **OK** para lançar a linha do diário.

    > [!NOTE]
    > Você pode visualizar o tipo de custo absorvido lançado em um centro de trabalho, o centro de custo correspondente ao qual o centro de trabalho está associado, a taxa por hora e a capacidade planejada para os detalhes do centro de trabalho na página <STRONG>Custos absorvidos</STRONG>.

## <a name="close-absorption-costs"></a>Fechar custos de absorção

Você pode lançar os custos de absorção para um mês e um ano específicos no razão. Você pode especificar a conta de transferência e a contrapartida de transferência nos campos **Contas - WIP** e **Contas - custos** na página **Recursos** . 

1.  Clique em **Controle de produção** \> **Periódico** \> **Custos de absorção** \> **Custos por absorção - Fechamento mensal**.

2.  No campo **Mês/ano de fechamento**, selecione o mês e ano nos quais os custos absorvidos são lançados.

3.  Clique em **OK** para lançar os custos de absorção para o mês e o ano selecionados.

## <a name="cancel-absorbed-costs"></a>Cancelar custos absorvidos

Use este procedimento para cancelar os custos absorvidos que não são lançados no razão para um mês e um ano específicos. Não será possível cancelar os custos absorvidos depois que o fechamento mensal for concluído.

1.  Clique em **Controle de produção** \> **Periódico** \> **Custos de absorção** \> **Cancelamento dos custos de absorção**.

2.  No campo **Mês/ano para cancelar**, selecione o mês e ano nos quais os custos absorvidos serão cancelados.

3.  Clique em **OK** para cancelar os custos absorvidos para o mês e o ano selecionados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]