---
title: Gerenciamento de horário e de presença no Retail
description: Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Dynamics 365 Commerce.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e28df09ecb592ae7df360d1b2d0bf06339c1410d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989368"
---
# <a name="time-and-attendance-management-in-retail"></a>Gerenciamento de horário e de presença no Retail

[!include [banner](includes/banner.md)]

Este tópico descreve os cenários com suporte para o Gerenciamento de horário e presença no in Dynamics 365 Commerce.

## <a name="manage-worker-setup-and-scheduling"></a>Gerenciar configuração e planejamento do trabalhador

### <a name="initial-configuration"></a>Configuração inicial de 

- Execute o assistente de configuração.
- Registre os trabalhadores como trabalhadores com registro de horas.

### <a name="plan-worker-schedules"></a>Planejar agendas do trabalhador

- Aplique perfis usando o planejador de trabalho. Para obter mais informações, consulte [Aplicar perfis usando o planejador de trabalho](https://technet.microsoft.com/library/aa551234.aspx).

Para obter informações sobre as etapas de configuração, consulte [Configurando tempo e presença](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="commerce-specific-configuration"></a>Configuração específica do Commerce

- Habilite um perfil de funcionalidade do relógio de ponto, para os funcionários para os quais você deseja habilitar registros de horas. Clique em **Perfis de funcionalidade de PDV** &gt; **Funções** &gt; **Registros de horas do PDV** &gt; **Habilitar registros de horário**.
- Configure grupos permissões de PDV (ponto de venda) para habilitar a permissão Exibir entradas do relógio de ponto. Essa permissão permite que um usuário exiba os registros do relógio de ponto de outros trabalhadores na loja (e em qualquer outra loja à qual o usuário esteja associado via catálogo de endereços). Convém habilitar essa permissão para uma função gerente, mas não para uma função caixa. Clique em **Grupos de permissões de PDV** &gt; **Exibir entradas do relógio de ponto**.

## <a name="register-time"></a>Hora de registro

### <a name="cashier-and-non-cashier-time-registrations"></a>Registros de horas para caixa e não caixa

- No PDV:

    - Operações de registro de entrada.

        - Faça logon com uma operação não sacadora ou novo turno.
        - Selecione uma operação de relógio de ponto.
        - Selecione uma operação desejada:

            - Registro de entrada
            - Intervalo de trabalho
            - Intervalo para o Almoço
            - Registro de saída

        <table>
        <thead>
        <tr>
        <th>Status atual</th>
        <th>Operações disponíveis</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Registro de entrada</td>
        <td>
        <ul>
        <li>Intervalo de trabalho</li>
        <li>Intervalo para o Almoço</li>
        <li>Registro de saída</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>Intervalo de trabalho</td>
        <td>Registro de entrada</td>
        </tr>
        <tr>
        <td>Intervalo para o Almoço</td>
        <td>Registro de entrada</td>
        </tr>
        <tr>
        <td>Registro de saída</td>
        <td>Registro de entrada</td>
        </tr>
        </tbody>
        </table>

        [![Estados do relógio de ponto](./media/timeclockstates.png)](./media/timeclockstates.png)

- Exiba a mensagem de confirmação e valide que o tempo da atividade atual está correto.
- Livro de registros:

    - Clique em **Livro de registros** para exibir a atividade do relógio de ponto.
    - Use os filtros de tempo para selecionar períodos diferentes.
    - Se você trabalhar em vários locais de loja, verá os registros de horas de todas as lojas em que você registrou ponto. Você pode usar o filtro de loja para exibir os registros de horas de uma loja selecionada.

- Fusos horários diferentes:

    - Se você exibir as horas de um local diferente (para o livro de registros do caixa ou usando **Exibir entradas do relógio de ponto** em um cenário do gerente) e esse local estiver em um fuso horário diferente, os registros de horas exibidos serão convertidos em seu fuso horário local. Por exemplo, você é gerente de duas lojas, uma no Arizona e outra em Nevada. Um caixa registra a entrada às 9:00 A.M. no Arizona. Nesse momento, são 8h em Nevada. Portanto, se você estiver na loja de Nevada e observar os registros de horas, verá o registro marcando 8h.

## <a name="view-worker-time-registrations"></a>Exibir registros de tempo de funcionário

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Exibir registros de horas do trabalhador e filtrar por tipo de loja ou atividade

No PDV:

- Selecione **Exibir entradas do relógio de ponto**.
- Você verá atividades de registro do relógio de ponto de todos os trabalhadores atribuídos às mesmas lojas às quais você está atribuído.
- Você pode usar os filtros de loja e tipo de atividade para filtrar os registros de horas.

## <a name="process-and-manage-time-registrations"></a>Processar e gerenciar registros de tempos

Um usuário do Commerce segue o fluxo de trabalho para calcular, aprovar e transferir registros de horas para a folha de pagamento.

### <a name="primary-operations"></a>Operações principais

- Calcular
- Aprovar
- Enviar para folha de pagamento

### <a name="other-common-operations"></a>Outras operações comuns

- Saída em massa
- Registrar ausência

Para obter mais informações sobre como processar registros de tempo e presença, consulte [Processar os registros de tempo e presença](https://technet.microsoft.com/library/aa573180.aspx).


[!INCLUDE[footer-include](../includes/footer-banner.md)]