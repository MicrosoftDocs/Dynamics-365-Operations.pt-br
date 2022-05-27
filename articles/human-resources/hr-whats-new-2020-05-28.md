---
title: Novidades ou alterações no Dynamics 365 Human Resources (28 de maio de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 28 de maio de 2020.
author: andreabichsel
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 88e0938ab9be8066d6ed4709ca2c7074ebe46dc3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685957"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (28 de maio de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3287. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>A entidade LeaveRequest não funciona ao habilitar vários tipos por plano de licença (447498)

Com essa alteração, a **LeaveEnrollmentV2Entity** agora está disponível para corrigir o erro que ocorre quando você habilita vários tipos de licença.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Recurso de redução de contenção de lotes (versão prévia) (446619)

Ao habilitar esse recurso, você pode esperar uma redução no bloqueio em tabelas de estrutura de lotes ao selecionar tarefas e concluir trabalhos.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>UpdateConflict ao salvar o trabalhador impede a edição de um registro em Pessoas (427915)

Essa alteração corrige um erro ao adicionar um novo funcionário, atualizar as informações de endereço e alterar a preferência do idioma. Neste cenário único, um erro foi exibido indicando que não foi possível atualizar o registro. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>Não é possível adicionar um anexo a uma solicitação de licença aprovada para reenvio (425407)

Essa alteração agora permite anexos a solicitações de licença aprovadas.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>O usuário pode inserir remuneração para um funcionário em um formulário de entidade legal diferente (409529)

Essa alteração desativa as opções de remuneração para impedir a entrada inadvertida de registros de remuneração da entidade legal errada.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Erro ao transferir um funcionário e a data de atribuição da posição do trabalhador é anterior à duração da posição (429402)

As mensagens de erro ao transferir um funcionário neste cenário foram atualizadas para descrever melhor as alterações necessárias para corrigir o problema.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Recursos de anexos da inscrição de benefícios de Autoatendimento para funcionários
 
Agora você pode adicionar anexos durante o processo de inscrição de benefícios para cada plano em que o funcionário se inscreva. Em seguida, você poderá exibir os anexos no formulário **Benefício do trabalhador inscrito**.

## <a name="in-preview"></a>Em visualização

## <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte [aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md). 

## <a name="leave-suspension"></a>Sair da suspensão

Você pode suspender a licença e a ausência em Human Resources para um funcionário. Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados. Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário. Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Atualizar a experiência do usuário para indicar que a acumulação foi suspensa (429550)

Agora, a experiência do usuário indica que a acumulação foi suspensa para um plano.

## <a name="coming-soon"></a>Em breve

## <a name="database-logging-in-preview-in-june"></a>Log do banco de dados (na visualização em junho)

O recurso de log de banco de dados permite determinar a tabela e os campos que devem ser monitorados. Ele também permite que você determine os eventos que devem disparar o controle de alterações. Os recursos de consulta estão disponíveis para ver essas alterações ao longo do tempo.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Licença de compra e venda (na visualização de 1º de junho)

Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças. Esse processo costuma ser gerenciado manualmente. Esse recurso oferece uma forma mais automatizada de gerenciar políticas e solicitações para o departamento de RH, além de ajudar a eliminar erros e simplificar o processo de gerenciamento de licenças. Para obter mais informações, consulte:

- [Gerenciar políticas de compra e venda de licenças](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar e vender licenças](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios
 
Entidades de gerenciamento de benefícios estão sendo liberadas. As entidades DMF permitem importar e exportar dados para configurar facilmente o gerenciamento de benefícios. Um modelo de gerenciamento de benefícios também estará disponível para mover dados. O modelo exporta e importa os dados de uma forma sequencial para respeitar as dependências de dados.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Adicionar código de motivo a suspensões de acúmulos (1º de junho)

Os códigos de motivo foram adicionados à suspensão de acúmulos.

## <a name="carry-forward-rules-june-1"></a>Regras de postergação (1º de junho)

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Suspender a acumulação de licenças para tipos de licença especificados (1º de junho)

Nesta versão, o HR pode criar uma regra para suspender as competências de licença para funcionários com solicitações de licença inseridas para licenças não pagas. A licença não remunerada pode ser um tipo, mas não precisa ser. Você pode suspender qualquer licença com base em outro tipo de licença.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>Entidade DMF disponível para suspensões de acúmulos (1º de junho)

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]