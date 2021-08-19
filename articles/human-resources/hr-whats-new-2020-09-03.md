---
title: Novidades ou alterações no Dynamics 365 Human Resources (03 de setembro de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 3 de setembro de 2020.
author: andreabichsel
ms.date: 09/03/2020
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
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d7c3e3070d6c3b8dad7b3ae4d50e928d0060d5892d606cd78bc701c2e7985cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759686"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (3 de setembro de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3504. Os números entre parênteses em alguns cabeçalhos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.

Para obter mais informações sobre os recursos futuros do Human Resources, consulte a [Visão geral do ciclo de lançamentos 2 de 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). Para obter mais informações sobre o processo de atualização do Human Resources, consulte [Processo de atualização](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>Nesta versão

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Nova grade padrão de dimensões financeiras e padrão de diálogo durante Human Resources (469495)

O novo padrão para dimensões financeiras agora está disponível nas seguintes áreas:

- Ações de posição (formulário: **HcmPositionActionDetail**)
- Códigos de ganhos da folha de pagamento (formulário: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>As entradas não aparecerão no calendário de licença da empresa se não forem habilitados os aprimoramentos do calendário de licença e ausência (484406)

Esta versão corrige um problema em que as entradas de licença não são exibidas no calendário de licenças da empresa. Esse problema ocorre apenas quando a opção de Gerenciamento de recursos **Aprimoramentos do calendário de licença e ausência** não está habilitada.

### <a name="benefitplanemployeeentity-issue-467597"></a>Problema BenefitPlanEmployeeEntity (467597)

Esta versão corrige um problema com a entidade **BenefitsPlanEmployee** . Ao importar inscrições do trabalhador, o **Código de cobertura** e o **Código do tipo de plano** agora são definidos corretamente. Esse problema levou à exibição incorreta dos planos de benefícios do funcionário nos formulários **Plano de benefícios do trabalhador** e **Inscrição aberta** no autoatendimento para funcionários.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>Saída de arquivo eletrônico 1094-C com letra ausente em XML (435190)

Esta alteração corrige um problema no arquivo de saída 1094-C, em que falta um caractere necessário ao enviar para a Administração Fiscal.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Tabela de remuneração variável do funcionário mapeada para formulário de remuneração fixa (476117)

Essa alteração alinha os campos de remuneração fixa ao formulário de remuneração fixa. Os campos de remuneração variável agora só estão disponíveis com o formulário de remuneração variável.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>Deixar solicitações permitidas antes da registro se esse tipo de licença tiver um saldo mínimo negativo (469917)

Essa alteração proíbe a inserção de solicitações de licença antes de ser registrada no plano, mesmo que o registro tenha um saldo mínimo negativo. Você só pode inserir ou enviar solicitações quando o plano está ativo.

### <a name="document-templates-dont-download-457279"></a>Os modelos de documento não são baixados (457279)

Com essa alteração, agora é possível baixar todos os modelos de documento. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>Os dados são exibidos como cabeçalhos de coluna em vez de linhas para o campo Taxa de pagamento no relatório plano de remuneração (476077)

O relatório de análise agora exibe as informações corretas para **Taxa de pagamento** .

## <a name="in-preview"></a>Em visualização

### <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte:

- [Licença e ausência do funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do ciclo de lançamentos 1 de 2020 do Dynamics 365
- [Aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md) na documentação do Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Aplicativo Human Resources nos recursos de visualização do Teams
 
-  **Notificações**: os remetentes e aprovadores de solicitações de folga serão notificados no aplicativo Human Resources no Teams. Os aprovadores poderão aprovar ou negar solicitações de folgas. Os remetentes serão notificados caso a solicitação seja aprovada ou negada. Para obter mais informações, consulte:
   - [Licença e ausência do funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do ciclo de lançamentos 2 de 2020 do Dynamics 365
   - [Habilitar notificações para o aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) na documentação do Human Resources
   - [Ativar ou desativar notificações do Teams para usuários individuais](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) na documentação do Human Resources
   - [Notificações do Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) na documentação do Human Resources
   - [Exibir calendário de licenças da sua equipe](./hr-teams-leave-app.md#view-your-teams-leave-calendar) na documentação do Human Resources
 
- **Calendário de folga do gerente**: Os gerentes poderão ver o tempo de folga aprovado e pendente para seus subordinados direto em um modo de exibição de calendário. Esta exibição fornece uma compreensão fácil de quando os membros da equipe estão ausente do trabalho. Para obter mais informações, consulte:
   - [Licença e ausência do funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do ciclo de lançamentos 2 de 2020 do Dynamics 365
   - [Exibir calendário de licenças da sua equipe](./hr-teams-leave-app.md#view-your-teams-leave-calendar) na documentação do Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim (477004)

Uma nova opção agora está disponível para posicionar a lista **Itens de trabalho atribuídos a mim** na coluna direita do painel. Com essa alteração, todas as listas de itens de trabalho e tarefas pendentes são exibidas na mesma área. Habilite essa funcionalidade ativando **Versão prévia - Aperfeiçoamentos de experiência de fluxo de trabalho** no gerenciamento de recursos. Para obter mais informações sobre a ativação de recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).

Esse recurso também promove as opções de fluxo de trabalho que aparecem nos formulários de ações de pessoal. As opções de fluxo de trabalho também aparecem acima da guia rápida de ação para acesso rápido. Para obter mais informações, consulte: 

- [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) no plano do ciclo de lançamentos 2 de 2020 do Dynamics 365

![Itens de trabalho atribuídos a mim.](./media/hr-workflow-work-items-assigned-to-me.png)

![Acesso rápido aos itens de fluxo de trabalho.](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Em breve

### <a name="checklist-entities-included-in-dataverse"></a>Entidades de lista de verificação incluídas no Dataverse

Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.

### <a name="benefits-management-reason-codes"></a>Códigos de motivo de gerenciamento de benefícios

Os códigos de motivo de gerenciamento de benefícios serão em breve combinados com os códigos de motivo existentes no Human Resources. Se você tiver criado códigos de motivo no gerenciamento de benefícios com mais de 15 caracteres, deverá alterar o nome do código de motivo no formulário **Códigos de motivo** de gerenciamento de benefícios para 15 caracteres ou menos. Depois de atualizar o nome, o código de motivo aparecerá no formulário de código de motivo existente em Gerenciamento de pessoal. Esta alteração estará disponível no futuro e não afetará a funcionalidade existente.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
