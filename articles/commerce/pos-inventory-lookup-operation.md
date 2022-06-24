---
title: Operação de consulta de inventário no POS
description: Este artigo descreve como usar a operação de consulta de inventário no Dynamics 365 Commerce Ponto de vendas (POS) para visualizar a disponibilidade de inventário em mãos de produtos entre as lojas e armazéns.
author: boycezhu
ms.date: 08/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.openlocfilehash: 01f10c348c61ffbcb30be26a57b3edd436aacc8f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850240"
---
# <a name="inventory-lookup-operation-in-pos"></a>Operação de consulta de inventário no POS

[!include [banner](includes/banner.md)]

Este artigo descreve como usar a operação de consulta de inventário no Dynamics 365 Commerce Ponto de vendas (POS) para visualizar a disponibilidade de inventário em mãos de produtos entre as lojas e armazéns.

Uma exibição precisa do inventário em toda uma organização ajuda os associados da loja a fornecer atendimento ao cliente oportuno e eficiente. O momento que mais importa é quando um cliente está pronto para tomar uma decisão de compra. É importante que os caixas de uma loja de varejo tenham fácil acesso a informações sobre inventário em tempo real (ou quase), para que possam prometer com precisão a entrega e retirada de produtos.

A operação de consulta de inventário no Commerce POS ajuda os varejistas a alcançar a excelência operacional e obter insights ao conectar lojas com o Commerce headquarters. Esta funcionalidade fornece uma exibição de disponibilidade do inventário de produtos entre todas as lojas e armazéns. Também ajuda os varejista a determinar poupanças de gastos e eficiências adicionais melhorando o planejamento de estoque em tempo real.

Quando a operação de consulta de inventário for iniciada no aplicativo de POS, o caixa do POS usa o teclado numérico para inserir um número de produto para consultar suas informações de inventário. Se o produto inserido tiver variantes, o caixa poderá selecionar dimensões ou outros valores para verificar informações de inventário sobre uma variante de produto específica.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Lista de consulta de inventário para produtos individuais

Para um produto individual, a operação de consulta de inventário fornece uma exibição em lista de consulta de inventário que mostra as seguintes informações de produto em diversos locais:

- **Estoque** — se refere à quantidade "física disponível" de um produto.
- **Reservado** — se refere à quantidade "física reservada" recuperada do headquarters.
- **Encomendado** — se refere à quantidade "total encomendada" recuperada do headquarters.
- **Unidade** — se refere à unidade de medida de estoque configurada no headquarters.

A exibição em lista de locais inclui todas as lojas e armazéns que são configuradas nos grupos de atendimento aos quais a loja atual é vinculada, conforme mostrado na seguinte imagem de exemplo.

