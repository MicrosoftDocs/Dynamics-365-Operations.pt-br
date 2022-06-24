---
title: Criar um calendário de equipe
description: Exibir e criar calendários de equipe no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6dffcb265030922e5134cfab1310027be43d87ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904149"
---
# <a name="view-team-and-company-calendars"></a>Exibir calendários da equipe e da empresa

>[!Important]
>A funcionalidade mencionada neste artigo está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode exibir calendários da equipe e da empresa no Dynamics 365 Human Resources. Os calendários de equipe só exibem os relatórios diretos, conforme definido na hierarquia de linhas.

## <a name="view-your-team-calendar-as-an-employee"></a>Exibir o calendário da equipe como um funcionário

- No espaço de trabalho **Autoatendimento para funcionários**, selecione **Calendário de ausências da equipe** em **Resumo**.

## <a name="view-your-team-calendar-as-a-manager"></a>Exibir o calendário da equipe como um gerente

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Minha equipe**.

2. Selecione **Licença e ausência** e depois **Exibir calendário de ausências do gerente**.

Os gerentes também podem acessar o calendário da equipe de **Solicitações de licença pendentes de minha equipe**, **Licença aprovada** e **Solicitações de licença**. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Exibir o calendário do gerente de ausências como gerente de ausências

> [!NOTE]
> Para exibir o calendário do gerente de ausências, é necessário primeiro ativar o recurso **(Versão preliminar) Gerente de ausências para gerenciar a licença** no Gerenciamento de recursos. Para obter mais informações sobre como ativar a versão prévia dos recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

Os usuários na função Gerente de ausências podem exibir solicitações de folga no calendário. Siga estas etapas para acessar o calendário de licenças.

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Gerenciamento de licenças** e **Calendário do gerente de ausências**.

2. No campo **Data**, insira as datas desejadas.

3. Atualize as opções de exibição, conforme necessário.

O calendário do gerente de ausências mostra todos os registros dos funcionários subordinados ao gerente de ausências na hierarquia de licenças.

## <a name="view-a-company-calendar"></a>Exibir um calendário da empresa

As pessoas que estão nas funções de recursos humanos podem exibir calendários da empresa. Os calendários da empresa exibem todos os funcionários. Por padrão, o calendário exibe a data de hoje mais 28 dias, mas você pode alterar o intervalo de datas. Você também pode filtrar o calendário por **Nome**, **Número de pessoal** e **Tipo de licença**.

1. No espaço de trabalho **Licença e ausência**, selecione **Links**.

2. Selecione **Calendário de licenças e ausências**.

As funções de recursos humanos também podem acessar o calendário da empresa em **Solicitações de licença e ausência**, **Licença aprovada** e **Solicitações de licença**. 

Os calendários agora contêm filtros e opções adicionais. Todos os calendários incluem opções de exibição para:

- Solicitações aprovadas
- Solicitações pendentes
- Funcionários com solicitações de licença
- Funcionários sem solicitações de licença
- Aniversários de funcionários
- Solicitações de folga 
- Solicitações de licença

A configuração de calendário na página **Parâmetros de licença e ausência** determina as opções de exibição disponíveis.

Também é possível filtrar calendários por gerente ou departamento. A atribuição de posição principal determina os funcionários exibidos quando esses filtros são definidos. 

> [!IMPORTANT]
> Você pode ativar o recurso **Exibição de licença entre empresas** no Gerenciamento de recursos. Em seguida, é necessário habilitar o recurso na página **Parâmetros compartilhados de recursos humanos** para mostrar o filtro da entidade legal em calendários. Para obter mais informações, consulte [Configurar parâmetros de licença e ausência](hr-leave-and-absence-parameters.md).
> 
> Você pode filtrar o calendário por entidade legal. Para exibir todos os funcionários, independentemente da entidade legal, limpe o campo de filtro e selecione **Inserir**. 

Para obter informações sobre configurações de calendário, consulte [Configurar parâmetros de calendário](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
