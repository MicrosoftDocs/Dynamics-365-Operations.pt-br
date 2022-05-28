---
title: Modo de criação de cliente assíncrono
description: Este tópico descreve o modo de criação de cliente assíncrono no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: ca7cceb066d30b7bba82265a3654f3bfb26f57f6
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689093"
---
# <a name="asynchronous-customer-creation-mode"></a>Modo de criação de cliente assíncrono

[!include [banner](includes/banner.md)]

Este tópico descreve o modo de criação de cliente assíncrono no Microsoft Dynamics 365 Commerce.

No Commerce, há dois modos de criação de clientes: síncrono e assíncrono. Por padrão, os clientes são criados de forma síncrona. Em outras palavras, eles são criados no Commerce Headquarters em tempo real. O modo síncrono de criação de clientes é vantajoso porque novos clientes são pesquisados imediatamente nos canais. No entanto, ele também tem uma desvantagem. Como ele gera chamadas do [Commerce Data Exchange: Serviço em tempo real](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) para o Commerce Headquarters, o desempenho poderá ser afetado se várias chamadas simultâneas de criação de clientes forem feitas.

Se a opção **Criar cliente no modo assíncrono** estiver definida como **Sim** no perfil de funcionalidade da loja (**Varejo e Comércio \> Configuração do canal \> Configuração da loja online \> Perfis de funcionalidade**), as chamadas do Serviço em Tempo Real não são usadas para criar registros de cliente no banco de dados do canal. O modo assíncrono de criação de clientes não afeta o desempenho da matriz do Commerce. Um GUID (identificador global exclusivo) temporário é atribuído a cada novo registro de cliente assíncrono e usado como a ID da conta do cliente. Esse GUID não é exibido aos usuários do ponto de venda (PDV). Em vez disso, esses usuários verão **Sincronização pendente** como a ID da conta do cliente.

> [!IMPORTANT]
> Sempre que o PDV ficar offline, o sistema criará automaticamente os clientes de forma assíncrona, mesmo se o modo de criação de cliente assíncrono estiver desabilitado. Portanto, independentemente da seleção entre criação de clientes síncrono e assíncrono, os administradores da matriz do Commerce precisam criar e programar um trabalho em lotes recorrente para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** (anteriormente denominado trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono**) e o trabalho **1010**, para que todos os clientes assíncronos sejam convertidos para clientes síncronos na matriz do Commerce.

## <a name="async-customer-limitations"></a>Limitações do cliente Assíncrono

No momento, a funcionalidade de cliente assíncrono tem as seguintes limitações:

- Os registros de clientes Assíncronos não podem ser editados a menos que o cliente tenha sido criado no Commerce Headquarters e a nova ID da conta do cliente tenha sido sincronizada novamente com o canal.
- Os cartões-fidelidade não podem ser emitidos para clientes assíncronos a menos que a nova ID da conta do cliente tenha sido sincronizada novamente para o canal.

## <a name="async-customer-enhancements"></a>Aprimoramentos do cliente assíncrono

A partir da versão 10.0.24 do Commerce, você pode habilitar o recurso **Habilitar a criação avançada de clientes assíncronos** no workspace **Gerenciamento de recursos**. Esse recurso preenche a lacuna entre os modos de criação de clientes assíncronos e síncronos no PDV e no comércio eletrônico das seguintes maneiras:

- As afiliações não podem ser associadas a clientes assíncronos.
- Os títulos podem ser adicionados a clientes assíncronos.
- Não é possível capturar endereços de email e números de telefone secundários para clientes assíncronos.

A partir da versão 10.0.22 do Commerce, você pode habilitar o recurso **Habilitar a criação assíncrona para endereços de clientes** no workspace **Gerenciamento de recursos**. Este recurso permite que endereços de clientes recém-criados sejam salvos de forma assíncrona para clientes síncronos e assíncronos.

Depois de habilitar os recursos mencionados anteriormente, você deve criar e agendar um trabalho em lotes recorrente para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que todos os clientes assíncronos sejam convertidos em clientes síncronos na matriz do Commerce.

### <a name="customer-creation-in-pos-offline-mode"></a>Criação de cliente no modo offline do PDV

Como mencionado anteriormente, sempre que o PDV ficar offline, o sistema cria automaticamente os clientes de forma assíncrona, mesmo se o modo de criação de cliente assíncrono estiver desabilitado. Portanto, os administradores da matriz do Commerce devem criar e agendar um trabalho em lotes recorrente para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que todos os clientes assíncronos sejam convertidos em clientes síncronos na matriz do Commerce.

> [!NOTE]
> Se a opção **Filtrar tabelas de dados do cliente compartilhadas** for definida como **Sim** na página **Esquema de canal do Commerce** (**Varejo e Comércio \> Configuração do Headquarters \> Agendador do Commerce \> Grupo de bancos de dados do canal**), os registros de cliente não serão criados no modo offline de PDV. Para obter mais informações, consulte [Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciamento de clientes em lojas](customer-mgmt-stores.md)

[Converter clientes assíncronos em clientes síncronos](convert-async-to-sync.md)

[Atributos de clientes](dev-itpro/customer-attributes.md)

[Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
