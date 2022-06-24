---
title: Novidades ou alterações no Dynamics 365 Human Resources 5 de abril de 2021
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 5 de abril de 2021.
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1b8074877b8d2b2c05596406cbf2d98febd2e8cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899517"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 5 de abril de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve os recursos novos, alterados ou que serão lançados em breve no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4074.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Restringir a edição de detalhes de contato comercial por funcionários | [Restringir a edição de detalhes de contato comercial por funcionários](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restringir a edição de informações pessoais](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este artigo para incluir correções de bugs feitas no build após a publicação inicial deste artigo.

| Número do problema | Problema |  Descrição |
| --- | --- | --- |
| 550852 | O botão **Aprovação** não é validado com campos obrigatórios definidos no formulário **Avaliação**. | Quando você define um campo no formulário **Avaliação** como obrigatório e publica as alterações para a função de gerente, o formulário não é validado conforme esperado. |
| 559564 | As ações históricas de trabalhador para alteração de remuneração fixa retornam erro para usuários demitidos. | A ação de trabalho relativa a uma remuneração de funcionário demitido gera um erro. Depois que um funcionário é demitido, a ação de trabalho da promoção antes da demissão gera um erro. |
| 560074 | A lista suspensa de categoria de emprego não está filtrando o **Tipo de trabalhador** e mostra categorias para funcionários e prestadores de serviço. | No formulário **Funcionário**, a lista suspensa **Categoria de emprego** deve mostrar as categorias funcionário ou prestador de serviço, com base no tipo de trabalho do funcionário. |
| 567388 | Algumas informações de funcionários recém-criados não são logo sincronizadas com a tabela **cdm_worker** no Dataverse. | Ao criar um novo registro de funcionário, o novo registro seria sincronizado com a tabela **cdm_worker** no Dataverse, mas nem todas as propriedades seriam incluídas no registro Dataverse. |
| 563837 | Recursos que não estão disponíveis em Human Resources são exibidos. | Vários recursos que não se aplicam a Human Resources são exibidos no gerenciamento de recursos. Esses recursos agora são removidos da lista de recursos disponíveis para habilitar Human Resources. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| As habilidades inseridas por um gerente para os funcionários podem ser aprovadas automaticamente por um fluxo de trabalho | Em breve. |
| Atualização da plataforma 10.0.17 (41) | A atualização da plataforma 10.0.17 está agendada para começar a ser implementada na próxima versão, em 19 de abril de 2021. Para mais informações, consulte [Atualizações de plataforma para a versão 10.0.17 dos aplicativos de finanças e operações (abril de 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]