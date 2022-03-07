---
title: Habilitar vários modos de entrega de retirada para ordens de cliente
description: Este tópico explica a funcionalidade no Microsoft Dynamics 365 Commerce que permite criar ordens de cliente para retirada em uma loja.
author: hhainesms
ms.date: 06/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: a8fec96eb644cccea3566a32f3eb2ac3c699faa412be2bb9cdb2690d34999542
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745347"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Habilitar vários modos de entrega de retirada para ordens de cliente

[!include [banner](includes/banner.md)]


Na versão 10.0.16 e posterior do Microsoft Dynamics 365 Commerce, as organizações podem definir vários modos de entrega que os compradores ou representantes de vendas podem escolher ao criar uma ordem que será retirada em uma loja. Dessa forma, as organizações podem fornecer várias opções de retirada aos seus compradores. Por exemplo, muitos varejistas agora oferecem aos compradores a opção de retirada na loja ou retirada em frente à loja para suas ordens. O Commerce oferece suporte à configuração desses diferentes modos de entrega de retirada. Os usuários podem, então, utilizá-los ao criar ordens de cliente em qualquer canal do Commerce com suporte (comércio eletrônico, call center ou loja).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Habilitar e configurar modos de entrega de retirada

Para usar esta funcionalidade, ative o recurso **Suporte para vários modos de entrega de retirada** no espaço de trabalho **Gerenciamento de recursos** na sede do Commerce. Depois que você ativar o recurso, uma configuração adicional será necessária.

No Commerce versão 10.0.15 e anteriores, as organizações podem definir somente um modo de entrega como o modo de entrega de retirada designado. Essa definição é feita na página **Parâmetros do Commerce**. Na versão 10.0.16 e posteriores, ao ativar o recurso **Suporte para vários modos de entrega de retirada**, o modo de entrega definido anteriormente como o modo de entrega de retirada na página **Parâmetros do Commerce** será copiado de forma automática para a nova configuração de modos de entrega de retirada.

![Modos de entrega de retirada na página Parâmetros do Commerce.](media/multiplepickupparameter.png)

Depois de ativar o recurso **Suporte para vários modos de entrega de retirada**, você poderá definir vários modos de entrega de retirada na grade **Modo de entrega de retirada** na FastTab **Modos de entrega** na guia **Ordens de cliente** da página **Parâmetros do Commerce**.

Os campos **Executar modo de entrega** e **Modo eletrônico de entrega**, e a opção **Mostrar somente opções de modo de transportadora para ordens de remessa**, foram realocados para essa FastTab.

Antes de configurar modos de entrega de retirada adicionais, você deve definir os modos de entrega. Na página **Modos de entrega** na sede do Commerce, adicione os modos de entrega que devem ser considerados modos de entrega de retirada. Verifique se toda a configuração foi concluída. Por exemplo, se você está oferecendo a retirada em frente à loja como uma opção de entrega para seus compradores online para determinadas lojas, será necessário criar um novo modo de entrega para esta finalidade. Você pode criar este modo de entrega usando "retirada em frente à loja" como a descrição. Em seguida, você procurará garantir que o modo de entrega "retirada em frente à loja" seja mapeado para todos os canais de comércio que podem oferecê-lo, inclusive lojas online que podem oferecer essa opção e os canais de loja individuais que oferecerão esse método de atendimento. Os modos de entrega também devem estar vinculados aos produtos. Neste exemplo, se há determinados produtos que não podem ser entregues usando "retirada em frente à loja", será necessário garantir que esses itens sejam excluídos. Quando terminar de adicionar novos modos de entrega, execute o trabalho **Processar modos de entrega** para criar os relacionamentos entre modo de entrega, canais e itens. Quando o trabalho for concluído, abra a página **Agenda de distribuição** na sede do Commerce e execute o trabalho de distribuição **1120** para garantir que os bancos de dados relevantes do canal do Commerce sejam atualizados com a nova configuração de modo de entrega.

![Exemplo de uma configuração de modo de entrega para retirada em frente à loja.](media/pickupmodes.png)

Depois de definir os modos de entrega de retirada adicionais, adicione-os à grade **Modo de entrega de retirada** na página **Parâmetros do Commerce**. Em seguida, execute os trabalhos de distribuição adequados para atualizar os bancos de dados relevantes do canal do Commerce com a alteração de configuração.

