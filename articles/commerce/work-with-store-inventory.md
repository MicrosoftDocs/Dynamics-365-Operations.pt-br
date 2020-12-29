---
title: Gerenciamento de estoque de loja
description: Este tópico descreve os tipos de documentos que você pode usar para gerenciar estoque.
author: rubencdelgado
manager: AnnBe
ms.date: 05/15/2020
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
ms.openlocfilehash: a3e6450c358d12dc62c2ffa20e7ff529be86bbe5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410203"
---
# <a name="store-inventory-management"></a>Gerenciamento de estoque de loja

[!include [banner](includes/banner.md)]

Ao trabalhar com estoque no Microsoft Dynamics 365 Commerce e usar o aplicativo de ponto de venda (PDV), é importante saber que o PDV fornece suporte limitado para algumas dimensões de estoque e alguns tipos de item de estoque. O aplicativo de PDV não oferece suporte a todo o intervalo de recursos de configuração de itens que está disponível nas opções de configuração de item no Dynamics 365 Supply Chain Management.

A solução de PDV atualmente não oferece suporte às seguintes dimensões de produto e configurações de item:

- Dimensão de produto de configuração e itens de lista de materiais (BOM) (exceto produtos do kit de varejo, que usam alguns componentes da estrutura da BOM)
- Itens de peso variável
- Itens controlador por dimensão de versão do produto

O aplicativo PDV atualmente não oferece suporte para as seguintes dimensões de rastreamento no PDV:

- Dimensão de rastreamento de lote
- Dimensão de proprietário

PDV fornece suporte limitado para as dimensões a seguir. Em outras palavras, PDV deve inserir automaticamente algumas dessas dimensões nas transações de estoque, com base na configuração do depósito ou configuração de loja. As dimensões não terão suporte completo na PDV na forma como têm suporte se uma transação de venda for inserida manualmente no Commerce headquarters. 