![Exibição em lista da operação de consulta de inventário.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Certifique-se de que o armazenamento atual esteja incluído nos grupos de preenchimento associados.

As seguintes ações estão disponíveis na barra do aplicativo de POS:

- **Classificar** — essa ação permite que o usuário do PDV classifique os dados na exibição de lista com base em vários critérios. A classificação baseada em local é a opção de classificação padrão.

    - **Localização geográfica** (do local mais próximo ao mais distante, com base na distância até a loja atual)
    - **Nome** (em ordem crescente ou decrescente)
    - **Número da loja** (em ordem crescente ou decrescente)
    - **Inventário** (em ordem decrescente)
    - **Reservado** (em ordem decrescente)
    - **Encomendado** (em ordem decrescente)

- **Filtrar** — essa ação permite que o usuário do PDV exiba os dados filtrados para um local específico.
- **Exibir disponibilidade da loja** — essa ação permite que o usuário do PDV exiba as quantidades de ATP (disponível para promessa) de um produto na loja selecionada.
- **Exibir localização da loja** — essa ação abre uma página separada para mostrar a exibição de mapa, endereço e horário de funcionamento da loja selecionada.
- **Retirar na loja** — essa ação cria um ordem do cliente para o produto que será retirado na loja selecionada e redireciona o usuário para a tela de transação.
- **Enviar produto** — essa ação cria uma ordem do cliente para o produto que será enviado da loja selecionada e redireciona o usuário para a tela de transação.
- **Exibir todas as variantes** — para um produto com variantes, essa ação muda de uma exibição de lista para uma exibição de matriz que exibe informações de estoque de todas as variantes do produto.
- **Adicionar à transação** — essa ação adiciona o produto ao carrinho e redireciona o usuário para a tela de transação.

> [!NOTE]
> A classificação com base no local que foi introduzida na versão 10.0.17 do Commerce mostra a loja atual na parte superior. Para outras localizações, a distância entre a localização e a loja atual é determinada pelas coordenadas (latitude e longitude) que são definidas no Commerce headquarters. Para uma loja, as informações de localização são definidas no endereço principal da unidade operacional associada à loja. Para um armazém que não é loja, as informações de localização são definidas no endereço do armazém. Antes da versão 10.0.17, a exibição de lista sempre mostra a loja atual na parte superior e classifica outras localizações em ordem alfabética.
>
> As ações **Exibir disponibilidade da loja**, **Exibir localização da loja**, **Retirar na loja** e **Enviar produto** não estão disponíveis para locais que não são lojas.

## <a name="inventory-lookup-matrix-view-for-variants"></a>Exibição em matriz de consulta de inventário para variantes

Para um produto principal com variantes, a operação de consulta de inventário também fornece uma exibição em matriz baseada nas dimensões que exibe informações de disponibilidade do inventário sobre todas as variantes do produto principal em um local selecionado. Por padrão, a exibição em matriz exibe dados da loja atual. Você pode usar a ação **Loja** na barra do aplicativo para consultar informações do inventário em outras lojas configuradas nos grupos de atendimento aos quais a loja atual é vinculada.

A imagem de exemplo a seguir mostra a exibição em matriz da consulta de inventário no POS.

![Exibição em matriz da operação de consulta de inventário.](media/inventory-lookup-matrix-view.png)

Na exibição em matriz, cada célula representa uma variante individual e exibe um valor de inventário em mãos (fisicamente disponível) no canto direito inferior, bem como os valores **reservado** (fisicamente reservado) e **encomendado** (encomendado no total) no canto superior esquerdo. A tabela a seguir explica o significado dos diversos valores em mãos.

| Valor disponível                            | descrição |
|------------------------------------------|-------------|
| Valor numérico que é maior que 0 (zero) | Uma grade foi liberada para o local selecionado e você pode executar ações adicionais na célula. |
| **0** (zero)                             | Uma variante foi lançada para o local selecionado, mas o item não está disponível no local selecionado. Você pode executar ações adicionais na célula. |
| **n/d**, ou uma célula inativa              | Uma grade não foi liberada para o local selecionado, e você pode não pode executar ações adicionais na célula. |

A ordem de exibição dos valores de dimensão na exibição em matriz é baseada na configuração ordem de exibição de dimensão no Commerce headquarters. Você pode alterar a configuração da ordem de exibição da dimensão selecionando uma nova dimensão para usar. 

As seguintes ações estão disponíveis na célula da exibição em matriz:

- **Vender agora** — essa ação adiciona a variante selecionada ao carrinho e redireciona o usuário para a tela de transação..
- **Retirar na loja** — essa ação cria uma ordem do cliente para a variante selecionada que será retirada na loja selecionada e redireciona o usuário para a tela de transação.
- **Enviar produto** — essa ação cria uma ordem do cliente para a variante selecionada que será enviada da loja selecionada e redireciona o usuário para a tela de transação.
- **Disponibilidade** — essa ação leva o usuário a uma página separada que mostra as quantidades de ATP da variante selecionada na loja selecionada.
- **Exibir todos os locais** — essa ação muda para a exibição de lista de disponibilidade de estoque padrão, mostrando as informações de estoque da variante selecionada.
- **Exibir detalhes do produto** — essa ação redireciona o usuário para a PDP (página de detalhes do produto) da variante selecionada.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Acessar a consulta de inventário em outras páginas do POS

Os usuários do POS podem acessar a operação de consulta do inventário em outras páginas do POS.

A imagem de exemplo a seguir mostra os resultados da consulta de inventário em uma PDP no POS.

![Consulta de inventário na página de detalhes do produto.](media/inventory-lookup-from-product-details-page.png)

Na PDP de um produto principal, você pode usar a ação **Exibir todas as variantes** na barra do aplicativo para iniciar a exibição em matriz da consulta do inventário que exibe informações de disponibilidade na loja atual de todas as variantes de um produto. Para um produto individual, a PDP exibe o valor em mãos do inventário (fisicamente disponível) desse produto para a loja atual. Adicionalmente, você pode selecionar na **Inventário de outras lojas** para realizar a operação de consulta de inventário e verificar a disponibilidade no inventário de um produto entre todas as lojas ou armazéns.

> [!NOTE]
> A ação **Visualizar todas as variantes** na PDP está disponível somente para produtos principais que tenham variantes. Ela não está disponível para produtos específicos ou kits.

Você pode configurar a operação de consulta de inventário para que ela apareça como um link na grade de botões na tela de transação do POS. Após a configuração, quando o usuário selecionar uma linha de carrinho e selecionar o botão **Consulta de inventário**, será aberta a exibição em lista da consulta de inventário para o produto selecionado. Para mais informações sobre como configurar as grades de botão usando a ferramenta designer de layout de tela do POS, consulte [configurações visuais da interface de usuário do POS](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Consulta de inventário com cálculo no canal

Na versão 10.0.09 do Commerce e anterior, o valor **físico disponível** na operação de consulta de inventário é obtida do Commerce headquarters em uma chama de serviço em tempo real. Na versão 10.0.10 e posterior do Commerce, você pode configurar a operação de consulta do inventário de POS para usar o cálculo no canal no servidor do Commerce para determinar o valor físico disponível, que pode oferecer uma estimativa mais confiável e precisa do inventário em mãos levando em consideração os dados transacionais que ainda não estão sincronizados para o headquarters. Para mais informações sobre cálculo de inventário no canal e configuração de POS relacionado no headquarters, consulte [Calcular disponibilidade de inventário para canais de varejo](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurações visuais da interface do usuário de PDV](pos-screen-layouts.md)

[Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
