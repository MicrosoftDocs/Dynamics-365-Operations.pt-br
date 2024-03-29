---
title: Acumular planos de licença e ausência
description: Você pode acumular licenças e ausências no Dynamics 365 Human Resources para vários funcionários ou para uma pessoa.
author: twheeloc
ms.date: 09/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aac35177ca120b1ae1b4759b98278fafadc3e033
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702110"
---
# <a name="accrue-leave-and-absence-plans"></a>Acumular planos de licença e ausência

>[!Important]
>A funcionalidade mencionada neste artigo está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode acumular licenças e ausências no Dynamics 365 Human Resources para vários funcionários ou para uma pessoa.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Acumular licenças e ausências para vários funcionários

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Gerenciar licença**, selecione **Acumular planos de licença e ausência**.

3. A caixa de diálogo **Acumular planos de licença e ausência** é exibida. Em **Acumular a partir de**, selecione **Data de hoje** ou selecione **Data personalizada** e insira uma data personalizada.

4. Se quiser executar competências para todas as empresas, selecione **Todas as empresas**. Se quiser processar competências para um único plano de licença, selecione **Não** para **Todos os planos** e selecione um **Plano de licença**. Se selecionar todas as empresas, não poderá selecionar um plano de licença individual.

5. Se você deseja executar o processo de acúmulo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

    1. Insira informações para o processo de acúmulo.
    2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e depois selecione **OK**.
    3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.
    4. Selecione **OK**. O processo de acúmulo será executado com os parâmetros definidos por você. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>Acumular licenças e ausências para um funcionário

1. No registro do funcionário, selecione **Licença**.

2. Selecione **Acumular licenças e ausências**.

3. A caixa de diálogo **Acumular planos de licença e ausência** é exibida. Em **Acumular a partir de**, selecione **Data de hoje** ou selecione **Data personalizada** e insira uma data personalizada.

4. Se quiser executar competências para todas as empresas, selecione **Todas as empresas**. Se quiser processar competências para um único plano de licença, selecione **Não** para **Todos os planos** e selecione um **Plano de licença**. Se selecionar todas as empresas, não poderá selecionar um plano de licença individual.

5. Se você deseja executar o processo de acúmulo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo de acúmulo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo de acúmulo será executado com os parâmetros definidos por você.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Excluir acúmulos de licenças e ausências para vários funcionários

Exclua os registros de acúmulo para um plano e um intervalo de datas específicos. As datas de acúmulo devem ser datadas hoje ou no futuro.

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Gerenciar licença**, selecione **Excluir acúmulos de plano de licença e ausência**.

3. Na caixa de diálogo **Excluir competências do plano de licença e ausência**, selecione o **Plano de licença**.

4. Se aplicável, escolha **Excluir ajustes de saldo**.

5. Insira ou selecione uma **Data da competência de licença**. Essa data deve ser hoje ou futuramente.

6. Selecione **OK**. O processo de acúmulo excluirá acúmulos com os parâmetros definidos por você.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Excluir acúmulos de licenças e ausências para um único funcionário

1. No registro do funcionário, selecione **Licença**.

2. Selecione **Excluir competências do plano de licença e ausência**.

3. Na caixa de diálogo **Excluir competências do plano de licença e ausência**, selecione o **Plano de licença**.

4. Se aplicável, escolha **Excluir ajustes de saldo**.

5. Insira ou selecione uma **Data da competência de licença**. Essa data deve ser hoje ou futuramente.

6. Selecione **OK**. O processo de acúmulo excluirá acúmulos com os parâmetros definidos por você.

## <a name="review-leave-accrual-and-deletion-processes"></a>Revisar processos de acúmulo de licença e exclusão

**Auditoria do acúmulo de folgas** é exibido cada vez que você executar ou excluir uma competência para um ou todos os funcionários. A data e a pessoa que executou a ação também são exibidas.

1. Na página **Licença e ausência**, selecione a guia **Links**.
2. Em **Gerenciar licença**, selecione **Excluir auditoria de acúmulo de licença**.

## <a name="leave-accrual-rounding"></a>Arredondamento do acúmulo de licenças
Quando um funcionário for registrado ou tiver o registro cancelado, o arredondamento de acúmulo de licenças será rateado. Anteriormente, o arredondamento só era permitido quando um plano de licença era definido para rateamento, e um funcionário era registrado ou tinha o registro cancelado durante o período intermediário. Os acúmulos de licenças agora serão arredondados, independentemente do registro/cancelamento do registro no meio do período ou no início de um período.

## <a name="leave-accrual-transaction-auditing"></a>Auditoria de transações de acúmulo de licenças

Este recurso ajuda os gerentes de licenças e ausências a entenderem as transações de acumulação de licenças e ausências relacionadas aos saldos de folgas de um funcionário para um tipo específico de licença.

Para exibir os detalhes da transação:

1. No registro do funcionário, selecione **Licença**.

2. Selecione **Exibir folga** e, em seguida, selecione a guia **Saldos**.

Para exibir as transações de competência relacionadas a um tipo de licença específico, selecione o valor numérico na coluna **Saldo atual**.

Para exibir os detalhes da transação para um valor de acúmulo específico, selecione uma linha de acúmulo, abra o painel **Informações relacionadas** à direita e, em seguida, abra a seção **Detalhes da transação**. A seção detalhes da Transação é exibida:

- Alterações no saldo de tipo de licença do funcionário
- Detalhes do emprego para o período de acúmulo especificado
- Detalhes sobre o período de acúmulo e as taxas
- Qualquer alteração feita nas configurações do plano de licença

![Auditoria de transações de acúmulo de licenças.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>Consulte também

[Visão geral de licença e ausência](hr-leave-and-absence-overview.md)</br>
[Criar um plano de licença e ausência](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
