---
title: Adicionar um endereço a uma ordem de serviço
description: Este artigo descreve como adicionar um endereço do cliente em uma ordem de serviço.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015715"
---
# <a name="add-an-address-to-a-service-order"></a>Adicionar um endereço a uma ordem de serviço

[!include [banner](../includes/banner.md)]

Este artigo descreve como adicionar um endereço do cliente em uma ordem de serviço. Ao criar uma ordem de serviço, as informações de endereço são transferidas do projeto ao qual a ordem de serviço está anexada. No entanto, você pode selecionar um local alternativo a partir dos endereços que já foram inseridos no Microsoft Dynamics AX para clientes, fornecedores, sites, depósitos, ordens de serviço e projetos.

Também é possível criar um novo endereço. Por padrão, o novo endereço é transferido para o projeto. No entanto, você pode especificar que o novo endereço é relevante apenas para essa instância de serviço. Se fizer isso, o novo endereço não será transferido para o projeto.

## <a name="create-a-customer-address-for-a-service-order"></a>Criar um endereço do cliente para uma ordem de serviço

Para adicionar um endereço em uma ordem de serviço, siga estas etapas:

1. Acesse **Gerenciamento de serviços** \> **Ordens de serviço** \> **Ordens de serviço**.

1. Abra a ordem de serviço para a qual você deseja criar um endereço.

1. Abra a guia **Cabeçalho**.

1. Expanda a Guia Rápida **Endereço** e selecione **Adicionar endereço** na barra de ferramentas da Guia Rápida.

1. Na caixa de diálogo **Novo endereço**, insira um nome exclusivo para o endereço e preencha os campos restantes. 

    > [!WARNING]
    > Se você inserir o mesmo nome de um endereço existente, as informações inseridas nos campos restantes substituirão as informações do endereço existente.

1. Selecione **OK** para copiar o novo endereço para sua ordem de serviço.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Especificar um endereço alternativo em uma ordem de serviço

Para adicionar um endereço alternativo em uma ordem de serviço, siga estas etapas:

1. Acesse **Gerenciamento de serviços** \> **Ordens de serviço** \> **Ordens de serviço**.

1. Abra a ordem de serviço para a qual você deseja inserir um endereço alternativo.

1. Abra a guia **Cabeçalho**.

1. Expanda a Guia Rápida **Endereço** e selecione **Outro endereço** na barra de ferramentas da Guia Rápida.

1. Na caixa de diálogo **Seleção de endereço**, selecione **Ordens de serviço** na lista suspensa acima da grade.

1. Selecione um endereço e, em seguida, selecione **OK** para copiá-lo na sua ordem de serviço.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]