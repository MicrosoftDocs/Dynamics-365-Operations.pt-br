---
title: Criar devoluções no POS
description: Este tópico descreve como iniciar devoluções para transações cash-and-carry ou ordens de clientes no aplicativo Microsoft Dynamics 365 Commerce Point of Sale (POS).
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: 53cad70e2c4866a18427157bc8b7fa1c3fda4daa
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638135"
---
# <a name="create-returns-in-pos"></a>Criar devoluções no POS

[!include [banner](includes/banner.md)]

Este tópico descreve como iniciar devoluções para transações cash-and-carry ou ordens de clientes no aplicativo Microsoft Dynamics 365 Commerce Point of Sale (POS).

> [!NOTE]
> Na versão 10.0.20 e posterior do Commerce, um novo recurso chamado **Experiência de processamento de devolução unificado para POS** está disponível. Este recurso oferece um processo de devolução consistente e unificado no POS, não importa o tipo de transação (cash-and-carry ou ordem de cliente) ou o canal original em que a ordem foi criada. Recomendamos que todas as organizações ativem este novo recurso para ajudar a melhorar a confiabilidade geral do processamento de devoluções no POS.
>
> Depois que o recurso é ativado, não é possível desativá-lo.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Processar devoluções usando a operação de transação de devolução

Recomendamos que você adicione a operação de transação de devolução ao seu [layout de tela](pos-screen-layouts.md) do POS. Em versões anteriores à versão 10.0.20 do Commerce, a operação de transação de devolução dá o devido suporte ao processamento de devoluções somente para transações cash-and-carry. Depois que você ativar o recurso **Experiência de processamento de devolução unificado para POS** na versão 10.0.20 ou posterior do Commerce, a operação de transação de devolução também dará suporte ao processamento de devoluções derivadas de ordens de clientes, como "retirada" ou "enviar à residência" que já foram faturados.

Na operação de transação de devolução, os usuários podem pesquisar uma transação cash-and-carry ou ordem de cliente para devolução inserindo um destes quatro critérios de pesquisa. Os usuários podem inserir esses critérios usando um teclado de dispositivo, teclado virtual ou scanner de código de barras.

- ID do recibo
- Número da ordem
- ID de referência de canal (também conhecido como ID de confirmação de ordem)
- ID da fatura

Se uma transação ou ordem for encontrada que corresponda aos critérios de pesquisa, a página **Produtos que podem ser devolvidos**. Lá, os usuários podem especificar os itens que estão sendo devolvidos. Eles também podem inserir as quantidades e os códigos de motivo da devolução.

Para cada linha de ordem de produtos que podem ser devolvidos, o POS exibe informações sobre a quantidade de compra original e as quantidades de quaisquer devoluções processadas anteriormente. A quantidade de devolução que um usuário insere para uma linha de ordem deve ser menor ou igual ao valor do campo **Disponível para devolução**.

![Página Produtos que podem ser devolvidos.](media/returnslist.png)

Durante o processamento de devolução, se um usuário tiver o produto físico, e o produto tiver um código de barras, o usuário pode digitalizar o código de barras para registrar a devolução. Cada digitalização do código de barras aumenta a quantidade de devolução em um item. No entanto, se o rótulo do código de barras tiver uma quantidade incorporada, essa quantidade será inserida no campo **Devolvendo agora**.

Os usuários também podem selecionar manualmente itens para devolver na página **Produtos que podem ser devolvidos** e atualizar o campo **Devolvendo agora** usando o painel de detalhes à direita.

Se a quantidade máxima disponível de **Devolvendo agora** estiver sendo especificada para uma transação, o usuário pode selecionar a operação **Selecionar todos** na barra de aplicativos de POS para definir a quantidade máxima que pode ser devolvida em todas as linhas.

Para cada linha que tiver uma quantidade **Devolvendo agora**, o usuário deve selecionar um código de motivo de devolução usando o painel de detalhes. Para devoluções de transações cash-and-carry, os motivos de devolução são configurados como códigos de informação no perfil de funcionalidade da loja. Para devoluções de ordens de cliente, os motivos de devolução são configurados na página **Códigos de motivo de devolução** na sede do Dynamics 365 Commerce.

