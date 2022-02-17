---
title: Chaves de configuração e entidades de dados
description: Este tópico descreve o relacionamento entre chaves de configuração e entidades de dados.
author: peakerbl
ms.date: 05/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: e9cc92563c426136b2543511ad943fd64b335b70
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065730"
---
# <a name="configuration-keys-and-data-entities"></a>Chaves de configuração e entidades de dados

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Antes de usar entidades de dados para importar ou exportar dados, recomendamos que primeiro determine o impacto de chaves de configuração nas entidades de dados que você pretende usar.

Para saber mais sobre chaves de configuração, consulte o [Relatório de códigos de licença e chaves de configuração](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Atribuições da chave de configuração
As chaves de configuração podem ser atribuídas a um ou a todos os seguintes artefatos.

- Entidades de dados
- Tabelas usadas como fontes de dados
- Campos de tabela
- Campos da entidade de dados

A tabela a seguir resume como valores de chave de configuração em diferentes artefatos que estão subjacentes em um objeto alteram o comportamento esperado do objeto.

| Configuração da chave de configuração na entidade de dados | Definição da chave de configuração na tabela | Definição da chave de configuração no campo da tabela | Chave de configuração no campo da entidade de dados | Comportamento esperado |
|-----------------------------------------|------------------------------------|------------------------------------------|----------------------------------------|------------------|
| Desabilitado                                | Não avaliado                      | Não avaliado                            | Não avaliado                          | Se a chave de configuração para a entidade de dados estiver desabilitada, a entidade de dados não será funcional. Não importa se as chaves de configuração nas tabelas e campos subjacentes estão habilitadas ou desabilitadas. |
| Habilitado                                 | Desabilitado                           | Não avaliado                            | Não avaliado                          | Se a chave de configuração para uma entidade de dados estiver habilitada, a estrutura de gerenciamento de dados verifica a chave de configuração em cada uma das tabelas subjacentes. Se a chave de configuração de uma tabela estiver desativada, essa tabela não ficará disponível na entidade de dados para uso funcional. Se a chave de configuração de uma tabela for desabilitada, as definições da chave de configuração da entidade de dados e da tabela não serão avaliadas. Se a tabela principal na entidade tiver sua chave de configuração desativada, então o sistema atuará como se a chave de configuração da entidade estivesse desativada. |
| Habilitado                                 | Habilitado                            | Desabilitado                                 | Não avaliado                          | Se a chave de configuração de uma entidade de dados estiver habilitada, as chaves de configuração das tabelas subjacentes serão habilitadas, a estrutura de gerenciamento de dados verificará a chave de configuração nos campos nas tabelas. Se a chave de configuração de um campo for desabilitada, esse campo não ficará disponível na entidade de dados para uso funcional, mesmo se o campo da entidade de dados correspondente tiver a chave de configuração habilitada. |
| Habilitado                                 | Habilitado                            | Habilitado                                  | Desabilitado                               | Se a chave de configuração estiver habilitada em todos os outros níveis, mas a chave de configuração do campo da entidade não estiver habilitada, então o campo não ficará disponível para uso na entidade de dados. |

> [!NOTE]
> Se uma entidade tiver outra entidade como uma fonte de dados, então as semânticas acima serão aplicadas de uma maneira recursiva.

### <a name="entity-list-refresh"></a>Atualização da lista de entidades
Quando a lista da entidades é atualizada, a estrutura de gerenciamento de dados cria os metadados da chave de configuração para uso no tempo de execução. Esses metadados são criados com a lógica descrita acima. É altamente recomendável que você aguarde a conclusão da atualização da lista de entidades antes de usar trabalhos e entidades na estrutura de gerenciamento de dados. Se você não aguardar, os metadados da chave de configuração talvez não sejam atualizados e poderão ter resultados inesperados. Quando a lista de entidades está sendo atualizada, a seguinte mensagem é exibida na página de listagem da entidade.

![Atualização da lista de entidades.](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Página de listagem de entidade de dados
A página de listagem de entidade de dados no espaço de trabalho Gerenciamento de dados mostra as definições da chave de configuração para as entidades. Comece nesta página para compreender o impacto das chaves de configuração na entidade de dados.

Essa informações são mostradas usando os metadados que são criados somente durante a atualização da entidade. A coluna da chave de configuração exibe o nome da chave de configuração associado à entidade de dados. Se essa coluna estiver em branco, isso significa que não há chave de configuração associada à entidade de dados. A coluna de status da chave de configuração mostra o estado da chave de configuração. Se tiver uma marca de seleção, isso significa que a chave está habilitada. Se estiver em branco, significa que a chave está desabilitada ou não há chave associada.

![Página de listagem da entidade.](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Campos de destino
A próxima etapa é analisar a entidade de dados para exibir o impacto das chaves de configuração em tabelas e campos. O formulário de campos de destino de uma entidade de dados mostra a chave de configuração e as informações de status da chave para as tabelas e campos relacionados na entidade de dados. Se a própria entidade de dados tiver sua chave de configuração desabilitada, uma mensagem de aviso será exibida informando que as tabelas e os campos nos campos de destino dessa entidade não estarão disponíveis, independentemente do status da chave de configuração.

![Campos de destino.](./media/Target_fields_1.png)

### <a name="child-entities"></a>Entidades filhas 
Determinadas entidades têm outras entidades como fontes de dados, ou são entidades de dados compostas: as informações da chave de configuração destas entidades são exibidas no formulário de entidades filha. Use este formulário de forma semelhante para a página de listagem das entidades descrita acima. O formulário de campos de destino da entidade filha também comporta-se conforme descrito acima.

![Campos de destino.](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Usando entidades de dados
Após entender o impacto total, se houver, das chaves de configuração nas entidades de dados que você deseja usar, você agora pode continuar usando as entidades de dados adicionando-as aos projetos de dados. 

### <a name="run-time-validations-for-configuration-keys"></a>Validação de tempo de execução das chaves de configuração
Usando os metadados da chave de configuração criados durante a lista de atualizações da entidade, as validações do tempo de execução são executadas nos seguintes casos de uso.

- Quando uma entidade de dados for adicionada a um trabalho
- Quando os cliques de usuário são "validados" na lista de entidades
- Quando o usuário carrega um pacote de dados em um projeto de dados
- Quando o usuário carregar um modelo para um projeto de dados
- Quando um projeto de dados existente for carregado
- Quando um modelo é carregado para um projeto de dados
- Antes que o trabalho de exportação/importação seja executado, (lote, não lote, recorrente, OData)
- Quando o usuário gera o mapeamento
- Quando o usuário mapeia os campos na interface do mapeamento
- Quando o usuário adiciona somente 'campos importáveis'

### <a name="managing-configuration-key-changes"></a>Gerenciando alterações da chave de configuração
A qualquer momento que você atualizar as chaves de configuração na entidade, tabela ou nível de campo, a lista de entidades na estrutura de gerenciamento de dados deve ser atualizada. Este procedimento garante que a estrutura selecionará as definições de chave de configuração mais recentes. Até a lista de entidades ser atualizada, a seguinte advertência será mostrada na página de listagem da entidade. As alterações da chave de configuração atualizadas terão efeito imediatamente após a lista de entidades ser atualizada. Recomendamos que você valide os projetos e trabalhos de dados existentes para certificar-se de que eles funcionam como esperado, depois que as alterações das chaves de configuração entrarem em vigor.

![Campos de destino.](./media/Target_fields_3.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
