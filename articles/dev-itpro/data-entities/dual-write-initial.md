---
title: Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service
description: Esse tópico especifica a ordem de sincronização que você deve seguir para criar os dados iniciais.
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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797289"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a>Ordem de execução para sincronização inicial do Finance and Operations e do Common Data Service

Antes de usar a integração de dados, você deve criar os dados iniciais necessários para clientes, fornecedores e contatos. Por exemplo, se quiser criar um novo item **Grupo de fornecedores** e definir **Condições de Pagamento** como **Net30**, antes de tentar criar o item **Grupo de fornecedores**, você precisará garantir que exista **Net30** em Finance and Operations e Common Data Service. (No futuro, liberaremos uma funcionalidade de plataforma de gravação dupla chamada **Sincronização Inicial**. Ela fará uma sincronização de dados única entre o Finance and Operations e o Common Data Service como parte da configuração de gravação dupla.)

Dicas: estamos liberando um mapa de gravação dupla para todos os dados de referência, incluindo **Condições de Pagamento** (condições de pagamento). Se você já tiver os dados iniciais em um sistema, uma operação de atualização pequena em um registro poderá acionar uma gravação dupla nesse registro. 

Obedeça a ordem de precedência a seguir e verifique se os dados iniciais estão disponíveis no Finance and Operations e no Common Data Service.   

## <a name="vendor"></a>Fornecedor

A ordem de execução do fornecedor é:

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a>Cliente (Organização)

A ordem de execução do cliente é:

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a>Contato (Pessoa)

A ordem de execução do contato é:

```
Customer
Vendor               
```
