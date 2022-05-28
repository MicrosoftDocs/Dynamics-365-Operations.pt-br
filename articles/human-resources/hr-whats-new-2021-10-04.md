---
title: Novidades ou alterações no Dynamics 365 Human Resources 5 de outubro de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 5 de outubro de 2021.
author: marcelbf
ms.date: 10/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3cf83421d5385e3c95dfda6db35edfb8eb4b9336
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695750"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 5 de outubro de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Microsoft Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4485.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
|---|---|---|
| Atualização da plataforma 10.0.21 (45) | -- | [Atualizações de plataforma para a versão 10.0.21 dos aplicativos de Finanças e Operações (outubro de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema | Descrição |
|---|---|---|
| 598896 | O valor do funcionário só será exibido depois que o funcionário concluir a inscrição | Na página **Autoatendimento para funcionários**, o valor do funcionário para o benefício não foi exibido. O valor do funcionário agora é exibido na página **Autoatendimento de benefícios**.  |
| 613440 | Não é possível exportar dados do **Gerenciamento de dados** | Ao exportar dados para um projeto no **Gerenciamento de dados**, a exportação falha inesperadamente. |
| 618327 | Os períodos fechados e futuros são exibidos na página **Parâmetros de relatórios** para o demonstrativo de benefícios | Ao navegar até **Demonstrativo de benefícios** em **Autoatendimento para funcionários**, a página **Parâmetros de relatório** exibe os **Registros a serem incluídos** nas Guias Rápidas **Executar em segundo plano**. Essas seções foram removidas.|
| 618326 | A página incorreta **Parâmetros de relatório** é exibida em **Autoatendimento para funcionários** para o demonstrativo de benefícios| Ao navegar até a página de destino **Relatório de demonstrativo de benefícios**, o usuário pôde selecionar os períodos de planejamento de benefício que estão fechados ou que são futuros, o que resulta em uma página em branco. Somente o período atual do plano de benefícios deve ser exibido na lista. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre como ativar ou desativar os recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
|---|---|---|
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Campos personalizados na qualificação |[Suporte a campos personalizados no processamento de qualificação](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Usando campos personalizados no processamento de qualificação](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Demonstrativo de benefícios |[Demonstrativo de Benefícios](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Demonstrativo de benefícios](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Problemas conhecidos do Demonstrativo de benefícios

| Problema | Descrição |
|---|---|
|Erro ao enviar o relatório por email usando o **destino do relatório GER** | O demonstrativo de benefícios pode ser definida para usar os parâmetros de email na página **Destinos do relatório GER**. Ao concluir a configuração e imprimir o relatório, o usuário receberá um erro de formatação e o demonstrativo de benefícios não será enviada.|

## <a name="feature-management-changes"></a>Alterações no gerenciamento de recursos

| Recurso | Descrição |
|---|---|
|Exibição de diários de desempenho de subordinados por extensão | Esse recurso ficará habilitado por padrão nesta versão. |

## <a name="coming-soon"></a>Em breve

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Recurso | Detalhes |
|---|---|
| Atualização da plataforma 10.0.22 (46) | A implementação da atualização da plataforma 10.0.22 está agendada para começar na versão de serviço, em 1 de novembro de 2021. Para mais informações, consulte [Atualizações de plataforma para a versão 10.0.22 dos aplicativos de finanças e operações (novembro de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Consulte também

[Novidades ou mudanças no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
