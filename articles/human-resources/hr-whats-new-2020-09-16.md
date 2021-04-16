---
title: Novidades ou alterações no Dynamics 365 Human Resources (16 de setembro de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 16 de setembro de 2020.
author: jcart1106
ms.date: 09/16/2020
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
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf0e2d90b07cb488429311d04dfbc4d1d3520842
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800084"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (16 de setembro de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3557. Os números entre parênteses ao lado de alguns recursos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.

## <a name="included-in-this-release"></a>Incluídos nesta versão

-  [Exibições salvas - disponibilidade geral](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- Para obter mais informações, consulte [Exibições salvas](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/saved-views). 

- O formulário **Ações de posição** tem uma grade de dimensões atualizada e um novo diálogo (469495).

- Se você definir **Restringir o acesso às informações do trabalhador** como Sim em **Acesso avançado** em **Parâmetros compartilhados do Human Resources**, os formulários de benefícios agora mostram somente os trabalhadores apropriados (393384).

- Novas opções de geração de calendário na entidade **WorkCalendar** (477055):<br>- Hora de término padrão<br>- Hora de início padrão<br>- Sexta-feira é dia útil<br>- Segunda-feira é dia útil<br>- Sábado é dia útil<br>- Domingo é dia útil<br>- Quinta-feira é dia útil<br>- Terça-feira é dia útil<br>- Quarta-feira é dia útil<br>- ID de feriado do calendário de trabalho

- A entidade **LeaveBankTransactionV1** agora inclui o código de razão (477823).

- Agora você pode salvar gravações de tarefas (492923).

- Os dados agora são publicados com sucesso em **HCMWorkerContactEntity** (427620).

- A guia rápida **Compensação** agora é exibida para o tipo de trabalhador contratado no formulário **Ações do trabalhador** (482494).

- Os campos **Nível** e **Plano** agora são obrigatórios se você definir **Compensação fixa**. Uma mensagem de erro será exibida se você deixar esses campos em branco (482497).

- O campo **Tipo de plano** em **Benefícios** é agora uma lista suspensa (488768).

- Os administradores do sistema agora recebem uma notificação se um campo personalizado for excluído do Human Resources (481408).

- Durante o processo de demissão do funcionário, o departamento do Human Resources se comporta conforme o esperado e não muda a empresa selecionada após parecer estar bloqueado (479877). 

- Os gerentes não podem mais adicionar uma coluna de número por meio da personalização (485317).

- Os gerentes não podem mais remover o filtro de intervalo de dados dos números de identificação que expiram (485321).

- Quando o campo **Subordinado a** está vazio, os detalhes da posição ainda são exibidos ao passar o mouse sobre a posição (433328).

- Os funcionários agora podem exibir as informações do plano de benefícios no Autoatendimento para funcionários (481676).

- Os funcionários agora podem ver todos os cursos registrados (429048).

- Agora você pode restringir as opções de exibição para a página **Certificados profissionais**. Você pode restringir as opções de exibição à entidade legal atual, por status do trabalhador e por tipo de trabalhador (451501). 


## <a name="in-preview"></a>Em Visualização

### <a name="human-resources-app-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte:

- [Licença e ausência do funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do ciclo de lançamentos 1 de 2020 do Dynamics 365
- [Aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841) na documentação do Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Aplicativo Human Resources nos recursos de visualização do Teams
 
-  **Notificações**: os remetentes e aprovadores de solicitações de folga serão notificados no aplicativo Human Resources no Teams. Os aprovadores poderão aprovar ou negar solicitações de folgas. Os remetentes serão notificados caso a solicitação seja aprovada ou negada. Para obter mais informações, consulte:
   - [Licença e ausência do funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do ciclo de lançamentos 2 de 2020 do Dynamics 365
   - [Habilitar notificações para o aplicativo Human Resources no Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) na documentação do Human Resources
   - [Ativar ou desativar notificações do Teams para usuários individuais](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) na documentação do Human Resources
   - [Notificações do Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) na documentação do Human Resources
   - [Exibir calendário de licenças da sua equipe](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) na documentação do Human Resources
 
- **Calendário de folga do gerente**: Os gerentes poderão ver o tempo de folga aprovado e pendente para seus subordinados direto em um modo de exibição de calendário. Esta exibição fornece uma compreensão fácil de quando os membros da equipe estão ausente do trabalho. Para obter mais informações, consulte:
   - [Licença e ausência do funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do ciclo de lançamentos 2 de 2020 do Dynamics 365
   - [Exibir calendário de licenças da sua equipe](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) na documentação do Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim (477004)

Uma nova opção agora está disponível para posicionar a lista **Itens de trabalho atribuídos a mim** na coluna direita do painel. Com essa alteração, todas as listas de itens de trabalho e tarefas pendentes são exibidas na mesma área. Habilite essa funcionalidade ativando **Versão prévia - Aperfeiçoamentos de experiência de fluxo de trabalho** no gerenciamento de recursos. Para obter mais informações sobre a ativação de recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).

Esse recurso também promove as opções de fluxo de trabalho que aparecem nos formulários de ações de pessoal. As opções de fluxo de trabalho também aparecem acima da guia rápida de ação para acesso rápido. Para obter mais informações, consulte: 

- [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) no plano do ciclo de lançamentos 2 de 2020 do Dynamics 365

![Itens de trabalho atribuídos a mim](./media/hr-workflow-work-items-assigned-to-me.png)

![Acesso rápido aos itens de fluxo de trabalho](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>Calendário de licenças e ausências

Essa versão inclui opções de calendário adicionais para calendários de licenças e ausências. Para obter mais informações, consulte [Exibir calendários da equipe e da empresa](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-calendar).

## <a name="coming-soon"></a>Em breve

### <a name="checklist-entities-included-in-dataverse"></a>Entidades de lista de verificação incluídas no Dataverse

Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.

### <a name="benefits-management-reason-codes"></a>Códigos de motivo de gerenciamento de benefícios

Os códigos de motivo de gerenciamento de benefícios serão em breve combinados com os códigos de motivo existentes no Human Resources. Se você tiver criado códigos de motivo no gerenciamento de benefícios com mais de 15 caracteres, deverá alterar o nome do código de motivo no formulário **Códigos de motivo** de gerenciamento de benefícios para 15 caracteres ou menos. Depois de atualizar o nome, o código de motivo aparecerá no formulário de código de motivo existente em Gerenciamento de pessoal. Esta alteração estará disponível no futuro e não afetará a funcionalidade existente.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]