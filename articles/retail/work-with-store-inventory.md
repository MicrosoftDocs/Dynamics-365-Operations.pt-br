---
title: Gerenciamento de estoque de loja
description: Este tópico descreve os tipos de documentos que você pode usar para gerenciar estoque.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "339225"
---
# <a name="store-inventory-management"></a>Gerenciamento de estoque de loja

[!include [banner](includes/banner.md)]

Este tópico descreve os tipos de documentos que você pode usar para gerenciar estoque.

Você pode usar os tipos de documentos a seguir para gerenciar o estoque da sua organização.

Ao trabalhar com estoque no Dynamics 365 for Retail e usar o aplicativo POS, é importante observar que o POS fornece suporte limitado para dimensões de estoque e certos tipos de item de estoque.  

A solução POS não oferece suporte para as configurações de item:
- Itens de BOM (exceto produtos de kit que utilizam alguns componentes da estrutura de BOM)
- Itens de peso variável
- Itens controlados em lotes

O aplicativo POS atualmente não oferece suporte para as seguintes dimensões de rastreamento no POS:
- Dimensão de rastreamento de lote
- Dimensão de proprietário

A solução POS fornece suporte limitado para as dimensões a seguir. Suporte limitado indica que o POS pode padronizar algumas dessas dimensões nas transações de estoque automaticamente com base na configuração do depósito/loja. As dimensões não terão suporte completo no POS na forma como têm suporte se uma transação de venda for inserida manualmente no ERP. 

- Localização
- Placa de licença (somente aplicável quando **O uso do processo de gerenciamento de depósito** tiver sido habilitado no item e no depósito da loja)
- Nº de série
- Status do estoque

> [!NOTE]
> Todas as organizações devem testar configurações do item por meio do POS em ambientes de desenvolvimento ou de teste antes de implantá-lo na produção. Testar seus itens executando transações de vendas à vista e realizadas e criando ordens de cliente (se aplicável) com o POS com seus itens. Os testes devem incluir a execução de processos de lançamento de extratos completos em seu ambiente de teste e a verificação de que não haja nenhum problema.
> Configurar itens de um modo que não tenha suporte no aplicativo POS, sem testes apropriados, pode resultar na falha do processo de lançamento de extrato na produção sem uma maneira fácil de corrigir problemas. As personalizações de parceiro ou cliente para o aplicativo também podem ser consideradas para permitir que esses processos de lançamento sejam concluídos com êxito. Se as personalizações não forem necessárias, a organização deve garantir que a configuração de produto de seus produtos seja feita de uma forma que tenha suporte no aplicativo POS/na criação de ordem/no processo de lançamento de extrato padrão.

## <a name="purchase-orders"></a>Ordens de Compra

As ordens de compra são criadas na matriz. Se um depósito de varejo for incluído no cabeçalho da ordem de compra, a ordem poderá ser recebida na loja usando o Modern POS (MPOS) ou no Cloud POS Microsoft Dynamics 365 for Retail. Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional. Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz. Na matriz, as quantidades recebidas na loja são exibidas no Dynamics 365 for Retail, no campo **Receber agora** na ordem de compra.

## <a name="transfer-orders"></a>Ordens de transferência

Uma ordem de transferência pode especificar que uma loja específica é um local de onde os itens podem ser enviados. Nesse caso, a ordem de transferência aparece na loja como solicitação de separação no MPOS ou PDV em Nuvem. Após a separação das quantidades solicitadas, elas são confirmadas e enviadas à matriz. Na matriz, as quantidades separadas na loja são exibidas no Dynamics 365 for Retail, no campo **Remeter agora** na ordem de transferência. Uma ordem de transferência pode especificar que uma loja específica é um local para onde os itens podem ser enviados. Nesse caso, a ordem de transferência aparece na loja como solicitação de recebimento no MPOS ou PDV em Nuvem. Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional. Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz. Na matriz, as quantidades recebidas na loja são exibidas no Dynamics 365 for Retail, no campo **Receber agora** na ordem de transferência.

## <a name="stock-counts"></a>Contagens de estoque

Contagens de estoque podem ser agendadas ou não agendadas. As contagens de estoque agendadas são iniciadas na matriz, que especifica os itens que devem ser contados. A matriz cria um documento de contagem que pode ser recebido na loja, onde as quantidades disponíveis em estoque reais são inseridas no MPOS ou PDV em Nuvem. Contagens de estoque não agendadas são iniciadas em uma loja, e as quantidades disponíveis em estoque reais são atualizadas no MPOS ou PDV em Nuvem. Diferente das contagens de estoque agendadas, as contagens de estoque não agendadas não têm uma lista predefinida de itens. Quando uma contagem de estoque de qualquer tipo é concluída, ela é confirmada e enviada para a matriz. Na matriz, a contagem é validada e lançada.

## <a name="inventory-lookup"></a>Pesquisa de estoque

A quantidade de produtos atual disponível para várias lojas e depósitos pode ser exibida na página de pesquisa Estoque. Além da quantidade atual disponível, as quantidades futuras disponíveis para promessa (ATP) podem ser exibidas para cada loja individual. Para fazê-lo, selecione a loja em que deseja exibir o ATP e clique em **Mostrar disponibilidade da loja**.
