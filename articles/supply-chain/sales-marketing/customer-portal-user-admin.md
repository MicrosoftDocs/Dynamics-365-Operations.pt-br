---
title: Criar e gerenciar usuários do portal do cliente
description: Este tópico explica como criar contas de usuário do portal do cliente e definir permissões para elas.
author: dasani-madipalli
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a751cbffd98b8d47ca7dad222f0ce374381a393d
ms.sourcegitcommit: 074fe7e77feb795148c3daf2e6ccbb8a88679343
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "3645304"
---
# <a name="create-and-manage-customer-portal-users"></a>Criar e gerenciar usuários do portal do cliente

Na implementação pronta para uso, não é possível o autorregistro de usuários para sites criados usando o portal do cliente. Para entrar e usar um site, os usuários devem ser convidados pelo administrador. A Microsoft bloqueou intencionalmente a capacidade de os usuários fazerem autorregistro.

Para que um usuário possa usar um site, um registro de contato deve ser criado para esse usuário. Esse registro indica a conta do cliente e a entidade legal à qual o usuário pertence. Essas informações são essenciais para garantir que o usuário possa criar e exibir ordens de venda.

Quando os usuários fazem autorregistro, os registros de contatos são criados automaticamente para eles. Portanto, não é possível garantir que um usuário selecione a conta do cliente e a entidade legal corretas. Por outro lado, o processo de convite permite que um administrador atribua a conta do cliente e a entidade legal corretas ao registro de contato antes do envio de um convite. Se você está pensando em personalizar a solução para que os usuários possam fazer um autorregistro, considere as possíveis consequências.

## <a name="video"></a>Vídeo
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

O vídeo [Convidar clientes para se registrar e usar o portal de cliente](https://youtu.be/drGUYHX9QIQ) (mostrado acima) é incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="prerequisite-setup"></a>Configuração de pré-requisitos

Os contatos em portais do Power Apps são armazenados como registros na entidade **Contatos** no Common Data Service. A gravação dupla sincroniza esses registros para o Microsoft Dynamics 365 Supply Chain Management, conforme necessário.

![Diagrama de sistema para contatos do portal do cliente](media/customer-portal-contacts.png "Diagrama de sistema para contatos do portal do cliente")

Antes de começar a convidar novos clientes, verifique se você habilitou o mapeamento da entidade **Contato** em gravação dupla.

## <a name="the-invitation-process"></a>O processo de convite

Para convidar um contato existente para o Portal do cliente, siga as etapas em [Convidar contatos para seus portais](https://docs.microsoft.com/powerapps/maker/portals/configure/invite-contacts)na documentação de portais do Power Apps.

Antes de convidar um cliente para ingressar no portal do cliente, verifique se o [registro de contato](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-contacts) do cliente está disponível e configurado da seguinte maneira:

1. Defina o campo **Empresa** como a entidade legal à qual você deseja que o cliente pertença no Supply Chain Management.
2. Defina o campo **Número da Conta** como o número da conta do cliente que você deseja que o usuário tenha no Supply Chain Management.

Depois que um contato for criado, você poderá vê-lo no Supply Chain Management.

Para obter mais informações, consulte [Configurar um contato para uso em um portal](https://docs.microsoft.com/powerapps/maker/portals/configure/configure-contacts) na documentação de portais do Power Apps.

## <a name="out-of-box-web-roles-and-entity-permissions"></a>Funções da Web e permissões de entidade prontas para uso

As funções de usuário em portais do Power Apps são definidas por [funções da Web](https://docs.microsoft.com/powerapps/maker/portals/configure/create-web-roles) e [permissões de entidade](https://docs.microsoft.com/powerapps/maker/portals/configure/assign-entity-permissions). Algumas funções são definidas para o portal do cliente prontas para uso. Você pode criar novas funções e pode modificar ou remover funções existentes.

### <a name="out-of-box-web-roles"></a>Funções da Web prontas para uso

Esta seção descreve as funções da Web fornecidas com o portal do cliente.

Para obter mais informações sobre como modificar as funções de usuário prontas para uso, consulte [Criar funções da Web para portais](https://docs.microsoft.com/powerapps/maker/portals/configure/create-web-roles)e [Adicionar segurança baseada em registro usando permissões de entidade para portais](https://docs.microsoft.com/powerapps/maker/portals/configure/assign-entity-permissions) na documentação de portais do Power Apps.

#### <a name="administrator"></a>Administrador

O administrador supervisiona e mantém o site. Esta pessoa provisiona e configure o portal do cliente. O administrador mantém os aspectos de TI e de segurança do portal e verifica se tudo está funcionando bem. O administrador também pode personalizar e/ou alterar o portal adicionando novas funcionalidades, criando novas funções e muito mais.

#### <a name="customer-representative"></a>Representante do cliente

Um representante do cliente trabalha para uma empresa do cliente e é responsável por gerenciar os pedidos da empresa. O representante do cliente pode ver todas os pedidos feitos para a empresa e os usuários fizeram os pedidos. Além disso, o representante do cliente pode ver informações sobre a conta geral e quais contatos podem fazer pedidos em nome dessa conta.

#### <a name="authorized-users"></a>Usuários autorizados

Os usuários autorizados podem fazer pedidos e exibir o status dos pedidos feitos. No entanto, não é possível exibir o status dos pedidos feitos por outros usuários da empresa.

#### <a name="unauthorized-users"></a>Usuários não autorizados

Os usuários não autorizados não podem exibir dados. Eles podem ver somente informações públicas, como termos e condições, além de detalhes sobre a empresa que está executando o portal do cliente.

#### <a name="example"></a>Exemplo

A tabela a seguir mostra quais ordens de venda os usuários em cada função da Web podem ver no sistema.

| Ordem de Venda | Administrador | Representante do cliente para o cliente&nbsp;X | Usuário autorizado: Jane | Usuário autorizado: Sam | Usuário autorizado: May |
|---|---|---|---|---|---|
| Cliente&nbsp;X Autor da ordem:&nbsp;Jane | Sim | Sim | Sim | Não | Não |
| Cliente&nbsp;X Autor da ordem:&nbsp;Sam | Sim | Sim | Não | Sim | Não |
| Cliente&nbsp;Autor da ordem Y:&nbsp;May | Sim | Não | Não | Não | Não |

> [!NOTE]
> Embora os Sam e Jane sejam contatos que trabalham para o cliente X, eles podem ver somente os pedidos feitos por eles mesmos e nada mais. Embora May possa ter uma ordem no sistema, ela não pode ver essa ordem no portal do cliente, pois ela é um usuário não autorizado. (Além disso, ela deve ter feito o pedido por um canal diferente do portal do cliente.)