Depois que a quantidade de devolução e o código de motivo tiverem sido definidos para cada item que deve ser devolvido, o usuário pode selecionar a operação **Devolver** na barra de aplicativos de POS para proceder com o processamento. A página da transação do POS aparece, na qual os itens que podem ser devolvidos selecionados na página anterior foram adicionados ao carrinho. As quantidades de **Devolvendo agora** para os itens aparecem como linhas de quantidade negativa na transação, e o reembolso total é calculado.

Os usuários podem adicionar linhas a uma transação de devolução se eles estiverem criando uma ordem de troca. Os usuários também podem adicionar mais itens de devolução ad-hoc a uma transação de devolução usando a operação **Devolver produto** para uma linha de vendas de quantidade positiva selecionada que foi adicionada.

> [!NOTE]
> A operação **Devolver produto** no POS não oferece qualquer validação contra qualquer transação original e permite que qualquer produto seja devolvido. Portanto, recomendamos que somente usuários autorizados tenham autorização para realizar esta operação, ou que uma substituição de gerente seja obrigatória se esta operação for usada.

Se um reembolso for necessário no checkout, as organizações podem configurar as [políticas de pagamento de devolução](refund_policy_returns.md) que limitam os métodos de pagamento que podem ser usados para reembolsar os clientes. Se a transação original tiver sido paga usando um cartão de crédito, dependendo do processador de pagamento e do sistema de configuração, os usuários podem ter a opção de [emitir um reembolso ao cartão original](dev-itpro/linked-refunds.md). Neste caso, o reembolso podem ser processados sem exigir que o cliente passe o cartão de crédito novamente. O token de pagamento original é usado para emitir o reembolso.

## <a name="other-return-options-in-pos"></a>Outras opções de devolução no POS

Quando o recurso **Experiência de processamento de devolução unificada no POS** estiver ativo, os usuários também podem usar a operação **Exibir diário** no POS para iniciar uma devolução para uma transação cash-and-carry ou uma ordem de cliente. Então, eles também podem selecionar uma transação no diário e então selecionar a operação **Devolução** na barra de aplicativos do POS. Esta operação estará disponível apenas se houver linhas que podem ser devolvidas na ordem. Isso inicia a mesma experiência de usuário que a operação **Transação de devolução**.

Os usuários também podem usar a operação **Recuperar ordem** no POS para pesquisar e recuperar ordens de clientes. (Esta operação não pode ser usada para transações cash-and-carry). Neste caso, depois que uma ordem de cliente é selecionada, a operação **Devolução** na barra de aplicativos do POS pode ser usada para iniciar uma devolução para a ordem de cliente. Esta operação estará disponível apenas se houver linhas que podem ser devolvidas na ordem. Isso inicia a mesma experiência de usuário que a operação **Transação de devolução** ou **Exibir diário**.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>As ordens de devolução são postadas na sede do Commerce como pedidos de venda. 

Quando o recurso **Experiência de processamento de devolução unificada no POS** for ativado, todas as devoluções que forem criadas no POS serão gravadas na sede do Commerce como pedidos de venda que têm linhas negativas. Em versões anteriores ao Commerce 10.0.20, os usuários podem escolher se as ordens de devolução devem ser postadas como pedidos de venda que têm linhas negativas, ou se devem ser ordens de devolução que são criadas por meio do processo de autorização de devolução de mercadoria (RMA). 

No recurso **Experiência de processamento de devolução unificado no POS**, a opção de usar o processo de RMA para criar devoluções no POS foi suspenso. Depois da ativação deste recurso, todas as devoluções serão criadas como ordens de vendas que tenham linhas negativas.

## <a name="offline-return-processing-improvements"></a>Melhorias do processamento de devoluções offline

Na maioria dos casos, quando uma devolução é processada no POS, o sistema tenta fazer uma chamada de serviço em tempo real (RTS) para a sede do Commerce para validar as quantidades atuais que estão disponíveis para devolução. Esta validação ajuda a evitar cenários fraudulentos em que um cliente tenta devolver o mesmo item em mais de um local.

