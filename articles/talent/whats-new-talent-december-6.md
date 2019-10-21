---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (6 de dezembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
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
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 73e0875c3e072bc29050a096888459c6e4bb1b7b
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025947"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-december-6-2018"></a>Novidades ou alterações no Dynamics 365 Talent: Core HR (6 de dezembro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.2071**

Este tópico descreve os recursos novos ou alterados no Core HR.


## <a name="platform-update-22-for-finance-and-operations"></a>Atualização de plataforma 22 do Finance and Operations

### <a name="export-up-to-1-million-rows-to-excel"></a>Exportar até 1 milhão de linhas para o Excel

O recurso Exportar para o Excel agora pode ser configurado para permitir que os usuários exportem até 1 milhão de linhas de uma grade no Talent, um aumento substancial do limite anterior de 10.000 linhas. 

### <a name="restyled-personalization-toolbar"></a>Barra de ferramentas de personalização reformulada

A barra de ferramentas de personalização foi reformulada na atualização de plataforma 22 do Finance and Operations para ajudar os usuários a personalizar mais facilmente suas próprias experiências no Talent. Foram feitas as seguintes alterações: 

-  O nome de cada ferramenta de personalização agora é exibido juntamente com um ícone, o que ajuda os usuários a reconhecer com rapidez a ferramenta que desejam usar.
-  A descrição de como usar a ferramenta atual agora também é exibida, o que ajuda os usuários a entender como fazer as personalizações necessárias.  
-  A barra de ferramentas de personalização inteira pode ser movida pela tela arrastando-a e soltando-a em uma região específica na extremidade esquerda da barra de ferramentas. Isso permite que os usuários personalizem elementos que estavam anteriormente encobertos pela barra de ferramentas.   

### <a name="optimized-is-one-of-filtering-experience"></a>Experiência de filtragem "é um de" otimizada

O operador de filtragem "é um de" está disponível para a maioria dos campos ao usar o Painel de Filtragem e as listas suspensas do cabeçalho da grade. Esse operador permite que o usuário filtre um campo com base em diversos valores. Uma experiência nova e aprimorada do operador "é um de" está disponível na atualização de plataforma 22 do Finance and Operations. Para saber mais, consulte [Experiência de filtragem "é um de" otimizada](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Colar listas do Excel em campos de filtragem com o operador "é um de"

Para algumas tarefas, os usuários podem ter uma lista de valores no Excel que gostariam de usar para filtrar dados no Talent. Por exemplo, um usuário de Recursos Humanos pode ter identificado um conjunto de funcionários em um relatório que necessita de pesquisa adicional no sistema e seria ideal para ele poder copiar diretamente do Excel em um campo de filtro no Talent.

A partir da atualização de plataforma 22 do Finance and Operations, o operador "é um de" no Painel de filtragem e a filtragem de colunas da grade agora reconhece listas copiadas do Excel de modo que elas possam ser coladas diretamente em um campo de filtro. Isso inclui um conjunto de valores copiados das diferentes linhas e colunas no Excel. Para saber mais sobre este recurso, consulte [Colar listas do Excel em campos de filtragem com o operador "é um de"](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>Em visualização

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Configurar a integração da folha de pagamento do Reino Unido entre o Talent e o Dayforce

A integração entre o Talent e o Ceridian Dayforce está disponível em visualização para o Reino Unido. Consulte o seguinte tópico para obter mais informações [Configurar a integração da folha de pagamento entre o Talent e o Dayforce](https://docs.microsoft.com/dynamics365/unified-operations/talent/configure-payroll-integration).

## <a name="coming-soon"></a>Em breve

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Licença e ausência: saldos futuros de licença e de previsão de licença

Com as alterações que estão sendo feitas para permitir que funcionários prevejam folgas e solicitem futuras folgas sem afetar seus saldos atuais de folga, a forma como os saldos de folga são exibidos também está sendo alterada. 

O saldo disponível atualmente exibido é a quantidade de folgas disponíveis para solicitações, incluindo os acúmulos até hoje e todas as solicitações de licença aprovadas. 

Quando a possibilidade de previsão for liberada, o saldo exibido será alterado para ser o saldo atual de folga, incluindo os acúmulos até hoje e as solicitações até hoje. Os funcionários e gerentes verão esses saldos atualizados no autoatendimento para funcionários e gerentes no cartão **Folga** e na janela **Saldos de folga** . Os gerentes de RH verão esses saldos atualizados no espaço de trabalho **Pessoas** e na janela **Planos de licença atribuídos** do funcionário.

## <a name="other-changes"></a>Outras alterações 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>O código de demissão não é preenchido no registro de atribuição de posição do trabalhador

Uma alteração foi implementada que preenche o código de motivo no registro de atribuição de posição durante o processo de demissão.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>A validação do número de pessoal que está em uso necessita de detalhes adicionais

São exibidas informações adicionais quando as sequências numéricas estão em uso, para compreender melhor problemas quando não é possível gerar um novo número.
 
### <a name="attachments-buttons-not-available-for-workers"></a>Os botões de anexos não estão disponíveis para os trabalhadores

Alterações foram feitas para corrigir os anexos. Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** agora ficarão disponíveis quando os Quadros de Fatos forem abertos na janela do trabalhador. 

## <a name="known-issues"></a>​Problemas conhecidos​

### <a name="mapping-errors-in-the-integration-with-finance"></a>Erros de mapeamento na integração com o Finance

Os problemas a seguir foram identificados no modelo atual de integração do Talent com o Finance. Um novo modelo será publicado em breve e aplicado a todos os novos projetos de integração que forem criados. Para projetos de integração existentes, os mapeamentos de tarefas podem ser atualizados. Consulte a tabela a seguir para os mapeamentos atualizados. 

>[!NOTE]
> A tarefa Posições de trabalho para Atribuição de Trabalho Pai às Posições não integra dados. Este é um problema que está sendo investigado no momento. Não há uma solução alternativa no mapeamento atual. 

A tarefa Departamentos para a Unidade operacional necessita dos seguintes mapeamentos atualizados.

| Campo de origem existente          | Novo campo de origem |
| -------------------------------|------------------|
| cdm_description (Descrição)  | cdm_name (Nome)  |

Também é necessário acrescentar um mapeamento adicional Selecione o último campo **Nenhum** para adicionar o mapeamento a seguir.

| Campo de origem                   | Campo de destino    |
| -------------------------------|----------------------|
| cdm_description (Descrição)  | NAMEALIAS (NAMEALIAS)|

Os mapeamentos atualizados devem ter a seguinte aparência:

![Tarefa Departamentos para a Unidade operacional](./media/DepartmentMapping.png)


A tarefa Trabalhos para Detalhes do Trabalho necessita dos seguintes mapeamentos atualizados.

| Campo de origem existente          | Novo campo de origem                   |
| -------------------------------|------------------------------------|
| cdm_name (Nome)                | cdm_description (Descrição)      |
| cdm_name (Descrição)         | cdm_jobdescription(Descrição do trabalho)|


Os mapeamentos atualizados devem ter a seguinte aparência:

![Trabalhos para Detalhes do Trabalho](./media/JobMapping.png)

A tarefa Trabalhadores para o Trabalho necessita dos seguintes mapeamentos atualizados.

| Campo de origem existente                 | Novo campo de origem                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (Endereço de email 1)   | cdm_primaryemailaddress (Endereço de email principal) |
| cdm_telephone1 (Telefone 1)          | cdm_primarytelephone (Telefone principal)       |

A transformação do campo Sexo também deve ser atualizada. Selecione o tipo de mapa **fn** (função) para o Sexo e atualize os seguintes mapeamentos de valor.

| Valor do Common Data Service   | Valor do Finance and Operations | | ------------|------------------ -----------| | 75440000    | Masculino                         | | 75440001    | Feminino                       | | 75440002    | Nenhum                         | | 75440003    | Não especificado                  |

Os mapeamentos atualizados devem ter a seguinte aparência:

![Tarefa Trabalhadores para o Trabalho](./media/WorkerMapping.png)

![Transformação do campo Sexo](./media/WorkerTransform.png)

