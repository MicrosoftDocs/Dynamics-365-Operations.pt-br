---
title: Operação de consulta de inventário no POS
description: Este tópico descreve como usar a operação de consulta de inventário no Dynamics 365 Commerce Ponto de vendas (POS) para visualizar a disponibilidade de inventário em mãos de produtos entre as lojas e armazéns.
author: boycezhu
ms.date: 05/11/2021
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
ms.openlocfilehash: b697583f2ebf9950ad805d4f415dafb2c891de8052d4a47563b048059475030f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745323"
---
# <a name="inventory-lookup-operation-in-pos"></a>Operação de consulta de inventário no POS

[!include [banner](includes/banner.md)]

Este tópico descreve como usar a operação de consulta de inventário no Dynamics 365 Commerce Ponto de vendas (POS) para visualizar a disponibilidade de inventário em mãos de produtos entre as lojas e armazéns.

Uma exibição precisa do inventário em toda uma organização ajuda os associados da loja a fornecer atendimento ao cliente oportuno e eficiente. O momento que mais importa é quando um cliente está pronto para tomar uma decisão de compra. É importante que os caixas de uma loja de varejo tenham fácil acesso a informações sobre inventário em tempo real (ou quase), para que possam prometer com precisão a entrega e retirada de produtos.

A operação de consulta de inventário no Commerce POS ajuda os varejistas a alcançar a excelência operacional e obter insights ao conectar lojas com a matriz do Commerce. Esta funcionalidade fornece uma exibição de disponibilidade do inventário de produtos entre todas as lojas e armazéns. Também ajuda os varejista a determinar poupanças de gastos e eficiências adicionais melhorando o planejamento de estoque em tempo real.

Quando a operação de consulta de inventário for iniciada no aplicativo de POS, o caixa do POS usa o teclado numérico para inserir um número de produto para consultar suas informações de inventário. Se o produto inserido tiver variantes, o caixa poderá selecionar dimensões ou outros valores para verificar informações de inventário sobre uma variante de produto específica.

## <a name="inventory-lookup-list-view-for-individual-products"></a>Lista de consulta de inventário para produtos individuais

Para um produto individual, a operação de consulta de inventário fornece uma exibição em lista de consulta de inventário que mostra as seguintes informações de produto em diversos locais:

- **Inventário** - Refere-se à quantidade "física disponível" de um produto.
- **Reservado** - Refere-se à quantidade "física reservada" recuperada da matriz.
- **Encomendado** - Refere-se à quantidade "encomendada no total" recuperada da matriz.
- **Unidade** - Refere-se à unidade de medida do inventário configurada na matriz.

A exibição em lista de locais inclui todas as lojas e armazéns que são configuradas nos grupos de atendimento aos quais a loja atual é vinculada, conforme mostrado na seguinte imagem de exemplo.

![Exibição em lista da operação de consulta de inventário.](media/inventory-lookup-list-view.png)

> [!NOTE]
> Certifique-se de que o armazenamento atual esteja incluído nos grupos de preenchimento associados.

As seguintes ações estão disponíveis na barra do aplicativo de POS:

- **Classificar** - Esta ação permite que o usuário do POS classifiquem os dados na exibição em lista com base em diversos critérios. A classificação baseada em local é a opção de classificação padrão. 
  - **Localização geográfica** (do local mais próximo ao mais distante, em comparação com a loja atual)
  - **Nome** (em ordem crescente ou decrescente)
  - **Número da loja** (em ordem crescente ou decrescente)
  - **Inventário** (em ordem decrescente)
  - **Reservado** (em ordem decrescente)
  - **Encomendado** (em ordem decrescente)
- **Filtrar** - Esta ação permite que o usuário do POS visualize dados filtrados sobre um local específico.
- **Exibir disponibilidade da loja** - Esta ação permite que o usuário do POS visualize as quantidades disponíveis para promessa (ATP) de um produto na loja selecionada.
- **Exibir localização da loja** - Esta ação abre uma página separada para exibir a visualização no mapa, o endereço e o horário de funcionamento da loja selecionada.
- **Retirar na loja** - Esta ação cria uma ordem do cliente para um produto que será retirado na loja selecionada e redireciona o usuário para a tela de transação.
- **Enviar produto** - Esta ação cria uma ordem do cliente para um produto que será enviado da loja selecionada e redireciona o usuário para a tela de transação.
- **Visualizar todas as variantes** - Para um produto com variantes, esta ação alterna a exibição em lista para uma exibição em matriz que exibe informações de inventário de todas as informações do produto.
- **Adicionar à transação** - Esta ação adiciona o produto ao carrinho e redireciona o usuário para a tela de transação.

