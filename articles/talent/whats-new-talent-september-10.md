---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (10 de setembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: b41ce93c8ae93054d2b0d71340b99e0910d4510f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303314"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-september-10-2018"></a>Novidades ou alterações no Dynamics 365 for Talent Core HR (10 de setembro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.138.0**

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a>Permitir hora específica do dia em solicitações de folga (meios dias)

Se a licença e a ausência estão configuradas para que a folga seja enviada em dias, agora você também pode habilitar uma definição de meio dia. Em seguida, quando os usuários enviarem solicitações de folga, eles poderão especificar se estão solicitando a primeira metade ou a segunda metade do dia de folga.

Por padrão, essa opção está desativada. Para que os funcionários solicitem a primeira metade ou a segunda metade do dia de folga, você deve ativar essa opção na área **Licença e ausência** dos parâmetros de recursos humanos.

O privilégio de segurança para esse recurso é Manter parâmetros de recursos humanos.

## <a name="validation-of-leave-and-absence-entries"></a>Validação de entradas de licença e ausência

Dependendo da maneira que a licença estiver configurada, os funcionários que tentarem enviar uma solicitação de folga maior do que o dia útil receberão uma mensagem de aviso. Ou seja, eles são avisados se tentarem demorar mais de um dia inteiro de folga em qualquer data específica.

Essa validação está sempre ativada. Sempre que esses funcionários excederem o limite do dia definido, eles receberão um aviso em sua solicitação de folga.

## <a name="additional-fields-for-conditional-statements-in-workflows"></a>Campos adicionais para instruções condicionais em fluxos de trabalho

Foram adicionados campos adicionais a instruções condicionais e espaços reservados para vários fluxos de trabalho no Core HR.

Os seguintes campos foram adicionados aos fluxos de trabalho de remuneração, rescisão e transferência:

- EmploymentType
- LegalEntity
- AdjustedWorkerStartDate
- EmployerNoticeAmount
- EmployerUnitOfNotice
- TransitionDate
- WorkerNoticeAmount
- WorkerStartDate
- WorkerUnitOfNotice
- ProbationEndDate
- Cargo
- Sindicato
- Departamento
- PositionType
- CompLocation
- Cargo
- Trabalho
- JobType
- JobFamily
- JobFunction

Os seguintes campos foram adicionados ao fluxo de trabalho de cargo:

- Cargo
- Sindicato
- Departamento
- PositionType
- CompLocation
- Cargo
- Trabalho
- JobType
- JobFamily
- JobFunction

Os campos em instruções condicionais e espaços reservados estão disponíveis a todos os usuários que têm acesso para configurar os fluxos de trabalho mencionados anteriormente.

## <a name="navigation-to-attract-from-personnel-management"></a>Navegação para o Attract no gerenciamento de equipes

No gerenciamento de equipes, se o Attract não foi configurado, a seção **Candidatos a contratar** direcionará os usuários para a introdução ao Attract, em vez de mostrar a mensagem "Não encontramos nada para mostrar aqui".

## <a name="other-changes"></a>Outras alterações

Esta versão inclui várias correções de bug adicionais:

- Quando um prestador de serviço é contratado, a guia **Remuneração** não deve estar disponível na página de solicitação/ação.
- Durante o processo de rescisão de solicitação, você não pode prosseguir até que todos os campos obrigatórios contenham dados.
- Problemas de exibição de data e ordem de classificação na análise do gerenciamento de equipes foram resolvidos.
