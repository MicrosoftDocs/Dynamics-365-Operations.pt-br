---
title: Processamento de mercadorias em trânsito
description: Este tópico descreve como trabalhar com ordens de mercadorias em trânsito. Quando uma ordem ou viagem é configurada para usar o processamento de mercadorias em trânsito, as mercadorias podem ser faturadas antes de serem recebidas no depósito para consumo.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e85e3ba92b61e0208e1cf95d3f361d38772d83cb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571032"
---
# <a name="goods-in-transit-processing"></a>Processamento de mercadorias em trânsito

[!include [banner](../../includes/banner.md)]

Este tópico descreve como trabalhar com ordens de mercadorias em trânsito. Esse tipo de ordem é usado somente pelo módulo de **Custo de entrega**. Quando uma ordem ou viagem é configurada para usar o processamento de mercadorias em trânsito, não é necessário aguardar até as mercadorias serem recebidas no depósito para faturá-las. Em vez disso, as mercadorias são faturadas quando deixam o depósito ou a porta de origem do fornecedor, e os custos financeiros são reconhecidos quando a viagem começa. Essa funcionalidade permite que você se aproprie corretamente do estoque, pois as mercadorias sempre se tornam a propriedade da sua organização quando deixam a porta de remessa.

Quando as ordens de mercadorias em trânsito são usadas, os itens atualizados financeiramente são recebidos em um depósito provisório conhecido como um depósito de mercadorias em trânsito. As mercadorias permanecem neste depósito até que possam ser recebidas no depósito de destino final (ou seja, o depósito definido na linha de compra). Elas não podem ser removidas manualmente.

Enquanto os itens estiverem em trânsito, eles não estarão disponíveis no estoque e não poderão ser separados do estoque para uma entrega. No entanto, você pode exibir o estoque de mercadorias em trânsito. Você também pode usar as mercadorias para o planejamento mestre. Nesse caso, use a data de entrega confirmada na linha da ordem de compra como a data esperada quando o estoque estará disponível para consumo.

As seções a seguir descrevem a configuração necessária para processar o estoque e viagens usando o conceito e a funcionalidade de mercadorias em trânsito.

## <a name="terms-of-delivery"></a>Condições de entrega

Ao habilitar o módulo **Custo de entrega**, a entidade padrão *Condições de entrega* é aprimorada para dar suporte ao recurso mercadorias em trânsito.

Quando a opção **Gerenciamento de mercadorias em trânsito** estiver definida como *Sim* para o registro de condições de entrega aplicável, as mercadorias serão colocadas no depósito de mercadorias em trânsito. Esta ação será disparada somente se o recebimento do estoque não for processado antes de uma fatura ser processada. Quando as condições de entrega de uma ordem são definidas para usar mercadorias em trânsito, os usuários não podem mais lançar um recebimento de produtos para a ordem de compra. Se tentarem fazer isso, ocorrerá um erro. A mensagem de erro informa que eles devem usar a funcionalidade de mercadorias em trânsito para prosseguir.