> [!NOTE]
> Para uma classificação baseada em localizadas, a distância entre uma localização e a loja atual é determinada pelas coordenadas (latitude e longitude) definidas na matriz do Commerce. Para uma loja, as informações de localização são definidas no endereço principal da unidade operacional associada à loja. Para um armazém que não é loja, as informações de localização são definidas no endereço do armazém. Se as coordenadas da loja atual não estiverem definidas, a opção de classificação baseada na localização exibirá a loja atual no topo da lista e, então, classificará outros locais por nome.

> [!NOTE]
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

A ordem de exibição dos valores de dimensão na exibição em matriz é baseada na configuração ordem de exibição de dimensão na matriz do Commerce. Você pode alterar a configuração da ordem de exibição da dimensão selecionando uma nova dimensão para usar. 

As seguintes ações estão disponíveis na célula da exibição em matriz:

- **Vender agora** - Esta ação adiciona a variante selecionada ao carrinho e redireciona o usuário para a tela de transação.
- **Retirar na loja** - Esta ação cria uma ordem do cliente para a variante selecionada que será retirada na loja selecionada e redireciona o usuário para a tela de transação.
- **Enviar produto** - Esta ação cria uma ordem do cliente para uma variante selecionada que será enviado da loja selecionada e redireciona o usuário para a tela de transação.
- **Disponibilidade** - Esta ação leva o usuário a uma página separada exibindo as quantidades ATP da variante selecionada na loja selecionada.
- **Exibir todos os locais** - Esta ação alterna para a exibição em lista da disponibilidade do inventário padrão exibindo as informações sobre a variante selecionada.
- **Exibir detalhes do produto** - Esta ação redireciona o usuário para a página de detalhes do produto (PDP) da variante selecionada.

## <a name="access-inventory-lookup-from-other-pages-in-pos"></a>Acessar a consulta de inventário em outras páginas do POS

Os usuários do POS podem acessar a operação de consulta do inventário em outras páginas do POS.

A imagem de exemplo a seguir mostra os resultados da consulta de inventário em uma PDP no POS.

![Consulta de inventário na página de detalhes do produto.](media/inventory-lookup-from-product-details-page.png)

Na PDP de um produto principal, você pode usar a ação **Exibir todas as variantes** na barra do aplicativo para iniciar a exibição em matriz da consulta do inventário que exibe informações de disponibilidade na loja atual de todas as variantes de um produto. Para um produto individual, a PDP exibe o valor em mãos do inventário (fisicamente disponível) desse produto para a loja atual. Adicionalmente, você pode selecionar na **Inventário de outras lojas** para realizar a operação de consulta de inventário e verificar a disponibilidade no inventário de um produto entre todas as lojas ou armazéns.

> [!NOTE]
> A ação **Visualizar todas as variantes** na PDP está disponível somente para produtos principais que tenham variantes. Ela não está disponível para produtos específicos ou kits.

Você pode configurar a operação de consulta de inventário para que ela apareça como um link na grade de botões na tela de transação do POS. Após a configuração, quando o usuário selecionar uma linha de carrinho e selecionar o botão **Consulta de inventário**, será aberta a exibição em lista da consulta de inventário para o produto selecionado. Para mais informações sobre como configurar as grades de botão usando a ferramenta designer de layout de tela do POS, consulte [configurações visuais da interface de usuário do POS](pos-screen-layouts.md).

## <a name="inventory-lookup-with-channel-side-calculation"></a>Consulta de inventário com cálculo no canal

Na versão 10.0.09 do Commerce e anterior, o valor **físico disponível** na operação de consulta de inventário é obtida da matriz Commerce em uma chama de serviço em tempo real. Na versão 10.0.10 e posterior do Commerce, você pode configurar a operação de consulta do inventário de POS para usar o cálculo no canal no servidor do Commerce para determinar o valor físico disponível, que pode oferecer uma estimativa mais confiável e precisa do inventário em mãos levando em consideração os dados transacionais que ainda não estão sincronizados para a matriz. Para mais informações sobre cálculo de inventário no canal e configuração de POS relacionado na matriz, consulte [Calcular disponibilidade de inventário para canais de varejo](calculated-inventory-retail-channels.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurações visuais da interface do usuário de PDV](pos-screen-layouts.md)

[Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
