---
title: Criar hierarquias de modelagem de organização para organizações B2B
description: Este tópico descreve como criar hierarquias de modelagem organizacional para organizações business-to-business (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 487af939f92ece8bc3e543b3beeffa239baa1863
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799820"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Criar hierarquias de modelagem de organização para organizações B2B

[!include [banner](../../includes/banner.md)]

Este tópico descreve como criar hierarquias de modelagem organizacional para organizações business-to-business (B2B) no Microsoft Dynamics 365 Commerce.

Na sede do Commerce, as organizações parceiras comerciais são representadas por entidades de clientes e hierarquia de clientes. A organização parceira comercial e seus usuários são representados como clientes, e as hierarquias do cliente são usadas para associar esses clientes entre si.

Quando é aprovada uma solicitação de parceiro comercial para ingressar em um site de comércio eletrônico B2B, as seguintes ações são executadas:

- Dois novos registros de clientes são criados no sistema: um registro de cliente de **Tipo Organização** para a organização parceira comercial e um registro de cliente de **Tipo Pessoa** para o solicitante (ou seja, o usuário parceiro comercial que enviou a solicitação).
- Um novo registro de hierarquia de cliente é criado em **Cliente \> Hierarquia do cliente**. Este registro tem as seguintes propriedades de cabeçalho:

    - **ID da hierarquia do cliente** – uma ID exclusiva para a hierarquia do cliente. Essa ID usa a sequência numérica definida em parâmetros compartilhados do Commerce na sede do Commerce.
    - **Nome** – o nome da organização parceira comercial, conforme especificado na solicitação de integração.
    - **Finalidade** – esta propriedade é definida como o valor predefinido da **organização B2B**.
    - **Organização** – a ID de cliente do parceiro comercial.

Estes são os detalhes do registro da hierarquia do cliente:

- O registro de cliente do solicitante está associado à hierarquia do cliente.
- A função de administrador está associada ao solicitante.

Quando o administrador adiciona mais usuários à organização parceira comercial em um site B2B, um novo registro de cliente para cada usuário é criado na sede do Commerce. Esse registro de cliente também é adicionado ao registro de hierarquia de cliente relevante para o parceiro comercial e tem a função de "usuário".

> [!NOTE]
> Na maioria dos casos, os valores de propriedade correspondentes de todos os registros de cliente em uma hierarquia devem coincidir. Por exemplo, como todos os usuários parceiros comerciais devem obter preços semelhantes para produtos, seu grupo de preços e configurações associadas devem coincidir. No entanto, o sistema não impõe essa consistência. Portanto, os usuários da sede do Commerce relevantes são responsáveis por garantir que os valores de propriedade e as configurações correspondam a todos os clientes em determinada hierarquia.

Os usuários da sede do Commerce podem verificar os valores de propriedade de todos os registros de clientes na hierarquia em um modo de exibição lado a lado. Selecione as propriedades de registro de cliente relevantes selecionando os nomes de guias no menu suspenso. Os usuários podem exibir e editar diretamente os valores de propriedade neste modo de exibição. Como alternativa, se você desejar aplicar todos os valores do registro de cliente administrador a todos os registros de cliente do usuário, selecione **Substituir** nos detalhes da hierarquia do cliente.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um site de comércio eletrônico B2B](set-up-b2b-site.md)

[Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B](manage-b2b-users.md)

[Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B](payment-method.md)

[Definir limites de quantidade de produto para sites de comércio eletrônico B2B](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]