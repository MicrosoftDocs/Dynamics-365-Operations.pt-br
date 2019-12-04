---
title: Fornecedor mestre integrado
description: Este tópico descreve a integração de dados do fornecedor entre aplicativos do Finance and Operations e o Common Data Service.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: da451c63c23444da564307505d38699faf9df19a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770967"
---
# <a name="integrated-vendor-master"></a>Fornecedor mestre integrado

[!include [banner](../includes/banner.md)]

O termo *fornecedor* se refere a uma organização fornecedora ou um único proprietário que faça parte do processo da cadeia de suprimentos, e que forneça mercadorias para a empresa. Embora *fornecedor* seja um conceito estabelecido em aplicativos do Finance and Operations, ele não existe em outros aplicativos do Dynamics 365. No lugar, algumas empresas sobrecarregam a entidade Conta para armazenar as informações do cliente e as informações do fornecedor. Outras empresas usam um conceito personalizado de fornecedor. A integração do Common Data Service oferece suporte a ambos os designs. Portanto, você pode habilitar qualquer design, dependendo de seu cenário empresarial.

A integração de dados dos fornecedores entre aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 permite dominar os dados. Independentemente de onde os dados do fornecedor são originados, eles são integrados em segundo plano nos limites dos aplicativos e nas diferenças de infraestrutura. 

### <a name="vendor-data-flow"></a>Fluxo de dados do fornecedor

Se você deseja usar outros aplicativos do Dynamics 365 para controlar os fornecedores e quer separar as informações dos fornecedores das informações dos clientes, pode usar o novo design de fornecedor.

![Fluxo de dados do fornecedor](media/dual-write-vendor-data-flow.png)

Se você deseja usar outros aplicativos do Dynamics 365 para controlar os fornecedores e quer continuar usando a entidade Conta para armazenar informações dos fornecedores, pode usar o novo design de fornecedor estendido. Nesse design, informações estendidas de fornecedor, como grupo de fornecedores e o perfil de lançamentos do fornecedor, são armazenadas nos detalhes do fornecedor.

![Fluxo de dados estendidos do fornecedor](media/dual-write-vendor-detail.jpg)

As informações de contato do fornecedor se assemelham às informações de contato do cliente. Em segundo plano, as informações da pessoa de contato são armazenadas e recuperadas das mesmas entidades.

## <a name="templates"></a>Modelos

Os dados do fornecedor incluem todas as informações sobre ele, como o grupo de fornecedores, os endereços, as informações de contato, o perfil do pagamento e o perfil da fatura. Um conjunto de mapas de entidades funcionam juntos durante a interação de dados dos fornecedores, conforme mostrado na tabela a seguir.

Aplicativos do Finance and Operations | Outros aplicativos do Dynamics 365         | Descrição
----------------------------|---------------------------------|------------
Fornecedor V2               | Conta | As empresas que usam a entidade Conta para armazenar informações do fornecedor podem continuar a usá-la da mesma maneira. Elas também podem aproveitar a funcionalidade explícita de fornecedor que será disponibilizada com a integração de aplicativos do Finance and Operations.
Fornecedor V2               | Msdyn\_vendors | As empresas que usam uma solução personalizado para fornecedores podem aproveitar o conceito de fornecedor pronto para uso que está sendo apresentado no Common Data Service com a integração de aplicativos do Finance and Operations. 
Grupos de fornecedores | msdyn_vendorgroups | Este modelo sincroniza informações do grupo de fornecedores.
Método de pagamento do fornecedor | msdyn_vendorpaymentmethods | Este modelo sincroniza informações sobre o método de pagamento dos fornecedores.
Contatos do CDS V2             | contatos                        | O modelo [contatos](dual-write-customer.md#cds-contacts-v2-to-contacts) sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores.
Linhas de plano de pagamento      | msdyn_paymentschedulelines      | O modelo [linhas de plano de pagamento](dual-write-customer.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sincroniza dados de referência de clientes e fornecedores.
Agenda de pagamento            | msdyn_paymentschedules          | O modelo [planos de pagamento](dual-write-customer.md#payment-schedule-to-msdyn_paymentschedules) sincroniza dados de referência de planos de pagamento de clientes e fornecedores.
Linhas de dia de pagamento CDS V2    | msdyn_paymentdaylines           | O modelo [linhas de dia de pagamento](dual-write-customer.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sincroniza dados de referência de linhas de dia de pagamento de clientes e fornecedores.
Dias de pagamento CDS            | msdyn_paymentdays               | O modelo [dias de pagamento](dual-write-customer.md#payment-days-cds-to-msdyn_paymentdays) sincroniza dados de referência de dias de pagamento de clientes e fornecedores.
Condições de pagamento            | msdyn_paymentterms              | O modelo [condições de pagamento](dual-write-customer.md#terms-of-payment-to-msdyn_paymentterms) sincroniza dados de referência de condições de pagamento de clientes e fornecedores.
Afixos de nome                | msdyn_nameaffixes               | O modelo [afixos de nome](dual-write-customer.md#name-affixes-to-msdyn_nameaffixes) sincroniza dados de referência de afixos de nome de clientes e fornecedores.

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [Vendors](dual-write/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](dual-write/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](dual-write/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
