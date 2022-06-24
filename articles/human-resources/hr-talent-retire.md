---
title: Desativação do Dynamics 365 Talent -Aplicativos Attract e Onboard
description: Este artigo descreve a desativação do Dynamics 365 Talent - aplicativos-Attract e Onboard.
author: twheeloc
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3039b0a837335a777cdd6ff22b8b6e7c014ef956
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845074"
---
# <a name="dynamics-365-talent-attract-and-onboard-apps-retirement"></a>Dynamics 365 Talent: Attract -desativação dos aplicativos Attract e Onboard


Em dezembro de 2019, anunciamos a desativação dos aplicativos Dynamics 365 Talent - Attract e Onboard em 1º de fevereiro de 2022, dando a nossos clientes dois anos para planejar.

Para obter mais informações sobre a desativação desses aplicativos, consulte:
 - [Desativação do Dynamics 365 Talent - aplicativos Attract e Dynamics 365 Talent: Onboard ](https://community.dynamics.com/365/humanresources/b/dynamics365forhumanresources/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)
 - [Criação de uma força de trabalho mais bem-sucedida com Dynamics 365 Human Resources](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources)

Continuaremos a dar suporte ao Dynamics 365 Human Resources, o que ajudará nossos clientes a receberem insights de força de trabalho necessárias para criar experiências de funcionário orientada a dados em várias áreas, como:

- Remuneração
- Benefícios
- Licença e ausência
- Conformidade
- Payroll
- Comentários sobre desempenho
- Treinamento e certificação
- Programas de autoatendimento

## <a name="dynamics-365-talent-apps-retirement-faq"></a>Dynamics 365 Talent- Perguntas frequentes sobre a desativação dos aplicativos

### <a name="what-is-the-user-experience-for-both-dynamics-365-talent---attract-and-onboard-apps-starting-february-1-2022"></a>Qual é a experiência do usuário com os aplicativos Dynamics 365 Talent - Attract e Onboard com início em 1 de fevereiro de 2022?

Os usuários não poderão usar os aplicativos e serão redirecionados para uma página de desativação.

### <a name="can-customers-continue-to-export-data-for-both-dynamics-365-talent---attract-and-onboard-apps-after-february-1-2022"></a>Os clientes podem continuar a exportar dados para o aplicativos Dynamics 365 Talent- Attract e Onboard após 1 de fevereiro de 2022?
  
Não, a aposentadoria foi anunciada em dezembro de 2019 e os recursos de exportação necessários foram fornecidos até 1 de fevereiro de 2022. 

### <a name="will-the-customers-data-related-to-both-dynamics-365-talent---attract-and-onboard-apps-in-dataverse-be-deleted-after-february-1-2022"></a>Os dados do cliente relacionados a aplicativos Dynamics 365 Talent - Attract e Onboard em Dataverse serão deletados após 1 de fevereiro de 2022?

Não, as entidades Dataverse permanecerão no ambiente do cliente Microsoft Dataverse mesmo após a desativação, a menos que a solução de talento de gerenciamento de capital humano seja excluída ou desinstalada.

### <a name="i-know-the-name-of-the-talent-environment-how-can-i-see-the-attract-and-onboard-data-in-dataverse"></a>Eu sei o nome do ambiente de talento. Como faço para ver os dados do Attract e do Onboard no Dataverse?

1.  Acessar Power Apps: https://make.powerapps.com
2.  Selecionar o ambiente no qual você deseja ver os dados do Attract e Onboard.
3.  Ir para **Dataverse > Tabelas**. 
4.  Digitar msdyn_ em **Pesquisar**. Se você vir a lista de tabelas começando por “msdyn_” + nomes de tabela (por exemplo, msdyn_candidate), então você descobriu o ambiente com dados do Attract e do Onboard.

[![Power Apps](./media/Powerapps.png)](./media/Powerapps.png)

### <a name="i-dont-know-the-name-of-the-talent-environment-how-can-i-find-the-environment-that-has-the-data-for-the-dynamics-365-talent-attract-and-dynamics-365-talent-onboard-applications"></a>Eu não sei o nome do ambiente de talento. Como encontrar o ambiente que contém os dados para os aplicativos Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard?

1)  Fazer logon no Power Platform admin center: https://admin.powerplatform.microsoft.com/
2)  Selecione **Ambientes**.
3)  Selecionar um ambiente particular para avaliar.
4)  Selecionar **Recursos > aplicativos Dynamics 365**.
5)  Se você encontrar a solução **Talento HCM** instalada, esse ambiente deverá ter dados armazenados do Attract e do Onboard nela. 

[![Power Platform](./media/HCMTalent.png)](./media/HCMTalent.png)

> [!NOTE] 
> A solução **Talento HCM** também é usada em Dynamics 365 Human Resources.
