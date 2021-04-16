---
title: Materiais perigosos em produtos, ordens, remessas e cargas
description: Este tópico explica como definir propriedades de materiais perigosos para produtos liberados, como colocar limites de estoque em itens perigosos e como incluir materiais perigosos em uma ordem de venda, remessa ou carga.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: b0fb2f77b4e95c90e3eb8a4c74929deead34de5c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829393"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Materiais perigosos em produtos, ordens, remessas e cargas

[!include [banner](../includes/banner.md)]

Este tópico explica como definir propriedades de materiais perigosos para produtos liberados, como colocar limites de estoque em itens perigosos e como incluir materiais perigosos em uma ordem de venda, remessa ou carga.

## <a name="set-hazardous-material-specifications-for-products"></a>Definir especificações de materiais perigosos para produtos

Depois de definir uma regulamentação de materiais perigosos e configurar os códigos de referência relacionados, conforme descrito em [Configurar materiais perigosos](hazmat-setup.md), você poderá associar essas informações a itens liberados. O texto de remessa para documentos de remessa será emitido a partir das informações de materiais perigosos para os itens liberados.

Como parte do processo de associar um item liberado a um material perigoso, você deve especificar o código da regulamentação e o material. Diferentes códigos de regulamentação podem ser associados a um item, dependendo dos modos de transporte, e você pode associar várias regulamentações e códigos de material a cada item.

Para configurar um produto liberado como um material perigoso, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione ou crie um produto para abrir sua página **Detalhes do produto liberado**.
1. Na FastTab **Gerenciar estoque**, defina a opção **Materiais perigosos** como **Sim**. Esta configuração identifica o item como uma mercadoria perigosa e é usada quando a documentação da remessa é impressa.
1. No Painel de Ações, na guia **Gerenciar estoque**, no grupo **Conformidade**, selecione **Materiais perigosos de item**.
1. Preencha a página **Materiais perigosos de item** para o item selecionado usando os campos descritos nas subseções a seguir.

### <a name="item-hazardous-materials-header"></a>Cabeçalho de materiais perigosos de item

A tabela a seguir descreve os campos disponíveis na parte superior da página **Materiais perigosos de item**.

| Campo | descrição |
|---|---|
| Nº de itens | O produto liberado com o qual você está trabalhando. |
| Código de regulamentação | Selecione a regulamentação de materiais perigosos que se aplica ao produto. A regulamentação define como o texto impresso de remessa é criado para um item e para os modos de entrega associados. Depois de atribuído, o código não poderá ser editado nesta página. No entanto, você pode atribuir um novo código de regulamentação selecionando **Novo**. |
| Código do material | (Opcional) Selecione o código de materiais perigosos que se aplica ao produto. O código de material fornece um modelo que inclui valores padrão para muitos outros campos nesta página. Quando você seleciona um código, todas as especificações de materiais perigosos são copiadas para o produto atual. No entanto, o sistema solicita primeiro que você confirme que os dados de material do item devem ser preenchidos a partir do código do material. |
| Código do grupo | (Opcional) Selecione o código do grupo de classificação de materiais perigosos que se aplica ao produto. Em relação ao campo **Código do material**, quando você selecionar um código, todas as especificações de materiais perigosos serão copiadas para o produto atual. No entanto, o sistema solicita primeiro que você confirme que os dados do grupo de classe do item devem ser preenchidos a partir do código do grupo. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>FastTab Descrições

A tabela a seguir descreve os campos disponíveis na FastTab **Descrições**.

| Campo | descrição |
|---|---|
| Nome de remessa apropriado | Insira a descrição padrão do material, conforme especificado pela regulamentação aplicável. Você pode fornecer traduções para esse valor na FastTab **Tradução de texto para remessa de itens**, conforme descrito na próxima seção. |
| Nome técnico | Selecione o nome comum ou genérico do material. Esse nome pode ser um nome que sua empresa usa internamente para o material. |
| N.O.S. | Marque esta caixa de seleção para indicar que o valor **Nome de remessa apropriado** é um nome de remessa não especificado de outra forma (N.O.S.) para o item. N.O.S. Os nomes de remessa são usados para grupos de produtos químicos e materiais semelhantes que têm usos específicos, mas podem não estar listados por nome na tabela hazmat em uma regulamentação específica. |

### <a name="item-ship-text-translation-fasttab"></a>FastTab Tradução de texto para remessa de itens

A FastTab **Tradução de texto para remessa de itens** contém uma grade que mostra traduções dos valores **Nome de remessa apropriado** definidos para o idioma principal na FastTab **Descrições**. Essas traduções podem ser usadas no texto de impressão de remessa para um ou mais idiomas adicionais.

A tabela a seguir descreve os campos disponíveis na FastTab **Tradução de texto para remessa de itens**.


