---
title: Novidades ou alterações no Dynamics 365 Talent (27 de fevereiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
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
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f175c6e60cf87c7dcbde0eaf35357130fa035712
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023990"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-27-2019"></a>Novidades ou alterações no Dynamics 365 Talent (27 de fevereiro de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

Alterações descritas nesta seção aplicam-se à versão número 8.1.2163

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Adiciona um Item de menu de campos personalizados à Administração do sistema

Navegação ao menu **Campos personalizados** foi adicionada ao espaço de trabalho **Administração do sistema**.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Oculta a importação e cria opções para novos aplicativos móveis

Atualmente, novos aplicativos móveis não podem ser criados no Talent. A opção de criar novas experiências móveis foi removida do menu **Aplicativo móvel**.

### <a name="variable-compensation-award-dmf-entity"></a>Prêmio de remuneração variável (entidade DMF)

Nessa versão, uma entidade do Data Management Framework (DMF) de **Prêmio de remuneração variável** agora está disponível para exportação.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Os endereços do Reino Unido aparecem na página de análise de gerenciamento de equipe como endereços suíços

Nessa versão, endereços são mostrados por cidade. Esta versão corrige problemas onde as visualizações deturparam a localização de um funcionário.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>O relatório de força de trabalho do Power BI mostra um erro quando uma data de aniversário de tempo de serviço do trabalhador é dia 29 de fevereiro

Uma correção foi efetuada no Microsoft Power BI para explicar as datas de tempo de serviço que caiam em 29 de fevereiro.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>Remuneração fixa do funcionário, prêmios variáveis do funcionário, planos variáveis do funcionário (cadastros) permitem campos personalizados

Campos personalizados agora podem ser adicionados para remuneração fixa de funcionário, prêmios variáveis de funcionário, e planos variáveis de funcionário (cadastros). Agora você pode rastrear mais informações sobre os planos de funcionário fixo e remuneração variável, além de informações disponíveis por padrão. Os campos personalizados podem ser inseridos e atualizados por meio da interface do usuário ou por meio de entidades que são fornecidas.

### <a name="other-miscellaneous-bug-fixes"></a>Outras correções de bugs diversos

Esta versão inclui outras correções de bug menores.

## <a name="coming-soon"></a>Em breve

### <a name="advanced-compensation-security-fixed-and-variable"></a>Segurança de compensação avançada (fixa e variável)

Em muitas organizações, gerentes de compensação e benefícios podem ter acesso apenas a registros de compensação específica. Esses registros podem ser para funcionários executivos ou regionais. Essa alteração permitirá que os Recursos Humanos (RH) gerenciem e mantenham os planos de compensação para populações de funcionário diferentes na organização. Funções de segurança que podem ser atribuídas a planos fixos e variáveis determinam o acesso a esses planos e os dados de funcionário relacionado a eles (por exemplo, informações de salário e registros de bônus). Apenas as funções com acesso especificado poderão processar compensação para esses funcionários.

### <a name="platform-update-24-for-finance-and-operations"></a>Atualização de plataforma 24 do Finance and Operations

Para obter mais informações sobre atualização de plataforma 24 do Microsoft Dynamics 365 Finance and Operations (março de 2019), consulte [Visualização de recursos na Atualização de plataforma 24 do Finance and Operations (março de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Tornar remuneração fixa de funcionário disponível para atribuições de cargo futuras

É normal que funcionários que entrem em uma organização tenham uma data de início futura. Esta alteração permitirá que a remuneração fixa seja definida para funcionários que possuem atribuições de cargo futuras.

## <a name="known-issues"></a>​Problemas conhecidos​

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance"></a>Alterações no modelo de integração do Core HR (Talent Common Data Service para Finance)
O modelo para Core HR foi atualizado em um "modelo de consulta avançado". Portanto, por padrão, a consulta avançada estará disponível para projetos criados usando esse modelo. Além disso, todas as funções de mapeamentos padrão estarão visíveis apenas no editor de consulta anterior. (As funções de mapeamento padrão aparecem como "FN" nos mapeamentos.)

Para obter mais informações sobre os erros de mapeamento, consulte [Novidades ou alterações no Dynamics 365 Talent: Core HR (14 de dezembro de 2018)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Para usar o novo modelo, crie um novo projeto e selecione o novo método de integração do Talent.

Para atualizar o seu modelo existente, rastreie essas etapas.

1. Atualize os mapeamentos a seguir:

    - **Cargos a cargos de trabalho:** Remova esse mapeamento.
    - **Atribuição de trabalho pai dos cargos a cargos de trabalho:** Remova esse mapeamento.
    - **Cargos de Trabalho a Posição Base:** Adicione um novo mapeamento da entidade **Cargos de Trabalho** do Common Data Service à entidade **Posição Base** do Finance and Operations. Mova-o para a posição 7 na sequência.

        [![Cargos de trabalho a mapeamento de cargo base](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Cargos de Trabalho a Detalhes da Posição:** Adicione um novo mapeamento da entidade **Cargos de Trabalho** do Common Data Service para a entidade **Detalhes da Posição** do Finance and Operations. Mova-o para a posição 8 na sequência.

        [![Detalhes de cargos de trabalho a mapeamento de cargo](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Cargos de Trabalho a Durações da Posição:** Adicione um novo mapeamento da entidade **Cargos de Trabalho** do Common Data Service para a entidade **Durações da Posição** do Finance and Operations.

        [![Duração de cargos de trabalho a mapeamento de cargo](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Cargos de Trabalho a Hierarquias do Cargo:** Adicione um novo mapeamento da entidade **Cargos de Trabalho** do Common Data Service para a entidade **Hierarquias do Cargo** do Finance and Operations. Selecione **Consulta avançada** para deixar sua consulta avançada disponível para seu projeto.

       [![Botão de consulta avançada](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Adicione os mapeamentos a seguir.
    
    [![Mapeamento](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Selecione o link **Filtragem e consulta avançada** próximo ao campo **Pesquisar**.  

    3. Localize a coluna **cdm_parentjobpositionid.cdm_jobpositionnumber**, e selecione o botão de seta para baixo à direita da tela.

    4. Na caixa de diálogo exibida, selecione **Remover vazio**.

    5. Selecione **Adicionar coluna \> Adicionar coluna condicional** para adicionar uma transformação de valor padrão para HIERARCHYTYPENAME.

        [![Adicionar comando de coluna condicional](./media/Add-column.png)](./media/Add-column.png)

    6. Na caixa de diálogo **Adicionar coluna condicional**, insira **HIERARCHYTYPENAME** como o nome da nova coluna.
    7. Na parte **Se** da condição, selecione qualquer campo, use **igual a** como o relacionamento e insira qualquer valor. Nas partes ***Então** e **Caso contrário** da condição, especifique qual deve ser o valor padrão. Nesse caso, insira **Linha** em ambas as partes.

        [![Adicionar caixa de diálogo da coluna condicional](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Selecione **OK** para fechar a caixa de diálogo **Consulta e filtragem avançadas**.
    9. Na página **Tarefa de mapeamento**, selecione a nova coluna como a fonte para criar outro mapeamento para HIERARCHYTYPENAME.

        [![Mapeamento](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)
