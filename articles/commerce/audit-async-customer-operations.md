---
title: Auditar a sincronização das operações do cliente no headquarters
description: Este artigo explica como auditar a sincronização de operações do cliente no Microsoft Dynamics 365 Commerce headquarters para ajudar a corrigir qualquer problema de usuário do site.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691052"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Auditar a sincronização das operações do cliente no headquarters

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo explica como auditar a sincronização de operações do cliente no Microsoft Dynamics 365 Commerce headquarters para ajudar a corrigir qualquer problema de usuário do site.

À medida que as empresas começam a adotar a capacidade de criar e editar clientes de forma assíncrona, os administradores do site precisam de uma forma de exibir e solucionar problemas de operações, com base nas solicitações de usuário do site ou no processo. Nessas situações, os administradores do site devem ser capazes de auditar as operações de criação e edição do cliente e corrigir as falhas usando um modelo de autoatendimento.

## <a name="customer-synchronization-status"></a>Status da sincronização de cliente

Quando você opta pelo modo assíncrono de gerenciamento de clientes e seus recursos correspondentes, os administradores do Commerce headquarters devem criar e programar um trabalho em lotes recorrentes para o **trabalho P**, o trabalho **Sincronizar clientes e parceiros comerciais do modo assíncrono** e o trabalho **1010**, para que quaisquer clientes assíncronos sejam convertidos em clientes sincronizados na sede do Commerce. A sincronização das operações de gerenciamento de clientes ocorre sempre que esses trabalhos são executados. Para obter mais informações, consulte [Modo de criação de cliente assíncrono](async-customer-mode.md).

Como um proprietário de negócios, você pode realizar as seguintes operações:

- Exibir todas as operações de criação/edição de usuários do site. Os detalhes incluem o status e um carimbo de data/hora.
- Filtrar as operações usando quaisquer campos e valores da tabela do cliente para restringir o log de auditoria.
- Exibir descrições breves de alterações juntamente com os detalhes do status para compreender as operações em um nível alto.
- Para falhas, edite e corrija os campos problemáticos, salve e sincronize operações específicas do cliente.

### <a name="elements-on-the-customer-synchronization-status-page"></a>Elementos na página Status da sincronização de cliente

Para exibir uma lista de todas as operações de sincronização, no Commerce headquarters vá para **Commerce and Retail \> Customers \> Status da sincronização de cliente**. A ilustração a seguir mostra um exemplo da página **Status da sincronização de cliente**.

![Página Status da sincronização de cliente no Commerce Headquarters.](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

Por padrão, a lista de operações de sincronização de clientes no lado esquerdo da página **Status da sincronização de cliente** inclui as seguintes colunas:

- Nome do canal
- Conta do cliente
- Conta de cliente assíncrona
- Carimbo de data/hora das operações
- Status de sincronização do cliente

A parte superior direita da página mostra os detalhes da conta do cliente, como os valores de **Conta do cliente**, **Operação do Retail Async**, **Status de sincronização do cliente** e **Último erro conhecido**.

A seção **Alterar descrição** contém uma descrição do tipo de operação de gerenciamento de clientes executada (por exemplo, criação de cliente, atualização de conta ou falha de sincronização com detalhes).

A seção **Atributos do cliente** contém uma grade que mostra todos os atributos de clientes, juntamente com os valores antigos e novos. Você pode editar esta seção se quiser alterar os valores de atributo de cliente para corrigir bugs e sincronizar novamente.
