---
title: Pesquisa de estoque no Ponto de Venda
description: "Este tópico descreve as opções disponíveis para exibir informações de estoque no ponto de venda (PDV)."
author: ashishmsft
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application update 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 933875f56b0f47990cb1cb767f84b23b9c9710d4
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="inventory-lookup-in-the-point-of-sale"></a>Pesquisa de estoque no Ponto de Venda 

[!INCLUDE [banner](includes/banner.md)]

A Pesquisa de estoque no Ponto de Venda (PDV) ajuda os varejistas a atingirem a excelência operacional em tempo real e a obterem insights conectando lojas, o PDS e o back office. Essa funcionalidade fornece uma visão exata em tempo real de estoque do produto pelas lojas e centros de distribuição. Também ajuda os varejista a determinar poupanças de gastos e eficiências adicionais melhorando o planejamento de estoque em tempo real.

Uma exibição exata de tempo real de estoque em uma organização ajuda os associados da loja a fornecerem serviço ao cliente oportuno, superior. O momento mas importante é aquele em que o cliente está pronto para tomar uma decisão de compra. É importante que os caixas da loja tenham informações de estoque em tempo real ao seu alcance, para que possam prometer entrega e retirada do produto precisamente.

Você pode abrir a página **Pesquisa de estoque** do espaço de trabalho **Retail Modern POS** ou do espaço de trabalho **Retail Cloud POS**.

![Quadro de pesquisa de estoque na home page do PDV](media/POSHomepage.png)

Na página **Pesquisa de estoque** , você pode usar o teclado numérico para inserir um número do produto. Você pode exibir a quantidade disponível para várias lojas e depósitos.

![Página padrão de pesquisa de estoque](media/InventoryLookUp.png)

Quantidades **Reservadas** e **Encomendas** também são mostradas para cada local.

- **Reservada** – Esta quantidade refere-se ao valor **Físico reservado** do back office para o número do produto especificado no local.
- **Encomendado** – Esta quantidade refere-se ao valor **Total encomendado** do back office para o número do produto especificado no local.

## <a name="locations-that-inventory-availability-information-is-shown-for"></a>Os locais nos quais as informações de disponibilidade de estoque são mostradas

A lista de locais incluem dois tipos de entidades:

- **Lojas de varejo** – A lista mostra as lojas configuradas usando o grupo de localizadores de lojas da loja atual na sede de varejo. 
- **Centros de distribuição** – Os vários tipos de centros de distribuição (como depósitos) podem ser configurados no Microsoft Dynamics 365 for Retail. Entretanto, a lista mostra informações de disponibilidade de estoque somente para centros de distribuição do tipo **Padrão** . 

    > [!NOTE]
    > A disponibilidade das informações de estoque não é exibida para os depósitos dos tipos **Trânsito**, **Quarentena** e **Mercadorias no Roteiro** para o PDV.

Na página **Pesquisa de estoque** , você pode exibir as quantidades disponíveis para promessa (ATP) de cada loja, além das quantidades atuais disponíveis, quantidades reservadas e as quantidades encomendadas. Selecione a loja para exibir as informações ATP e, em seguida, seledione **Mostrar disponibilidade da loja**.

![Quantidades do ATP](media/ATP.png)

## <a name="opening-the-dimension-based-matrix-view-to-show-all-variants"></a>Abrindo a exibição da matriz com base na Dimensão para motrar todas as grades

Na **Detalhes do produto** de um produto mestre ou na página **Pesquisa de estoque** , selecione **Exibir todas as grades** na barra do aplicativo na parte inferior da página. A exibição **Matriz com base na dimensão** da inicialização inicial dessas páginas mostra as informações sobre disponibilidade de estoque para todas as grades de um produto para a loja atual.

> [!NOTE]
> O botão **Exiba todas as grades** está disponível apenas para os produtos mestre de itens com grades de produto. Não está disponível para produtos autônomos ou kits.

![Exiba todas as grades na página de pesquisa de estoque](media/StandardToMatrix.png)

