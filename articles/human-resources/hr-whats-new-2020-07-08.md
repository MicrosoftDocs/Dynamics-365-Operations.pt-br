---
title: Novidades ou alterações no Dynamics 365 Human Resources (08 de julho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 8 de julho de 2020.
author: Darinkramer
manager: AnnBe
ms.date: 07/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2f542195693e825391b85efc4a7e91fdfea3944
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "3711883"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (8 de julho de 2020)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3382. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="database-logging"></a>Log de banco de dados

O de log de banco de dados permite determinar quais tabelas e campos devem ser monitorados. Ele também permite que você determine os eventos que devem disparar o controle de alterações. Use os recursos de log de banco de dados para ver essas alterações ao longo do tempo. Para obter mais informações, consulte [Configurar e gerenciar o log de banco de dados](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Configurar o nome do Autoatendimento para funcionários

Em **Parâmetros do Human Resources**, agora é possível alterar o nome do espaço de trabalho **Autoatendimento para funcionários** para **Autoatendimento**. Para obter mais informações, consulte [Alterar o nome do espaço de trabalho Autoatendimento para funcionários](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Acesso para inscrição aberta do gerenciamento de benefícios fora do período

Esta versão corrige um bug em que os funcionários podiam acessar a inscrição aberta para benefícios fora do período de inscrição ou sem um evento de vida. Como resultado, se você precisar demonstrar a inscrição aberta no Autoatendimento para funcionários, deverá ajustar as datas de inscrição aberta para hoje (ou antes disso) para torná-la acessível. Você pode alterar essa configuração em **Gerenciamento de benefícios > Regras e períodos de opções**.

## <a name="email-employee-enrollment-confirmation"></a>Confirmação de inscrição de funcionário por email

Agora, você pode enviar emails aos funcionários depois que eles concluem a seleção de benefícios. Você pode enviar uma mensagem padrão ou usar um modelo de email da organização. Essas configurações estão em **Parâmetros do Human Resources > Gerenciamento de benefícios**.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>Licença cancelada ainda aparece na próxima folga no espaço de trabalho Pessoas (441358)

A licença cancelada não é mais exibida como próxima folga nos cartões de licença do espaço de trabalho **Pessoas**.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>Não é possível usar a propriedade de entidade de departamento na entidade PositionV2 (456486)

Agora você pode adicionar um departamento sem criar uma relação duplicada.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity deve usar somente o campo calculado para planos de aposentadoria (459779)

Ao exportar a entidade **PayrollWorkerEnrolledBenefitDetailEntity**, a exportação determina se ela deve usar um campo calculado com base em uma tabela de taxas ou usar o campo **ContributionAmountCur** na tabela de backup. A lógica usada pela entidade de dados usa a tabela de taxas nas situações em que o aplicativo normalmente não usa. Essa lógica faz com que as exportações da entidade retornem um valor zero para essa coluna, porque não há uma tabela de taxas de cálculo e o produto não permite que o cliente especifique uma.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Traduções confusas no idioma tcheco em Gerenciamento de pessoal e Autoatendimento para funcionários (400276)

Esta versão corrige as traduções de **Diretório da empresa**, **Próximo curso registrado**, **Trabalho** e **Posição**.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>A tabela WorkCalendarEmployment não tem os campos de sistema criados e modificados habilitados (460171)

Os campos do sistema criados e modificados agora estão habilitados na tabela **WorkCalendarEmployment** do Human Resources.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Exceção de referência nula para Contratar e adicionar detalhes de futuro funcionário (455475)

Esta versão corrige um erro (referência nula) em uma entrada de funcionário simplificada quando você contrata um funcionário usando a opção **Contratar e adicionar detalhes**.

## <a name="changes-made-in-the-common-data-service-worker-entity-dont-reflect-in-human-resources-455652"></a>Alterações feitas na entidade Trabalhador do Common Data Service não são refletidas no Human Resources (455652)

Agora, as alterações feitas nos seguintes campos da entidade **Trabalhador** do Common Data Service serão mostradas no Human Resources:

- **Trabalha de casa**
- **Aniversário de tempo de serviço**
- **Data do aniversário de tempo de serviço**
- **Data original da contratação**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>O nível salarial correto não está padronizado com base no trabalho atribuído à posição (394136)

Com esta alteração, o nível salarial correto foi padronizado com base nos registros de **Data de efetivação** para **Detalhes da posição** e **Data de início** de **Atribuição do plano de remuneração**.

## <a name="in-preview"></a>Em visualização

## <a name="mandatory-fields"></a>Campos obrigatórios 

Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources. Este recurso exige **Exibições salvas**.

## <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios
 
Entidades de gerenciamento de benefícios estão sendo liberadas. As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios. Um modelo de gerenciamento de benefícios estará disponível para mover dados. O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.

## <a name="buy-and-sell-leave"></a>Comprar e vender licenças 

Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças. Esse processo costuma ser gerenciado manualmente. Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH. Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros. Para obter mais informações, consulte:

- [Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar e vender licenças](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Deixar o acúmulo para uma única empresa ou um plano

Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência. Essa capacidade esclarece sobre o processo de competência para clientes com diferentes políticas de anos de licença ou acúmulo de licenças. Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md).

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

## <a name="checklist-entities-included-in-common-data-service"></a>Entidades de lista de verificação incluídas no Common Data Service

Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Common Data Service.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)