> [!NOTE]
> Além do modo de entrega de retirada existente que é copiado para a grade **Modo de entrega de retirada** quando você ativa o recurso **Suporte para vários modos de entrega de retirada**, para cada configuração de modo de entrega de retirada adicional criada, será necessário configurar novos modos de entrega. Quando você adiciona modos de entrega à grade **Modo de entrega de retirada**, o Commerce valida se as linhas de venda abertas e ativas já os usam. Se forem encontradas linhas de venda abertas, você receberá uma mensagem de erro. Os modos de entrega não são considerados modos de entrega de retirada até que todas as linhas de venda abertas que os usam tenham sido fechadas (faturadas ou canceladas).

> [!IMPORTANT]
> Depois que você definir mais de um modo de entrega de retirada na página **Parâmetros do Commerce**, o recurso **Suporte para vários modos de entrega de retirada** se tornará obrigatório e não poderá mais ser desativado. Se for necessário desativá-lo, remova todos os modos de entrega de retirada, exceto um, da grade **Modo de entrega de retirada**. Quando somente um modo de entrega de retirada estiver definido, o recurso não será mais considerado obrigatório e poderá ser desativado.

### <a name="e-commerce-site-configurations"></a>Configurações de sites de comércio eletrônico

Quando o recurso **Suporte para vários modos de entrega de retirada** está ativado, os seguintes módulos nas páginas de comércio eletrônico mostram os novos modos de entrega de retirada, conforme configurado:

- Caixa de compra
- Seletor de lojas
- Carrinho
- Informações de separação
- Confirmação da ordem
- Detalhes da Ordem

Nenhuma etapa adicional é necessária nas páginas de comércio eletrônico para disponibilizar os modos de entrega de retirada.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Trabalhar com vários modos de entrega de retirada

Quando vários modos de entrega de retirada estiverem disponíveis para um canal, uma experiência aprimorada será fornecida aos clientes quando eles comprarem produtos que serão retirados. 

- Em canais de comércio eletrônico, os compradores podem selecionar qualquer modo de entrega de retirada válido disponível. Por exemplo, um varejista define dois modos de entrega de retirada (retirada na loja e retirada em frente à loja), ambos são configurados na grade **Modo de entrega de retirada** e ambos são válidos para o canal de atendimento de ordens e o produto que um comprador está adquirindo no momento. Nesse caso, o comprador pode selecionar o modo de entrega de retirada de sua preferência. O modo de entrega de retirada selecionado passa a ser o modo de entrega vinculado à linha da ordem de venda quando a ordem é criada na sede do Commerce.

    ![Selecionar uma opção de retirada no comércio eletrônico.](media/pickupecommerce.png)

- Em canais de loja, se uma ordem de cliente para retirada for criada por meio do aplicativo de ponto de venda (PDV), o representante de vendas será solicitado a escolher entre os modos de entrega de retirada disponíveis, caso algum tenha sido configurado. Se apenas um modo de entrega de retirada válido estiver disponível para o canal e o item, o representante de vendas não será solicitado a selecioná-lo. Em vez disso, o modo de entrega de retirada disponível será aplicado automaticamente às linhas da ordem.

    ![Selecionar uma opção de retirada no aplicativo de PDV.](media/pickuppos.png)

- Em canais de call center, quando os usuários criam ordens de retirada, eles podem selecionar manualmente qualquer modo de entrega de retirada definido que esteja vinculado ao canal de call center. Em seguida, o sistema valida que o modo de entrega de retirada selecionado pode ser usado quando o item que está sendo vinculado a ele é encomendado. Quando um modo de entrega de retirada é selecionado em canais de call center, as linhas da ordem de venda devem ser vinculadas a um depósito de loja válido. Se um depósito não referente a uma loja for definido em uma linha de venda de call center, não será possível definir um modo de entrega de retirada nessa linha de venda.
- Os representantes de vendas podem usar a operação **Cancelamento da ordem** ou **Atendimento da ordem** no aplicativo de PDV para recuperar uma lista de ordens ou linhas de ordem para retirada. Se um representante de vendas usar um filtro de pesquisa predefinido para mostrar todas as ordens que serão retiradas na loja atual, as consultas serão modificadas para garantir que os resultados da pesquisa incluam todas as ordens elegíveis que usam qualquer modo de entrega de retirada. Os usuários do PDV também podem usar filtros existentes para restringir a lista de ordens a um modo de entrega de retirada específico. Por exemplo, eles podem mostrar somente as ordens para retirada em frente à loja.

    ![Filtro para modos de entrega de retirada aplicado a uma lista de ordens de cancelamento.](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Considerações para o gerenciamento de ordem distribuído

Os recursos de [gerenciamento de ordem distribuído (DOM)](./dom.md) no Commerce ignoram as linhas de venda marcadas para retirada na loja. Esses recursos foram atualizados para garantir que as linhas de venda vinculadas a modos de entrega de retirada configurados ignorem a lógica DOM e não sejam realocadas para um novo depósito de atendimento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
