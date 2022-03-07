---
title: Novidades ou alterações no Dynamics 365 Human Resources (11 de junho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 11 de junho de 2020.
author: andreabichsel
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f7e8f2b158f3d3274fee87f94c69c599380f2e2c06cf0bd2284f963d46d81c02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774912"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (11 de junho de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3316. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>O formulário de funcionário simplificado às vezes faz com que os botões fechar (X) do formulário filho parem de funcionar (442369)

Com o formulário **Trabalhador** habilitado, o botão fechar (**X**) ocasionalmente não funcionava em formulários filhos. Esse problema era intermitente. Você pode fechar o formulário depois de sair e voltar para ele. Por exemplo, você pode selecionar um item de menu à esquerda, e navegar novamente para o formulário **Trabalhador** e fechá-lo. A versão desta semana corrige esse problema. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>A entidade Pessoa de contato pessoal do trabalhador não exporta contatos pessoais com um tipo de relacionamento pai

Com esta versão, a entidade **Pessoa de contato pessoal do trabalhador** exporta todos os tipos de relacionamento.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity deve fazer parte do pacote de integração da folha de pagamento Ceridian por padrão (448506)

Com essa alteração, **HcmPositionWorkerAssignmentV2Entity** é incluído no pacote de integração da folha de pagamento Ceridian.

## <a name="in-preview"></a>Em visualização

## <a name="database-logging"></a>Log de banco de dados

O recurso de log de banco de dados permite determinar as tabelas e os campos que devem ser monitorados. Ele também permite que você determine os eventos que devem disparar o controle de alterações. Use os recursos de log de banco de dados para ver essas alterações ao longo do tempo. Para obter mais informações, consulte [Configurar e gerenciar o log de banco de dados](hr-admin-database-logging.md).

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

## <a name="new-platform-capabilities"></a>Novos recursos da plataforma 

Você poderá tornar os campos obrigatórios usando a personalização. Este recurso exigirá que você habilite **Exibições salvas**.

## <a name="configure-the-name-of-employee-self-service"></a>Configurar o nome do autoatendimento para Funcionários

Uma nova opção estará disponível nos parâmetros de Recursos Humanos para atualizar o nome do espaço de trabalho de autoatendimento para Funcionários para Autoatendimento. 

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]