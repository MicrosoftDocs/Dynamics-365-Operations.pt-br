---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab4b2b3adefa388acfadc77c7b25a6b47d01571f0e58f6ab81101e25d1b548e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777950"
---
# <a name="configure-leave-and-absence-parameters"></a>Configurar parâmetros de licença e ausência

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:

- Sequência numérica para solicitações de licença
- Lei de família de licença e médica (FMLA)
- Configurações de autoatendimento para funcionário para solicitações de licença e ausência
- Parâmetros de licença e ausência

## <a name="view-and-change-human-resources-parameters"></a>Exibir e alterar parâmetros de recursos humanos

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de recursos humanos**.

3. Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias. Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.

4. Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.

5. Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.

7. Selecione **Salvar**.

>[!IMPORTANT]
>A exibição de licenças e ausências em empresas está no momento em versão prévia. Você precisará habilitá-la no ambiente **Área restrita** para exibir a opção de licença e ausência. Para obter mais informações sobre as versões prévias do recurso, consulte [Gerenciar recursos](hr-admin-manage-features.md).

## <a name="view-and-change-human-resources-shared-parameters"></a>Exibir e alterar parâmetros compartilhados de recursos humanos

1. Na página **Gerenciamento de pessoal**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros compartilhados de recursos humanos**.

3. Na guia **Acesso avançado**, selecione **Sim** para **Habilitar a exibição de licença entre empresas** para permitir que a licença seja exibida entre empresas.

4. Selecione **Salvar**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Exibir e alterar parâmetros de licença e ausência

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de licença e ausência**.

3. Na guia **Geral**, defina os seguintes parâmetros:
 
    - Defina a **Unidade para licença e ausência** em horas ou dias. Em caso de dias, você pode selecionar **Habilitar definição de meio dia** para permitir que os funcionários escolham a primeira ou a segunda metade do dia em suas solicitações de tempo limite. 

    - Selecione **Meses de data de efetivação do serviço** para definir quando as taxas de acumulação entram em vigor para os planos de licença usando meses de serviço.

    - Selecione **Cálculo de saldo** para exibir saldos a partir de hoje ou a partir do período de competência. Se você selecionar **Saldo a partir de hoje**, o saldo exibirá o total de todas as competências, ajustes e solicitações a partir de hoje. Se você selecionar **Saldo como período de acumulação**, o saldo exibirá o total de todas as competências, ajustes e solicitações, a partir do período de acumulação definido pela frequência no plano de licença. 

    - Defina a hora inicial do trabalho em lotes de expiração postergada.  
    
    - Selecione **Sim** para **Permitir que os funcionários comprem licenças** e **Permitir que os funcionários vendam licença**. Se você selecionar **Sim** para essas opções, poderá criar políticas de licença de compra e venda e permitir que os funcionários enviem solicitações de compra e venda de licenças.

## <a name="configure-calendar-parameters"></a>Configure parâmetros de calendário.

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de licença e ausência**.

3. Na guia **Calendário**, altere as configurações de calendário, conforme necessário.

4. Selecione **Salvar**.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]