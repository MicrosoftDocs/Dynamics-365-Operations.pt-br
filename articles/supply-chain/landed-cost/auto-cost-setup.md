---
title: Configuração de custos automáticos
description: Este tópico descreve como configurar regras de custo para vários níveis de viagem de entrada. Com base nessas regras, o sistema calcula os custos e os adiciona automaticamente. Portanto, os usuários não precisam adicionar os custos manualmente.
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e1db6c1da4ab311cc3e304d4f422004d5b8423d76f24c8bc8e528f742b1f42fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736758"
---
# <a name="auto-costs-setup"></a>Configuração de custos automáticos

[!include [banner](../../includes/banner.md)]

Você pode usar a página **Custos automáticos** para configurar regras de custo para várias áreas de custo (como viagens, contêineres de remessa, fólios, ordens de compra, itens ou linhas da ordem de transferência). Com base nas regras e nos campos que os usuários selecionam ao criarem registros para uma das áreas de custo, o sistema calcula os custos e os adiciona automaticamente. Portanto, os usuários não precisam adicionar os custos manualmente.

Para trabalhar com custos automáticos, acesse **Custo de entrega \> Configuração de custos \> Custos automáticos**. Em seguida, configure as regras de custo automático conforme descrito no restante deste tópico.

## <a name="work-with-cost-areas"></a>Trabalhar com áreas de custo

Os custos automáticos funcionam como contratos comerciais ou encargos diversos automáticos. Cada registro de custo automático pertence a um nível de custo específico. Use o campo **Área de custo** no painel de lista da página **Custos automáticos** para selecionar a área de custo com a qual você deseja trabalhar. O painel de lista mostra somente os custos automáticos que pertencem à área de custo selecionada no momento. Qualquer custo automático criado pertencerá à área de custo selecionada no momento.

As áreas de custo permitem que o sistema divida os custos nas linhas da ordem de compra em uma área de custo. Por exemplo, o valor do custo de um contêiner de remessa será dividido para todos os produtos desse contêiner de remessa. Se houver dois ou mais contêineres de remessa, o mesmo tipo de custo poderá ser especificado para cada contêiner de remessa. Portanto, o tipo de contêiner pode ser usado para encontrar o custo automático correto.

## <a name="buttons-on-the-action-pane"></a>Botões no Painel de Ações

A tabela a seguir descreve os botões disponíveis no Painel de Ações da página **Custos automáticos**.

| Botão | descrição |
|---|---|
| Edição | Edite um custo automático existente. |
| Criar | Crie um custo automático. |
| Delete | Exclua um custo automático. |
| Copiar de | Crie um registro de custo automático com base em um registro existente. Em seguida, você poderá editar o novo registro livremente. Este botão ajuda você a criar custos automáticos rapidamente. |
| Exibir dimensões | Abra uma caixa de diálogo na qual você pode selecionar as dimensões de estoque que são mostradas para as transações de custo exibidas. Se você desmarcar as caixas de seleção, serão exibidas menos dimensões de estoque para as transações de custo. Portanto, menos detalhes serão exibidos para a transação. Se uma dimensão de estoque for especificada para um custo automático, o custo automático será aplicado somente quando a dimensão de estoque especificada for usada para o item em uma viagem. |

## <a name="settings-on-the-header"></a>Configurações no cabeçalho

A combinação de configurações na seção de cabeçalho determina quando e como um custo automático específico é adicionado a uma viagem. Um custo automático será aplicado a uma viagem, a um contêiner de remessa ou a um fólio somente quando os detalhes do custo automático coincidirem com os detalhes no cabeçalho da área de custo. A soma de todos os custos automáticos correspondentes determina o custo de entrega estimado de uma viagem. Esse custo é dividido entre todos os itens no navio ou na viagem.

A tabela a seguir descreve todos os campos que podem ser exibidos na seção de cabeçalho. No entanto, os campos específicos que estão disponíveis variam, dependendo da área de custo e das dimensões de exibição que estão selecionadas no momento.