| Campo | descrição |
|---|---|
| Idioma | O código de idioma usado pela linha. Por exemplo, **pt-br** indica português brasileiro. |
| Texto impresso da remessa | O valor do **Nome de remessa apropriado** traduzido no idioma usado pela linha. |

Para adicionar ou editar uma tradução, selecione **Traduções** acima da grade para abrir a página **Traduções de texto**. E então, siga uma destas etapas:

- Para adicionar uma nova tradução, no Painel de Ações, selecione **Adicionar**. Selecione o idioma a ser adicionado e, em seguida, no campo **Texto traduzido**, insira o texto traduzido.
- Para editar uma tradução existente, selecione um idioma de destino no campo **Idioma** e edite o texto traduzido no campo **Texto traduzido**, conforme necessário.

### <a name="material-management-fasttab"></a><a name="material-management"></a>FastTab de gerenciamento de material

A tabela a seguir descreve os campos disponíveis na FastTab **Gerenciamento de material**.

| Campo | descrição |
|---|---|
| Classe | Selecione a classe de materiais perigosos à qual o produto pertence, conforme definido pela regulamentação cumprida. Você deve atribuir uma divisão e uma classe a cada produto que inclui materiais perigosos. |
| descrição | A descrição definida para a classe selecionada no campo **Classe**. O campo é somente leitura. |
| Divisão | Selecione a divisão de materiais perigosos à qual o produto pertence, conforme definido pela regulamentação cumprida. A divisão é um subconjunto da classe. Você deve atribuir uma divisão e uma classe a cada produto que inclui materiais perigosos. |
| Identificação | Selecione o código de identificação de materiais perigosos. Normalmente, esse código se baseia em um padrão das Nações Unidas (UN). |
| Grupo de embalagens | Selecione o grupo de embalagens que se aplica ao item atual. |
| descrição | A descrição definida para o grupo selecionado no campo **Grupo de embalagens**. O campo é somente leitura. |
| Descrições de embalagem | Selecione o código de descrição de embalagem aplicável. Esse código faz referência a uma descrição que indica como o produto deve ser embalado. |
| Etiquetas de materiais perigosos | Selecione um código que referencie a etiqueta aplicável de mercadorias perigosas que deve ser aplicada ao produto. |
| Quantidade limitada | Defina esta opção como **Sim** para relatar o peso total do produto incluído em cada carga e em cada linha de carga. |
| Quantidade | Insira a quantidade de materiais perigosos no produto, na unidade especificada. Esse valor será usado para calcular a pontuação total de materiais perigosos para cargas e remessas que incluam o produto. |
| Multiplicador | Insira o multiplicador que é aplicado quando a pontuação de materiais perigosos é calculada para cada linha de carga que inclui o produto. Esse valor é especificado pela regulamentação aplicável, de acordo com o tipo de material perigoso contido no produto. |
| Unidade | Selecione a unidade de medida que se aplica à quantidade de materiais perigosos no produto, conforme especificado no campo **Quantidade**. Esse valor será usado para calcular a pontuação total de materiais perigosos para cargas e remessas que incluam o produto. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>Como a pontuação de materiais perigosos é calculada

Muitos dos valores especificados na FastTab **Gerenciamento de material** para um produto são usados para calcular uma *Pontuação de materiais perigosos* para cada linha de carga que inclui esse produto. A pontuação é calculada por meio da seguinte fórmula:

Pontuação de materiais perigosos = *&lt;LineQty&gt;* × *&lt;HazmatQty&gt;* × *&lt;UnitConversion&gt;* × *&lt;Multiplier&gt;*

Esta é uma chave para a fórmula:

- *&lt;LineQty&gt;* é a quantidade do produto especificada para uma linha de carga.
- *&lt;HazmatQty&gt;* é a quantidade de materiais perigosos especificada para um produto no campo **Quantidade** na FastTab **Gerenciamento de material**.
- *&lt;UnitConversion&gt;* é um fator de conversão para converter entre a unidade usada na quantidade de linha de carga e a unidade especificada para um produto no campo **Unidade** da FastTab **Gerenciamento de material**.
- *&lt;Multiplier&gt;* é o multiplicador especificado para um produto no campo **Multiplicador** na FastTab **Gerenciamento de material**.

