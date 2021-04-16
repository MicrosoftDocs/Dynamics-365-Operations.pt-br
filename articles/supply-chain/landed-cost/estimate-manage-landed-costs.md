---
title: Estimar e gerenciar custos de entrega
description: O sistema usa a configuração de custo automático para determinar uma estimativa do custo de entrega. Este tópico explica como é possível definir vários cenários para fornecer uma estimativa mais precisa.
author: sherry-zheng
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 510f5fc4910dde2f91fe2d666abb23a9bd7381f1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823424"
---
# <a name="estimate-and-manage-landed-costs"></a>Estimar e gerenciar custos de entrega

[!include [banner](../../includes/banner.md)]

O sistema usa a [configuração de custo automático](auto-cost-setup.md) para determinar uma estimativa do custo de entrega. Além disso, é possível definir vários cenários para fornecer uma estimativa mais precisa. Esses cenários são armazenados. Portanto, você pode examiná-las posteriormente e compará-las com dados reais em um relatório. Também é possível atualizar o preço do item.

## <a name="set-up-cost-estimates"></a>Configurar estimativas de custo

### <a name="set-up-cost-templates"></a>Configurar modelos de custo

Os modelos de custo estabelecem configurações padrão que os usuários que obtêm a estimativa não sabem necessariamente. Os modelos podem ajudar a reduzir a complexidade no processo de estimativa, minimizando as seleções que os usuários devem especificar para obter uma estimativa precisa. Se estiver usando o modelo de custo padrão, você poderá usar os modelos de custo ao configurar o custo de mercadorias.

Para configurar modelos de custo, acesse **Custo de entrega \> Configuração de custos \> Modelos de custo**. Na página **Modelos de custo**, o painel de lista à esquerda mostra todos os modelos de custo atuais. Você pode usar os botões no Painel de Ações para criar, excluir e editar modelos.

A tabela a seguir descreve os campos disponíveis para cada modelo.

| Campo | Descrição |
|---|---|
| Modelo de custo | Insira um nome exclusivo para o modelo de custo. O nome costuma descrever o fator ou multiplicador de custo para o modelo. |
| descrição | Insira uma descrição do modelo de custo. |
| Transportadora | Selecione a transportadora que deve ser aplicada quando o modelo for usado. |
| Modo de entrega | Selecione o modo de entrega, como via marítima ou aérea, que deve ser aplicado quando o modelo é usado. Este campo ajuda a determinar os custos automáticos associados às mercadorias em uma estimativa de custo. |
| Tipo de contêiner de remessa | Selecione o tipo de contêiner de remessa que deve ser aplicado quando o modelo é usado. Este campo ajuda a determinar os custos automáticos associados às mercadorias em uma estimativa de custo. |
| Agente alfandegário | O agente alfandegário (fornecedor) que deve ser aplicada quando o modelo for usado. Esse campo ajuda a determinar os custos automáticos associados à estimativa de custo. |
| Fator | Insira o multiplicador (porcentagem) que deve ser aplicado automaticamente à estimativa de custo quando o modelo é usado. Por exemplo, para adicionar 10% à estimativa de custo calculada, digite *1,10*. |

### <a name="create-a-cost-estimate"></a>Criar uma estimativa de custo

Use a caixa de diálogo **Estimativa de custo** para gerar uma nova estimativa de custo baseada em um modelo de custo selecionado, um conjunto de itens selecionado e outros detalhes de um percurso. Essas configurações são usadas para determinar os custos de entrega estimados de mercadorias. Essas estimativas de custo são usadas principalmente para trabalhar com itens de custo padrão. Ao adicionar os custos de entrega estimados ao custo padrão de mercadorias no estoque, você deve testar transações de variação reduzida quando as mercadorias são adicionadas a uma viagem, pois o custo padrão refletirá as estimativas desses custos de entrega.

Para abrir a caixa de diálogo **Estimativa de custo**, acesse **Custo de entrega \> Tarefas periódicas \> Estimativa de custo**. Defina os campos que são descritos nas subseções a seguir. Finalmente, selecione **OK** para criar a estimativa. A página **Estimativa de custo** (**Custo de entrega \> Consultas \> Estimativas de custo**) aparece e mostra sua nova estimativa, conforme descrito posteriormente neste tópico.

### <a name="settings-on-the-parameters-tab"></a>Configurações na guia Parâmetros

A tabela a seguir descreve os campos disponíveis na guia **Parâmetros** da caixa de diálogo **Estimativa de custo**.


