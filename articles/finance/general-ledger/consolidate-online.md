---
title: Consolidações financeiras online
description: Este tópico descreve consolidações financeiras online na contabilidade.
author: aprilolson
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 8a946a8325afebf76639991c60135d7425f5f211
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826753"
---
# <a name="online-financial-consolidations"></a>Consolidações financeiras online

[!include [banner](../includes/banner.md)]

Este tópico descreve consolidações financeiras online na contabilidade. Antes ler este tópico, leia o tópico [Visão geral de consolidações financeiras e conversão de moeda](financial-consolidations-currency-translation.md).

Depois de concluir sua instalação, insira os detalhes da consolidação na página **Consolidar [Online]** . Quando terminar, clique em **OK** ou **Lote** para processar a consolidação.

## <a name="criteria"></a>Critérios
Na guia **Critérios** da página **Consolidar [Online]**, você define as contas, os períodos e os tipos de dados que estão sendo consolidados.

![Guia Critérios](./media/criteria-consolidate-online.png "Guia Critérios")

Aqui está uma explicação sobre os vários campos nessa guia:

- **Descrição** – Insira uma descrição precisa para o período que você está consolidando.
- **Conta principal** – Use os campos desta seção para definir as contas principais que serão processadas.

    - **De** e **Até** – Especifique um intervalo de contas para processar. Se esses campos estiverem vazios, todas as contas das empresas serão movidas para a empresa de consolidação. Portanto, se estiver consolidando quatro empresas, e cada empresa possuir um plano de contas diferente, todas as contas das quatro empresas serão criadas na empresa de consolidação.
    - **Usar conta de consolidação** – Se você definir esta opção como **Sim**, o campo **Selecionar conta de consolidação de** se tornará disponível. Neste campo, selecione se todas as contas devem ser consolidadas na conta de consolidação que está definida na página **Contas principais** ou se você quer selecionar a conta de um dos grupos de contas de consolidação.
    - **Grupo de contas de consolidação** – Selecione o grupo a ser usado para o mapeamento da conta principal para consolidação.

- **Período de consolidação** – Use os campos desta seção para definir o período de consolidação.

    - **De** e **Até** – Especifique um intervalo de datas para a consolidação. Se você deixar esses campos vazios, a consolidação será processada para todos os períodos que são definidos no calendário do razão da empresa. Recomendamos que você não deixe esses campos vazios.
    - **Incluir valores reais** – Defina esta opção como **Sim** para consolidar os dados reais.
    - **Incluir valores de orçamento** – Defina esta opção como **Sim** para consolidar dados de registro de orçamento.
    - **Recriar saldos durante a consolidação** – Não recomendamos que você defina esta opção como **Sim**. Em vez disso, reconstrua saldos em um trabalho em lote separado.

- **Modelos de orçamento** – Se você optou por consolidar os dados do orçamento, use os campos desta seção para definir modelos de orçamento.

    - **De** e **Até** – Especifique o intervalo de modelos a usar.
    - **Tipo de taxa de orçamento** – Selecione o tipo de taxa de orçamento a usar para a conversão de moeda de dados de orçamento.

## <a name="financial-dimensions"></a>Dimensões financeiras
Na guia **Dimensões financeiras**, você define as dimensões que devem ser incluídas na empresa de consolidação. Para selecionar uma dimensão, defina o campo **Especificação** como **Dimensão** e defina a ordem da dimensão na empresa de consolidação.

![Guia Dimensões financeiras](./media/financial-dimensions-cons.png "Guia Dimensões financeiras")

Independentemente da ordem que você definir, a **Conta principal** será sempre o primeiro segmento.

## <a name="legal-entities"></a>Entidades legais
Na guia **Entidades legais**, você define as empresas que devem ser incluídas na empresa de consolidação. Você também define a porcentagem de participação das empresas. Se você especificar a participação em menos de 100%, o percentual especificado será acumulado para a empresa de consolidação. Para todas as diferenças de conversão, o campo **Tipo de contas das diferenças de conversão** será usado para selecionar a conta principal de instalação na página **Contas para transações automáticas** .

![Guia Entidades legais](./media/legal-entities-cons.png "Guia Entidades legais")

![Página Contas para transações automáticas](./media/accounts-for-automatic-cons.png "Página Contas para transações automáticas")

## <a name="elimination"></a>Eliminação
Na guia **Eliminação**, você tem três opções para processar eliminações:

- Selecione a regra de eliminação e, em seguida, no campo **Opções da proposta**, selecione **Somente proposta**. Esta opção processará a eliminação durante o processo de consolidação, mas não lançará tudo em uma etapa. Você também pode lançar o diário posteriormente.
- Selecione a regra de eliminação e, em seguida, no campo **Opções da proposta**, selecione **Lançar somente**. Esta opção processará a eliminação durante o processo de consolidação e lançará tudo em uma etapa.
- Use um diário de eliminação para executar uma proposta de eliminação separada do processo de consolidação.

![Guia Eliminação](./media/elimination-cons-onl.png "Guia Eliminação")

Para obter mais informações sobre eliminações, consulte [Regras de eliminação](./elimination-rules.md).

## <a name="currency-translation"></a>Conversão de moeda
Na guia **Conversão de moeda**, você define a entidade legal, a conta, o tipo de taxa de câmbio e a taxa. Há três opções disponíveis no campo **Aplicar taxa de câmbio de**:

- **Data de consolidação** – A data de consolidação será usada para obter a taxa de câmbio. Essa taxa é equivalente à taxa de ponto ou de fim de mês. Você terá uma visualização da taxa, mas não poderá editá-la.
- **Data da transação** – A data de cada transação será usada para selecionar uma taxa de câmbio. Essa opção é a mais usada normalmente para ativos fixos e é também conhecida como uma taxa histórica. Você não terá uma visualização da taxa, porque haverá várias taxas para diversas transações no intervalo de conta.
- **Taxa definida pelo usuário** – Após selecionar esta opção, você poderá inserir a taxa de câmbio que deseja. Esta opção pode ser útil para as taxas de câmbio médias ou se você estiver realizando uma consolidação em relação a uma taxa de câmbio fixa.

![Guia Conversão de moeda](./media/currency-translation-cons-online.png "Guia Conversão de moeda")

## <a name="additional-resources"></a>Recursos adicionais

Para obter mais informações sobre consolidação e conversão de moeda, consulte o tópico principal deste tópico, [Visão geral de consolidações financeiras e conversão de moeda](./financial-consolidations-currency-translation.md).

Para obter informações sobre os cenários onde você poderá gerar demonstrativos financeiros consolidados, consulte [Gerar demonstrativos financeiros consolidados](./generating-consolidated-financial-statements.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]