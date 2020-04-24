---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197972"
---
# <a name="configure-leave-and-absence-parameters"></a>Configurar parâmetros de licença e ausência

Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:

- Sequência numérica para solicitações de licença
- Lei de família de licença e médica (FMLA)
- Configurações de auto-atendimento para funcionário para solicitações de licença e ausência
- Parâmetros de licença e ausência

## <a name="view-and-change-human-resources-parameters"></a>Exibir e alterar parâmetros de recursos humanos

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de recursos humanos**.

3. Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias. Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.

4. Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.

5. Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.

6. Na guia **Licença e ausência**, verifique as configurações e altere conforme necessário.

7. Selecione **Salvar**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Exibir e alterar parâmetros de licença e ausência

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de licença e ausência**.

3. Na guia **Geral**, defina os seguintes parâmetros:
 
    - Defina a **Unidade para licença e ausência** em horas ou dias. Em caso de dias, você pode selecionar **Habilitar definição de meio dia** para permitir que os funcionários escolham a primeira ou a segunda metade do dia em suas solicitações de tempo limite. 

    - Selecione **Meses de data de efetivação do serviço** para definir quando as taxas de acumulação entram em vigor para os planos de licença usando meses de serviço.

    - Selecione **Cálculo de saldo** para exibir saldos a serem exibidos a partir de hoje ou a partir do período de acumulação. Se você selecionar **Saldo a partir de hoje**, o saldo exibirá o total de todas as competências, ajustes e solicitações a partir de hoje. Se você selecionar **Saldo como período de acumulação**, o saldo exibirá o total de todas as competências, ajustes e solicitações, a partir do período de acumulação definido pela frequência no plano de licença. 

## <a name="configure-calendar-parameters"></a>Configure parâmetros de calendário.

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de licença e ausência**.

3. Na guia **Calendário**, altere as configurações de calendário, conforme necessário.

4. Selecione **Salvar**.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
