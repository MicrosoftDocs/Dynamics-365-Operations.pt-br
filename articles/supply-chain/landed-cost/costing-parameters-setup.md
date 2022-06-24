---
title: Configuração de valores de parâmetro de custos
description: Ao configurar o módulo de Custo de entrega, é possível definir vários conjuntos de valores comuns que estarão disponíveis quando você selecionar tipos específicos de valores de parâmetro de custo em outras partes do aplicativo. Este artigo explica como configurar esses conjuntos de valores.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ca3633cd8a3fb053bda597b968003685aa2326ef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852321"
---
# <a name="costing-parameter-values-setup"></a>Configuração de valores de parâmetro de custos

[!include [banner](../../includes/banner.md)]

Ao configurar o módulo de **Custo de entrega**, é possível definir vários conjuntos de valores comuns e as configurações relacionadas por valor. Esses valores ficarão disponíveis quando você selecionar tipos específicos de valores de parâmetro de custo em outras partes do aplicativo. Este artigo explica como configurar esses conjuntos de valores.

## <a name="set-up-cost-type-codes"></a>Configurar códigos de tipo de custo

Os códigos de tipo de custo determinam o tipo de custo incorrido quando as mercadorias são entregues no depósito, ou os custos de entrega da viagem. Embora normalmente aumentem o valor das mercadorias, eles também podem ser usados para acumular valores no razão. Os ajustes contábeis são usados quando um custo é acumulado ao longo do tempo ou durante uma série de viagens e compensado em uma única transação.

> [!NOTE]
> Se a tabela de tipos de custo for compartilhada entre entidades legais, o plano de contas também deverá ser compartilhado entre entidades legais. Caso contrário, as transações de lançamento não funcionarão corretamente.

Para configurar os códigos de tipo de custo, acesse **Custo de entrega \> Configuração de custos \> Códigos de tipo de custo**. Você pode usar os botões no Painel de Ações para criar novos códigos de tipo de custo, editar códigos existentes ou excluir um tipo de custo selecionado.

A tabela a seguir descreve os campos disponíveis para cada código de tipo de custo.

| Campo | descrição |
|---|---|
| Código de tipo de custo | Insira um nome para o código de tipo de custo. |
| descrição | Insira uma descrição para o código de tipo de custo. |
| Usar taxa de remessa | Defina esta opção como *Sim* se a taxa de câmbio da viagem (às vezes referida como taxa de gerenciamento) deve ser usada para calcular o valor desses custos. Nesse caso, a taxa de remessa será usada no lugar da taxa de câmbio padrão ou pontual para trocar faturas de moeda estrangeira. |
| Categoria de relatórios | Esse campo estabelece uma categoria de relatório para o tipo de custo. Os relatórios podem ser impressos por categorias de relatório ou por tipo de custo. |
| Tipo de débito | Selecione se o tipo de custo deve debitar o item, a conta contábil ou o fornecedor. |
| Lançamento de débito | Se o campo **Tipo de débito** for definido como *Conta contábil*, selecione a descrição do lançamento. |
| Conta de débito | Se o campo **Tipo de débito** for definido como *Conta contábil*, selecione a conta contábil a ser usada. |
| Tipo de crédito | Selecione se esse tipo de custo deve creditar o item, a conta contábil ou o fornecedor. |
| Lançamento de crédito | Se o campo **Tipo de crédito** for definido como *Conta contábil*, selecione a descrição do lançamento. |
| Conta de crédito | Se o campo **Tipo de crédito** for definido como *Conta contábil*, selecione a conta contábil a ser usada. |
| Conta de compensação | Selecione a conta de compensação para o tipo de custo. Recomendamos que você especifique uma conta de compensação separada por tipo de custo para ajudar na reconciliação. |
| Tipo de lançamento de custo padrão | Se você estiver usando custos padrão, selecione a descrição do lançamento. |
| Conta de variação de custo padrão | <p>Se você estiver usando custos padrão, a conta especificada aqui será usada para lançar qualquer variação. Essa conta usa a divisão de custo de entrega na página **Preços do item**. Essa divisão é criada usando a rotina periódica para atualizar preços.</p><p>Por exemplo, o custo padrão de um item é R$ 15,00, o FOB é R$ 13,00 e o frete é R$ 2,00. Quando a fatura é recebida para o estoque, o item é recebido a R$ 15,00, mas há uma variação de preço padrão de R$ 2,00 para o item, pois o FOB real é R$ 13,00. Essa variação é lançada na conta de variação de preço padrão que é configurada no perfil de lançamentos de itens. Como o frete previsto é R$ 2,00, não há variação quando a fatura de estoque é lançada. No entanto, quando a fatura do frete é recebida, o frete é R$ 2,50 por unidade. Portanto, uma variação de R$ 0,50 é lançada no custo especificado. |
| Conta de variação da média móvel | <p>Se você estiver usando custo de média móvel, a conta especificada aqui será usada para lançar qualquer variação.</p><p>Por exemplo, o frete previsto é R$ 2,00. No entanto, quando a fatura do frete é recebida, o frete é R$ 2,50 por unidade. Portanto, uma variação de R$ 0,50 deve ser lançada.</p><p>Quando a opção **Lançar ajustes como variação** estiver definida como *Sim* na página **Parâmetros de custo de entrega**, todas as variações entre os custos de remessa estimados e reais serão lançadas na conta variação da média móvel especificada aqui. Quando a opção **Lançar ajustes como variação** estiver definida como *Não*, a funcionalidade padrão será usada e a variação será aplicada ao estoque ou à conta de variação da média móvel especificada aqui, dependendo do estoque disponível.</p> |
| Conta de provisão de encargo | Selecione a conta usada para acumular as estimativas de custo quando a fatura de compra é lançada. Este campo será usado somente quando a opção **Usar conta de competência de encargo do tipo de custo** estiver definida como *Sim* na FastTab **Custos** na guia **Geral** da página **Parâmetros de custo de entrega**. |
| Conta de encargo | Selecione a conta usada para capturar os custos de transporte de entrada que foram faturados por um fornecedor. O valor é lançado como um débito. A contrapartida é a conta de variação de estoque. Esse lançamento será usado somente quando a opção **Lançar na conta de encargos do razão** estiver definida como *Sim* na página **Parâmetros de contas a pagar**. |
| Conta de variação | A conta que será usada para compensar o acúmulos de encargos quando a fatura de compra for lançada. Este campo será usado somente quando a opção **Usar conta de competência de encargo do tipo de custo** estiver definida como *Sim* na FastTab **Custos** na guia **Geral** da página **Parâmetros de custo de entrega**. |