| Campo | Descrição |
|---|---|
| Modelo de custo | Selecione um modelo de custo. As configurações associadas ao modelo selecionado serão usadas para determinar os custos automáticos aplicados. |
| Estimar data | Por padrão, este campo é definido como a data de hoje, mas você pode alterar o valor. A data especificada será usada para selecionar os preços de venda adequados, os preços de compra, os custos automáticos e a taxa de câmbio se for usada uma taxa de remessa. |
| Medição | Os custos podem depender de uma medição. Por exemplo, quando o frete é usado, a definição de preços volumétricos pode ser aplicada. Se o custo depender de uma medição, insira o valor dessa medição. Caso contrário, é recomendável definir este campo como *1*, a menos que você tenha certeza de que não haverá divisão com a medição. Insira um valor decimal. A unidade é definida no registro de custo automático aplicável. |
| Modelo de percurso | Selecione um [modelo de percurso](multi-leg-journey-setup.md). Este campo é usado para determinar os custos automáticos corretos que devem ser aplicados. |
| Porta de origem | A porta da qual os itens serão enviados. Este campo é definido com base no modelo de percurso selecionado. |
| Porta de destino | A porta para a qual os itens serão enviados. Este campo é definido com base no modelo de percurso selecionado. |
| Moeda | Selecione a moeda na qual os itens serão comprados. |
| Contêineres | Em geral, se vários contêineres forem usados, especifique o número de contêineres. O sistema usará os custos de vários contêineres ao estimar os custos. |
| Fólios | Em geral, se vários fólios forem usados, especifique a quantidade. (A quantidade costuma ser *1*.) |
| Site | Especifique o site em que as mercadorias serão entregues. |

### <a name="settings-on-the-items-tab"></a>Configurações na guia Itens

Na guia **Itens**, você poderá adicionar à estimativa quantos itens forem necessários. Use a barra de ferramentas para adicionar itens à grade ou remover itens. Selecione **Estoque \> Exibir dimensões** na barra de ferramentas para abrir uma caixa de diálogo em que você possa adicionar colunas de dimensão à grade ou remover colunas.

A tabela a seguir descreve os campos disponíveis para cada item.

| Campo | Descrição |
|---|---|
| Número do item | Selecione o item para determinar o preço. (Se o item ainda não existir no sistema, crie um item fictício, opcionalmente anexe-o a um grupo de custo de item de viagem e deixe o preço em branco, ou crie ou altere o preço.) |
| Conta de fornecedor | Selecione o fornecedor a ser usado para a estimativa deste item. Se um fornecedor padrão for atribuído ao item, este campo será definido automaticamente. |
| Quantidade | Selecione a quantidade que você comprará. |
| Preço de custo | O sistema usa as regras de preços para encontrar um preço inicial, mas você pode substituir esse preço, se necessário. |
| Preço de venda | Insira o preço de venda esperado das mercadorias. |
| Medição | Insira um valor decimal para a medição das mercadorias. A unidade é aquela que está configurada para o produto liberado aplicável. |
| Atualizar peso/volume do item | Marque esta caixa de seleção para atualizar a medição de peso ou de volume do produto liberado para que ele corresponda ao valor de **Medição** inserido para essa linha. |
| (Outras dimensões) | Dependendo das dimensões selecionadas para exibição, você pode ver colunas adicionais de informações sobre cada item. |

Para exibir ou ajustar o volume e/ou detalhes de peso de um item, selecione o item na grade e use os campos na parte inferior da página.

## <a name="manage-estimated-costs"></a>Gerenciar custos estimados

Para exibir e editar as estimativas de custo criadas, acesse **Custo de entrega \> Consultas \> Estimativas de custo**. Na página **Estimativas de custo**, o painel de lista à esquerda mostra todas as estimativas de custo atuais. Você pode usar os botões no Painel de Ações para trabalhar com uma estimativa selecionada. Observe que não é possível criar uma nova estimativa de custo na página **Estimativas de custo**. Em vez disso, use a caixa de diálogo **Estimativa de custo** (**Custo de entrega \> Tarefas periódicas \> Estimativa de custo**), conforme descrito anteriormente neste tópico.

A página **Estimativas de custo** mostra como cada custo estimado foi derivado. Ela também mostra o custo de entrega estimado para cada item. Você pode modificar uma estimativa de custo alterando o preço de custo e/ou a moeda associada a várias mercadorias. Também é possível modificar os custos de viagem associados nos níveis de viagem e de contêiner. Ao usar esta página para modificar os custos, você será solicitado a recalcular os custos estimados para os itens na estimativa de custo. Quando estiver pronto, você poderá usar as estimativas para atualizar o preço de custo dos itens no modelo de custo.

### <a name="information-on-the-header"></a>Informações no cabeçalho

A parte superior da página **Estimativas de custo** mostra as configurações que foram usadas para gerar a estimativa de custo selecionada, conforme descrito na seção anterior. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>Configurações e botões na FastTab Linhas

A FastTab **Linhas** lista cada item incluído na estimativa atual. A tabela a seguir descreve o campo disponível para cada linha.

