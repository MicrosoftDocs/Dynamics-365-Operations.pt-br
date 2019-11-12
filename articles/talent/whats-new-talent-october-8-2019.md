---
title: Novidades ou alterações no Dynamics 365 Talent (8 de outubro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 159320dcbdf257862378b347172ef71832e293dc
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626053"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Novidades ou alterações no Dynamics 365 Talent (8 de outubro de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2542. Os números em parênteses em alguns cabeçalhos referem-se aos números de suporte no Microsoft Dynamics Lifecycle Services (LCS).

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>Remoção da inscrição aberta de benefícios da versão prévia pública

Junto com o comunicado em [Investimentos estratégicos](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/) na postagem do blog de incentivo à excelência operacional do core HR, a Microsoft removerá a versão prévia da inscrição aberta de benefícios da versão prévia pública em 18 de outubro de 2019. Em vez disso, a nova funcionalidade será lançada no futuro. O uso da produção do recurso de inscrição aberta de benefícios atualmente na versão prévia pública não será compatível. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>A integração com o Common Data Service está desativada por padrão nas novas provisões (343675)
 
Quando os novos ambientes forem provisionados, a integração com o Common Data Service será desativada. Para obter mais informações, consulte [Configurar a integração com o Common Data Service](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada e navegação simplificada de funcionário

A funcionalidade para a entrada e navegação de funcionários está disponível em todos os ambientes. Para ativar este recurso, vá para **Administração do sistema \> Links \> Configuração \> Parâmetros do sistema \> Recursos da versão prévia** e selecione **Formulário e navegação aprimorados do funcionário**. Em seguida, o recurso será ativado para todos os usuários. Você pode desativar esta opção a qualquer momento.

Para obter mais informações, consulte [Entrada de dados simplificada do funcionário](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) no plano da onda 2 da versão 2019 do Dynamics 365.

### <a name="issue-attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Problema: os recursos Attract e Onboard criam funcionários inativos no Core HR (380517)

A versão desta semana corrige um problema em que os recursos Attract e Onboard criam funcionários inativos no Core HR.

### <a name="issue-the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>Problema: o fluxo de trabalho falha quando o gerente é conectado a uma outra empresa ao demitir um funcionário (346852)

Não ocorrem mais falhas no fluxo de trabalho com base na entidade legal na qual o gerente está conectado.

### <a name="issue-missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Problema: informações ausentes no HcmOnboardingWorkerChecklistTaskEntity (349591)

Esta versão inclui informações adicionais em **HcmOnboardingWorkerChecklistTaskEntity**. Eis alguns exemplos:

- **Nome do grupo** quando o tipo atribuído for **grupo**
- **Nome do funcionário** quando o tipo atribuído for **funcionário**
- **Nome do gerente** quando o tipo atribuído for **gerente**

### <a name="issue-entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Problema: as entidades não estão listadas em ordem alfabética em Common Data Service Administration (377414)

Problema: agora estão listadas em ordem alfabética na página **CDS Administration**.

### <a name="issue-changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>Problema: alterar o tipo de emprego com uma data futura não permite uma atribuição de posição (339958)

Esta alteração permite atribuições de posição quando os tipos de trabalhador forem alterados (por exemplo, de funcionário para prestador de serviço).

### <a name="issue-updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>Problema: atualizar a entidade de transação bancária de licença do Common Data Service cria um novo registro em Talent (352938)

A transação de licença é atualizada quando uma atualização é feita no Common Data Service para transações bancárias de licença.

### <a name="issue-the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>Problema: o título de anexos para itens de comentário mostra a descrição de comentários (343765)

A descrição do comentário não aparece mais no título do anexo.

### <a name="issue-compensation-workflow-comments-field-shows-incorrect-content-339297"></a>Problema: o campo Comentários do fluxo de trabalho Compensação mostra um conteúdo incorreto (339297)

Esta alteração mostra o conteúdo do campo **%HcmActionState.HcmWorkerActionComment.Comments%**.

### <a name="issue-workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>Problema: WorkCalendarEntity e WorkCalendarDayEntity não são expostos por meio do OData (376329)

Nesta versão, **WorkCalendarEntity** e **WorkCalendarDayEntity** estão disponíveis através do Open Data Protocol (OData).

### <a name="issue-hcmworkerentity-is-slow-when-odata-is-used-375221"></a>Problema: HCMWorkerEntity fica lento quando o OData é usado (375221)

As alterações melhoram o desempenho de **HCMWorkerEntity** quando o designer de pastas de trabalho do Microsoft Excel é usado.

### <a name="issue-manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>Problema: a entrada de diário de desempenho do gerente mostra um erro após excluir um diário de desempenho e criar outro (336061)

Esta versão corrige um problema que ocorre após um diário de desempenho ser excluído e outro ser criado logo em seguida. Esta correção altera o comportamento em autoatendimento para gerentes.

## <a name="coming-soon"></a>Em breve

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Consulte [Revisões de desempenho de impressão](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) no plano da onda 2 da versão 2019 do Dynamics 365.
