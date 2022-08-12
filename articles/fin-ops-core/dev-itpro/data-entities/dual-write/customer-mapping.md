---
title: Cliente mestre integrado
description: Este artigo descreve a integração de dados do cliente entre finanças e operações e o Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1b16eab5c107a3176f0890372d397947698e71de
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111714"
---
# <a name="integrated-customer-master"></a>Cliente mestre integrado

[!include [banner](../../includes/banner.md)]



Os dados do cliente podem ser dominados em mais de um aplicativo do Dynamics 365. Por exemplo, uma linha de cliente pode se originar durante a atividade de vendas no Dynamics 365 Sales (um aplicativo de engajamento do cliente) ou uma linha pode se originar por meio da atividade de varejo no Dynamics 365 Commerce (um aplicativo de finanças e operações). Não importa onde os dados do cliente se originam, eles são integrados em segundo plano. O cliente mestre integrado oferece a flexibilidade para os dados principais do cliente em qualquer aplicativo Dynamics 365 e fornece uma visão abrangente do cliente no pacote de aplicativos do Dynamics 365.

## <a name="customer-data-flow"></a>Fluxo de dados do cliente

*Cliente* é um conceito bem definido nos aplicativos. Portanto, a integração de dados de clientes envolve apenas a harmonização do conceito de cliente entre os dois aplicativos. A ilustração a seguir mostra o fluxo de dados do cliente.

![Fluxo de dados do cliente.](media/dual-write-customer-data-flow.png)

Os clientes podem ser classificados amplamente em dois tipos: clientes comerciais/organizacionais e clientes/usuários finais. Esses dois tipos de cliente são armazenados e processados de maneiras diferentes em finanças e operações e no Dataverse.

Em finanças e operações, os clientes comerciais/organizacionais e os clientes/usuários finais são dominados em uma única tabela denominada **CustTable** (CustCustomerV3Entity) e são classificados com base no atributo **Tipo**. (Se **Tipo** estiver definido como **Organização**, o cliente será um cliente comercial/organizacional. Se **Tipo** estiver definido como **Pessoa**, o cliente terá um cliente/usuário final.) As informações da pessoa de contato principal é manipulada através da tabela SMMContactPersonEntity.

No Dataverse, clientes comerciais/organizacionais são dominados na tabela Conta e identificados como clientes quando o atributo **RelationshipType** é definido como **Cliente**. Os clientes/usuários finais e a pessoa de contato são representados pela tabela Contato. Para fornecer uma separação clara entre um consumidor/usuário final e uma pessoa de contato, a tabela **Contato** tem um sinalizador booliano denominado **Comercializável**. Quando **Comercializável** for **Verdadeiro**, o contato será um cliente/usuário final; as cotações e ordens podem ser criadas para esse contato. Quando **Comercializável** for **Falso**, o contato será apenas uma pessoa de contato principal de um cliente.

Quando um contato não comercializável participar de uma cotação ou processo de ordem, **Comercializável** será definido como **Verdadeiro** para sinalizar o contato como contato comercializável. Um contato que tornou-se um contato comercializável permanece um contato comercializável.

## <a name="templates"></a>Modelos

Os dados do cliente incluem todas as informações sobre ele, como o grupo de clientes, os endereços, as informações de contato, o perfil do pagamento, o perfil da fatura e o status de fidelidade. Diversos mapas de tabelas trabalham juntos durante a interação de dados do cliente, conforme mostrado na tabela a seguir.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement         | descrição
----------------------------|---------------------------------|------------
[Contatos do CDS V2](mapping-reference.md#115) | contatos | Este modelo sincroniza todas as informações de contato principais, secundárias e terciárias de clientes e fornecedores.
[Grupos de clientes](mapping-reference.md#126) | msdyn_customergroups | Este modelo sincroniza informações do grupo de clientes.
[Método de pagamento do cliente](mapping-reference.md#127) | msdyn_customerpaymentmethods | Este modelo sincroniza informações sobre o método de pagamento dos clientes.
[Clientes V3](mapping-reference.md#101) | contas | Este modelo sincroniza informações mestre de clientes relacionadas a clientes comerciais e organizacionais.
[Clientes V3](mapping-reference.md#116) | contatos | Este modelo sincroniza dados mestres de clientes relacionados a clientes e usuários finais.
[Afixos de nome](mapping-reference.md#155) | msdyn_nameaffixes | Este modelo sincroniza dados de referência de afixos de nome de clientes e fornecedores.
[Linhas de dia de pagamento CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Este modelo sincroniza dados de referência de linhas de pagamento de clientes e fornecedores.
[Dias de pagamento CDS](mapping-reference.md#158) | msdyn_paymentdays | Este modelo sincroniza dados de referência de dias de pagamento de clientes e fornecedores.
[Linhas de plano de pagamento](mapping-reference.md#159) | msdyn_paymentschedulelines | Sincroniza dados de referência de linhas de plano de pagamento de clientes e fornecedores.
[Agenda de pagamento](mapping-reference.md#160) | msdyn_paymentschedules | Este modelo sincroniza dados de referência de planos de pagamento de clientes e fornecedores.
[Condições de pagamento](mapping-reference.md#161) | msdyn_paymentterms | Este modelo sincroniza dados de referência de condições de pagamento (condições de pagamento) de clientes e fornecedores.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