| Campo | Descrição |
|---|---|
| Conta de fornecedor | A conta de fornecedor associada ao item. |
| Número do item | O número do item. |
| Quantidade | O número de itens usados para determinar o custo. |
| Preço de custo | O preço de custo de acordo com o contrato comercial. Este valor é exibido na moeda local. |
| Medição | A medição individual. A unidade é aquela definida para o produto liberado aplicável. |
| Custo de entrega estimado | O custo de entrega estimado para a quantidade total. |
| Unitário | O custo de entrega estimado dividido pela quantidade. |
| (Outras dimensões) | Dependendo das dimensões selecionadas para exibição, você pode ver colunas adicionais de informações sobre cada item. |

A tabela a seguir descreve os botões disponíveis na barra de ferramentas na FastTab **Linhas**.

| Botão | Descrição |
|---|---|
| Adicionar | Adicione itens à estimativa de custo. Após adicionar itens, selecione **Recalcular** no Painel de Ações. |
| Remover | Remova itens da estimativa de custo. Após remover itens, selecione **Recalcular** no Painel de Ações. |
| Custos de viagem | Abra uma página na qual é possível exibir e editar vários tipos de custos de viagem para o item. |
| Estoque \> Exibir dimensões | Abra uma caixa de diálogo na qual você possa adicionar colunas de dimensão à grade ou remover colunas. |

### <a name="settings-on-the-general-fasttab"></a>Configurações na FastTab Geral

A FastTab **Geral** mostra detalhes do item selecionado no momento na FastTab **Linhas**. Grande parte dessas informações é repetida na guia **Linhas** e pode ser editada em qualquer lugar. No entanto, detalhes adicionais também estão disponíveis aqui. Os valores dos campos extras se baseiam na configuração do produto liberado aplicável.

### <a name="settings-on-the-dimension-fasttab"></a>Configurações na FastTab Dimensão

A FastTab **Dimensão** mostra valores para todas as dimensões de estoque disponíveis para o item selecionado na FastTab **Linhas**, independentemente das dimensões escolhidas para exibir ali. Os valores exibidos aqui são obtidos do modelo de estimativa de custo aplicável. Eles são opcionais no modelo de estimativa de custo.

### <a name="buttons-on-the-action-pane"></a>Botões no Painel de Ações

Você pode usar os botões no Painel de Ações da página **Estimativas de custo** para trabalhar com a estimativa de custo selecionada. A tabela a seguir descreve os botões disponíveis.

| Ação | Descrição |
|---|---|
| Consulta de Custo | Exiba todos os custos da viagem. Você pode exibir os custos no nível do item individual, conforme necessário. |
| Atualizar custo padrão | <p>Atualize o custo padrão usando a versão de custo padrão definida na página **Parâmetros de custo de entrega**. Você pode substituir essa versão.</p><p>**Observação:** se um item tiver várias dimensões de item (por exemplo, vários tamanhos, cores e configurações), mas essas dimensões não tiverem sido selecionadas para a previsão, o sistema criará um preço pendente para cada combinação.</p><p>**Importante:** o detalhamento de preço é criado e usado para determinar a variação de custo padrão por custo de entrega.</p> |
| Custos de viagem | Exiba e edite custos de viagem para todas as mercadorias na remessa. |
| Recalcular | Atualize os custos de entrega estimados após a atualização, adição ou remoção de custos de viagem. |
| Bloquear | Bloqueie o registro de estimativa de custo de forma que não seja possível fazer mais alterações. |

## <a name="item-cost-price-update"></a>Atualização de preço de custo de item

A tarefa periódica **Atualização do preço de custo do item** atualiza todas as estimativas de custo que correspondem aos filtros definidos quando você executa a tarefa. O efeito é semelhante ao de selecionar **Atualizar custo padrão** no Painel de Ações para uma única estimativa. No entanto, nesse caso, a atualização se aplica a todas as estimativas correspondentes.

Para executar a tarefa periódica, siga estas etapas.

1. Acesse **Custo de entrega \> Tarefas periódicas \> Atualização do preço de custo do item**.
1. Na caixa de diálogo **Atualizar preço de custo da estimativa**, defina os seguintes campos conforme necessário para limitar o escopo da atualização:

    - **Versão** – atualiza somente as estimativas que usam a versão de avaliação de custo especificada.
    - **Site** – atualiza somente as estimativas que usam o site especificado.
    - **Modelo de custo** – atualiza somente as estimativas que usam o modelo especificado.
    - **Porta de destino** – atualiza somente as estimativas que usam a porta "para".
    - **Data estimada** – atualize somente as estimativas com a data especificada.

1. Defina as opções nas FastTabs **Registros a serem incluídos** e **Executar em segundo plano** como de costume para tarefas periódicas.
1. Selecione **OK** para executar a tarefa.

> [!NOTE]
> Esta tarefa periódica só será executada com êxito se as seguintes informações estiverem disponíveis:
>
> - Cada produto relevante deve ter **Profundidade bruta**, **Largura bruta** e **Altura bruta** definidas.
> - Cada fornecedor relevante deve ter uma **Porta de origem** definida.