Para trabalhar com as informações de condições de entrega para mercadorias em trânsito, acesse **Compras e fornecimento \> Configuração \> Distribuição \> Condições de entrega**. A tabela a seguir descreve os campos que o módulo **Custo de entrega** adiciona à página **Condições de entrega** para dar suporte à funcionalidade de mercadorias em trânsito. Ambos os campos estão na Guia Rápida **Geral**. Para obter mais informações sobre os outros campos desta página, consulte [Condições de entrega (formulário)](/dynamicsax-2012//terms-of-delivery-form).

| Campo | descrição |
|---|---|
| Porta de remessa obrigatória | Defina esta opção como *Sim* se uma porta de remessa for obrigatória quando as condições de entrega se aplicarem. |
| Gerenciamento de mercadorias em trânsito | Defina esta opção como *Sim* para usar o gerenciamento de mercadorias em trânsito quando as condições de entrega se aplicarem. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Depósitos para mercadorias em trânsito e subentregas

Ao habilitar o módulo **Custo de entrega**, a entidade padrão *Depósitos* é aprimorada para permitir que as ordens de compra sejam faturadas enquanto as mercadorias estão em um depósito de mercadorias em trânsito.

O custo de entrega adiciona dois novos tipos de depósito: *mercadorias em trânsito* e *subentregas*. Os depósitos de ambos os tipos podem ser selecionados como depósitos padrão. O processamento bem-sucedido de ordens de mercadorias em trânsito exige que o depósito de mercadorias em trânsito e o depósito de subentrega sejam configurados na página **Depósitos**. Em seguida, para cada depósito padrão que será usado com o custo de entrega e as mercadorias em trânsito, o depósito de mercadorias em trânsito e de subentrega deverão ser selecionados para os depósitos disponíveis de cada tipo.

O tipo de depósito *Mercadorias em trânsito* será associado ao depósito de mercadorias em trânsito e o depósito será usado para processar as mercadorias em ordens de mercadorias em trânsito antes que elas sejam recebidas no depósito de destino final. Em geral, um depósito de mercadorias em trânsito será suficiente para cada site se o site e o depósito forem as únicas dimensões de estoque usadas para gerenciamento de estoque. Se a dimensão de estoque de local também for usada, um depósito de mercadorias em trânsito deverá ser configurado para cada combinação de site e depósito; assim, o local padrão também poderá ser especificado.

Para trabalhar com configurações de mercadorias em trânsito para depósitos, acesse **Gerenciamento de estoque \> Configuração \> Divisão do estoque \> Depósitos**. A tabela a seguir descreve os campos que o módulo **Custo de entrega** adiciona à página **Depósitos** para dar suporte à funcionalidade de mercadorias em trânsito. Ambos os campos aparecem na Guia Rápida **Geral**. Para obter informações sobre outros campos na página, consulte [Depósitos (formulário)](/dynamicsax-2012//warehouses-form).

| Campo | Descrição |
|---|---|
| Depósito de mercadorias em trânsito | Identifique o depósito de mercadorias em trânsito que está relacionado ao depósito principal. |
| Depósito de entrega insuficiente | Identifique o depósito de subentrega que está relacionado ao depósito principal. |

## <a name="posting-rules-for-landed-cost"></a>Regras de lançamento para custo de entrega

O custo de entrega adiciona duas novas regras de lançamento que podem ser configuradas. Essas regras de lançamento são usadas para lançar financeiramente os valores da fatura da ordem de compra direta a fim de identificar a propriedade das mercadorias quando elas deixam o ponto de origem. Esse processo substitui o conceito de *mercadorias recebidas não faturadas*, pois as mercadorias são faturadas antes de serem recebidas. <!-- KFM: Add a link to the related scenario when available. -->

Para trabalhar com perfis de lançamento, acesse **Gerenciamento de estoque \> Configuração \> Lançamento \> Lançamento**. Na guia **Ordem de compra**, as seguintes regras de lançamento novas estão disponíveis:

- **Custo de entrega, mercadorias em trânsito** – especifique as regras de lançamento para o gerenciamento de mercadorias em trânsito.
- **Custo de entrega, acumulação de custos** – especifique as regras de lançamento para a provisão da conta de encargo.

## <a name="goods-in-transit-orders"></a>Ordens de mercadorias em trânsito

Você pode revisar e gerenciar ordens de mercadorias em trânsito diretamente no módulo **Custo de entrega**. Você pode processar ordens de mercadorias em trânsito diretamente na página **Ordens de mercadorias em trânsito**. Outra alternativa é a viagem associada às ordens de mercadorias em trânsito e processar toda a viagem, o contêiner de remessa ou o fólio. Quando você fatura uma viagem e cria ordens de mercadorias em trânsito, uma nova ordem de mercadorias em trânsito é criada para cada combinação de dimensões de estoque e estoque associada à linha da ordem de compra.

Para gerenciar mercadorias em trânsito, o custo de entrega usa um procedimento de duas etapas:

1. Um item é recebido quando uma fatura de estoque é processada e recebe um status *Em trânsito*.
1. A ordem de mercadorias em trânsito é processada na página **Ordens de mercadorias em trânsito** e, em seguida, recebida no depósito especificado na ordem de compra. Nesse ponto, o status é alterado para *Recebido*.

Para trabalhar com ordens de mercadorias em trânsito, acesse **Custo de entrega \> Tarefas periódicas \> Ordens de mercadorias em trânsito**.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Receber estoque do depósito de mercadorias em trânsito

É possível receber mercadorias de uma ordem de mercadorias em trânsito de várias formas, de acordo com a configuração do sistema.

### <a name="in-transit-receiving"></a>Recebimento em trânsito

Você pode receber em trânsito a partir de uma das seguintes páginas:

- Na página **Ordens de mercadorias em trânsito**, selecione a linha e, no Painel de Ações, selecione **Receber**.
- Na página **Todas as viagens**, selecione ou abra uma viagem. Em seguida, no Painel de Ações, na guia **Gerenciar** , no grupo **Mercadorias em trânsito**, selecione **Receber mercadorias em trânsito**.
- Na página **Todos os contêineres de remessa**, selecione ou abra um contêiner de remessa. Em seguida, no Painel de Ações, na guia **Gerenciar** , no grupo **Mercadorias em trânsito**, selecione **Receber mercadorias em trânsito**.
- Na página **Todos os fólios**, selecione ou abra um fólio. Em seguida, no Painel de Ações, na guia **Gerenciar** , no grupo **Mercadorias em trânsito**, selecione **Receber mercadorias em trânsito**.

> [!NOTE]
> O recebimento em trânsito é geralmente usado em situações em que locais e acompanhamento de lote/série não são usados.

### <a name="arrival-journal"></a>Diário de entrada

Você também pode receber mercadorias criando um diário de entrada. Você pode criar um diário de entrada diretamente na página viagens. As práticas recomendadas que sua organização estabeleceu determinam se o diário de entrada é usado para receber mercadorias.

1. Abra a viagem, o contêiner ou o fólio.
1. No Painel de Ações, na guia **Gerenciar**, no grupo **Funções**, selecione **Criar diário de entrada**.
1. Na caixa de diálogo **Criar diário de entrada**, defina os seguintes valores:

    - **Inicializar quantidade** – defina esta opção como *Sim* para definir a quantidade a partir da quantidade em trânsito. Se esta opção for definida como *Não*, nenhuma quantidade padrão será definida a partir das linhas de mercadorias em trânsito.
    - **Criar a partir de mercadorias em trânsito** - defina esta opção como *Sim* para obter quantidades das linhas em trânsito selecionadas para a viagem, o contêiner ou o fólio selecionado.
    - **Criar a partir das linhas da ordem** – defina esta opção como *Sim* para definir a quantidade padrão no diário de entrada das linhas da ordem de compra. A quantidade padrão no diário de entrada poderá ser definida dessa forma somente se a quantidade na linha da ordem de compra coincidir com a quantidade na ordem de mercadorias em trânsito.

1. Processe o diário de entrada conforme descrito em [Registrar recebimentos de itens com um diário de entrada de itens](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> O diário de entrada geralmente é usado em situações nas quais locais e acompanhamento de lote/série são usados, mas o gerenciamento de depósito não é usado.
>
> Os locais de recebimento padrão não deverão ser especificados nas linhas da ordem se uma localização de armazenamento for especificada no diário de entrada.

## <a name="warehouse-management"></a>Gerenciamento de depósito

Ao habilitar o módulo **Custo de entrega**, várias páginas no módulo **Gerenciamento de depósito** são modificadas para que o processamento de ordens (especificamente, processamento de mercadorias em trânsito) possa ser feito por meio do módulo **Custo de entrega**. Esta seção descreve os campos e os processos adicionados ao módulo **Gerenciamento de depósito**.

### <a name="mobile-device-menu-items"></a>Itens de menu do dispositivo móvel

É possível receber mercadorias usando um dispositivo móvel, desde que o menu do dispositivo móvel e o módulo **Gerenciamento de depósito** estejam configurados para receber mercadorias em uma ordem de mercadorias em trânsito. Esta seção descreve a configuração associada ao recebimento de mercadorias em trânsito.

Para configurar dispositivos móveis para o processamento de mercadorias em trânsito, acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.

O custo de entrega adiciona os seguintes processos de criação de trabalho aos itens de menu do dispositivo móvel para dar suporte ao processamento de mercadorias em trânsito:

- Recebimento do item de mercadorias em trânsito
- Recebimento e armazenamento de item de mercadorias em trânsito

As definições de configuração para esses processos se assemelham às configurações de [processos de recebimento de ordens de compra e criação de trabalhos de armazenamento](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work). No entanto, o processo *Recebimento e armazenamento de itens de mercadorias em trânsito* também adiciona o campo a seguir.

- **Habilitar contêiner de remessa completo** – se essa opção for definida como *Sim*, quando o trabalho de armazenamento for concluído, o aplicativo móvel Warehouse Management fornecerá uma opção adicional chamada **Contêiner de remessa completo**. Quando essa opção for selecionada, o trabalhador será solicitado a confirmar que o contêiner está completo. Nesse ponto, todos os recebimentos curtos serão processados como uma transação.

### <a name="location-directives"></a>Diretivas de localização

O custo de entrega adiciona um novo tipo de ordem de trabalho chamado *Mercadorias em trânsito*  à página **Diretivas de localização**. Esse tipo de ordem de trabalho deve ser configurado da mesma forma que os [tipos de ordem de trabalho da ordem de compra](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Modelos do trabalho

Esta seção descreve recursos que o módulo **Custo Landed** adiciona a modelos de trabalho.

#### <a name="goods-in-transit-work-order-type"></a>Tipo de ordem de trabalho de mercadoria em trânsito

O custo de entrega adiciona um novo tipo de ordem de trabalho chamado *Mercadorias em trânsito*  à página **Modelos de trabalho**. Esse tipo de ordem de trabalho deve ser configurado da mesma forma que os [Modelos de trabalho da ordem de compra](/dynamicsax-2012/appuser-itpro/create-a-work-template).

#### <a name="work-header-breaks"></a>Quebras de cabeçalho de trabalho

Os modelos de trabalho que têm um tipo de ordem de trabalho de *Mercadoria em trânsito* podem ser configurados para dividir os cabeçalhos de trabalho. Na página **Modelos de trabalho**, siga uma destas etapas:

- Na guia **Geral** do modelo, defina os máximos de cabeçalho de trabalho. Esses máximos funcionam da mesma forma que para modelos de trabalho de ordem de compra. (Para obter mais informações, consulte [modelos de trabalho de ordem de compra](/dynamicsax-2012/appuser-itpro/create-a-work-template).)
- Use o botão **Quebras de cabeçalho de trabalho** para definir quando o sistema deve criar novos cabeçalhos de trabalho, com base nos campos que são usados para separação. Por exemplo, para criar um cabeçalho de trabalho para cada ID de contêiner, selecione **Editar consulta** no Painel de Ações e, depois, adicione o campo **ID de contêiner** à guia **Classificação** do editor de consultas. Os campos adicionados à guia **Classificação** estão disponíveis para seleção como *campos de agrupamento*. Para configurar campos de agrupamento, selecione **Quebras de cabeçalho de trabalho** no Painel de Ações. Para cada campo a ser usado como um campo de agrupamento, marque a caixa de seleção na coluna **Agrupar por este campo**.

O custo Landed [cria uma transação em excesso](over-under-transactions.md) se a quantidade registrada excede a quantidade original da ordem. Quando um cabeçalho de trabalho é concluído, o sistema atualiza o status das transações de estoque para a quantidade da ordem principal. No entanto, ele atualiza primeiro a quantidade vinculada à transação em excesso depois que o principal é completamente comprado.

Se você cancelar um cabeçalho de trabalho para uma transação em excesso que já foi registrada, a transação em excesso será reduzida primeiro pela quantidade cancelada. Depois que a transação em excesso é reduzida a uma quantidade de 0 (zero), o registro é removido e todas as quantidades adicionais são canceladas em relação à quantidade da ordem principal.
