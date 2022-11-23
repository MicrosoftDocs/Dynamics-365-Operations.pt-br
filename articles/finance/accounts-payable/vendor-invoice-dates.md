---
title: Datas de fatura de fornecedor
description: Este artigo descreve as datas exibidas nas faturas de fornecedor. Também explica como ajustar automaticamente a data de lançamento.
author: sunfzam
ms.date: 2/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 022fd0ce07fbb4c54afcf7334c1c9411e01dcf26
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775259"
---
# <a name="vendor-invoice-dates"></a>Datas de fatura de fornecedor

[!include [banner](../includes/banner.md)]

Este artigo descreve as datas exibidas nas faturas de fornecedor. Também explica como ajustar automaticamente a data de lançamento.

Na página **Fatura de fornecedor pendente detalhada**, o cabeçalho da fatura mostra quatro datas: **Data de recebimento da fatura**, **Data da fatura**, **Data de lançamento** e **Data de vencimento**. Quando uma fatura de fornecedor é criada, as seguintes datas são inseridas por padrão:

- **Data de recebimento da fatura** – esse campo é definido como a data atual do sistema.
- **Data de lançamento** – esse campo é definido como a data atual do sistema. 
- **Data de conclusão** – a data nesse campo é calculada com base na data de lançamento e nos termos de pagamento.
- **Data da fatura** – por padrão, esse campo fica em branco. No entanto, você pode inserir um valor conforme desejado. Nesse caso, a data no campo **Data de conclusão** é recalculada com base na data da fatura e nos termos de pagamento.

Às vezes, uma fatura de fornecedor pode estar em um estado pendente por muito tempo após o fechamento do período. Quando estiver pronta para o lançamento, a data de lançamento antiga do período de lançamento passado ainda será usada. No entanto, esse período foi fechado agora. Portanto, um auxiliar de AP (Contas a pagar) deve alterar manualmente todas as datas de lançamento para o novo período de lançamento para todas as faturas pendentes que foram criadas anteriormente.

O recurso descrito neste artigo permite ajustar automaticamente a data de lançamento de acordo com as necessidades do negócio.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Parâmetro para ajustar automaticamente a data de lançamento da fatura do fornecedor

Siga estas etapas para ajustar automaticamente a data de lançamento para faturas de fornecedor.

1.  Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
2.  Na guia **Razão e imposto**, no **campo Ajustar a data de lançamento automaticamente**, selecione um dos seguintes valores:

    - **Nenhuma alteração** – o sistema não altera automaticamente a data de lançamento durante o lançamento. Esse valor está selecionado por padrão.
    - **Sempre altere a data de lançamento para a data do sistema** – A data de lançamento é automaticamente alterada para a data do sistema durante o lançamento.
    - **Alterar data de lançamento para a data do sistema quando o período de data de lançamento estiver fechado ou em espera** – A data de lançamento é alterada automaticamente para a data do sistema durante o lançamento, mas somente se o período correspondente da data de lançamento tiver um status **Fechado** ou **Em espera**.
    - **Alterar data de lançamento para o primeiro dia do novo período quando o período de data de lançamento estiver fechado ou em espera** – A data de lançamento é alterada para o primeiro dia do novo período aberto, mas somente se o período correspondente da data de lançamento tiver um status **Fechado** ou **Em espera**.

> [!NOTE]
> Se a nova data de lançamento ajustada automaticamente estiver em um novo ano fiscal, a data de lançamento da fatura não será atualizada. O usuário receberá uma mensagem de erro "O ano fiscal foi alterado. Verifique e insira novamente a data de lançamento." A data de lançamento da fatura deve ser atualizada para a nova data do ano fiscal a fim de lançá-la.

## <a name="impact-of-posting-date-changes"></a>Impacto do lançamento de alterações de data

Quando a data de lançamento em uma fatura de fornecedor pendente é alterada, a alteração tem os seguintes efeitos:

- **Data de vencimento**

    - Se o campo **Data da fatura** estiver vazio, a data de conclusão será recalculada com base na nova data de lançamento e nos termos de pagamento.
    - Se o campo **Data da fatura** tiver sido definido anteriormente, a alteração da data de lançamento não afetará a data de conclusão.

- **Data do desconto à vista**

    - Se o campo **Data da fatura** estiver em branco, a nova data de lançamento será usada para calcular o desconto à vista.
    - Se o campo **Data da fatura** tiver sido definido anteriormente, o desconto à vista não será alterado.

- **Taxa de câmbio** – a data da taxa de câmbio é determinada pela definição da configuração da opção **Atualizar contabilidade de fornecedor usando a data da fatura** na guia **Fatura** da página **Parâmetros de contas a pagar** (**Contas a pagar \> Configuração \> Parâmetros de contas a pagar**).

    - Se essa opção estiver definida como **Sim**, a **Data da fatura** será usada e a alteração da **Data de lançamento** não afetará a taxa de câmbio.
    - Se essa opção for definida como **Não**, a data de lançamento será usada para calcular a taxa de câmbio. Quando a data de lançamento é atualizada, os valores de contabilidade e relatório são recalculados. Portanto, a validação correspondente deve ser feita novamente.

## <a name="validation"></a>Validação

Dois outros campos na guia **Fatura** da página **Parâmetros de contas a pagar** (**Contas a pagar \> Configuração \> Parâmetros de contas a pagar**) afetam o processamento de faturas:

- Se o campo **Verificar o número da fatura usada** estiver definido como **Rejeitar duplicatas no ano fiscal**, a data de lançamento será usada para verificar se há faturas duplicadas durante o lançamento da fatura.
- Se o campo **Exigir data do documento na fatura de fornecedor** estiver definido como **Opção de erro**, o campo **Data da fatura em cabeçalho de fatura pendente** será obrigatório. Se a data da fatura for posterior à data de lançamento, uma mensagem de erro será exibida.
