---
title: Ordem de execução da sincronização inicial entre aplicativos do Finance and Operations e o Common Data Service
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
ms.openlocfilehash: 3110cb809558d168e9d97f640701b249caf73f6c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184499"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a>Ordem de execução da sincronização inicial entre aplicativos do Finance and Operations e o Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Antes de usar a integração de dados, você deve criar os dados iniciais necessários para clientes, fornecedores e contatos. Por exemplo, você deseja criar um item **Grupo de Fornecedores** e definir seu valor **Condições de Pagamento** como **Net30**. Nesse caso, antes de tentar criar o item **Grupo de fornecedores**, você deve verificar se **Net30** existe no aplicativo e no Common Data Service. (No futuro, a Microsoft liberará a funcionalidade de plataforma de gravação dupla chamada Sincronização Inicial. Ela fará uma sincronização de dados única entre o aplicativo e o Common Data Service como parte da configuração de gravação dupla.)

> [!TIP]
> A Microsoft está liberando um mapa de gravação dupla para todos os dados de referência, incluindo **Condições de Pagamento**. Se você já tiver os dados iniciais em um sistema, uma operação de atualização pequena em um registro poderá acionar uma gravação dupla nesse registro.

Obedeça à ordem de precedência a seguir e verifique se os dados iniciais estão disponíveis no aplicativo e no Common Data Service.

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
