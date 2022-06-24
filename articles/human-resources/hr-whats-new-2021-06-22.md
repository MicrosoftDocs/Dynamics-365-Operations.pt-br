---
title: Novidades ou alterações no Dynamics 365 Human Resources de 22 de junho de 2021
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 22 de junho de 2021.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aacb605374d99a3c0bad3438c89e33a04a4d7faf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897767"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources de 22 de junho de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve os recursos novos, alterados ou que serão lançados em breve no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4258.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Recurso Informar os usuários sobre trabalhadores sem emprego - Quando o acesso avançado estiver ativado e o recurso **Visualizar todos os trabalhadores sem emprego** estiverem desabilitados no gerenciamento de recursos, uma faixa será exibida no formulário de trabalhadores sem emprego. A faixa direcionará o usuário a ativar o recurso **Visualizar todos os trabalhadores sem emprego**. | Não Aplicável| [Trabalhadores sem emprego](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Suporte a campo personalizado para Regras de qualificação de gerenciamento de benefícios | [Suporte a campos personalizados para processamento de qualificação](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configurando regras de qualificação](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Auditoria de transações de acúmulo de licenças | Não Aplicável | [Auditoria de transações de acúmulo de licenças](hr-leave-and-absence-accrue.md)|
| Aprimoramentos de experiência de fluxo de trabalho de licença e ausência | [Aprimoramentos de experiência de fluxo de trabalho de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar folga](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este artigo para incluir correções de bugs feitas no build após a publicação inicial deste artigo.

| Número do problema | Problema |  Descrição |
| --- | --- | --- |
| 583052 | O usuário que recebe feedback é capaz de editar o feedback recebido | Quando um funcionário que recebe feedback em um diário de desempenho selecionar **Adicionar link externo**, o formulário ficará editável, permitindo que o funcionário edite o feedback de desempenho que recebeu. |
| 522281 | Se você selecionar o número de funcionários nos blocos da estrutura de remuneração no Gerenciamento de remuneração, isso gerará resultados incorretos| Ao detalhar os planos de remuneração no espaço de trabalho de remuneração, o número correto de funcionários agora é exibido. |
| 580683 | Os usuários atribuídos às funções Funcionário e Gerente não podem anexar notas ou atualizar um Diário de desempenho | Os usuários atribuídos às funções Funcionário e Gerente não podem anexar notas ou atualizar um Diário de desempenho. O usuário recebe o erro: "Não é possível criar um registro na entrada do Diário de desempenho (HcmPerfJournal). Permissão de política de segurança negada." |
| 583077 | A data de nascimento de um funcionário no calendário de licenças e ausências da empresa mostra uma data incorreta | Os usuários poderão visualizar a data de nascimento correta dos funcionários no calendário de licenças e ausências da empresa. |
| 586996 | O recurso de visualização de licença entre empresas faz com que os saldos fiquem vazios quando o acesso é restrito a uma única empresa | Os usuários podem visualizar os saldos de licenças futuras do funcionário corretamente quando a visualização de licença entre empresas é ativada. |
| 581014 | Habilitar a visualização de licença e ausência entre empresas causa um erro ao visualizar saldos futuros | Erros foram corrigidos quando os usuários estavam visualizando os saldos de licenças futuras com a visualização de licenças entre empresas habilitada. |
| 509404 | Análise do departamento de pessoal não considerando a movimentação de funcionários entre departamentos. | Quando um funcionário migra de um departamento para outro, os dados do departamento não refletem o antigo departamento de onde o funcionário foi enviado se o detalhe do cargo expirar no ano atual. |
| 584851 | A regra de rateio de crédito de benefícios "Nenhum" nunca fornece crédito |A regra de rateio de crédito flexível "Nenhum" fazia com que os funcionários recebessem créditos zero durante o período do benefício, independentemente de quando foram contratados. Isso foi corrigido, de forma que o funcionário receberá créditos flexíveis totais se tiver sido contratado antes do início do período de benefícios, e nenhum crédito se tiver sido contratado após o início do período. |
| 584897 | A duplicação da obrigação "Usar funcionalidade externa básica" resulta em um erro | Ao tentar duplicar a obrigação "Usar funcionalidade externa básica", o usuário recebia o erro: "Não foi possível encontrar o objeto com o identificador UserDefinedAppHostDialogView." |
| 575692 | O recurso Acumular licença e ausência não está disponível para trabalhadores pendentes | O acúmulo de licenças e ausências pode ser executado em contratações futuras quando a **Entrada simplificada do funcionário** estiver ativada. |
| 580110 | Ao adicionar uma empresa à integração da folha de pagamento, a integração é redefinida para usar todas as entidades, mesmo que a opção seja definida para não atualizar o projeto | Se um cliente tiver removido entidades ou alterado o projeto de dados para integração de folha de pagamento e a opção de evitar uma atualização automática do projeto estiver configurada, a adição de uma nova empresa à integração ignora a configuração e atualiza o projeto.  |
| 584518 |Problema de desempenho para se inscrever no processamento de benefícios | Esse bug abordou problemas de desempenho no processo legado de inscrição em benefícios. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| Atualização da plataforma 10.0.19 (43) | A atualização da plataforma 10.0.19 está agendada para começar a ser implementada na versão de serviço, em 28 de junho de 2021. Para mais informações, consulte [Atualizações de plataforma para a versão 10.0.19 dos aplicativos de Finanças e Operações (junho de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  Opção Exibição de anos de serviço | Este recurso oferece a opção de usar datas diferentes para calcular os anos de serviço exibidos no formulário de **Entrada de funcionário simplificada** e no formulário **Pessoas**.  Isso estará disponível nos parâmetros de Recursos Humanos. |
|  Habilitar um gerente de ausência para gerenciar a licença | [Habilitar um gerente de ausência para gerenciar a licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Anexos de mandato para tipos de licenças específicas | Esse recurso permite que os administradores exijam que sejam adicionados anexos ao enviar solicitações de licença para tipos específicos de licença. |
|  Configurar unidades de licença por tipo de licença | Esse recurso permite que os administradores configurem unidades de licença (horas ou dias) para cada tipo de licença.  |
| Permitir que os funcionários sejam marcados como prontos para serem pagos | [Permitir que os funcionários sejam marcados como prontos para serem pagos](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