Selecione **Exibir todas as grades** na página **Detalhes do produto** de um produto mestre ou na página **Pesquisa de estoque**, sem selecionar um local, vá para a exibição **Matriz com base na dimensão** para exibir as informações de disponibilidade de estoque para todas as grades de um produto da loja atual.

![Exibição da matriz com base na dimensão para a página de pesquisa de Estoque](media/Matrix.png)

> [!NOTE]
> Na ilustração anterior, a ordem de exibição das dimensões é alfabética, pois a ordem de exibição das dimensões não foi configurada para o produto selecionado.

Na exibição **Matriz com base na dimensão** , as células das grades do produto incluem um valor disponível no canto inferior direito. A tabela a seguir explica o significado vários valores.

| Valor disponível                            | descrição |
|------------------------------------------|-------------|
| Valor numérico que é maior que 0 (zero) | Uma grade foi liberada para o local selecionado e você pode executar ações adicionais na célula. (Essas ações são descritas em mais detalhes posteriormente neste tópico). |
| **0** (zero)                             | Uma grade foi liberada para o local selecionado, mas o item não está disponível no local selecionado. Entretanto, você pode executar ações adicionais na célula. (Essas ações são descritas em mais detalhes posteriormente neste tópico). |
| **n/a** ou uma célula inativa              | Uma grade não foi liberada para o local selecionado, e você pode não pode executar ações adicionais na célula. |

Você também pode alterar a tabela dinâmica de dimensões marcando a nova dimensão a ser usada. 

![Alterando a tabela dinâmica](media/ChangePivot.png)

![Tabela dinâmica alterada](media/PivotChanged.png)

> [!NOTE]
> Nas ilustrações anteriores, a ordem de exibição das dimensões para o produto selecionado personalizada (não alfabética). É baseana na ordem de exibição de dimensões definida no back office.

Além disso, na exibição **Matriz com base na dimensão** , mais ações podem ser executadas para ajudar a impulsionar a produtividade de um associado da loja. Eis alguns exemplos:

- Alterar o local da loja para pesquisar a disponibilidade de estoque de todas as grades de produto em outros locais. Esses locais incluem outras lojas nos centros de distribuição e no grupo de localizadores da loja do tipo **Padrão** .
- Vender uma grade de produto individual para um cliente usando pague e leve, retirada na loja ou remessa para um endereço.
- Forneça ao cliente informações ATP para uma grade de produtos individuais em um local específico.

![Ações adicionais sobre quadros da grade](media/VariantActions.png)

> [!NOTE]
> Na ilustração anterior, a ordem de exibição das dimensões é alfabética, pois a ordem de exibição das dimensões não foi configurada para o produto selecionado.

A tabela a seguir fornece mais informações sobre ações adicionais disponíveis.


|        Ação        |                                                                                                                    descrição                                                                                                                    |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Vender agora       |                               Adicionar a grade de itens selecionada para a transação e redirecionar o usuário para a tela da transação. (Esta ação não está disponível quando o local selecionado é um centro de distribuição.)                               |
|   Retirar na loja   |      Criar uma ordem de cliente para a grade do produto que será retirada do local selecionado e redirecionar o usuário para a tela da transação. (Esta ação não está disponível quando o local selecionado é um centro de distribuição.)       |
|     Enviar produto     |                                                 Criar uma ordem de cliente para a grade do produto que será enviada do local selecionado e redirecionar o usuário para a tela da transação.                                                 |
|     Disponibilidade     |                                                                             Mostra as informações de ATP para a combinação de grade selecionada para o local selecionado.                                                                              |
|  Mostrar todos os locais  | Alterne para as informações de exibição padrão de pesquisa de estoque e de disponibilidade de estoque de destaque para a grade de item em todas as lojas no grupo de localizador de loja e, também em centros de distribuição do tipo <strong>Padrão/padrão</strong>. |
| Exibir detalhes do produto |                                                                         Redirecionar o usuário para a página <strong>Detalhes do produto</strong> do produto mestre associado.                                                                          |