Para lidar com situações em que a chamada de RTS não pode ser feita devido a problemas de rede ou conectividade, um processo foi implementado para sincronizar periodicamente os dados da quantidade da devolução na sede do Commerce com o banco de dados do canal de uma loja. Este rastreamento de devolução no canal ajuda a garantir que as quantidades **Disponíveis para devolução** que são mostradas no POS como razoavelmente precisas, mesmo quando o POS está offline. Isso também garante que o POS possa continuar validando as informações no canal para ajudar a evitar devoluções fraudulentas.

Para usar o processo de devolução offline da forma adequada, as organizações devem agendar o trabalho em lote **Atualizar quantidades para devolução** na sede do Commerce para que o processo seja executado frequentemente. Recomendamos que esse trabalho seja executado com a mesma frequência que o trabalho P que extrai novas transações dos canais do Commerce para a sede do Commerce.

O trabalho **Atualizar quantidades para devolução** calcula a quantidade que está disponível para devolução para todas as ordens de venda que forem encontradas na sede do Commerce. Em seguida, os dados que o trabalho calcula devem ser enviados aos bancos de dados do canal para que os canais da loja possam ser atualizados. O trabalho de distribuição **Quantidades para devolução** (1200) é usado para esta finalidade. Como os dados sobre a quantidade para devolução são sincronizados a partir da sede do Commerce, se uma devolução for processada no POS e não for possível fazer a chamada RTS, o POS pode usar as informações de devolução no canal para validar as quantidades **Disponíveis para devolução** para uma determinada linha de venda.

Quando não for possível fazer chamadas RTS, e o POS estiver usando dados no canal para validação de devolução, uma mensagem de aviso informará os usuários que eles estão criando uma devolução "offline". Portanto, eles estarão cientes de que a quantidade **Disponível para devolução** que é mostrada no POS pode estar desatualizada e ser imprecisa, dependendo de quando o trabalho **Atualizar quantidades para devolução** foi processada e sincronizada com o canal.

Por exemplo, um cliente processou recentemente uma devolução para uma linha de ordem em outro canal, mas esses dados ainda não foram sincronizadas com os bancos de dados do canal por meio do trabalho **Atualizar quantidades para devolução**. Em seguida, o cliente vai para outra loja e tenta devolver o mesmo item de novo. Neste caso, se a loja não puder fazer a chamada RTS para a sede do Commerce para obter os dados de devolução em tempo real, o POS permitirá que o item seja devolvido de novo. No entanto, o usuário é avisado de que as informações que estão sendo usadas para validar a devolução podem estar desatualizadas. A mensagem que o usuário recebe é a única mensagem de aviso. Ela não evita que o usuário continue o processamento da devolução.

Se as informações no canal não estiverem atualizadas por algum motivo e uma devolução offline for processada para uma quantidade que exceda a quantidade real **Disponível para devolução**, um erro pode ser gerado quando a postagem da declaração for executada para criar a transação na sede do Commerce.

> [!NOTE]
> Quando o recurso **Experiência de processamento de devolução unificado no POS** é ativado, novos recursos opcionais que permitem a validação de devoluções de produto serializadas tornam-se disponíveis. Para mais informações, consulte [Devolver produtos controlados por número de série no Ponto de Venda (POS)](POS-serial-returns.md).

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial

Esse recurso garante que, quando uma ordem é devolvida com várias faturas, os impostos serão basicamente iguais ao valor do imposto cobrado originalmente.
1.  Acesse o espaço de trabalho **Gerenciamento de recursos** e procure **Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial**.
2.  Selecione **Habilitar o cálculo de imposto apropriado para devoluções com quantidade parcial** e clique em **Habilitar**.


## <a name="additional-resources"></a>Recursos adicionais

[Devolver produtos controlados por número de série no Ponto de Venda (POS)](POS-serial-returns.md)

[Devolução vinculadas de transações aprovadas e confirmadas](dev-itpro/linked-refunds.md)

[Criar e atualizar uma política de devolução e reembolso para um canal](refund_policy_returns.md)

[Configurações visuais da interface do usuário de PDV](pos-screen-layouts.md)
