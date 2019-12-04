---
title: Cliente mestre integrado
description: Este tópico descreve a integração de dados do cliente entre o Finance and Operations e o Common Data Service.
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
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769674"
---
# <a name="integrated-customer-master"></a>Cliente mestre integrado

[!include [banner](../includes/banner.md)]

É comum que registros de cliente sejam dominados em mais de um aplicativo. Por exemplo, a atividade de vendas pode exibir registros de cliente comercial por meio de um aplicativo de vendas. O comércio eletrônico ou as vendas de varejo podem exibir registros de clientes por meio de um aplicativo do Finance and Operations. Seja qual for a origem do registro do cliente, ele é integrado em segundo plano nos limites dos aplicativos e nas diferenças de infraestrutura. O domínio do cliente integrado ajuda a tratar vários cenários de domínio e fornece uma exibição abrangente do cliente ao pacote de aplicativos do Dynamics 365.

## <a name="customer-data-flow"></a>Fluxo de dados do cliente

*Cliente* é um conceito bem definido nos aplicativos. Portanto, a integração de dados de clientes envolve apenas a harmonização do conceito de cliente entre os dois aplicativos. A ilustração a seguir mostra o fluxo de dados do cliente.

![Fluxo de dados do cliente](media/dual-write-customer-data-flow.png)

Os clientes podem ser classificados amplamente em dois tipos: clientes comerciais/organizacionais e clientes/usuários finais. Esses dois tipos de cliente são armazenados e processados de maneiras diferentes no Finance and Operations e no Common Data Service.

No Finance and Operations, os clientes comerciais/organizacionais e os clientes/usuários finais são dominados em uma única tabela denominada **CustTable** (CustomerCustomerV3Entity) e são classificados com base no atributo **Tipo**. (Se **Tipo** estiver definido como **Organização**, o cliente será um cliente comercial/organizacional. Se **Tipo** estiver definido como **Pessoa**, o cliente terá um cliente/usuário final.) As informações da pessoa de contato principal é manipulada através da entidade SMMContactPersonEntity.

No Common Data Service, clientes comerciais/organizacionais são dominados na entidade Conta e identificados como clientes quando o atributo **RelationshipType** é definido como **Cliente**. Os clientes/usuários finais e a pessoa de contato são representados pela entidade Contato. Para fornecer uma separação clara entre um consumidor/usuário final e uma pessoa de contato, a entidade **Contato** tem um sinalizador booliano denominado **Comercializável**. Quando **Comercializável** for **Verdadeiro**, o contato será um cliente/usuário final; as cotações e ordens podem ser criadas para esse contato. Quando **Comercializável** for **Falso**, o contato será apenas uma pessoa de contato principal de um cliente.

Quando um contato não comercializável participar de uma cotação ou processo de ordem, **Comercializável** será definido como **Verdadeiro** para sinalizar o contato como contato comercializável. Um contato que tornou-se um contato comercializável permanece um contato comercializável.

## <a name="templates"></a>Modelos

Os dados do cliente incluem todas as informações sobre ele, como o grupo de clientes, os endereços, as informações de contato, o perfil do pagamento, o perfil da fatura e o status de fidelidade. Um conjunto de mapas de entidades funcionam juntos durante a interação de dados do cliente, conforme mostrado na tabela a seguir.

Aplicativos do Finance and Operations | Outros aplicativos do Dynamics 365         | Descrição
----------------------------|---------------------------------|------------
Contatos do CDS V2             | contatos                        | Este modelo sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores.
Grupos de clientes             | msdyn_customergroups            | Este modelo sincroniza informações do grupo de clientes.
Método de pagamento do cliente     | msdyn_customerpaymentmethods    | Este modelo sincroniza informações sobre o método de pagamento dos clientes.
Clientes V3                | contas                        | Este modelo sincroniza informações mestre de clientes relacionadas a clientes comerciais e organizacionais.
Clientes V3                | contatos                        | Este modelo sincroniza dados mestres de clientes relacionados a clientes e usuários finais.
Cartão-fidelidade                | msdyn_loyaltycards              | Este modelo sincroniza informações do cartão-fidelidade dos clientes.
Afixos de nome                | msdyn_nameaffixes               | Este modelo sincroniza dados de referência de afixos de nome de clientes e fornecedores.
Linhas de dia de pagamento CDS V2    | msdyn_paymentdaylines           | Este modelo sincroniza dados de referência de linhas de pagamento de clientes e fornecedores.
Dias de pagamento CDS            | msdyn_paymentdays               | Este modelo sincroniza dados de referência de dias de pagamento de clientes e fornecedores.
Linhas de plano de pagamento      | msdyn_paymentschedulelines      | Sincroniza dados de referência de linhas de plano de pagamento de clientes e fornecedores.
Agenda de pagamento            | msdyn_paymentschedules          | Este modelo sincroniza dados de referência de planos de pagamento de clientes e fornecedores.
Condições de pagamento            | msdyn_paymentterms              | Este modelo sincroniza dados de referência de condições de pagamento (condições de pagamento) de clientes e fornecedores.

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
