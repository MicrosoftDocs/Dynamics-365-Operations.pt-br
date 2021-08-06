---
title: Novidades ou alterações no Dynamics 365 Human Resources – 12 de julho de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 12 de julho de 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2851c36594384dd62f4bb95263cfd4407aec104
ms.sourcegitcommit: 71952e97774547230285026c6a3a6caea2512920
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "6614824"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources – 12 de julho de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4353.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
|  Opção Exibição de anos de serviço | |Este recurso oferece a opção de usar datas diferentes para calcular os anos de serviço exibidos na página **Entrada de funcionário simplificada** e na página **Pessoas**.  Isso estará disponível nos [Parâmetros de Recursos Humanos](/dynamics365/human-resources/hr-setup-parameters). |


### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  descrição |
| --- | --- | --- |
| 595871 | O painel Sobre no Human Resources tem a terminologia incorreta do Dataverse | Com a mudança da marca de Common Data Service para Dataverse, a terminologia foi atualizada no painel de informações do Microsoft Dynamics 365 Human Resources (**Ajuda e Suporte > Sobre**). |
| 598676 | A tarefa simplificada de substituição do formulário de entrada do funcionário pode criar um erro quando usada com a Exibição salva| Na página **Trabalhador**, se o recurso "Entrada de Funcionário Simplificada" estiver ativado, o aplicativo poderá falhar se **Sempre aberto para edição** estiver definido na exibição salva. |
| 592344 |A seção de remuneração de trabalhadores sobre o cargo deve ser somente leitura quando o gerenciamento de benefícios está habilitado | As informações de remuneração de trabalhadores são criadas usando a funcionalidade de benefícios legados.  Quando o gerenciamento de benefícios está habilitado, os campos serão somente leitura. Quando o gerenciamento de benefícios está ativado e os **Formulários de benefícios legados** estão definidos como **Sim** nos parâmetros compartilhados de RH, a guia **Remuneração de trabalhadores** será ocultada. |
| 598617 | A guia de ativação do formulário **HcmDiscussion** causa loop infinito quando as personalizações são aplicadas | Quando a grade e a exibição de detalhes têm **Sempre aberto para edição** ativado, o código que ativa a guia no método de tarefa substituído entra em conflito com a personalização sobre qual controle deve ter foco e cria um loop infinito. |
| 593553 | O campo Data do Diário no diário de desempenho é exibido em UTC | O campo **Data do Diário** para diários de desempenho é exibido no fuso horário UTC em vez do fuso horário definido na configuração da data do sistema, fazendo com que a data fique incorreta para alguns fusos horários. |
| 586930 | Abrir atividades para metas de desempenho abre um registro completamente diferente | Quando o recurso "Exibição de relatórios estendidos dos Diários de Desempenho" está habilitado no Gerenciamento de Recursos, a seleção das metas de desempenho para relatórios estendidos na guia **Minha equipe**, em **Autoatendimento para Funcionários**, abre as metas para um funcionário em vez do funcionário selecionado. |
| 569959 |  A entidade HcmPositionWorkerAssignmentV2 não atribui um trabalhador a um cargo | Os usuários receberam um erro ao adicionar um registro de atribuição de cargo por meio da entidade, e a publicação falhou. |
| 582259 | O relatório VETS 4212 usa o formulário 2017 em vez do formulário 2020 | Atualizado para o formato 2020.  Para carregar o novo formato, vá para **Configurações de relatório** e exclua o relatório VETS-4212 na coluna esquerda. Vá para **Relatório Eletrônico - Repositórios - Recursos de RH** e selecione **Aberto**.  Selecione **Impressão de PDF VETS-4212** e, em seguida, selecione **Importar**.|


## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|
|  Habilitar um gerente de ausência para gerenciar a licença | [Habilitar um gerente de ausência para gerenciar a licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Configurar função de gerente de ausências](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Configurar requisito de anexo por tipo de licença | [Configurar requisito de anexo por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurar unidades de licença por tipo de licença | [Configurar unidades de licença por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permitir que os funcionários sejam marcados como prontos para serem pagos | [Permitir que os funcionários sejam marcados como prontos para serem pagos](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto para Pagar](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| Atualização da plataforma 10.0.20 (44) | A atualização da plataforma 10.0.20 está agendada para começar a ser implementada na versão de serviço, em 26 de julho de 2021. Para obter mais informações, consulte [Atualizações de plataforma para a versão 10.0.20 dos aplicativos do Finance and Operations (agosto de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
