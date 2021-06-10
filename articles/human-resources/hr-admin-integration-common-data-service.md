---
title: Configurar integração do Dataverse
description: Você pode ativar ou desativar a integração entre o Microsoft Dataverse e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de acompanhamento e ressincronizar uma tabela para ajudar na solução de problemas de dados entre os dois ambientes.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 721799c9a6fafe0a809f447189ce6814b30ca863
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052448"
---
# <a name="configure-dataverse-integration"></a>Configurar integração do Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode ativar ou desativar a integração entre o Microsoft Dataverse e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de acompanhamento e ressincronizar uma tabela para ajudar na solução de problemas de dados entre os dois ambientes.

> [!NOTE]
> Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Quando você desativa a integração, os usuários podem fazer alterações no Human Resources ou no Dataverse, mas essas alterações não são sincronizadas entre os dois ambientes.

Por padrão, a integração de dados entre o Human Resources e o Dataverse está desativada.

Talvez você queira desativar a integração nestas situações:

- Você está preenchendo dados por meio da Estrutura de Gerenciamento de Dados e deve importar os dados várias vezes para que fiquem no estado correto.

- Há problemas com dados no Human Resources ou no Dataverse. Se você desativar a integração, será possível excluir um registro em um ambiente sem excluí-lo de outro. Quando você reativar a integração, o registro no ambiente onde ele não foi excluído sincroniza com o ambiente de onde ele foi excluído. A sincronização começa na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Dataverse** for executado.

> [!WARNING]
> Ao desativar a integração de dados, certifique-se de não editar o mesmo registro em ambos os ambientes. Quando você reativar a integração, o registro que você editou pela última vez será sincronizado. Portanto, se você não fizer as mesmas alterações no registro em ambos os ambientes, poderá ocorrer perda de dados.

## <a name="access-the-dataverse-integration-page"></a>Acessar a página integração do Dataverse

1. Na instância do Human Resources onde você deseja ver ou configurar definições para a integração ao Dataverse, selecione o bloco **Administração do sistema**.

    [![Bloco Administração do sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Selecione a guia **Links**.

    [![Guia Links](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Em **Integrações**, selecione **Configuração do Dataverse**.

    [![Link de configuração do Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a>Ativar ou desativar a integração de dados entre o Human Resources e o Dataverse

- Para ativar a integração, defina a opção **Habilitar a integração ao Dataverse** como **Sim** na página **Integração ao Microsoft Dataverse**.

    > [!NOTE]
    > Quando você ativar a integração, os dados serão sincronizados na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Dataverse** for executado. Todos os dados deverão estar disponíveis depois que o trabalho em lotes for concluído.

- Para desativar a integração, defina a opção como **Não**.

[![Ativando ou desativando a integração do Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)

> [!WARNING]
> É altamente recomendável desativar a integração do Dataverse enquanto as tarefas de migração de dados são executadas. Grandes uploads de dados podem afetar significativamente o desempenho. Por exemplo, fazer upload de 2000 trabalhadores pode levar várias horas quando a integração estiver habilitada e menos de uma hora quando estiver desabilitada. Os números fornecidos neste exemplo são somente para fins de demonstração. A quantidade exata de tempo necessária para importar registros pode variar bastante com base em vários fatores.

## <a name="view-data-integration-details"></a>Exibir detalhes da integração de dados

Na FastTab **Administração** da página **Integração ao Microsoft Dataverse**, você pode ver como linhas são vinculadas juntas entre o Human Resources e o Dataverse.

- Para exibir as linhas de uma tabela, selecione a tabela no campo **Tabela do Dataverse**. A grade mostra todas as linhas vinculadas à tabela selecionada.

> [!NOTE]
> Nem todas as tabelas do Dataverse estão listadas atualmente. Somente as tabelas que aceitam o uso de campos personalizados aparecem na grade. Novas tabelas são disponibilizadas por meio de lançamentos contínuos do Human Resources.

A grade inclui os seguintes campos:

- **Tabela do Dataverse** – o nome da tabela no Dataverse.
- **Referência da tabela do Dataverse** – o identificador que o Dataverse usa para identificar um registro. Esse valor é equivalente a um valor **RecId** do Human Resources. Você pode encontrar o identificador ao abrir a tabela do Dataverse no Microsoft Excel.
- **Nome da entidade do Human Resources** – a entidade do Human Resources que sincronizou dados pela última vez para o Dataverse. A entidade pode ter o prefixo do Dataverse ou outro prefixo.
- **Referência do Human Resources** – o valor **RecId** que é associado ao registro no Human Resources.
- **Excluído do Dataverse** – um valor que indica se a linha foi excluída do Dataverse.

> [!NOTE]
> Os registros no Human Resources correspondem a linhas no Dataverse.

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a>Remover a associação de um registro do Human Resources de uma linha do Dataverse

Se você tiver problemas durante a sincronização de dados entre o Human Resources e o Dataverse, talvez seja possível resolvê-los limpando o rastreamento e permitindo que a tabela de rastreamento seja ressincronizada. Se você remover a associação e alterar ou excluir uma linha no Dataverse, as alterações não serão sincronizadas com o Human Resources. Se você fizer alterações no Human Resources, um novo registro de acompanhamento será criado e a linha será atualizada no Dataverse.

- Para remover a associação de um registro do Human Resources e uma linha do Dataverse, selecione a tabela no campo **Tabela do Dataverse** e selecione **Limpar informações de acompanhamento**.

[![Limpando informações de rastreamento](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)

Para executar uma sincronização completa na tabela após limpar o acompanhamento, consulte o próximo procedimento.

## <a name="sync-a-table-between-human-resources-and-dataverse"></a>Sincronizar uma tabela entre o Human Resources e o Dataverse

Use este procedimento quando:

- As alterações de Dataverse são exibidas de forma muito longa em Human Resources.

- Você deve atualizar a tabela de controle depois de limpar o rastreamento.

Para executar uma sincronização completa em uma tabela entre o Human Resources e o Dataverse:

1. Selecione a tabela no campo **Tabela do Dataverse**.

2. Selecione **Sincronizar agora**.

[![Executando uma sincronização completa](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)

## <a name="see-also"></a>Consulte também

[Tabelas do Dataverse](hr-developer-entities.md)<br>
[Configurar tabelas virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Perguntas frequentes de tabelas virtuais do Human Resources](hr-admin-virtual-entity-faq.md)<br>
[O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Atualizações de terminologia](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]