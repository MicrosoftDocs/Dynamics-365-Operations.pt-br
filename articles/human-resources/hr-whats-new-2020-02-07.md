---
title: Novidades ou alterações no Dynamics 365 Human Resources (7 de fevereiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 7 de fevereiro de 2020.
author: andreabichsel
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0a45eed4e094cedb9d6d8ed0cb2bdc81eb31b76e
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128104"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (7 de fevereiro de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.2835. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>O Learning Analytics não mostrará o curso se a sala de aula estiver em branco (388289)

A página do Learning Analytics exibirá o curso se a sala de aula estiver vazia.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>A pesquisa de posição não leva o fuso horário em conta (405344)

A pesquisa por posições abertas agora leva em conta o fuso horário ao validar se uma posição está aberta.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>A exibição de análise de saldo atual não é atualizada com o saldo de licença atual correto após o envio de solicitações de tempo limite (409756)

O saldo atual agora inclui as solicitações de folga enviadas.

## <a name="in-preview"></a>Em visualização

Os seguintes recursos de visualização foram disponibilizados em 3 de fevereiro de 2020:

- **Recursos de exibição de licenças e ausências** - para obter mais informações, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Recurso de visualização de gerenciamento de benefícios** - para obter mais informações, incluindo problemas conhecidos, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Em breve

### <a name="platform-update-32"></a>Update 32 para plataforma 

A atualização da plataforma 32 estará disponível em breve. [Obtenha mais informações sobre a atualização de plataforma 32 aqui](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

### <a name="updated-dataverse-solution"></a>Solução Dataverse atualizada

Uma nova solução de Dataverse estará disponível em breve com as seguintes alterações:

| Descrição | Troco |
| ----------------------------------------- | --- |
| Alterações de entidade do **Trabalho/Posição** | **Região de remuneração** adicionado</br>**Dimensões financeiras** adicionado |
| Alterações de entidade do **Trabalhador** | **Sequência do nome** adicionado</br>**Trabalha de casa** adicionado</br>**Idioma** adicionado</br>**Aniversário de tempo de serviço** adicionado</br>**Data de aniversário** adicionado</br>**Data original de contratação** adicionado |
| Alterações de entidade do **Emprego** | **Dimensões financeiras** adicionado</br>**Motivo da demissão** adicionado</br>**Data da demissão** renomeada de **Data de transição**</br>**Data de experiência** adicionado |
| Alterações de entidade do **Endereço do trabalhador** | **Endereço** adicionado</br>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação |
| Novas entidades de configuração de remuneração variável | **Tipo de plano de remuneração variável**</br>**Plano de remuneração variável**</br>**Regras de benefício proporcional diferido**</br>**Nível do plano de remuneração variável** |
| Nova entidade **Emprego do calendário do trabalhador** | **Entidade do calendário de trabalho** adicionada |
| Nova entidade **Detalhe da posição de folha de pagamento** | **Detalhe da posição de folha de pagamento** adicionado |
| Nova entidade **Bloco** | **Bloco** adicionado. A nova entidade **Título** será incluída no processo de sincronização entre Human Resources e Dataverse. Não será inicialmente referenciada de entidades **Cargo** ou **Trabalho**. |

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]