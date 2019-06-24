---
title: Gerenciamento de estoque de loja
description: Este tópico descreve os tipos de documentos que você pode usar para gerenciar estoque.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
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
ms.openlocfilehash: 551a8408aa730bc1916f1c57b7cfd773966ce8bf
ms.sourcegitcommit: e2fb0846fcc6298050a0ec82c302e5eb5254e0b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2019
ms.locfileid: "1606794"
---
# <a name="store-inventory-management"></a>Gerenciamento de estoque de loja

[!include [banner](includes/banner.md)]

Ao trabalhar com estoque no Dynamics 365 for Retail e usar o aplicativo POS, é importante observar que o POS fornece suporte limitado para dimensões de estoque e certos tipos de item de estoque.

A solução POS não oferece suporte para as configurações de item:

- Itens de BOM (exceto produtos de kit que utilizam alguns componentes da estrutura de BOM)
- Itens de peso variável
- Itens controlados em lotes

O aplicativo POS atualmente não oferece suporte para as seguintes dimensões de rastreamento no POS:

- Dimensão de rastreamento de lote
- Dimensão de proprietário

A solução POS fornece suporte limitado para as dimensões a seguir. Suporte limitado indica que o POS pode padronizar algumas dessas dimensões nas transações de estoque automaticamente com base na configuração do depósito/loja. As dimensões não terão suporte completo no POS na forma como têm suporte se uma transação de venda for inserida manualmente no ERP. 

- **Local do depósito** – os usuários não terão a habilidade de gerenciar o recebimento local de depósito para itens recebidos em um armazenamento de loja quando a loja não foi configurada para usar o processo de gerenciamento de depósito. Um local de recebimento padrão definido no depósito de armazenamento será usado para os itens. Se o processo de gerenciamento de depósito estiver habilitado para a loja, o suporte limitado que pede ao usuário para escolher o local de recebimento do recibo por completo será disparado. Itens vendidos da loja sempre serão vendidos para fora do local de varejo padrão como definido na configuração de depósito de loja. A localização para gerenciar o estoque de devolução pode ser controlada por meio da definição do local de devolução padrão no depósito de loja ou baseado nos códigos de motivo de devolução na política de local de devolução.
- **Placa de licença** – Placas de licença só são aplicáveis quando **Usar processo de gerenciamento de depósito** tiver sido habilitado no item e no depósito da loja. Em PDV, se o estoque é recebido em um depósito de loja onde o processo de gerenciamento de depósito foi ativado, e o local escolhido para receber o item é vinculado ao perfil de local que requer controle de placa de licença, a aplicação de PDV aplicará, sistematicamente, uma placa de licença à linha de recebimento. Os usuários no PDV não terão a habilidade de mudar ou gerenciar esses dados de placa de licença. Se o gerenciamento de placas de licença é necessário, sugere-se que o armazenamento use o aplicativo móvel WMS ou o cliente ERP de back office para gerenciar o recibo desses itens.
- **Número de série** – A aplicação de PDV tem suporte limitado para um único número de série para ser registrado em uma linha de vendas de transação para pedidos criados no PDV em itens de série. Esse número de série não é validado contra números de série registrados já no estoque. Se uma ordem de venda é criada no canal de call center ou preenchido por meio do ERP e vários números de série são registrados a uma única linha de vendas durante o processo de preenchimento no ERP, esses números de série não poderão ser aplicados ou validados se uma devolução é processada no PDV para esses pedidos.
- **Status de estoque** – Para itens que usam o processo de gerenciamento de depósito e requerem um status de estoque, esse campo de status não pode ser definido ou alterado com a solicitação de PDV. O status de estoque padrão como definido na configuração de depósito de armazenamento será usado quando os itens são recebidos em estoque.

> [!NOTE]
> Todas as organizações devem testar configurações do item por meio do POS em ambientes de desenvolvimento ou de teste antes de implantá-lo na produção. Testar seus itens executando transações de vendas à vista e realizadas e criando ordens de cliente (se aplicável) com o POS com seus itens. Os testes devem incluir a execução de processos de lançamento de extratos completos em seu ambiente de teste e a verificação de que não haja nenhum problema.
>
> Configurar itens de um modo que não tenha suporte no aplicativo POS, sem testes apropriados, pode resultar na falha do processo de lançamento de extrato na produção sem uma maneira fácil de corrigir problemas. As personalizações de parceiro ou cliente para o aplicativo também podem ser consideradas para permitir que esses processos de lançamento sejam concluídos com êxito. Se as personalizações não forem necessárias, a organização deve garantir que a configuração de produto de seus produtos seja feita de uma forma que tenha suporte no aplicativo POS/na criação de ordem/no processo de lançamento de extrato padrão.

