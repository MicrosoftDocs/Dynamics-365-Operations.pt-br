---
title: Configurar integração do Common Data Service
description: Você pode ativar ou desativar a integração entre o Common Data Service e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d9ee4715526e18b33ae4b7e90b081ed5868bb19c
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527906"
---
# <a name="configure-common-data-service-integration"></a>Configurar integração do Common Data Service

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Você pode ativar ou desativar a integração entre o Common Data Service e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.

Quando você desativa a integração, os usuários podem fazer alterações no Human Resources ou no Common Data Service, mas essas alterações não são sincronizadas entre os dois ambientes.

Por padrão, a integração de dados entre o Human Resources e o Common Data Service está desativada.

Talvez você queira desativar a integração nestas situações:

- Você está preenchendo dados por meio da Estrutura de Gerenciamento de Dados e deve importar os dados várias vezes para que fiquem no estado correto.

- Há problemas com dados no Human Resources ou no Common Data Service. Se você desativar a integração, será possível excluir um registro em um ambiente sem excluí-lo de outro. Quando você reativar a integração, o registro no ambiente onde ele não foi excluído sincroniza com o ambiente de onde ele foi excluído. A sincronização começa na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.

> [!WARNING]
> Ao desativar a integração de dados, certifique-se de não editar o mesmo registro em ambos os ambientes. Quando você reativar a integração, o registro que você editou pela última vez será sincronizado. Portanto, se você não fizer as mesmas alterações no registro em ambos os ambientes, poderá ocorrer perda de dados.

## <a name="access-the-common-data-service-integration-page"></a>Acessar a página integração do Common Data Service

1. Na instância do Human Resources onde você deseja ver ou configurar definições para a integração ao Common Data Service, selecione o bloco **Administração do sistema**.

    [![Bloco Administração do sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)

2. Selecione a guia **Links**.

    [![Guia Links](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)

3. Em **Integrações**, selecione **Configuração do Common Data Service**.

    [![Link de configuração do Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a>Ativar ou desativar a integração de dados entre o Human Resources e o Common Data Service

- Para ativar a integração, defina a opção **Ativar a integração ao Common Data Service** como **Sim**.

    > [!NOTE]
    > Quando você ativar a integração, os dados serão sincronizados na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado. Todos os dados deverão estar disponíveis depois que o trabalho em lotes for concluído.

- Para desativar a integração, defina a opção como **Não**.

[![Ativando ou desativando a integração do Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)

> [!WARNING]
> É altamente recomendável desativar a integração do Common Data Service enquanto as tarefas de migração de dados são executadas. Grandes uploads de dados podem afetar significativamente o desempenho. Por exemplo, fazer upload de 2000 trabalhadores pode levar várias horas quando a integração estiver habilitada e menos de uma hora quando estiver desabilitada. Os números fornecidos neste exemplo são somente para fins de demonstração. A quantidade exata de tempo necessária para importar registros pode variar bastante com base em vários fatores.

## <a name="view-data-integration-details"></a>Exibir detalhes da integração de dados

Na FastTab **Administração** da página **Integração do Common Data Service**, você pode ver como os registros são vinculados juntos entre o Human Resources e o Common Data Service.

- Para exibir os registros de uma entidade, selecione a entidade no campo **Nome da entidade CDS**. A grade mostra todos os registros vinculados à entidade selecionada.

[![Exibindo os registros de uma entidade](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)

> [!NOTE]
> Nem todas as entidades do Common Data Service estão listadas atualmente. Somente as entidades que aceitam o uso de campos personalizados aparecem na grade. Novas entidades são disponibilizadas por meio de lançamentos contínuos do Human Resources.

A grade inclui os seguintes campos:

- **Nome da entidade CDS** – o nome da entidade no Common Data Service.
- **Referência da entidade CDS** – o identificador que o Common Data Service usa para identificar um registro. Esse valor é equivalente a um valor **RecId** do Human Resources. Você pode encontrar o identificador ao abrir a entidade do Common Data Service no Microsoft Excel.
- **Nome da entidade do Human Resources** – a entidade que sincronizou os dados pela última vez com o Common Data Service. A entidade pode ter o prefixo do Common Data Service ou outro prefixo.
- **Referência do Human Resources** – o valor **RecId** que é associado ao registro no Human Resources.
- **Foi excluído do CDS** – um valor que indica se o registro foi excluído do Common Data Service.

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a>Remover do Common Data Service a associação de um registro no Human Resources

Se você tiver problemas durante a sincronização de dados entre o Human Resources e o Common Data Service, talvez seja possível resolvê-los limpando o rastreamento e permitindo que a tabela de rastreamento seja ressincronizada. Se você remover a associação e alterar ou excluir um registro no Common Data Service, as alterações não serão sincronizadas com o Human Resources. Se você fizer alterações no Human Resources, um novo registro de rastreamento será criado e o registro será atualizado no Common Data Service.

- Para remover a associação de um registro entre o Human Resources e o Common Data Service, selecione a entidade no campo **Nome da entidade CDS** e selecione **Limpar informações de rastreamento**.

[![Limpando informações de rastreamento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)

Para executar uma sincronização completa na entidade depois de desmarcar o rastreamento, consulte o procedimento a seguir.

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a>Sincronizar uma entidade entre o Human Resources e o Common Data Service

Use este procedimento quando:

- As alterações de Common Data Service são exibidas de forma muito longa em Human Resources.

- Você deve atualizar a tabela de controle depois de limpar o rastreamento.

Para executar uma sincronização completa em uma entidade entre Human Resources e Common Data Service:

1. Selecione a entidade no campo **Nome da entidade CDS**.

2. Selecione **Sincronizar agora**.

[![Executando uma sincronização completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)