| Campo | descrição |
|---|---|
| **Código da conta** | <p>Selecione um dos seguintes valores:</p><ul><li>**Tabela** — a regra de custo se aplica somente a um fornecedor específico.</li><li>**Grupo** — a regra de custo se aplica somente a um grupo de fornecedores específico. O sistema procurará pelo [grupo de tipos de custo do fornecedor](costing-parameters-setup.md) que está associado ao registro do fornecedor.</li><li>**Todos** — a regra de custo se aplica a todos os fornecedores. |
| **Empresa transportadora** | Selecione o fornecedor ou grupo de fornecedores ao qual a regra de custo se aplica. Esse campo estará disponível somente se você selecionar *Tabela* ou *Grupo* no campo **Código da conta**. |
| **Agente alfandegário** | Selecione o fornecedor ou grupo de fornecedores ao qual a regra de custo se aplica. Esse campo estará disponível somente se você selecionar *Tabela* ou *Grupo* no campo **Código da conta**. |
| **Código do item** | <p>Selecione um dos seguintes valores:</p><ul><li>**Tabela** — a regra de custo se aplica somente a um item específico.</li><li>**Grupo** — a regra de custo se aplica somente a um grupo de itens específico. O sistema procurará pelo [grupo de tipos de custo do item](costing-parameters-setup.md) que está associado ao registro do item.</li><li>**Todos** — a regra de custo se aplica a todos os itens.|
| **Relação de item** | Selecione o item ou grupo de itens ao qual a regra de custo se aplica. Esse campo estará disponível somente se você selecionar *Tabela* ou *Grupo* no campo **Código do item**. |
| **Modo de entrega** | Selecione o modo de entrega (como Via área ou Via marítima ) ao qual a regra de custo se aplica. |
| **Tipo de contêiner** | O tipo de contêiner de remessa em que as mercadorias serão enviadas. Um custo automático só poderá ser aplicado a uma viagem se o tipo de contêiner da configuração de custo automático coincidir com o tipo de contêiner da viagem. |
| **Do porto** e **Para o porto** | O porto de origem ("de") e o porto de destino ("para") da viagem. (Alguns contêineres de remessa podem ter diferentes portos de destino porque a viagem pode parar em vários portos.) Um custo automático pode ser aplicado a uma viagem somente se os portos de origem e de destino na configuração de custo automático coincidirem com os portos de origem e de destino da viagem. |
| **Número de custo automático** | O identificador exclusivo da regra de custo automático. O valor deste campo é gerado automaticamente com base na sequência numérica configurada na página **Parâmetros de custo de entrega**. |
| **Dimensões de estoque** | Algumas áreas de custo permitem que você inclua uma ou mais dimensões de item no cabeçalho (como tamanho, cor, depósito e número do lote). Selecione **Exibir dimensões** no Painel de Ações para selecionar as dimensões que devem ser incluídas. |

## <a name="settings-on-the-lines-fasttab"></a>Configurações na FastTab Linhas

Na FastTab **Linhas**, adicione uma linha para cada moeda que pode ser usada quando um custo é aplicado a uma linha da ordem de compra em uma viagem. 

Para itens e ordens de compra, o sistema fará a correspondência entre a moeda de cada linha da ordem de compra e as moedas especificadas na FastTab **Linhas**. Ele aplicará somente o valor de custo definido para a linha ou o item correspondente. Se nenhuma linha estiver configurada para a moeda da linha ou do item, o custo automático não será aplicado a essa linha ou item.

Para outros tipos de áreas de custo, todas as linhas na FastTab **Linhas** se aplicarão a cada viagem, contêiner de remessa, fólio ou linha da ordem de transferência que coincidir com os valores estabelecidos no cabeçalho.

A tabela a seguir descreve todos os campos que podem ser exibidos em cada linha. No entanto, os campos específicos que estão disponíveis variam, dependendo da área de custo que está selecionada no momento.

