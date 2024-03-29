---
title: Criar requisições de itens para ordens de serviço
description: Este artigo descreve como criar requisições de itens para ordens de serviço.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f21cda0abb334432d22cc7e0ccfdab724253d91e
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016939"
---
# <a name="create-item-requirements-for-service-orders"></a>Criar requisições de itens para ordens de serviço

[!include [banner](../includes/banner.md)]

Você pode criar uma ordem de serviço para rastrear e gerenciar os serviços que você presta para seus clientes. Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele. Uma requisição de item pode ser consumida imediatamente do estoque ou pode iniciar uma ordem de produção do item.

Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção.

As requisições de itens para ordens de serviço são processadas através de um projeto. Para criar uma requisição de item em uma ordem de serviço, a ordem de serviço deverá ser atribuída a um projeto. Depois de criar uma requisição de item para uma ordem de serviço, você poderá exibir a requisição de item no formulário **Projetos** do projeto selecionado.

## <a name="create-an-item-requirement-for-a-service-order"></a>Criar uma requisição de itens para uma ordem de serviço

1. Acesse **Gerenciamento de serviços** \> **Ordens de serviço** \> **Ordens de serviço**.
1. Selecione a ordem de serviço para a qual você deseja criar uma requisição de item.
1. No **Painel de Ações**, na guia **Expedição**, selecione **Requisição de itens**.
1. No formulário **Requisição de itens**, insira informações sobre o item requisitado. Para obter informações sobre os campos específicos, consulte [Requisição de itens (formulário)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Criar uma requisição de item para um contrato de serviço

1. Acesse **Gerenciamento de serviços** \> **Contratos de serviço** \> **Contratos de serviço**.
1. Abra o contrato de serviço para o qual você deseja criar uma requisição de item.
1. Na Guia Rápida **Linhas**, selecione **Adicionar** para criar uma linha.
1. No campo **Tipo de transação**, selecione **Item**.
1. No campo **Configuração de item**, selecione **Requisição de itens**.
1. No campo **Número de item**, selecione o item necessário ao contrato de serviço.
1. Na Guia Rápida **Detalhes de linha**, na guia **Dimensões de produto**, no campo **Local**, selecione o local de estoque do item.
1. Para criar uma ordem de serviço da linha do contrato, na Guia Rápida **Linhas**, selecione **Criar ordens de serviço**, e insira as informações relevantes ao formulário **Criar ordens de serviço**.

## <a name="see-also"></a>Consulte também

[Criar ordens de serviço automaticamente](create-service-orders-automatically.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
