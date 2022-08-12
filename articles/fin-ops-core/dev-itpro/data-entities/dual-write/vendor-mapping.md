---
title: Fornecedor mestre integrado
description: Este artigo descreve a integração de dados do fornecedor entre aplicativos de finanças e operações e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a2c32ef546a5bc74e090591c0ac9d51529299041
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112184"
---
# <a name="integrated-vendor-master"></a>Fornecedor mestre integrado

[!include [banner](../../includes/banner.md)]



O termo *fornecedor* refere-se a uma organização fornecedora ou a um único proprietário que fornece bens ou serviços a uma empresa. Embora *fornecedor* seja um conceito estabelecido no Microsoft Dynamics 365 Supply Chain Management, nenhum conceito de fornecedor existe nos aplicativos do Customer Engagement. No entanto, você pode sobrecarregar a tabela **Conta/Contato** para armazenar informações do fornecedor. O fornecedor mestre integrado introduz um conceito explícito de fornecedor nos aplicativos do Customer Engagement. Você pode usar o novo design de fornecedor ou armazenar dados do fornecedor na tabela **Conta/Contato**. A gravação dupla oferece suporte às duas abordagens.

Nas duas abordagens, os dados do fornecedor são integrados entre os portais do Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service e Power Apps. No Supply Chain Management, os dados estão disponíveis para fluxos de trabalho, como requisições e ordens de compra.

## <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor

Se não quiser armazenar dados do fornecedor na tabela **Conta/Contato** no Dataverse, você poderá usar o novo design de fornecedor.

![Fluxo de dados do fornecedor.](media/dual-write-vendor-data-flow.png)

Se quiser continuar armazenando dados do fornecedor na tabela **Conta/Contato**, você poderá usar o design de fornecedor estendido. Para usar o design de fornecedor estendido, você deverá configurar os fluxos de trabalho do fornecedor no pacote da solução de gravação dupla. Para obter mais informações, consulte [Alternar entre designs de fornecedor](vendor-switch.md).

![Fluxo de dados estendidos do fornecedor.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Se você estiver usando os portais do Power Apps para fornecedores de autoatendimento, as informações do fornecedor poderão entrar diretamente nos aplicativos de finanças e operações.

## <a name="templates"></a>Modelos

Os dados do fornecedor incluem todas as informações sobre ele, como o grupo de fornecedores, os endereços, as informações de contato, o perfil do pagamento e o perfil da fatura. Um conjunto de mapas de tabelas funcionam juntos durante a interação de dados dos fornecedores, conforme mostrado na tabela a seguir.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement     | descrição
----------------------------|-----------------------------|------------
[Contatos do CDS V2](mapping-reference.md#115) | contatos | Este modelo sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores.
[Afixos de nome](mapping-reference.md#155) | msdyn_nameaffixes | Este modelo sincroniza dados de referência de afixos de nome de clientes e fornecedores.
[Linhas de dia de pagamento CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Este modelo sincroniza dados de referência de linhas de pagamento de clientes e fornecedores.
[Dias de pagamento CDS](mapping-reference.md#158) | msdyn_paymentdays | Este modelo sincroniza dados de referência de dias de pagamento de clientes e fornecedores.
[Linhas de plano de pagamento](mapping-reference.md#159) | msdyn_paymentschedulelines | Sincroniza dados de referência de linhas de plano de pagamento de clientes e fornecedores.
[Agenda de pagamento](mapping-reference.md#160) | msdyn_paymentschedules | Este modelo sincroniza dados de referência de planos de pagamento de clientes e fornecedores.
[Condições de pagamento](mapping-reference.md#161) | msdyn_paymentterms | Este modelo sincroniza dados de referência de condições de pagamento (condições de pagamento) de clientes e fornecedores.
[Fornecedores V2](mapping-reference.md#202) | msdyn_vendors | As empresas que usam uma solução personalizada para os fornecedores podem aproveitar o conceito pronto para uso que está sendo apresentado no Dataverse com a integração de aplicativos de finanças e operações.
[Grupos de fornecedores](mapping-reference.md#200) | msdyn_vendorgroups | Este modelo sincroniza informações do grupo de fornecedores.
[Método de pagamento do fornecedor](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Este modelo sincroniza informações sobre o método de pagamento dos fornecedores.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

