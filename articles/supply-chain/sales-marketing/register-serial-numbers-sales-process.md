---
title: Como trabalhar com itens serializados
description: Este tópico explica como você pode registrar números de série em guias de remessa ou em faturas durante o processo de vendas. Essa funcionalidade será útil se uma empresa quiser capturar números de série para fins de serviço e de garantia, e não precisa manter os números de série no estoque do recebimento até a saída.
author: omulvad
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResTrackingDimensionGroup, InventTrackingRegisterTrans, SalesEditLines, SalesTable, InventSerial
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 28931
ms.assetid: 5d39630f-607e-492b-8c1e-790ca53effa0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 989dcca499f6d27ae9680f184978d5500397fa57
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422110"
---
# <a name="working-with-serialized-items"></a>Como trabalhar com itens serializados

[!include [banner](../includes/banner.md)]

Este tópico explica como você pode registrar números de série em guias de remessa ou em faturas durante o processo de vendas. Essa funcionalidade será útil se uma empresa quiser capturar números de série para fins de serviço e de garantia, e não precisa manter os números de série no estoque do recebimento até a saída.

Muitas empresas desejam apenas capturar números de série para fins de serviço e de garantia, e não precisam manter os números de série no estoque do recebimento até a saída. Nessas situações, é possível registrar os números de série nas guias de remessa ou nas faturas quando o produto for vendido. Se os produtos forem devolvidos, você poderá rastrear um produto até uma fatura para determinar se vendeu o produto e se as obrigações de serviço ou de garantia estão válidas.

Você deve habilitar números de série para o processo de vendas no grupo de dimensões de rastreamento, selecionando a opção **Ativo no processo de venda** na página **Grupos de dimensões de rastreamento**. Os seguintes eventos ocorrem no Supply Chain Management:
-   Na Guia Rápida **Números de série**, a opção **Controle de números de série** é selecionada. Quando essa opção estiver selecionada, você deverá registrar um número de série para cada item na guia de remessa ou fatura.
-   Todas as seleções no grupo de dimensões de rastreamento para números de série estão desmarcadas, exceto a opção **Saída em branco permitida**. Você pode selecionar a opção **Saída em branco permitida** para substituir o controle do número de série e permitir que os produtos sejam embalados e faturados sem registrar números de série.

## <a name="when-do-i-register-serial-numbers-during-the-sales-process"></a>Quando devo registrar números de série durante o processo de vendas?
É possível registrar números de série na guia de remessa para uma ordem de venda ou na fatura. Quando você prepara uma fatura para um item serializado enviado junto com uma guia de remessa, pode selecionar quais dos números de série na guia de remessa devem receber fatura. A quantidade de números de série registrados não deve exceder a quantidade de itens enviados. Se você estiver criando uma fatura parcial, é possível selecionar menos itens de série que foram registrados na guia de remessa. Quando você imprime uma guia de remessa ou uma fatura, os números de série que foram registrados são incluídos.

## <a name="can-i-enter-serial-numbers-by-scanning-them-or-do-i-have-to-type-them"></a>Posso inserir os números de série digitalizando-os ou preciso digitá-los?
Você pode digitalizar ou digitar números de série. Quando você usa um scanner, o modo de digitalização determina se os números de série são adicionados ou removidos da lista de números de série na fatura ou na guia de remessa. Se você deseja verificar números de série usando, por exemplo, um scanner de código de barras manual, configurar o scanner para enviar um comando Enter ou TAB após o número de série. Esse comando indicará o final do fluxo de dados. Caso contrário, você deve pressionar Enter ou TAB no teclado após ter digitalizado cada número de série.

## <a name="if-i-enable-serial-numbers-for-the-sales-process-do-i-have-to-register-all-serial-numbers-for-all-items"></a>Se eu habilitar números de série para o processo de vendas, tenho de registrar todos os números de série para todos os itens?
A configuração do grupo de dimensões de rastreamento atribuiu ao produto determina se os números de série deverão ser registrados para todos os itens em uma guia de remessa ou fatura. Ao habilitar números de série para o processo de vendas, a opção **Controle de número de série** é selecionada automaticamente. Então, você deve registrar um número de série, ou registrar um registro em branco para um número ilegível, para cada item na guia de remessa ou fatura. Se não deseja exigir um número de série para cada item, selecione a opção **Saída em branco permitida** no grupo de dimensões de rastreamento atribuído ao item. Você poderá registrar menos números de série do que a quantidade de itens que estão sendo enviados. Caso você registre mais números de série do que a quantidade de itens que estão sendo enviadas, não poderá lançar a guia de remessa ou a fatura.