## <a name="vendor-cost-type-groups"></a>Grupos de tipos de custo de fornecedor

Grupos de tipos de custo de fornecedor ajudam a determinar como os encargos de *custos automáticos* são encontrados e aplicados a uma viagem. Os fornecedores com custos de importação semelhantes são vinculados. Por exemplo, todos os fornecedores de mercados emergentes pagam a mesma porcentagem de imposto para o mesmo tipo de produto adquirido de um mercado estabelecido.

Você pode manter grupos de tipos de custo de fornecedor acessando **Custo de entrega \> Configuração de custos \> Grupos de tipos de custo de fornecedor**. A página **Grupos de tipos de custo de fornecedor** fornece uma grade que lista todos os grupos de tipos de custo de fornecedor existentes. Você pode usar os botões no Painel de Ações para adicionar, remover e editar linhas na grade.

A tabela a seguir descreve os campos disponíveis em cada linha na grade.

| Campo | descrição |
|---|---|
| Grupos de tipos de custo de fornecedor | Insira um nome exclusivo para o grupo de tipos de custo de fornecedor (como *Mercados emergentes*). |
| descrição | Insira uma descrição do grupo de tipos de custo de fornecedor. Essa descrição pode fornecer detalhes sobre o nível ou o tipo de encargo associado ao grupo de fornecedores. |

## <a name="item-cost-type-groups"></a>Grupos de tipos de custo de item

Grupos de tipos de custo de item ajudam a determinar como os encargos de *custos automáticos* são encontrados e aplicados a uma viagem. Itens semelhantes são vinculados. Por exemplo, todos os itens com uma taxa de imposto de 5% podem pertencer a um grupo de tipos de custo específico.

Você pode manter grupos de tipos de custo de item acessando **Custo de entrega \> Configuração de custos \> Grupos de tipos de custo de item**. A página **Grupos de tipos de custo de item** fornece uma grade que lista todos os grupos de tipos de custo de item existentes. Você pode usar os botões no Painel de Ações para adicionar, remover e editar linhas na grade.

A tabela a seguir descreve os campos disponíveis em cada linha na grade.

| Campo | descrição |
|---|---|
| Grupos de tipos de custo de item | Insira um nome exclusivo para o grupo de tipos de custo de item (como *Imposto de 5%*). |
| descrição | Insira uma descrição do grupo de tipos de custo de item. Essa descrição pode fornecer detalhes sobre o nível ou o tipo de encargo associado ao grupo de itens. |

> [!NOTE]
> O tipo de custo do item é vinculado ao item por meio do campo **Grupo de tipos de custo** na FastTab **Compra** da página **Produto liberado** do item.

## <a name="transfer-order-cost-type-groups"></a>Grupos de tipos de custo da ordem de transferência

Grupos de tipos de custo da ordem de transferência ajudam a determinar como os encargos de *custos automáticos* são encontrados. Itens semelhantes são vinculados. Por exemplo, todos os itens com uma taxa de imposto de 7% podem pertencer a um grupo de tipos de custo específico.

Você pode manter grupos de tipos de custo da ordem de transferência **Custo de entrega \> Configuração de custos \> Grupos de tipos de custo da ordem de transferência**. A página **Grupos de tipos de custo da ordem de transferência** fornece uma grade que lista todos os grupos de tipos de custo da ordem de transferência existentes. Você pode usar os botões no Painel de Ações para adicionar, remover e editar linhas na grade.

