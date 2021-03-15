---
title: Criar uma ordem de compra
description: Este tópico mostra como criar uma ordem de compra manualmente.
author: RichardLuan
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a3da6b70054fac878ba6266017bffe75f634f61
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016619"
---
# <a name="create-a-purchase-order"></a>Criar uma ordem de compra

[!include [banner](../../includes/banner.md)]

Este tópico mostra como criar uma ordem de compra manualmente. É mais comum para ordens de compra serem criadas automaticamente como resultado de um planejamento mestre, entrega direta e outros processos. As ordens de compra geralmente são criadas com um agente de compra. O exemplo mostrado aqui pode ser usado na empresa de dados de demonstração USMF usando os valores que são sugeridos nas notas para várias etapas.


## <a name="create-the-purchase-order-header"></a>Criar o cabeçalho da ordem de compra
1. Vá para **Painel de navegação > Módulos > Compras e fornecimento > Ordens de compra > Todas as ordens de compra**.
2. Selecione **Novo**.
3. Selecione conta de fornecedor **US-101**. Quando você seleciona um fornecedor, os detalhes do registro de fornecedor como endereço, a conta de nota fiscal, condições de entrega, e o modo de entrega como os valores padrão serão copiados no cabeçalho da ordem. É possível alterar esses valores a qualquer momento.  
4. Expanda a seção **Geral**.

    - O campo **Site** com o campo **Depósito** especifica qual as mercadorias ou serviços obtidos devem ser entregues. O endereço de entrega padrão é o site. Ambos os campos podem ser preenchidos com valores configurados para o fornecedor selecionado, ou você pode especifica-los manualmente.  
    - O campo **Data de entrega** é usado para especificar quando mercadorias e serviços obtidos precisam ser entregues. Você pode especificar uma única data de entrega da ordem, ou as linhas da ordem individuais podem ter datas de dados de entrega exclusivos. Se a data de entrega especificada aqui não puder ser atendida pelo produto específico ou serviços que têm um prazos de entrega mais longos, essas linhas serão criadas com uma data de entrega posterior para acomodar isso.  

5. Expanda a seção **Administração**. O campo **Autor da ordem** pode ser usado para especificar quem está posicionando a ordem. Isso pode ser conveniente de compartilhar ao fornecedor caso seja necessário contatar essa pessoa. O campo pode ser atribuído a um valor automaticamente se a conta de usuário atual estiver associada com um nome na página **Usuários**.  
6. Selecione **OK**. O cabeçalho da ordem agora foi criado. Ao trabalhar com linhas de ordem de compra, apenas um resumo das informações de cabeçalho será exibido. Se você precisar exibir o restante das informações, selecione **Cabeçalho**.  

## <a name="add-a-purchase-order-line"></a>Adicionar uma linha de ordem de compra
1. Selecione uma **Linha de ordem de compra**.
2. Selecione **Dimensões**. Os produtos podem estar em grades que são diferenciadas por dimensões, como tamanho, cor ou estilo. O produto também pode ser configurado para usar dimensões de armazenamento, como o site e o depósito. Também existem dimensões de rastreamento opcionais, como os números de lote e de série. Para aumentar a eficiência de entrada de ordem, você pode adicionar os campos de dimensão que você geralmente usa diretamente na grade da ordem.  
3. Marque a caixa de seleção **Cor**. Opcional: Se você selecionar o campo **Salvar configuração**, as dimensões escolhidas também serão mostradas na grade da linha da ordem na próxima vez que você abrir a página da ordem de compra.  
4. Selecione **OK**.
5. No campo **Número de item**, selecione **T0004**.

    - As linhas de ordem são criadas para produtos e serviços especificando um número de item ou como despesas, especificando uma categoria de aquisição. 
    - O campo da categoria **Compras** é usado para adicionar as linhas em que os itens adquiridos são fixos diretamente, em vez de ir ao estoque. Isso significa que se você precisar de despesas de uma compra você pode fazer isso criando uma linha da ordem de compra que especifica uma categoria de aquisição, em vez de criar uma linha com um número de item. Os itens também podem ser associados a uma categoria de aquisição e, nesse caso, a categoria de aquisição é mostrada como somente informativa.  

6. No campo **Cor**, insira ou selecione um valor. Os campos **Site** e **Depósito** normalmente são preenchidos com valores do cabeçalho da ordem, mas é possível substituir os campos se algumas linhas precisarem ser emitidas em locais diferentes.  
7. No campo **Quantidade.**, insira um número

    - Selecione a quantidade que você deseja comprar. O campo **Quantidade** é preenchido automaticamente com a quantidade mínima de ordens para os produtos, se este for configurado, ou com o valor de 1.  
    - O campo **Unidade** indica a unidade de medida para a quantidade solicitada. Normalmente, a unidade é fornecida automaticamente da unidade de compra nos dados mestre do produto, mas você pode alterá-la.  
    - O campo **Preço unitário** normalmente contém um valor de um contrato de compra ou de um contrato comercial. É possível alterar o preço unitário das linhas da ordem individuais por exemplo, se um preço for exclusivamente negociado com o fornecedor.  
    - O campo **Desconto** representa um valor de desconto por unidade. Esse desconto reduz consequentemente o preço unitário por desconto. O desconto é fornecido geralmente automaticamente a partir dos contratos de compra ou de contratos comerciais, mas é possível substituir as linhas individuais se os descontos forem negociados de forma exclusiva ao fornecedor.  
    - Um percentual de desconto pode ser inserido para reduzir o valor líquido da linha de acordo. A porcentagem de desconto é fornecida geralmente automaticamente a partir dos contratos de compra ou de contratos comerciais, mas é possível substituir as linhas individuais se as porcentagens dos descontos forem negociados de forma exclusiva ao fornecedor.  
    - O valor no campo **Valor líquido** é calculado dos outros campos da linha que inclui a quantidade, o preço unitário, o desconto e a porcentagem de desconto. É possível alterar o Valor líquido, mas então os campos **Preço Unitário**, **Desconto** e **Porcentagem de desconto** ficarão vazios e quando você postar na linha, o valor postado será proporcional ao valor líquido. Geralmente, o campo **Valor líquido** é apenas usado para exibir o valor líquido da linha.  

8. Expanda a seção **Detalhes da linha**.
9. Selecione a guia **Entrega**. Uma data de entrega exclusiva pode ser atribuída a cada linha da ordem. A data é herdada do campo no cabeçalho da ordem de compra, mas você pode alterá-lo.  

## <a name="review-order-totals"></a>Rever totais da ordem
1. Selecione **Totais**.

    - Caso não veja a ação **Totais**, selecione a guia **Ordem de Compra** no Painel de Ações.  
    - Esta caixa de diálogo mostra os totais da ordem inteira.  
    - O campo **Seleção** permite que você altere a base de como os totais são calculados. Por exemplo, você pode escolher a **Quantidade de recebimento de produtos** para mostrar os totais relacionados à quantidade de produtos que foram recebidos, ou a **Quantidade encomendada** para mostrar o valor dos produtos que foram encomendados.  

2. Selecione **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]