- **Local do depósito** – quando eles usam as novas operações de PDV [Operação de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e [Operação de saída](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), os usuários podem selecionar uma localização de estoque de depósito para receber ou enviar itens da ordem de transferência de saída. Se usarem a operação **Separação e recebimento** obsoletas, o suporte a gerenciamento de local limitado estará disponível para o recebimento e a remessa de transferências de saída. Esse suporte só estará disponível se a opção **Usar processo de gerenciamento de depósito** estiver ativada para o item e para o depósito de armazenamento. Uma localização de estoque não pode ser usada no momento com a operação **Contagem de estoque** ou de **Pesquisa de estoque**.
- **Placa de licença** – Placas de licença só são aplicáveis quando a opção **Usar processo de gerenciamento de depósito** tiver sido habilitada no item e no depósito da loja. No PDV, se o estoque for recebido em um depósito de armazenamento usando a operação **Operação de entrada** ou a operação **Separação e recebimento** em que o processo de gerenciamento de depósito foi ativado, e se o local selecionado para receber o item estiver vinculado a um perfil de local que requer o controle da placa de licença, o aplicativo do PDV aplicará sistematicamente uma chapa de licença à linha de recebimento. Os usuários da PDV não podem alterar ou gerenciar os dados da placa de licença. Se o gerenciamento de placas de licença é necessário, recomendamos que a loja use o [aplicativo de depósito](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) ou do cliente de back-office para gerenciar o recibo desses itens.
- **Número de série** – A aplicação de PDV oferece suporte limitado para registro de um único número de série para em uma linha de transação de vendas para pedidos que são criados no PDV e incluem itens de série. Esse número de série não é validado contra números de série registrados já no estoque. Se uma ordem de venda é criada no canal de call center ou preenchida por meio do planejamento de recurso da empresa (ERP) e vários números de série são registrados em uma única linha de vendas durante o processo de preenchimento no ERP, esses números de série não podem ser aplicados ou validados se uma devolução é processada para o pedido no PDV. Quando o estoque é recebido usando a operação **Operação de entrada**, os usuários podem [registrar ou confirmar os números de série recebidos](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).
- **Status de estoque** – Para itens que usam o processo de gerenciamento de depósito e requerem um status de estoque, esse campo de status não pode ser definido ou alterado com a solicitação de PDV. O status de estoque padrão definido na configuração de depósito de armazenamento é usado quando os itens são recebidos em estoque.

> [!NOTE]
> Todas as organizações devem testar configurações do item por meio do PDV em ambientes de desenvolvimento ou de teste de implantarem essas configurações de item para ambientes de produção. Testar seus itens usando-os para realizar transações de vendas à vista e criar ordens de cliente (se aplicável) com o PDV com seus itens. Você também deve testar o cumprimento de PDV e os processos de estoque (como as operações de recebimento de estoque e de cumprimento de ordens) antes de implantar novas configurações de itens, para garantir que o aplicativo de PDV possa oferecer suporte a elas. O teste deve incluir a execução de um processo completo de lançamento do demonstrativo no seu ambiente de teste e a verificação de que nenhum problema ocorre quando as ordens desses itens são criadas e lançadas no Commerce Headquarters.
>
> Se os itens são configurados de uma forma que o aplicativo do PDV não oferece suporte e o teste apropriado não é feito, as falhas de dados que não são facilmente corrigidas ou que não são abordadas pelo suporte ao produto padrão podem ocorrer durante o processo de criação da ordem.

## <a name="purchase-orders"></a>Ordens de Compra

As ordens de compra são criadas no Commerce Headquarters. SSe o depósito da loja incluído no cabeçalho da ordem de compra ou em linhas de ordem de compra, as linhas podem ser recebidas na loja usando a operação [Operação de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) no PDV. 

## <a name="transfer-orders"></a>Ordens de transferência

As ordens de transferência podem ser criadas no Commerce Headquarters ou por meio da operação [Operação de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) ou operação [Operação de saída](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) no PDV. Use a operação de PDV **Operação de entrada** para criar uma solicitação de ordem de transferência para que o estoque seja enviado para o armazenamento de outro depósito ou local de armazenamento. Use a operação de PDV **Operação de saída** para criar uma solicitação de ordem de transferência para que o estoque enviado da loja a outro depósito ou local de loja. Depois que uma ordem de transferência para um armazenamento é criada, essa loja pode gerenciar o recebimento de estoque para a ordem de transferência por meio da operação **Operação de entrada** no PDV. Se o armazenamento estiver enviando um estoque para outro local, a operação **Operação de de saída** no PDV será usada para gerenciar o processo de remessa de saída do armazenamento.

## <a name="stock-counts"></a>Contagens de estoque

Contagens de estoque podem ser agendadas ou não agendadas. As contagens de estoque programadas são criadas por meio do Commerce Headquarters criando um documento de diário de contagem vinculado ao depósito da loja. Este diário especifica os itens que devem ser contados. Em seguida, o armazenamento pode acessar esses diários de contagem predefinidos e agir neles usando a operação **Contagem de estoque** no PDV. Os usuários do armazenamento iniciam uma contagem de estoque não programada conforme necessário quando usam a operação **Contagem de estoque** no PDV. Diferente das contagens de estoque agendadas, as contagens de estoque não agendadas não têm uma lista predefinida de itens. Quando uma contagem de estoque de qualquer tipo é concluída no PDV, ela é confirmada e enviada para a matriz. Na matriz, a contagem deve ser validada e lançada no Commerce Headquarters como uma etapa separada.

## <a name="inventory-lookup"></a>Pesquisa de estoque

A quantidade de produtos atualmente disponível para várias lojas e depósitos pode ser exibida na página de pesquisa **Estoque**. Além da quantidade atual disponível, as quantidades futuras disponíveis para promessa (ATP) podem ser exibidas para cada loja. Selecione a loja para exibir as quantidades de ATP e, em seguida, selecione **Mostrar disponibilidade da loja**. Para obter informações sobre as opções de configuração disponíveis, consulte [Calcular a disponibilidade de estoque para canais de varejo](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).