A tabela a seguir descreve as configurações disponíveis em cada linha na grade.

| Campo | descrição |
|---|---|
| Grupos de tipos de custo da ordem de transferência | Insira um nome exclusivo para o grupo de tipos de custo da ordem de transferência (como *Imposto de 7%*). |
| descrição | Insira uma descrição do grupo de tipos de custo da ordem de transferência. Essa descrição pode fornecer detalhes sobre o nível ou o tipo de encargo associado ao grupo de tipos de custo da ordem de transferência. |

> [!NOTE]
> O tipo de custo da ordem de transferência é vinculado ao item por meio do campo **Grupo de tipos de custo da ordem de transferência** na FastTab **Compra** da página **Produto liberado** do item.

## <a name="cost-templates"></a>Modelos de custo

Use os modelos de custo para definir valores padrão para as configurações que os usuários que estiverem obtendo a estimativa de custo talvez não saibam. Os modelos de custo podem ajudar a reduzir a complexidade no processo de estimativa, minimizando as seleções que os usuários devem fazer para obter uma estimativa precisa.

Para trabalhar com modelos de custo, acesse **Custo de entrega \> Configuração de custos \> Modelos de custo**. Na página **Modelos de custo**, o painel de lista à esquerda mostra todos os modelos de custo atuais. Você pode usar os botões no Painel de Ações para adicionar, remover e editar modelos.

A tabela a seguir descreve as configurações disponíveis para cada modelo.

| Campo | descrição |
|---|---|
| Modelo de custo | Insira um nome exclusivo para o modelo de custo. O nome costuma descrever o fator ou multiplicador de custo para o modelo. |
| descrição | Insira uma descrição do modelo de custo. |
| Empresa transportadora | Selecione a conta do fornecedor da empresa transportadora a ser associada ao modelo de custo. |
| Modo de entrega | Selecione o modo de entrega que o modelo de custo deverá usar quando o custo estimado de um item for calculado. Esse campo ajudará a determinar os custos automáticos associados às mercadorias na estimativa de custo. |
| Tipo de contêiner de remessa | Selecione o tipo de contêiner de remessa a ser associado ao modelo de custo. Esse campo ajudará a determinar os custos automáticos associados às mercadorias na estimativa de custo. |
| Agente alfandegário | Selecione o corretor de alfândega (fornecedor) a ser associado ao modelo de custo. Esse campo ajudará a determinar os custos automáticos associados à estimativa de custo. |
| Fator | Insira um fator a ser aplicado à estimativa de custo final das mercadorias. Por exemplo, para adicionar 10% à estimativa de custo calculada, digite *1,10*. |

## <a name="volumetric-divisors"></a>Divisores volumétricos

Os divisores volumétricos são usados para calcular o peso volumétrico. Cada empresa de transporte/frete formula seus próprios divisores volumétricos. Além disso, os divisores de uma empresa normalmente variam, dependendo do modo de entrega. Por exemplo, via área e via marítima geralmente têm divisores muito diferentes. Uma empresa também pode tornar suas regras mais complexas, dependendo de onde ela envia as remessas. O sistema usa a seguinte fórmula para encontrar o peso volumétrico: VolumetricWeight = Volume ÷ VolumetricDivisor.

Por exemplo, um pacote enviado por via área tem um volume de 3 metros cúbicos (m³). A empresa cobra por peso volumétrico e aplica um divisor volumétrico de 6. Esse divisor é dividido pelo volume para determinar o peso volumétrico. Portanto, o peso volumétrico desse exemplo é 3 ÷ 6 = 0,5 quilogramas (kg).

Para configurar divisores volumétricos, acesse **Custo de entrega \> Configuração de custos \> Divisores volumétricos**. A página **Divisores volumétricos** fornece uma grade que lista todos os divisores volumétricos existentes. Você pode usar os botões no Painel de Ações para adicionar, remover e editar linhas na grade.

A tabela a seguir descreve os campos disponíveis em cada linha na grade.

| Campo | descrição |
|---|---|
| Empresa transportadora | Selecione a conta do fornecedor da empresa transportadora associada ao divisor volumétrico. |
| Código de tipo de custo | Selecione o código do tipo de custo associado ao divisor volumétrico. Use esse campo para colocar tipos de custo em buckets de relatórios. Os relatórios podem ser impressos por categorias de relatório ou por tipo de custo. |
| Porta de origem | Selecione o porto de origem ao qual o divisor volumétrico se aplica. |
| Divisor volumétrico | Insira o valor do divisor volumétrico que se aplica à linha. O volume de cada pacote será dividido pelo valor inserido aqui para determinar o peso volumétrico desse pacote. |

> [!NOTE]
> O sistema usará o valor máximo entre **peso real** e **peso volumétrico**.
