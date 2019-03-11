---
title: Melhorias de ponto de venda (PDV) para produtos serializados
description: Este tópico lista as melhorias feitas a produtos serializados para ajudá-lo a ganhar tempo e ser mais produtivo.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 17cd46ba9ee972c92db8950eea1cd258d67c2e92
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "346194"
---
# <a name="point-of-sale-pos-improvements-for-serialized-products"></a>Melhorias de ponto de venda (PDV) para produtos serializados

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Visão Geral

Com base nas configurações do Retail Headquarters, os produtos podem ser classificados como serializados ou não serializados. Quando os produtos são serializados, a cada item pode ser atribuído um número exclusivo que ajuda a rastrear garantias, rastrear itens e confirmar propriedade. Apesar da capacidade de fornecer números de série para produtos serializados existentes em nosso Ponto de Venda Moderno/Nuvem, algumas melhorias foram adicionadas para que os caixas ganhem tempo e sejam mais produtivos.

## <a name="pos-improvements"></a>Melhorias POS

- **Os números de série não são necessários até a finalização da compra** – Antes, um caixa que adicionava um produto serializado à transação precisava fornecer um número de série. Esse requisito era um problema em cenários do cliente, se caixas e vendedores tivessem uma oportunidade de vender produtos. Até a etapa de pagamento, os produtos geralmente eram atualizados no carrinho. Portanto, sempre que um caixa adicionava um novo produto, o sistema solicitava o número de série. A caixa de diálogo de número de série agora tem um botão **Adicionar mais tarde**. Portanto, os vendedores podem adicionar o item à transação, mas podem fornecer o número de série depois. Os associados de vendas podem adicionar e substituir rapidamente itens serializados ao carrinho, e fornecer o número de série pouco antes da finalização da compra. Se o número de série não for fornecido para o produto serializado, um vendedor que tentar concluir a transação receberá uma mensagem de erro. Esta mensagem informa se o caixa deve fornecer os números de série que faltam antes de continuar.

    Para cada item serializado onde o número de série é ignorado, aparecerá um comentário abaixo da linha da transação. Esse comentário indica que o número de série não foi fornecido para o item. Portanto, o caixa poderá encontrar rapidamente os itens que estão sem um número de série.

    Uma nova operação **Adicionar número de série** também fornece o número de série para os itens que não têm um número de série. Depois que o número de série é fornecido, ele não pode ser editado. O caixa deve anular a linha e adicionar o produto novamente.
    
- **Os números de série não são necessários para gerar ordens de cliente** – As ordens do cliente podem ser substituídas em uma loja e atendidas de outra. Um caixa que gera uma ordem de cliente não precisa fornecer o número de série. O número de série será fornecido durante a etapa de separação ou de retirada. Entretanto, um número de série deve ser fornecido para todos os itens de linha no qual o tipo de entrega **Para viagem** for selecionado. Caso contrário, a transação não poderá ser concluída.
- **Produtos serializados não são agregadas na tela da transação** – A configuração **Agregar produtos** no grupo de campos **Terminal** na página **Perfil de funcionalidade** permite que você agregue os mesmos produtos não serializados na tela da transação. Quando os mesmos produtos são agregados, é mais fácil visualizá-los na grade da transação. Porém, como números de série geralmente são exclusivos e os vendedores não precisam inserir números de série até a finalização da compra, a configuração **Agregar produtos** não se aplica aos produtos serializados. Portanto, os produtos serializados não serão agregados na tela da transação, se a configuração **Agregar produtos** for selecionada.
- **Capacidade de pesquisar os diários por número de série** – os diários agora também podem ser pesquisados por números de série. Para isso, abra a operação "Diários" e pressione o botão "Pesquisa avançada" na barra de aplicativos. Usando o botão “Adicionar filtro”, um filtro pode ser aplicado para pesquisar também os números de série.
