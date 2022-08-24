---
title: Modo de criação de cliente assíncrono
description: Este artigo descreve o modo de criação de cliente assíncrono no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 1ac1bc842d5d12ece8951ffed18157e6f9b50d14
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228714"
---
# <a name="asynchronous-customer-creation-mode"></a>Modo de criação de cliente assíncrono

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve o modo de criação de cliente assíncrono no Microsoft Dynamics 365 Commerce.

No Commerce, há dois modos de criação de clientes: síncrono e assíncrono. Por padrão, os clientes são criados de forma síncrona. Em outras palavras, eles são criados no Commerce headquarters em tempo real. O modo síncrono de criação de clientes é vantajoso porque novos clientes são pesquisados imediatamente nos canais. No entanto, ele também tem uma desvantagem. Como ele gera chamadas do [Commerce Data Exchange: Serviço em tempo real](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) para o Commerce headquarters, o desempenho poderá ser afetado se várias chamadas simultâneas de criação de clientes forem feitas.

Se a opção **Criar cliente no modo assíncrono** estiver definida como **Sim** no perfil de funcionalidade da loja (**Varejo e Comércio \> Configuração do canal \> Configuração da loja online \> Perfis de funcionalidade**), as chamadas do Serviço em Tempo Real não são usadas para criar registros de cliente no banco de dados do canal. O modo assíncrono de criação de clientes não afeta o desempenho do Commerce headquarters. Um GUID (identificador global exclusivo) temporário é atribuído a cada novo registro de cliente assíncrono e usado como a ID da conta do cliente. Esse GUID não é exibido aos usuários do ponto de venda (PDV). Em vez disso, esses usuários verão **Sincronização pendente** como a ID da conta do cliente.

> [!IMPORTANT]
> Sempre que o PDV ficar offline, o sistema criará automaticamente os clientes de forma assíncrona, mesmo se o modo de criação de cliente assíncrono estiver desabilitado. Portanto, seja qual for a seleção entre criação de clientes síncronos e assíncronos, os administradores do Commerce headquarters devem criar e agendar um trabalho em lotes recorrente para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que todos os clientes assíncronos sejam convertidos em clientes síncronos no Commerce headquarters.

## <a name="async-customer-limitations"></a>Limitações do cliente Assíncrono

No momento, a funcionalidade de cliente assíncrono tem a seguinte limitação:

- Os cartões-fidelidade não podem ser emitidos para clientes assíncronos a menos que a nova ID da conta do cliente tenha sido sincronizada novamente para o canal.

## <a name="async-customer-enhancements"></a>Aprimoramentos do cliente assíncrono

Para ajudar as organizações a usar o modo de criação de clientes assíncronos para gerenciar clientes e ajudar a reduzir a comunicação em tempo real com o Commerce headquarters, os aperfeiçoamentos a seguir foram lançados para ativar a paridade entre os modos síncrono e assíncrono em canais. 

| Aprimoramento do recurso | Versão do Commerce | Detalhes do recurso |
|---|---|---|
| Melhorias de desempenho quando as informações do cliente são recuperadas do banco de dados do canal | 10.0.20 e posterior | Para ajudar a melhorar o desempenho, a entidade do cliente é dividida em entidades menores. O sistema recupera somente as informações necessárias do banco de dados de canal. |
| Capacidade de criar endereço assincronamente durante check-out | 10.0.22 e posterior | <p>Alternância de recurso: **Habilitar criação assíncrona para endereços de cliente**</p><p>Detalhes do recurso:</p><ul><li>Capacidade de adicionar endereços sem fazer chamadas de serviço em tempo real para o Commerce headquarters</li><li>Capacidade de identificar endereços de forma exclusiva no banco de dados do canal sem usar uma ID de registro (valor **RecId**)</li><li>Rastrear carimbos de data/hora para a criação de endereços</li><li>Sincronização de endereços no Commerce headquarters</li></ul><p>Esse recurso afeta clientes síncronos e clientes assíncronos. Para editar os endereços de forma assíncrona, além de criá-los de forma assíncrona, você deve habilitar o recurso **Edição de clientes no modo assíncrono**.</p> |
| Habilite a paridade entre a criação de clientes síncronos e assíncronos. | 10.0.24 e posterior | <p>Alternância de recurso: **Habilitar criação avançada de cliente assíncrono**</p><p>Detalhes do recurso: capacidade de capturar informações adicionais, como o título, afiliações do cliente padrão e informações de contato secundárias (número de telefone e endereço de email), enquanto você cria clientes de forma assíncrona</p> |
| Mensagens de erro amigáveis | 10.0.28 e posterior | Esses aperfeiçoamentos ajudarão a melhorar as mensagens de erro amigáveis se um usuário não puder editar logo as informações enquanto a sincronização estiver em andamento. Habilite esses aperfeiçoamentos usando o recurso **Permitir que certos elementos da interface do usuário sejam não modificáveis por um cliente assíncrono** em **Configurações do site \> Extensões** no construtor de sites do Commerce. |
| Capacidade de editar informações do cliente de forma assíncrona | 10.0.29 e posterior | <p>Alternância de recurso: **Habilitar edição de clientes no modo assíncrono**</p><p>Detalhes do recurso: capacidade de editar dados do cliente de forma assíncrona</p><p>Para obter respostas a perguntas comuns sobre questões relacionadas à edição de informações do cliente de forma assíncrona, consulte [Perguntas frequentes do modo de criação de cliente assíncrono](async-customer-mode-faq.md).</p> |

### <a name="feature-switch-hierarchy"></a>Hierarquia da alternância de recursos

Devido à hierarquia da alternância de recursos, antes de ativar o recurso **Habilitar edição de clientes no modo assíncrono**, você deve habilitar os seguintes recursos: 

- **Melhorias de desempenho para ordens e transações de clientes**: esse recurso é obrigatório desde a versão 10.0.28 do Commerce. 
- **Habilitar criação avançada de cliente assíncrono**
- **Habilitar criação assíncrona para endereços de cliente**

Para obter respostas para perguntas comuns de solução de problemas, consulte [Perguntas frequentes do modo de criação de cliente assíncrono](async-customer-mode-faq.md). 

Depois de habilitar os recursos mencionados anteriormente, você deve criar e agendar um trabalho em lotes recorrente para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que todos os clientes assíncronos sejam convertidos em clientes síncronos no Commerce headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Criação de cliente no modo offline do PDV

Como mencionado anteriormente, sempre que o PDV ficar offline, o sistema cria automaticamente os clientes de forma assíncrona, mesmo se o modo de criação de cliente assíncrono estiver desabilitado. Portanto, os administradores do Commerce headquarters devem criar e agendar um trabalho em lotes recorrente para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que todos os clientes assíncronos sejam convertidos em clientes síncronos no Commerce headquarters.

> [!NOTE]
> Se a opção **Filtrar tabelas de dados do cliente compartilhadas** for definida como **Sim** na página **Esquema de canal do Commerce** (**Varejo e Comércio \> Configuração do headquarters \> Agendador do Commerce \> Grupo de bancos de dados do canal**), os registros de cliente não serão criados no modo offline de PDV. Para obter mais informações, consulte [Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciamento de clientes em lojas](customer-mgmt-stores.md)

[Converter clientes assíncronos em clientes síncronos](convert-async-to-sync.md)

[Atributos de clientes](dev-itpro/customer-attributes.md)

[Exclusão de dados offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
