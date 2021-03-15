---
title: Fornecedor mestre integrado
description: Este tópico descreve a integração de dados do fornecedor entre os aplicativos Finance and Operations e o Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f2fc88ed0c0f4dbec55f8ca251cca3d071760b55
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744506"
---
# <a name="integrated-vendor-master"></a>Fornecedor mestre integrado

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



O termo *fornecedor* refere-se a uma organização fornecedora ou a um único proprietário que fornece bens ou serviços a uma empresa. Embora *fornecedor* seja um conceito estabelecido no Microsoft Dynamics 365 Supply Chain Management, nenhum conceito de fornecedor existe nos aplicativos baseados em modelo no Dynamics 365. No entanto, você pode sobrecarregar a tabela **Conta/Contato** para armazenar informações do fornecedor. O fornecedor mestre integrado introduz um conceito explícito de fornecedor em aplicativos baseados em modelo no Dynamics 365. Você pode usar o novo design de fornecedor ou armazenar dados do fornecedor na tabela **Conta/Contato**. A gravação dupla oferece suporte às duas abordagens.

Nas duas abordagens, os dados do fornecedor são integrados entre os portais do Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service e Power Apps. No Supply Chain Management, os dados estão disponíveis para fluxos de trabalho, como requisições e ordens de compra.

## <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor

Se não quiser armazenar dados do fornecedor na tabela **Conta/Contato** no Dataverse, você poderá usar o novo design de fornecedor.

![Fluxo de dados do fornecedor](media/dual-write-vendor-data-flow.png)

Se quiser continuar armazenando dados do fornecedor na tabela **Conta/Contato**, você poderá usar o design de fornecedor estendido. Para usar o design de fornecedor estendido, você deverá configurar os fluxos de trabalho do fornecedor no pacote da solução de gravação dupla. Para obter mais informações, consulte [Alternar entre designs de fornecedor](vendor-switch.md).

![Fluxo de dados estendidos do fornecedor](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Se você estiver usando os portais do Power Apps para fornecedores de autoatendimento, as informações do fornecedor poderão entrar diretamente nos aplicativos do Finance and Operations.

## <a name="templates"></a>Modelos

Os dados do fornecedor incluem todas as informações sobre ele, como o grupo de fornecedores, os endereços, as informações de contato, o perfil do pagamento e o perfil da fatura. Um conjunto de mapas de tabelas funcionam juntos durante a interação de dados dos fornecedores, conforme mostrado na tabela a seguir.

Aplicativos Finance and Operations | Outros aplicativos do Dynamics 365     | descrição
----------------------------|-----------------------------|------------
Fornecedor V2                   | Conta                     | As empresas que usam a tabela Conta para armazenar informações do fornecedor podem continuar a usá-la da mesma maneira. Elas também podem aproveitar a funcionalidade explícita de fornecedor que será disponibilizada com a integração de aplicativos do Finance and Operations.
Fornecedor V2                   | Msdyn\_vendors              | As empresas que usam uma solução personalizada para fornecedores podem aproveitar o conceito de fornecedor pronto para uso que está sendo apresentado no Dataverse com a integração de aplicativos do Finance and Operations. 
Grupos de fornecedores               | msdyn\_vendorgroups         | Este modelo sincroniza informações do grupo de fornecedores.
Método de pagamento do fornecedor       | msdyn\_vendorpaymentmethods | Este modelo sincroniza informações sobre o método de pagamento dos fornecedores.
Contatos do CDS V2             | contatos                    | O modelo [contatos](customer-mapping.md#cds-contacts-v2-to-contacts) sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores.
Linhas de plano de pagamento      | msdyn\_paymentschedulelines | O modelo [linhas de plano de pagamento](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sincroniza dados de referência de clientes e fornecedores.
Plano de Pagamento            | msdyn\_paymentschedules     | O modelo [planos de pagamento](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) sincroniza dados de referência de planos de pagamento de clientes e fornecedores.
Linhas de dia de pagamento CDS V2    | msdyn\_paymentdaylines      | O modelo [linhas de dia de pagamento](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sincroniza dados de referência de linhas de dia de pagamento de clientes e fornecedores.
Dias de pagamento CDS            | msdyn\_paymentdays          | O modelo [dias de pagamento](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) sincroniza dados de referência de dias de pagamento de clientes e fornecedores.
Condições de pagamento            | msdyn\_paymentterms         | O modelo [condições de pagamento](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) sincroniza dados de referência de condições de pagamento de clientes e fornecedores.
Afixos de nome                | msdyn\_nameaffixes          | O modelo [afixos de nome](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) sincroniza dados de referência de afixos de nome de clientes e fornecedores.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]