| Campo | descrição |
|---|---|
| **Moeda** | Selecione a moeda à qual a linha se aplica. Essa moeda está relacionada à ordem de compra. Quando o sistema tenta encontrar os custos automáticos que devem ser aplicados a uma viagem e a suas linhas de viagem, ele selecionará a linha que tenha a mesma moeda da ordem de compra. Este campo só estará disponível quando o campo **Área de custo** estiver definido como *Ordem de compra* ou *Item*. |
| **Código de tipo de custo** | O tipo de custo. |
| **Método de divisão proporcional** | <p>O método usado para distribuir custos para as linhas. As opções a seguir estão disponíveis:</p><ul><li><p>**Porcentagem** — o valor do campo **Valor do custo** é uma porcentagem que se aplica ao valor total das mercadorias.</p><p>Por exemplo, se o campo **Valor do custo** for definido como *10* e o valor total das mercadorias for R$ 800, o valor de custo será R$ 80 (= R$ 800 × 10%).</p></li><li>**Quantidade** — o custo será dividido com base na quantidade de mercadorias.</li><li>**Valor** — o custo será dividido com base no valor das mercadorias.</li><li>**Volume** — o custo será dividido com base no volume das mercadorias. O volume é especificado no item mestre.</li><li>**Peso** — o custo será dividido com base no peso das mercadorias. O peso é especificado no item mestre.</li><li>**Volumétrico** — o custo será dividido com base na medida volumétrica das mercadorias.</li><li><p>**Medida** — essa opção permite que uma medida seja especificada no módulo **Custo de entrega**. Geralmente, ela é usada por organizações que não sabem o volume ou o peso individual das mercadorias, mas que requerem uma divisão mais precisa do que as opções **Valor** e **Quantidade** permitem. O agente ou o controlador de frete fornecerá à organização a medida de peso ou cúbica, no nível do item ou o nível da ordem de compra.</p><p>Por exemplo, o frete marítimo é igual a R$ 900. O item A tem peso de 800 quilogramas (kg) e volume de 2 metros cúbicos (m³). O item B tem peso de 100 quilogramas (kg) e volume de 1 metro cúbico (m³). Estes são os resultados quando os custos são divididos por peso:</p><ul><li>Item A = R$ 800</li><li>Item B = R$ 100</li></ul><p>Estes são os resultados quando os custos são divididos por volume:</p><ul><li>Item A = R$ 600</li><li>Item B = R$ 300</li></ul><p>**Observação:** quando o campo **Método de divisão** é definido como *Medida*, o sistema usa as medidas inseridas para a área de custo (o contêiner de remessa) e as linhas. Essas medidas não precisam necessariamente ser a soma do total esperado. No entanto, se for necessário que elas sejam a soma do total esperado, você poderá fazer uma verificação usando as estatísticas para revisar o total das medidas. A configuração do aviso de medida e a atualização automática das medidas no nível de remessa ou de contêiner são definidas no cabeçalho de viagem.</p></li></ul> |
| **Data Inicial** | Especifique o início do intervalo de datas para os custos, se houver um intervalo de datas. Esta data é a primeira data em que o custo automático será aplicado. |
| **Data Final** | Especifique o fim do intervalo de datas para os custos, se houver um intervalo de datas. Esta data é a última data em que o custo automático será aplicado. |
| **Categoria** | <p>Selecione o método que deve ser usado para calcular o custo. As opções a seguir estão disponíveis:</p><ul><li>**Fixo** — o custo será dividido com base no método de divisão.</li><li>**Peças** — o custo será alocado por peça. Portanto, o método de divisão não será usado.</li><li>**Porcentagem** — uma porcentagem do valor das mercadorias será adicionada. Portanto, o método de divisão não será usado.</li><li>**Taxa** — selecione essa opção se houver detalhamentos de quantidade. O campo **Método de divisão** para a linha deve ser definido como *Medida*.</li><ul> |
| **Dividido por quantidade** | <p>Marque esta caixa de seleção para tornar o botão **Divisões de quantidade** disponível na FastTab **Linhas**. As divisões de quantidade permitem que o custo seja dividido e que os diferentes custos variem, dependendo da quantidade na linha da ordem de compra da viagem. Essa funcionalidade geralmente é usada quando o modo de entrega é por via área. O campo **Categoria** para a linha deve ser definido como *Taxa*.</p><p>A quantidade pertence à opção selecionada no campo **Método de divisão**. O valor do custo será até a quantidade inserida no campo **Valor do custo**.<p>Por exemplo, as quantidades de 45 a 100 kg produzem um encargo de R$ 6,00 por medida (como kg/m³). As quantidades que excedem 100 kg produzem um encargo de R$ 5,50 por medida (como kg/m³).</p> |
| **Valor de custo** | Insira o valor do custo. |
| **Código de moeda de custo** | Selecione a moeda do custo. |
| **Grupo de impostos do item** | Selecione o código do imposto para o custo. |
| **Custo mínimo** | <p>Este campo se aplica somente se a caixa de seleção **Dividido por quantidade** estiver marcada. Se a medida não atingir esse valor, o valor mínimo será selecionado, independentemente dos custos especificados na página **Divisões de quantidade**.<p>Por exemplo, as quantidades de 0 a 45 kg produzem um encargo de R$ 6 por medida (kg/m³). As quantidades de 46 a 100 kg produzem um encargo de R$ 5,50 por medida (kg/m³). Se 2 kg forem enviados, a divisão de quantidade criará um valor de custo de R$ 12. No entanto, se o campo **Custo mínimo** estiver definido como *R$ 100*, o custo final será R$ 100.</p> |
| **Agregação** | Marque essa caixa de seleção para permitir que os usuários movam este custo do nível do contêiner de remessa para o nível de viagem. Nesse caso, os custos podem ser calculados automaticamente no nível do contêiner de remessa. No entanto, eles também podem ser combinados e divididos entre todos os itens em todos os contêineres em uma viagem, em vez de todos os itens nos contêineres individuais de remessa. |
| **Tipo de custo vinculado** | <p>Vincule a linha atual a outra linha no mesmo registro de custo automático especificando o valor do **Código do tipo de custo** da linha à qual você deseja vincular. Essa funcionalidade está disponível somente quando o campo **Categoria** para a linha atual está definido como *Porcentagem*. Quando a linha atual está vinculada a outra linha, o custo da linha atual será baseado no custo da outra linha.</p><p>Por exemplo, frete é R$ 1.000 e você deseja que a sobretaxa de combustível seja 10% do custo do frete. Nesse caso, a linha deve ter um valor de **Categoria** de *Porcentagem*, um valor de **Valor do custo** de *10%* e um valor de **Tipo de custo vinculado** de *Frete*.</p> |
| **Ajuste de valor** e **Valor do ajuste** | <p>Use esses campos para ajustar o valor de vários valores de porcentagem. Eles só estarão disponíveis quando o campo **Área de custo** estiver definido como *Item*.</p><p>Custos diferentes podem ser configurados para componentes diferentes de um item. Um componente de um item pode ter uma porcentagem de custo diferente da de outros componentes do item. Às vezes, essa abordagem é necessária para avaliar uma parte específica das mercadorias com taxas diferentes.</p><p>Por exemplo, o imposto para um relógio é calculado com duas taxas: um componente do relógio tem uma taxa de imposto de 10% e um segundo componente tem uma taxa de imposto de 2%. Nesse caso, os custos serão divididos entre os dois componentes.</p><p>O custo é calculado para o item, mas o valor do custo é ajustado pelo valor dos componentes que tenham a categoria de custo diferente. Em seguida, o custo dos componentes restantes pode ser calculado usando o valor pelo qual o cálculo anterior foi ajustado.</p><p>Por exemplo, o componente A do relógio tem um custo de R$ 9,50 e um imposto de 10%, e o componente B tem um custo de R$ 0,50 e um imposto de 2%. Portanto, o total é de R$ 10,00. A primeira entrada é para a linha de 10%. Ela usa os seguintes valores:</p><ul><li>**Categoria:** *Porcentagem*</li><li>**Valor do custo:** *10*</li><li>**Valor ajustado:** *Ajustar por*</li><li>**Valor ajustado:** *-0,50*</li></ul><p>Esta configuração especifica que o custo do item (R$ 10) deve ser reduzido em R$ 0,50 (o preço do componente B) antes que um encargo de imposto de 10% seja calculado. Portanto, 10% serão aplicados a R$ 9,50.</p><p>A segunda entrada é para a linha de 2% (o valor de R$ 0,50 usado para ajustar a entrada anterior). Ela usa os seguintes valores:</p><ul><li>**Categoria:** *Porcentagem*</li><li>**Valor do custo:** *2*</li><li>**Valor ajustado:** *Usar*</li><li>**Ajuste:** *0,50*</li></ul><p>Essa configuração calcula o restante do imposto a ser pago no componente B.</p> |