## <a name="can-i-register-serial-numbers-for-partial-invoices-and-partial-shipments"></a>Posso registrar números de série para faturas parciais e remessas parciais?
Você pode criar faturas e guias de remessa parciais para ordens de venda e registrar somente os números de série para os itens que essas faturas e guias de remessa incluem. Se desejar criar uma fatura parcial e tiver mais de uma guia de remessa para a fatura, você pode incluir números de série de mais de uma guia de remessa. No entanto, só pode haver uma guia de remessa que não inclua todos os números de série. Por exemplo, se você tiver três guias de remessa e cada uma incluir dois itens serializados, não poderá criar uma fatura parcial para um item por guia de remessa.

## <a name="what-do-i-do-when-a-serial-number-isnt-readable"></a>O que fazer quando um número de série não for legível?
Se um número de série não puder ser lido ou digitalizado, você poderá criar uma linha em branco para o item, clicando em **Não está legível** na página **Números de série**. Se o número de série se tornar disponível posteriormente, você poderá atualizar a fatura ou a guia de remessa. Para obter mais informações, consulte a próxima seção, “Posso corrigir ou alterar os números de série que registrei para uma ordem de venda”?

## <a name="can-i-correct-or-change-the-serial-numbers-that-i-have-registered-for-a-sales-order"></a>Posso corrigir ou alterar os números de série registrados para uma ordem de venda?
Sim, você pode corrigir números de série se as seguintes condições forem atendidas:
-   **Faturas** – você pode alterar os números de série para os itens que ainda não foram faturados. A guia de remessa também é atualizada. Entretanto, se uma linha da ordem de venda tiver sido corrigida para registrar uma quantidade negativa, não será possível alterar números de série para a linha da ordem de venda.
-   **Guias de remessa** – não é possível corrigir parcialmente uma linha de guia de remessa que contém itens serializados. É preciso reverter a quantidade total para a linha. Se uma guia de remessa foi cancelada ou corrigida, não será necessário registrar os números de série revertidos novamente ao criar uma nova guia de remessa para os mesmos itens serializados. Os números que foram registrados serão usados.

## <a name="can-i-view-the-serial-numbers-that-were-shipped-together-with-a-specific-packing-slip-or-that-were-included-on-an-invoice"></a>Posso exibir os números de série que foram enviados junto com uma guia de remessa específica ou que foram incluídos em uma fatura?
Sim, você pode executar uma consulta na linha do diário da guia de remessa ou na linha do diário de faturas para exibir uma lista de todos os números de série que foram incluídos no documento.

## <a name="can-i-view-the-serialized-items-that-i-have-on-hand"></a>Posso exibir os itens serializados que tenho disponível?
Não, não é possível exibir os itens serializados disponíveis, pois os números de série não são registrados para itens até que eles sejam vendidos.

## <a name="can-i-register-serial-numbers-for-catchweight-items"></a>Posso registrar números de série para itens de peso variável?
Não, você não pode registrar números de série para itens de peso variável durante o processo de venda. Além disso, se um produto for configurado como um item de peso variável, você não poderá atribuir o produto a um grupo de dimensões de rastreamento configurado para usar números de série apenas durante o processo de venda.

## <a name="can-i-register-serial-numbers-at-the-retail-pos"></a>Posso registrar números de série no retail POS?

Sim, o Retail POS solicitará a inserção de um número de série quando o usuário vender um item que esteja atribuído a um grupo de dimensões de rastreamento configurado para usar números de série apenas durante o processo de venda.

## <a name="what-security-roles-are-required-in-order-to-register-serial-numbers-during-the-sales-process"></a>Quais funções de segurança são necessárias para registrar números de série durante o processo de venda?
Essa funcionalidade está disponível em todas as funções que podem atualizar as guias de remessa e as faturas de venda. Os seguintes impostos permitem que trabalhadores corrijam números de série e registrem entradas em branco para números de série que não podem ser lidos ou verificados:
-   Manter correções de número de série
-   Manter registro de números de série ilegíveis







[!INCLUDE[footer-include](../../includes/footer-banner.md)]