## <a name="purchase-orders"></a>Ordens de Compra

As ordens de compra são criadas na matriz. Se um depósito de varejo for incluído no cabeçalho da ordem de compra, a ordem poderá ser recebida na loja usando o Modern POS (MPOS) ou no Cloud POS no Microsoft Dynamics 365 for Retail por meio da operação **Separação/Recebimento**. Após as quantidades recebidas na loja serem inseridas no campo **Receber agora** no PDV para o documento de ordem de compra, ele pode ser salvo localmente ou confirmado. Salvar os dados localmente não tem efeito no inventário de estoque. A economia deve ser feita somente se o usuário não estiver pronto para lançar o recebimento na matriz e não precisar apenas de uma maneira de armazenar temporariamente os dados inseridos anteriormente nos dados **Receber agora**. Isso salva os dados Receber agora localmente para a base de dados do canal do usuário. Depois que o documento é processado usando a opção **Confirmar**, os dados **Receber agora** são enviados a matriz e o recebimento de ordem de compra será lançado. 

## <a name="transfer-orders"></a>Ordens de transferência

Um ordem de transferência pode especificar que um armazenamento específico é o local onde os itens podem ser enviados a partir de ou no local onde o estoque será recebido. Se o usuário do PDV é o depósito de envio para uma ordem de transferência, eles poderão inserir as quantidades de **Enviar agora** do PDV. Os dados inseridos pelo envio de remessa podem ser salvos localmente ou confirmada. Quando salvo localmente, nenhuma atualização é feita no documento de ordem de transferência na matriz. A economia deve ser feita somente se o usuário não estiver pronto para lançar o envio na matriz e não precisar de uma maneira de armazenar temporariamente os dados inseridos anteriormente nos dados **Enviar agora**. Depois que a loja está pronta para confirmar a remessa, a opção **Confirmar** deve ser marcada. Isso lança a remessa de ordem de transferência na matriz de modo que o depósito de recebimento possa receber agora nele. 

Se o usuário do PDV é o depósito de recebimento para uma ordem de transferência, eles poderão inserir as quantidades de **Receber agora** do PDV. Os dados inseridos pelo recebimento de remessa podem ser salvos localmente ou confirmada. A economia deve ser feita somente se o usuário não estiver pronto para lançar o recebimento na matriz e não precisar de uma maneira de armazenar temporariamente os dados inseridos anteriormente nos dados **Receber agora**. Isso salva os dados Receber agora localmente para a base de dados do canal do usuário. Depois que o documento é processado usando a opção **Confirmar**, os dados **Receber agora** são enviados a matriz e o recebimento de ordem de transferência será lançado. É importante observar que o armazenamento de recebimento só estará restrito ao poder enviar quantidades de recebimento que são iguais ou inferiores que as quantidades enviadas. Uma tentativa de receber as quantidades em uma ordem de transferência que não tiver sido enviada anteriormente resultará em erros e o recebimento não será confirmado na matriz.

## <a name="stock-counts"></a>Contagens de estoque

Contagens de estoque podem ser agendadas ou não agendadas. As contagens de estoque agendadas são iniciadas na matriz, que especifica os itens que devem ser contados. A matriz cria um documento de contagem que pode ser recebido na loja, onde as quantidades disponíveis em estoque reais são inseridas no MPOS ou PDV em Nuvem. Contagens de estoque não agendadas são iniciadas em uma loja, e as quantidades disponíveis em estoque reais são atualizadas no MPOS ou PDV em Nuvem. Diferente das contagens de estoque agendadas, as contagens de estoque não agendadas não têm uma lista predefinida de itens. Quando uma contagem de estoque de qualquer tipo é concluída, ela é confirmada e enviada para a matriz. Na matriz, a contagem é validada e lançada como uma etapa separada.

## <a name="inventory-lookup"></a>Pesquisa de estoque

A quantidade de produtos atual disponível para várias lojas e depósitos pode ser exibida na página de pesquisa **Estoque**. Além da quantidade atual disponível, as quantidades futuras disponíveis para promessa (ATP) podem ser exibidas para cada loja individual. Para fazê-lo, selecione a loja em que deseja exibir o ATP e clique em **Mostrar disponibilidade da loja**.
