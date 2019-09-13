---
title: Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service
description: Este tópico especifica a ordem de sincronização que você deve seguir para criar os dados iniciais.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873119"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a>Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Antes de usar a integração de dados, você deve criar os dados iniciais necessários para clientes, fornecedores e contatos. Por exemplo, você deseja criar um item **Grupo de Fornecedores** e definir seu valor **Condições de Pagamento** como **Net30**. Nesse caso, antes de tentar criar o item **Vendor group**, você deve se certificar de que **Net30** existe no Microsoft Dynamics 365 for Finance and Operations e no Common Data Service. (No futuro, a Microsoft liberará a funcionalidade de plataforma de gravação dupla chamada Sincronização Inicial. Ela fará uma sincronização de dados única entre o Finance and Operations e o Common Data Service como parte da configuração de gravação dupla.)

> [!TIP]
> A Microsoft está liberando um mapa de gravação dupla para todos os dados de referência, incluindo **Condições de Pagamento**. Se você já tiver os dados iniciais em um sistema, uma operação de atualização pequena em um registro poderá acionar uma gravação dupla nesse registro.

Obedeça a ordem de precedência a seguir e verifique se os dados iniciais estão disponíveis no Finance and Operations e no Common Data Service.

## <a name="vendor"></a>Fornecedor

Veja a ordem de execução da entidade **Fornecedor**:

1. Grupo de Fornecedores

    1. Condições de pagamento

        1. Dia e linhas de pagamento
        2. Agenda de pagamento

2. Método de pagamento do fornecedor

## <a name="customer-organization"></a>Cliente (Organização)

Veja a ordem de execução da entidade **Cliente**:

1. Grupo de clientes

    1. Condições de pagamento

        1. Dia e linhas de pagamento
        2. Pagamento 

2. Método de pagamento do cliente

## <a name="contact-person"></a>Contato (Pessoa)

Veja a ordem de execução da entidade **Contato**:

1. Cliente
2. Fornecedor
