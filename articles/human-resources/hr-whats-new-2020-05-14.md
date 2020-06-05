---
title: Novidades ou alterações no Dynamics 365 Human Resources (14 de maio de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/14/2020
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
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d46671f73a75a9ed3a652d76153c923a3542b5f6
ms.sourcegitcommit: 7c750711e9fe1d3726c6ee650669529684933001
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386098"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (14 de maio de 2020)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3244. Os números entre parênteses em alguns cabeçalhos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.

## <a name="platform-changes"></a>Alterações na plataforma

As alterações de plataforma são incluídas na versão desta semana. Para obter mais informações, consulte [Atualizações de plataforma para a versão 10.0.10 dos aplicativos do Finance and Operations (maio de 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34). Esta versão inclui correções de bug e alterações nas exibições salvas.
 
## <a name="ensure-common-data-service-picklists-are-consistent-with-leave-enums-436343"></a>Verifique se as listas de separação do Common Data Service estão consistentes com as enumerações Licença (436343)

Agora as listas de separação do Common Data Service estão consistentes com as enumerações Licença.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>Permita que os usuários configurem o fluxo de trabalho de solicitação de licenças com base no valor da solicitação (300044)

Os usuários podem configurar os fluxos de trabalho de solicitações de licença com base nos valores da solicitação.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>O novo formulário do trabalhador expõe dados por meio do menu Exibir quando a segurança avançada estiver habilitada (403185)

Esta versão corrige como a exibição de trabalhadores em entidades legais funciona quando o acesso avançado está habilitado e os trabalhadores em outras empresas estão acessíveis.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Permitir a execução de acúmulos de licenças para um único plano ou uma única empresa (318844)

Com essa alteração, você pode executar acúmulos para uma empresa ou um plano.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>Mostrar o equivalente ao horário integral (FTE) do cargo no formulário de Trabalhadores registrados (414658)

O valor do FTE do cargo de um trabalhador determina a taxa de acúmulo do trabalhador quando a opção FTE estiver habilitada no tipo de licença. Este campo agora está incluído no formulário **Trabalhadores registrados** e na caixa de diálogo **Inscrição em massa**.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Adicionar trabalho em lotes de expiração de saldo de licenças (431266)

Um novo trabalho em lotes agora está disponível e é executado diariamente. Ele diminui o saldo de licença restante quando as datas de vencimento são atualizadas.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>Exportar contatos pessoais de um funcionário usando a entidade Pessoa de contato pessoal do trabalhador não exporta os contatos pessoais com o tipo de relacionamento Principal (345893)

A entidade de dados **Pessoa de contato pessoal do trabalhador** (**HcmPersonalContactPersonEntity** no DMF e **PersonalContactPerson** em OData) não pôde exportar contatos pessoais que contenham um tipo de relacionamento **Principal**. Esse problema é corrigido para contatos pessoais criados após essa alteração. Os contatos pessoais existentes do tipo **Principal** serão corrigidos em uma versão posterior.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>Os códigos de motivo são exibidos em diferentes cenários quando estão marcados como Licença e ausência e o formulário simplificado do funcionário está habilitado (434163)

Essa alteração restringe os códigos de motivo para apenas códigos de Licença e ausência ao habilitar a entrada simplificada do funcionário.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>O recurso de versão preliminar Atribuir plano de licença a funcionários no futuro exibe um erro (433555)

Essa alteração corrige um erro quando um plano de licença tem dois tipos de licença atribuídos e você tenta atribuir um funcionário.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>A faixa de introdução aparece para todos os usuários (441731)

Com essa alteração, a faixa de introdução fica oculta para usuários que não são Administradores do sistema ou Administradores do gerenciamento de dados. 

## <a name="the-common-data-service-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>A entidade Endereço do Trabalhador do Common Data Service funciona de forma diferente em termos de datas de efetivação de data/hora no Human Resources (425071)

Essa alteração mantém as informações de endereço alinhadas em determinados cenários, com base nas datas do endereço.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>Não é possível adicionar um anexo a uma solicitação de licença aprovada (425407)

Com a versão desta semana, você pode adicionar anexos a solicitações de licença aprovadas sem alterar a solicitação de licença.

## <a name="in-preview"></a>Em visualização

## <a name="leave-suspension"></a>Sair da suspensão

Você pode suspender a licença e a ausência em Human Resources para um funcionário. Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados. Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário. Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Atualizar a experiência do usuário para indicar que a acumulação foi suspensa (429550)

Agora, a experiência do usuário indica que a acumulação foi suspensa para um plano.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Suspender a acumulação de licenças para tipos de licença especificados (272447)

Nesta versão, o HR pode criar uma regra para suspender as competências de licença para funcionários com solicitações de licença inseridas para licenças não pagas. A licença não remunerada pode ser um tipo, mas não precisa ser. Você pode suspender qualquer licença com base em outro tipo de licença.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Entidade DMF disponível para suspensões de acúmulos (429549)

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Adicionar código de motivo a suspensões de acúmulos (429547)

Os códigos de motivo foram adicionados à suspensão de acúmulos.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Iniciar transição dos parâmetros de Human Resources para os parâmetros de licença e ausência

Esta versão começa a combinar parâmetros de Human Resources com parâmetros de licença e ausência.

## <a name="carry-forward-rules"></a>Regras de postergação

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).