Essa pontuação é relatada para cada linha de carga que contém um produto em que esses valores são especificados. Para obter mais informações, consulte as seções [Remessas que incluem materiais perigosos](#hazmat-shipments) e [Cargas que incluem materiais perigosos](#hazmat-loads) mais adiante neste tópico.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>Como o peso de materiais perigosos é calculado

Cargas e linhas de carga que contêm produtos em que a opção **Quantidade limitada** na FastTab **Gerenciamento de material** é definida como **Sim** incluem o peso total de materiais perigosos, conforme descrito nas seções [Remessas que incluem materiais perigosos](#hazmat-shipments) e [Cargas que incluem materiais perigosos](#hazmat-loads) mais adiante neste tópico. O peso de materiais perigosos é calculado por meio da seguinte fórmula:

Peso de materiais perigosos = *&lt;LineQty&gt;* × *&lt;ProductWeight&gt;* × *&lt;UnitConversion&gt;*

Esta é uma chave para a fórmula:

- *&lt;LineQty&gt;* é a quantidade do produto especificada para uma linha de carga.
- *&lt;ProductWeight&gt;* é o peso líquido especificado para o produto, na unidade de estoque especificada para o produto.
- *&lt;UnitConversion&gt;* é um fator de conversão para converter entre a unidade usada para a quantidade da linha de carga e a unidade de estoque usada para *&lt;ProductWeight&gt;*.

### <a name="transport-information-fasttab"></a>FastTab Informações de transporte

A tabela a seguir descreve os campos disponíveis na FastTab **Informações de transporte**.

| Campo | descrição |
|---|---|
| Categoria de transporte | Selecione a categoria de transporte relacionada. |
| Código de túnel | Selecione o código de restrição de túnel relacionado ao item. |
| Estiva de material perigoso | Selecione o código de referência usado para o manuseio e o acondicionamento de frete marítimo quando o item é enviado por frete marítimo. |
| Tipo de aeronave | Selecione a restrição de aeronave que se aplica ao material quando ele é enviado por frete aéreo. |
| Embalagem - somente aeronaves de carga | Com base no valor selecionado no campo **Tipo de aeronave**, selecione o código de instruções de embalagem que se aplica quando o produto só pode ser enviado por aeronave de carga. |
| Embalagem - aeronave para passageiros e cargas | Com base no valor selecionado no campo **Tipo de aeronave**, selecione o código de instruções de embalagem que se aplica quando o produto pode ser enviado por aeronave de carga ou aeronave de passageiros. |
| IATA Star | Defina esta opção como **Sim** para indicar que as especificações de transporte aéreo inseridas nesta FastTab estão relacionadas ao padrão de mercadorias perigosas da IATA (Associação do Transporte Aéreo Internacional). Este campo é meramente informativo. |
| Resposta de emergência | Selecione o código que faz referência a instruções para manusear o material em caso de emergência. |

### <a name="environmental-information-fasttab"></a>FastTab Informações ambientais

A tabela a seguir descreve os campos disponíveis na FastTab **Informações ambientais**.

| Campo | Descrição |
|---|---|
| Perigoso para o meio ambiente | Defina esta opção como **Sim** para indicar que o produto é perigoso para o meio ambiente. Use este campo para fins de relatório. |
| Poluente marinho | Defina esta opção como **Sim** para indicar que o produto é um poluente marinho. Use este campo para fins de relatório. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>Definir limites de estoque para produtos perigosos

Por motivos de segurança, talvez seja preciso limitar o valor total de determinado produto que pode ser estocado em um único local. Para definir limites de estoque para um produto liberado, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione um produto para abrir a página **Detalhes do produto liberado**.
1. No Painel de Ações, na guia **Gerenciar estoque**, no grupo **Conformidade**, selecione **Detalhes do relatório**.
1. Nos campos **Limite de estoque perigoso** e **Limite de aviso perigoso**, defina os valores apropriados para o produto selecionado.

O relatório **Limite de estoque perigoso** permite que você monitore os níveis de estoque dos materiais perigosos em locais de depósito para garantir que eles permaneçam dentro dos limites de segurança estabelecidos aqui. Para obter mais informações, consulte [Relatório de limite de estoque de materiais perigosos](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>Transações de ordem de venda que incluem materiais perigosos

Para incluir um produto classificado como material perigoso em uma ordem de venda, você deve associar a transportadora relevante à ordem de venda. Abra a ordem de venda e, na FastTab **Entrega**, defina os campos **Transportadora** e **Serviço da transportadora**, conforme necessário.

A transportadora também está associada ao modo de entrega. Portanto, você deve verificar se essas informações estão alinhadas com a regulamentação de materiais perigosos. Em outras palavras, o modo de entrega especificado na regulamentação de materiais perigosos deve corresponder às especificações no cabeçalho da ordem de venda. Dessa forma, a regulamentação, a transportadora e o serviço estão conectados às linhas de remessa usadas em uma ordem de venda.

Depois que uma ordem de venda é finalizada e está pronta para ser enviada, ela pode ser liberada para o depósito a fim de indicar a transferência entre as operações de vendas e de depósito.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Remessas que incluem materiais perigosos

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Exibir pontuações de materiais perigosos para cada linha de remessa

A página **Detalhes da remessa** de uma remessa mostra o total de valores de peso e ponto de materiais perigosos que foram calculados para cada linha de carga incluída na remessa. Para exibir as pontuações e os pesos, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Selecione uma remessa para abrir a página **Detalhes da remessa**.
1. Na FastTab **Linhas de carga**, inspecione as linhas. Para cada linha, você verá os cálculos de materiais perigosos nos seguintes campos:

    - **Pontos de materiais perigosos** – este campo mostra a pontuação de materiais perigosos para a linha de carga. O valor é calculado de acordo com as regras e os valores que foram estabelecidos para a regulamentação aplicável e na configuração do produto liberado. O cálculo usa a quantidade na linha de carga e faz referência ao multiplicador na [configuração de gerenciamento de material](#material-management) para o produto liberado.
    - **Peso líquido de quantidade limitada** – para produtos marcados como produtos de quantidade limitada por causa do conteúdo de materiais perigosos, este campo mostra o peso líquido total do conteúdo perigoso incluído na linha de carga. O cálculo se baseia nos produtos marcados como materiais perigosos na configuração do produto liberado. Se um item for marcado como um item de quantidade limitada, o cálculo usará a quantidade em cada linha de carga e fará referências ao peso na [configuração de gerenciamento de material](#material-management) para o produto liberado.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Verificar a compatibilidade entre materiais perigosos incluídos em uma remessa

O sistema pode avaliar se todos os materiais perigosos incluídos em uma remessa são adequados para serem enviados juntos. Para avaliar a compatibilidade, o sistema verifica o grupo de compatibilidade atribuído a cada produto incluído na remessa. Para obter mais informações, consulte [Grupos de compatibilidade de materiais perigosos](hazmat-setup.md#compatibility-groups).

Para realizar a verificação de compatibilidade, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Selecione uma remessa para abrir a página **Detalhes da remessa**.
1. No Painel de Ações, na guia **Remessas**, no grupo **Ações**, selecione **Verificação de compatibilidade**.

Você recebe uma mensagem informando sobre os resultados da verificação.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Cargas que incluem materiais perigosos

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Exibir pontuações de materiais perigosos para cada linha de carga

A página **Detalhes da carga** de uma carga mostra o total de valores de peso e ponto de materiais perigosos que foram calculados para essa carga e para cada linha de carga. Para exibir as pontuações e os pesos, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as cargas**.
1. Selecione uma carga para abrir a página **Detalhes da carga**. (Você também pode abrir os detalhes da carga selecionando um link de uma remessa relacionada.)
1. Na FastTab **Carga**, você pode revisar o total de pontuações e pesos de materiais perigosos para a carga inteira inspecionando os seguintes campos:

    - **Pontos de materiais perigosos** – este campo mostra a pontuação de materiais perigosos para a carga. O valor é calculado de acordo com as regras e os valores que foram estabelecidos para a regulamentação aplicável e na configuração do produto liberado. O cálculo usa a quantidade incluída na carga e faz referência ao multiplicador na [configuração de gerenciamento de material](#material-management) para o produto liberado.
    - **Peso líquido de quantidade limitada** – para produtos marcados como produtos de quantidade limitada por causa do conteúdo de materiais perigosos, este campo mostra o peso líquido total do conteúdo perigoso incluído na carga. O cálculo se baseia nos produtos marcados como materiais perigosos na configuração do produto liberado. Se um item for marcado como um item de quantidade limitada, o cálculo usará a quantidade em cada carga e fará referências ao peso na [configuração de gerenciamento de material](#material-management) para o produto liberado.

1. Para revisar as pontuações e os pesos de linhas individuais, selecione a FastTab **Linhas de carga**. Os valores fornecidos para cada linha são semelhantes aos valores fornecidos para a carga inteira, conforme descrito na etapa anterior.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>Verificar a compatibilidade entre materiais perigosos incluídos em uma carga

O sistema pode avaliar se todos os materiais perigosos incluídos em uma carga são adequados para serem enviados juntos. Para avaliar a compatibilidade, o sistema verifica o grupo de compatibilidade atribuído a cada produto incluído na carga. Para obter mais informações, consulte [Grupos de compatibilidade de materiais perigosos](hazmat-setup.md#compatibility-groups).

Para realizar a verificação de compatibilidade, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as cargas**.
1. Selecione uma remessa para abrir a página **Detalhes da carga**. (Você também pode abrir os detalhes da carga selecionando um link de uma remessa relacionada.)
1. No Painel de Ações, na guia **Cargas**, no grupo **Ações**, selecione **Verificação de compatibilidade**.

Você recebe uma mensagem informando sobre os resultados da verificação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]