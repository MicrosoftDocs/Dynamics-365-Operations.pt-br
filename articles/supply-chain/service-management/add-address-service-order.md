---
title: Adicionar um endereço a uma ordem de serviço
description: Este tópico descreve como adicionar um endereço do cliente em uma ordem de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5b1c0e300edc45ae3f4be9eae8afa56e06cccd6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203080"
---
# <a name="add-an-address-to-a-service-order"></a>Adicionar um endereço a uma ordem de serviço    

[!include [banner](../includes/banner.md)]


Este tópico descreve como adicionar um endereço do cliente em uma ordem de serviço. Ao criar uma ordem de serviço, as informações de endereço são transferidas do projeto ao qual a ordem de serviço está anexada. No entanto, você pode selecionar um local alternativo a partir dos endereços que já foram inseridos no Microsoft Dynamics AX para clientes, fornecedores, sites, depósitos, ordens de serviço e projetos.

Também é possível criar um novo endereço. Por padrão, o novo endereço é transferido para o projeto. No entanto, você pode especificar que o novo endereço é relevante apenas para essa instância de serviço. Se fizer isso, o novo endereço não será transferido para o projeto.

## <a name="create-a-customer-address-for-a-service-order"></a>Criar um endereço do cliente para uma ordem de serviço

Para adicionar um endereço em uma ordem de serviço, siga estas etapas:

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Abra a ordem de serviço para a qual você deseja criar um endereço.

3.  No **Painel de Ação**, clique em **Editar** e, em seguida, clique em **Exibição do cabeçalho**.

4.  Na Guia Rápida **Endereço**, clique em **Adicionar endereço**.

5.  No formulário **Novo endereço**, insira um nome exclusivo para o endereço e preencha os campos restantes. 
    

    > [!WARNING]
    > <P>Se você inserir o mesmo nome de um endereço existente, as informações inseridas nos campos restantes substituirão as informações do endereço existente.</P>


6.  Clique em **OK** para copiar o novo endereço para sua ordem de serviço.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Especificar um endereço alternativo em uma ordem de serviço

Para adicionar um endereço alternativo em uma ordem de serviço, siga estas etapas:

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.

2.  Abra a ordem de serviço para a qual você deseja inserir um endereço alternativo.

3.  No **Painel de Ação**, clique em **Editar** e, em seguida, clique em **Exibição do cabeçalho**.

4.  Na Guia Rápida **Endereço**, clique em **Outro endereço**.

5.  No formulário **Seleção de endereço**, no campo **Tipo de registro**, selecione **Ordens de serviço**.

6.  Selecione um endereço e, em seguida, clique em **OK** para copiá-lo em sua ordem de serviço.


  


