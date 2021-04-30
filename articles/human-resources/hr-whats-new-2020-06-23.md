---
title: Novidades ou alterações no Dynamics 365 Human Resources (25 de junho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 23 de junho de 2020.
author: andreabichsel
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15e40152041ca6f531350a8403492dd98f8f3f0c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891904"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (23 de junho de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3347. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>Quando o registro de um funcionário demitido expira, o tipo de licença, o saldo e o valor são desmarcados no formulário de registro de licença (444867)

Agora os valores nos campos **Tipo de licença**, **Saldo** e **Valor** são mantidos em vez de serem apagados ao fazer essa seleção.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Saldo previsto incorreto quando o novo recurso (Acumulado de licenças de uma única empresa ou de um único plano) está habilitado (456553)

Agora é exibido o saldo previsto correto quando o acumulado de licenças de uma única empresa ou de um único plano está habilitado.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Entidades com relações que resultam em propriedades de navegação duplicadas (456486)

Esta versão corrige um problema nas propriedades de navegação (relação) de várias entidades. Relações duplicadas são detectadas. Esses cenários foram todos corrigidos.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Comentários interempresariais na Avaliação de desempenho (455536)

Agora os comentários interempresariais estão visíveis nas avaliações de desempenho com esta correção. Esta alteração corrige a exibição de comentários do revisor inseridos em diferentes empresas para a mesma avaliação de desempenho.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Inconsistência na exibição de dados de gerenciamento de remuneração (432562)

Agora uma exibição consistente dos dados de remuneração é mantida no autoatendimento para Gerentes. Agora, dependendo de como você navega até os **Detalhes de remuneração** de um trabalhador, os dados de remuneração são exibidos de maneira consistente para os gerentes.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>A data de efetivação do plano de remuneração fixa tem como padrão a data de hoje (411994)

Agora a data de início da remuneração está baseada na data de início do cargo que está sendo atribuído ao funcionário.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>A opção Habilitar definição de meio dia do formulário de licença e ausência está desabilitada quando o formulário é aberto (452607)

Com essa alteração, a opção **Habilitar definição de meio dia** ficará habilitada até surgir novas transações de licença. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Não é possível publicar em HcmDiscussionEntity via Excel; erro no campo TotalRatingScore (453899)

Agora você pode atualizar o campo **TotalRatingScore** usando **HCMDiscussionEntity** no designer de pasta de trabalho do Excel.

## <a name="in-preview"></a>Em visualização

## <a name="database-logging"></a>Log de banco de dados

O de log de banco de dados permite determinar quais tabelas e campos devem ser monitorados. Ele também permite que você determine os eventos que devem disparar o controle de alterações. Use os recursos de log de banco de dados para ver essas alterações ao longo do tempo. Para obter mais informações, consulte [Configurar e gerenciar o log de banco de dados](hr-admin-database-logging.md).

## <a name="mandatory-fields"></a>Campos obrigatórios 

Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources. Este recurso exige **Exibições salvas**.

## <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte [aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios
 
Entidades de gerenciamento de benefícios estão sendo liberadas. As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios. Um modelo de gerenciamento de benefícios estará disponível para mover dados. O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.

## <a name="buy-and-sell-leave"></a>Comprar e vender licenças 

Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças. Esse processo costuma ser gerenciado manualmente. Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH. Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros. Para obter mais informações, consulte:

- [Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar e vender licenças](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Deixar o acúmulo para uma única empresa ou um plano

Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência. Essa capacidade oferece esclarecimentos sobre o processo de acumulação para clientes com anos de licença diferentes ou para manter políticas de competência. Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Adicionar anexos a solicitações de folga

A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual. Os funcionários agora podem adicionar esses anexos. Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações. Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Adicionar código de motivo a suspensões de acúmulos 

Os códigos de motivo foram adicionados à suspensão de acúmulos.

## <a name="carry-forward-rules"></a>Regras de postergação 

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender a acumulação de licenças para tipos de licença especificados

Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas. A licença não remunerada pode ser um tipo, mas não precisa ser. Você pode suspender qualquer licença com base em outro tipo de licença.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidade DMF disponível para suspensões de acúmulos 

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="coming-soon"></a>Em breve

## <a name="configure-the-name-of-employee-self-service"></a>Configurar o nome do autoatendimento para Funcionários

Haverá uma nova opção disponível nos **Parâmetros de Human Resources** para atualizar o nome do espaço de trabalho de autoatendimento para Funcionários para Autoatendimento.

## <a name="checklist-entities-included-in-dataverse"></a>Entidades de lista de verificação incluídas no Dataverse

Entidades de lista de verificação relativas a Integração, Remoção, Transferência e Processos empresariais estarão disponíveis em breve no Dataverse.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]