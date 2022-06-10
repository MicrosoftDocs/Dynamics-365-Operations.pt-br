---
title: Perguntas frequentes sobre o custo de estoque
description: Este tópico fornece respostas a algumas perguntas frequentes sobre custo de estoque no Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 45f65bd4a5cfb9bd0c4eb03ceb56eca452f6ec95
ms.sourcegitcommit: cbe9493d479f96f271d94599ec1b85131b26169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "8809279"
---
# <a name="inventory-costing-faq"></a>Perguntas frequentes sobre o custo de estoque

[!include [banner](../includes/banner.md)]

Este tópico fornece respostas a algumas perguntas frequentes sobre custo de estoque no Microsoft Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Fechamento, ajuste e recálculo de estoque

### <a name="is-the-inventory-close-required"></a>O fechamento de estoque é necessário?

Se você planeja usar o recurso de arquivamento de estoque, o fechamento de estoque é necessário. Se você não planeja usar o recurso de arquivamento de estoque, é altamente recomendável que você ainda execute o fechamento de estoque, independentemente dos modelos de custos usados.

### <a name="how-often-should-the-inventory-close-be-run"></a>Com que frequência o fechamento de estoque deve ser executado?

O fechamento de estoque deve ser executado, pelo menos, uma vez por período contábil. Por exemplo, se o seu razão estiver definido como um calendário fiscal baseado nos meses, você deve executar o fechamento de estoque uma vez por mês.

### <a name="is-the-inventory-recalculation-required"></a>O recálculo de estoque é necessário?

Não, o recálculo de estoque não é necessário. Se usar um modelo de custos periódicos, como primeiro a entrar, primeiro a sair (PEPS), último a entrar, primeiro a sair (UEPS), média ponderada, você deverá considerar cuidadosamente se executará o recálculo de estoque. Ele pode fornecer custos mais precisos nos modelos heurísticos que você selecionou.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>Com que frequência o recálculo de estoque deve ser executado?

Se estiver planejando executar o recálculo de estoque, recomendamos que você considere executá-lo diariamente como um processo em lote. Se a sua organização não requer o relatório requente dos valores de estoque para os modelos de custos periódicos, você pode considerar a execução do cálculo de estoque com menos frequência.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>Quando devo usar o ajuste de estoque disponível na página Fechamento e ajuste?

O ajuste de estoque disponível pode ser executado somente após a conclusão de um fechamento de estoque. Ele geralmente é executado na data após o último fechamento. O ajuste de estoque disponível pode ajustar somente o estoque que ainda está disponível a partir da data em que o ajuste foi executado.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>Quando devo usar o ajuste de transação de estoque na página Fechamento e ajuste?

Você deve usar o ajuste de transação de estoque antes de executar um fechamento de estoque. Isso normalmente é usado para corrigir um recibo incorreto. Não é possível lançar o ajuste de transação de estoque após a execução de um fechamento de estoque e depois que uma transação for liquidada.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>As devoluções de ordem de compra são tratadas como outras saídas durante o fechamento de estoque?

Sim. O recebimento de uma ordem de compra é uma saída que é liquidada em um recebimento no modelo heurístico selecionado para o item. Se estiver usando um modelo de custos periódicos, você poderá usar a marcação para substituir o custo heurístico.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>O que acontece às devoluções de ordem de compra durante o fechamento de estoque?

Quando você executa o fechamento de estoque, uma devolução de ordem de compra é tratada como um recebimento no estoque. As saídas são liquidadas em relação ao estoque, com base no modelo heurístico selecionado para o item.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>Qual preço de custo é usado em uma devolução de ordem de venda?

Ao criar uma devolução que está relacionada a uma ordem de venda, o valor do campo **Preço unitário** é copiado da ordem de venda original e o campo **Preço de custo de devolução** na devolução é definido como o preço de custo ajustado da transação de estoque original para a linha da ordem de venda que está sendo devolvida. Se a opção **Valor aberto** para a transação de estoque relacionada estiver definida como *Sim*, o fechamento de estoque pode causar atualizações no custo de saída na ordem de venda original. O campo **Preço de custo de devolução** não é atualizado neste cenário. No entanto, quando um guia de remessa da ordem de devolução é lançado, o sistema verificará o preço de custo e usará o custo atualizado na transação de devolução de estoque.

Para a devolução de um item de custo padrão que esteja relacionado a uma ordem de venda, o sistema usará o custo padrão do momento da ordem de venda original, mesmo se um novo custo padrão esteja ativo para o item.

Ao criar uma devolução que não esteja relacionada a uma ordem de venda, o campo **Preço de custo de devolução** é definido como o preço ativo do item que você tem para o item no local para o qual você está criando a ordem de devolução. Se você não tiver um preço de custo ativo em uma versão de custo para o item, o valor será 0 (zero). Se deixar o valor como 0 (zero), você receberá um aviso informando que a ID do lote de devolução ou o preço de custo da devolução não foi especificado.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>Qual é o desempenho esperado do fechamento de estoque?

Muitos fatores podem afetar o desempenho do fechamento de estoque. Esses fatores incluem o número total de itens, o número total de transações no período, os modelos de estoque usados e o número de auxiliares de lote configurados nos parâmetros do gerenciamento do estoque e do depósito. Você pode esperar que o fechamento possa levar alguns poucos minutos ou até mesmo várias horas. Não há nenhuma orientação específica sobre a quantidade de tempo para a execução de um fechamento. Você deve definir seus requisitos empresariais não funcionais para o desempenho do fechamento de estoque e trabalhar em estreita colaboração com seu parceiro para definir a agenda de execução do processo de fechamento de estoque. Se houver um inesperado baixo desempenho do processo de fechamento de estoque, você deverá abrir um tíquete de suporte.

## <a name="costing-sheet-and-indirect-costs"></a>Planilha de custos e custos indiretos

### <a name="which-costing-models-support-the-costing-sheet"></a>Quais modelos de custos oferecem suporte à planilha de custos?

Embora a planilha de custos seja normalmente mais usada em organizações que usam custos padrão, você pode usá-la com qualquer modelo de custo que esteja disponível no Supply Chain Management.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>Posso ter várias planilhas de custos para várias partes de minha organização?

Não. Você só pode ter uma planilha de custos por entidade legal.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>Posso ter planilhas de custos diferentes para cada local?

Não, você não pode ter planilhas de custos diferentes para cada local. Você pode criar somente uma planilha de custos para cada entidade legal. No entanto, é possível configurar nós de total, grupos de custos ou nós de custo indireto por local. Essa configuração é um processo manual e você deve manter a hierarquia e as atribuições de item na planilha de custos quando ocorrerem alterações organizacionais ou operacionais. Se um único item for produzido ou comprado em mais de um local, não há nenhum mecanismo que permita que você trate o item de forma diferente na planilha de custos para cada local. Além disso, observe que todos os custos indiretos têm uma taxa ou sobretaxa que é definida em sua versão de custos. Os custos que você definir serão sempre específicos do local.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>Posso desativar e ativar versões da planilha de custos?

Embora nenhum histórico de versões detalhado da planilha de custos seja mantido, você pode fazer alterações na planilha de custos e, quando terminar, salvá-la e validá-la. Não há nenhum mecanismo que permita que você volte para uma versão mais antiga da planilha de custos ou exiba as alterações feitas nela. Se começar a fazer alterações e não quiser que elas entrem em vigor, você poderá fechar a página sem salvá-las e validá-las. Será solicitado que você descarte as alterações.

### <a name="can-i-create-indirect-costs-for-each-item"></a>Posso criar custos indiretos para cada item?

Em sua planilha de custos, você pode criar códigos de custo indireto em que o campo **Tipo de nó** seja definido como *Sobretaxa*, *Taxa* ou *Baseado na unidade de saída*. Você então poderá definir a taxa ou a sobretaxa que seja específica para um número de item. Na Guia Rápida **Taxa** ou **Sobretaxa**, adicione uma linha à grade. Defina o campo **Válido para** como *Tabela* e o campo **Relação** como o número de item específico.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>Posso criar um custo indireto que não esteja relacionado a um item específico?

Sim. É possível criar um código de custo indireto em que o campo **Tipo de nó** seja definido como *Baseado na unidade de saída*. Você pode definir o campo **Subtipo** como *Quantidade*, *Peso* ou *Volume* para especificar a quantidade, o peso ou o volume do item que está produzindo. A taxa que você especificar na Guia Rápida **Taxa** será aplicada ao subtipo selecionado. Por exemplo, você define o campo **Subtipo** como *Quantidade* e o campo **Taxa** como *US$ 1,00* e, em seguida, cria uma ordem de produção ou de lote para a quantidade de 10. Nesse caso, o custo indireto que será adicionado ao produto acabado será de US$ 10,00.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>Posso usar a planilha de custos para dividir meus custos de produção em horas e materiais?

Sim. É possível criar nós de **Total** em sua planilha de custos para separar os custos em qualquer agrupamento que você quiser. Por exemplo, você pode criar um nó de **Total** chamado *Horas* e outro chamado *Materiais*. No nó de **Horas**, adicione cada grupo de custos que esteja relacionado às suas horas. No nó de **Materiais**, adicione cada grupo de custos que esteja relacionado aos seus materiais.

## <a name="dimension-groups"></a>Grupos de dimensões

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>Posso gerenciar os custos no nível do lote ou do número de série?

Sim, se estiver usando um modelo de custos periódicos, como PEPS, UEPS, data de UEPS, média ponderada ou data da média ponderada, você poderá habilitar a opção **Estoque financeiro** para a dimensão **Lote** ou **Número de série** no grupo de rastreamento de dimensões para rastrear os custos em um nível detalhado.

### <a name="can-i-manage-costs-at-the-location-level"></a>Posso gerenciar os custos no nível do local?

Não, você não pode habilitar a opção **Estoque financeiro** para a dimensão **Local** no grupo de dimensões de armazenamento. Se a sua organização tiver que rastrear custos em um nível mais detalhado, considere se há a possibilidade de criar depósitos virtuais e, em seguida, selecione a opção **Estoque financeiro** para a dimensão **Depósito** no grupo de dimensões de armazenamento.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>Devo habilitar a opção Usar processos de gerenciamento de depósito para o grupo de dimensões de armazenamento?

Se achar que talvez queira usar os recursos avançados de gerenciamento de depósito no futuro, você deverá habilitar a opção **Usar processos de gerenciamento de depósito**. Depois que salvar um grupo de dimensões de armazenamento, não será mais possível alterar a configuração da opção **Usar processos de gerenciamento de depósito** para ele. Se decidir usar os processos de gerenciamento de depósito posteriormente, será necessário criar um depósito onde a opção estiver habilitada. Não há nenhum processo automatizado que possa ser usado para mover todo o estoque de um depósito para outro ou para copiar configurações relacionadas em um novo depósito.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-advanced-warehousing"></a>Posso habilitar a opção Usar processos de gerenciamento de depósito para o grupo de dimensões de armazenamento mesmo que eu não esteja planejando usar o depósito avançado?

Sim, mesmo que não esteja planejando usar os recursos de gerenciamento de depósito avançado, você pode habilitar a opção **Usar processos de gerenciamento de depósito** para o grupo de dimensões de armazenamento. Para criar e processar as transações, você deverá concluir a configuração mínima, com as hierarquias de reserva e os grupos de sequência de unidade. No entanto, as configurações de depósito avançado geralmente são ignoradas quando você processa listas de separação, guias de remessa e recebimentos de produtos manualmente (por exemplo, nas página da ordem de venda ou da ordem de compra).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Quando devo habilitar a opção Estoque físico para um grupo de dimensões de armazenamento?

Você deverá habilitar a opção **Estoque físico** para os grupos de dimensões de armazenamento e de rastreamento quando for necessário manter registros detalhados do estoque baseado nessa dimensão. Normalmente, qualquer dimensão que esteja ativa também será rastreada fisicamente. Portanto, qualquer recebimento, saída ou movimento do estoque será rastreado pela dimensão selecionada. Se uma dimensão não for obrigatória (por exemplo, a placa de licença), você poderá habilitar as opções **Recibo em branco permitido** e **Saída em branco permitida** para permitir que os usuários recebam, deem saída ou movam estoque quando a dimensão não for especificada.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Quando devo habilitar a opção Estoque financeiro para um grupo de dimensões de armazenamento ou de rastreamento?

Você deverá habilitar a opção **Estoque financeiro** para os grupos de dimensões de armazenamento e de rastreamento quando for necessário manter registros financeiros detalhados do estoque baseado nessa dimensão. As dimensões de **Local** são sempre rastreadas financeiramente, enquanto o rastreamento financeiro em outras dimensões é opcional. Se você usar um modelo de custos periódicos, como PEPS, UEPS ou média ponderada, habilitar a opção **Estoque financeiro** para uma dimensão indica que você fará liquidações somente em casos em que o recebimento e a saída tenham os mesmo valores de dimensão. Por exemplo, se habilitar a opção **Estoque financeiro** para a dimensão **Depósito**, você terá um custo diferente em cada depósito, e os recebimentos e as saídas de depósitos diferentes não poderão ser liquidadas.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>Posso fazer alterações em um grupo de dimensões de produto, armazenamento ou rastreamento depois que houver transações?

Depois que criar um grupo de modelos, você poderá alterar a configuração dos campos **Plano de cobertura por dimensão**, **Para preços de compra** e **Para preços de venda** se a caixa de seleção **Ativo** estiver marcada para uma dimensão no grupo de modelos de item. Nenhuma outra alteração será permitida. Por exemplo, não é possível habilitar ou desabilitar as opções **Ativo**, **Saída em branco permitida**, **Recibo em branco permitido**, **Estoque físico** e **Estoque financeiro**.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>Posso alterar o grupo de dimensões de produto, armazenamento ou rastreamento de um produto liberado?

Se o estoque disponível de um produto for 0 (zero) e a opção **Valor aberto** estiver definida como *Não* para todas as transações de estoque, você poderá alterar os grupos de dimensões de armazenamento e de rastreamento na página do produto liberado. Não será possível alterar o grupo de dimensões do produto depois que o registro for criado.

## <a name="item-model-groups"></a>Grupos de modelo do item

### <a name="when-should-i-enable-the-stocked-product-option"></a>Quando devo habilitar a opção Produto em estoque?

Você deve habilitar a opção **Produto em estoque** para qualquer item que será rastreado em seu estoque. Quando essa opção é habilitada, são mantidas transações de estoque detalhadas que rastreiam o recebimento e a saída do item. Essa opção normalmente é habilitada para qualquer item tangível que você mantenha no depósito, por exemplo. Você também deve habilitar essa opção se planeja adicionar itens intangíveis, como um item de serviço à suas listas de materiais (BOMs) ou fórmulas. Se não habilitar a opção **Produto em estoque**, nenhuma transação de estoque será rastreada no razão auxiliar de estoque e o custo dos itens serão incorridos na contabilidade. Essa opção geralmente é usada, por exemplo, para suprimentos ou serviços de lojas que não estejam incluídos em suas BOMs ou fórmulas.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>Quando devo habilitar a opção Lançar estoque físico?

A opção **Lançar estoque físico** geralmente é habilitada quando a opção **Produto em estoque** está habilitada. Quando essa opção é habilitada, o sistema rastreia a atualização física do item na transação de estoque. Essa opção é usada em coordenação com parâmetros em Contas a pagar, Contas a receber e no Controle de produção que especifica que a atualização física deve criar um comprovante. Você normalmente habilitará essa opção quando quiser que o razão seja atualizado sempre que o estoque for atualizado fisicamente. Se o Supply Chain Management não for o seu sistema de registros financeiros, talvez você queira desabilitar essa opção.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>Quando devo habilitar a opção Lançar estoque financeiro?

A opção **Lançar estoque financeiro** geralmente é habilitada quando a opção **Produto em estoque** está habilitada. Essa opção é usada em coordenação com parâmetros em Contas a pagar, Contas a receber e no Controle de produção que especifica que a atualização financeira deve criar um comprovante. Você normalmente habilitará essa opção quando quiser que o razão seja atualizado sempre que o estoque for atualizado financeiramente (por exemplo, ao faturar ordens de venda e ordens de compra ou encerrar uma ordem de produção). Se o Supply Chain Management não for o seu sistema de registros financeiros, talvez você queira desabilitar essa opção.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>Quando devo habilitar a opção Lançar na Conta de Receita Diferida na Entrega de Vendas?

Você usa a opção **Lançar na Conta de Receita Diferida na Entrega de Vendas** para indicar se deseja reconhecer a receita no razão quando lançar uma guia de remessa para uma ordem de venda. Essa opção é geralmente usada quando há uma longa demora entre a guia de remessa e a fatura em uma ordem de venda ou quando não é possível faturar todas as ordens de venda no período. Normalmente, você desabilita essa opção se lançar as faturas de ordem de venda imediatamente após lançar a guia de remessa. Dessa forma, você evita gerar lançamentos contábeis extras que serão imediatamente revertidos quando você faturar uma ordem de venda.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>Quando devo habilitar a opção Acumular passivo no recebimento de produtos?

Na maioria das organizações, você desejará habilitar a opção **Acumular passivo no recebimento de produtos** para todos os grupos de modelos de item, independentemente se você tem um produto em estoque ou um produto sem estoque. Essa opção é usada para lançar um acúmulo na contabilidade, com base no preço de recebimento do produto. Como normalmente há uma demora entre o lançamento do recebimento do produto de uma ordem de venda e o lançamento da fatura, a maioria das organizações devem reconhecer o passivo no balanço patrimonial para cumprir com os regulamentos locais, como as Práticas Contábeis Geralmente Aceitas (GAAP). Se o Supply Chain Management não for o seu sistema de registros financeiros, talvez você queira desabilitar essa opção. Se a sua organização usa categorias de compras nas ordens de compra, você pode controlar o requisito de acúmulo habilitando a opção **Despesas de compras acumuladas no recebimento** para a regra de política de categoria, na página **Políticas de compras**.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>Como posso impedir um usuário de lançar o recebimento do produto de uma ordem de compra se o registro do recebimento ainda não foi lançado?

Você pode impedir um usuário de lançar o recebimento do produto de uma ordem de compra se o registro do recebimento ainda não tiver sido lançado habilitando a opção **Requisitos de registro** para o grupo de modelos de item. Essa opção normalmente é usada em organizações que utilizam o processo de recebimento em duas etapas ou em cenários em que você deve registrar um lote ou número de série, por exemplo, nos itens que estiver recebendo. A opção **Requisitos de registro** aplica-se a *todos* os recebimentos de estoque de um item, não somente às ordens de compra. Por exemplo, ela aplica-se a um diário de estoque que tenha uma quantidade positiva e um relatório de ordem de produção como diário concluído.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>Como posso impedir um usuário de lançar uma fatura de ordem de compra se o recebimento do produto ainda não foi lançado?

Você pode impedir um usuário de lançar uma fatura de ordem de compra se o recebimento do produto da ordem de compra ainda não tiver sido lançado habilitando a opção **Requisitos de recebimento** para o grupo de modelos de item. Essa opção normalmente é usada em organizações que exigem que os recebimentos sejam reconhecidos fisicamente na contabilidade para acúmulos. A opção **Requisitos de recebimento** aplica-se a *todos* os recebimentos de estoque de um item, não somente às ordens de compra. Por exemplo, ela aplica-se a um diário de estoque que tenha uma quantidade positiva e um relatório de ordem de produção como diário concluído. Se a sua organização usa categorias de compras nas ordens de compra, você pode controlar o requisito de um recebimento habilitando a opção **Requisitos de recebimento** para a regra de política de categoria, na página **Políticas de compras**.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>Como posso impedir um usuário de lançar a guia de remessa de uma ordem de venda se a lista de separação da ordem de venda ainda não foi lançada?

Você pode impedir um usuário de lançar a guia de remessa de uma ordem de venda se a lista de separação da ordem de venda ainda não tiver sido lançada habilitando a opção **Requisitos de separação** para o grupo de modelos de item. Essa opção normalmente é usada em organizações que executam um processo físico de separação no depósito (por exemplo, usando o dispositivo móvel do depósito para fazer a separação). A opção **Requisitos de separação** aplica-se a *todas* as saídas de estoque de um item, não somente às ordens de venda. Por exemplo, ela aplica-se a um diário de estoque que tenha uma quantidade negativa e um diário de lista de separação da ordem de produção.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>Como posso impedir um usuário de lançar uma fatura de ordem de venda se a guia de remessa da ordem de venda ainda não foi lançada?

Você pode impedir um usuário de lançar a uma fatura de ordem de venda se a guia de remessa da ordem de venda ainda não tiver sido lançada habilitando a opção **Requisitos de dedução** para o grupo de modelos de item. Essa opção normalmente é usada em organizações que executam um processo físico de embalagem no depósito (por exemplo, usando o aplicativo móvel Warehouse Management para fazer a embalagem ou gerando um documento que será incluído com os itens enviados). A opção **Requisitos de dedução** aplica-se a *todas* as saídas de estoque de um item, não somente às ordens de venda. Por exemplo, ela aplica-se a um diário de estoque que tenha uma quantidade negativa e um diário de lista de separação da ordem de produção.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>Posso impedir que os itens que estiverem registrados sejam vendidos?

Quando um item é registrado em seu estoque no Supply Chain Management, a quantidade fica disponível fisicamente para ser emitida no sistema. Se os itens que forem registrados mas ainda não tiverem sido recebidos *não* devem estar disponíveis para serem emitidos para ordens de venda ou de produção, por exemplo, considere usar recursos de status do estoque, bloqueio do estoque, ordens de qualidade, ordens de quarentena ou recursos de reserva para gerenciar o processo empresarial.

## <a name="production-costing"></a>Avaliação de custo de produção

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>Posso usar um modelo de custos para matérias-primas e um modelo de custos diferente para os produtos acabados?

Você pode usar modelos de custos diferentes para cada item. Não é incomum para os fabricantes usarem um modelo de custos periódicos para matérias-primas e um custo padrão para mercadorias acabadas e semiacabadas.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>Como posso afastar as despesas gerais dos custos de máquinas?

Para afastar as despesas gerais dos custos de máquinas, você deve criar recursos e grupos de recursos para cada máquina, de acordo com seus requisitos comerciais. Cada recurso ou grupo de recursos pode ser atribuído a categorias de custo para controlar o custo da máquina. Cada categoria de custo pode ser vinculada a um grupo de custos e cada grupo de custos pode ser usado como a base para o cálculo dos custos indiretos na planilha de custos.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>Como faço para reconhecer o custo que está relacionado ao consumo de energia (por exemplo, consumo de água, energia ou gás) na planilha de custos?

Você geralmente reconhece os custos que estão relacionados ao consumo de energia de uma destas duas maneiras:

- Crie uma linha em sua BOM ou fórmula. Normalmente, essa linha é criada como um item de serviço e você pode especificar a unidade de medida que você está consumindo em relação à quantidade que você está produzindo. Dessa forma, o usuário pode consumir uma quantidade diferente durante o processo de produção. Você pode consumir automaticamente os itens com base no valor selecionado no campo **Princípio de liberação**.
- Crie um custo indireto na sua planilha de custos. Normalmente, essa abordagem é usada para alocar o custo total de seu consumo de energia em todo o processo de produção. Você pode usar os grupos de custos e a base de absorção para escalar o consumo baseado em materiais ou mão de obra em seu roteiro, por exemplo.

Você deve selecionar a melhor opção com base em seus requisitos de relatórios, reconciliação e de operação.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>Posso capturar detalhes do recurso na BOM ou na fórmula?

Os detalhes do recurso podem ser capturados somente em uma operação de roteiro. Embora você possa criar um item de serviço para representar um recurso e atribuir um custo para amentar o cálculo do custo de uma mercadoria acabada, normalmente, essa essa abordagem não é recomendada. Em vez disso, recomendamos que você crie um roteiro simples que tenha uma linha para rastrear os custos do recurso e configurar a operação para que ela seja consumida no início ou no final da ordem de produção.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>Posso exibir os detalhes do cálculo se o custo for inserido manualmente?

Não. Se você inserir o preço manualmente na página **Preço do item**, os botões **Exibir detalhes do cálculo** e **Relatar detalhes do cálculo** não ficarão disponíveis. Se você selecionar o botão **Acúmulo de custo por grupo de custo** para um preço de custo que seja inserido manualmente, uma linha resumida será exibida, e todos os custos serão acumulados para o item de mercadoria acabada.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>O sistema calcula variações em uma ordem de produção quando o custo é inserido manualmente?

Sim, o sistema calcula variações quando você insere um custo padrão manualmente. No entanto, quando você insere um custo padrão manualmente em vez de calculá-lo, todo o consumo de materiais, roteiros e custos indiretos na ordem de produção serão considerados uma variação de substituição. Se houver variações adicionais, como o consumo extra de materiais ou de mão de obra, elas serão registradas como variações da BOM de produção. Portanto, é altamente recomendável que você sempre execute um cálculo para os itens que tenham uma BOM, um roteiro ou custos indiretos.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>Como posso carregar as variações de uma ordem de subprodução para a ordem de produção principal?

Quando você usar um modelo de custos periódicos, como PEPS, UEPS ou média ponderada, os custos de uma subprodução serão reconhecidos no modelo heurístico selecionado para os itens. Se forem necessários os custos reais, considere usar o princípio de marcação para indicar qual subprodução foi emitida para uma ordem de produção principal. Como alternativa, considere usar a opção **Estoque financeiro** para a dimensão **Lote** ou **Número de série** no grupo de dimensões de rastreamento, por exemplo.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>Como o princípio de liberação afeta o consumo?

O princípio de liberação em uma linha de BOM, fórmula ou roteiro controla o tempo e a técnica usada para consumir o item ou a mão de obra. Se você selecionar *Início*, o item ou mão de obra é consumido automaticamente quando você inicia a ordem de produção. Se você selecionar *Término*, o item ou mão de obra é consumido automaticamente quando você relata a ordem de produção como concluída. Se você selecionar *Manual*, um usuário deverá selecionar os materiais ou registrar as horas em um trabalho ou em um diário de cartão de roteiro manualmente. As BOMs e fórmulas também têm uma opção *Disponível no local*. Se você selecionar essa opção, os itens serão consumidos automaticamente depois que forem transferidos para o local da área de produção.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>Como devo executar os cálculos de custo se tiver BOMs ou fórmulas de vários níveis?

Em geral, recomendamos que você inicie no nível mais baixo de suas BOMs ou fórmulas para o cálculo. Para facilitar a filtragem quando você executa cálculos de custo em massa, você pode usar grupos de cálculos para ajudar a segregar os produtos. Também recomendamos que você execute o trabalho periódico *Recalcular níveis de BOM* antes de iniciar a execução em massa dos cálculos de custo. Cada organização deve considerar a combinação de produtos e definir uma estratégia que atenda às necessidades específicas de suas estruturas de produtos e de BOM ou de fórmulas.

## <a name="transfer-order-costing"></a>Custos da ordem de transferência

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>Há uma maneira de alocar o frete no custo da ordem de transferência?

É possível adicionar encargos a uma ordem de transferência para incluir custos. O código dos encargos define o débito e o crédito do encargo sendo adicionado. Primeiro, você deve criar os códigos de encargo no módulo **Gerenciamento de estoque**. Para adicionar um encargo ou uma ordem de transferência, selecione **Encargos** na linha da ordem de transferência à qual você deseja adicionar um encargo.

## <a name="variances"></a>Variações

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>Posso tratar as variações de forma diferente, com base no local ou no depósito?

Não há nenhuma opção para configurar contas de variação por local. Ao usar custos padrão para um produto liberado, você poderá selecionar a conta principal que é usada para lançamentos de variação de custo padrão na página **Lançamentos**. Você pode optar por configurar as contas para um item, um grupo de itens ou todos os itens. Você também pode configurar um grupo de custos, um grupo de grupos de custo ou todos os grupos de custo.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>Posso separar as variações que são o resultado das taxas de câmbio de outros tipos de variações?

Se uma variação for o resultado da diferença da taxa de câmbio entre o preço da ordem de compra e o custo padrão de um item, não há nenhuma maneira de separar a diferença da taxa de câmbio das outras variações.

## <a name="reporting"></a>Relatório

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>Quantas configurações do relatório de valor de estoque posso criar e usar?

Não há um limite para o número de configurações do relatório de valor de estoque que podem ser criadas. Você deve avaliar seus requisitos específicos de relatórios e criar o número de configurações necessárias para atender a esses requisitos. Você precisará de pelo menos uma configuração de relatório de valor de estoque para executar o relatório na opção de armazenamento de relatório.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>Posso usar o relatório de valor de estoque para analisar o custo de um item em cada depósito?

Sim. Você pode habilitar a opção **Exibir** ou **Total** para cada dimensão de **Depósito** na configuração do relatório de valor de estoque. No entanto, o relatório mostrará valores somente para as dimensões em que a opção **Estoque financeiro** esteja habilitada para o grupo de dimensões de armazenamento. Para outras dimensões ele mostrará colunas em branco. Para obter mais informações, consulte [Exemplos de relatório de valor de estoque e lógica](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>Como posso exibir a quantidade de estoque a partir de uma data específica com a média ponderada?

Você pode usar o relatório **Classificação por vencimento do estoque**, que inclui uma coluna **Custo unitário médio** que mostra o valor do estoque a partir de uma data específica. Para obter mais informações, consulte [Exemplos de relatório de classificação por vencimento do estoque e lógica](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>Como posso ver quais transações foram liquidadas em relação a uma transação de saída?

Você pode exibir as liquidações de uma transação de estoque selecionando **Liquidações** ou **Explorador de custos** na guia **Estoque** no Painel de Ações da página **Transação de estoque** ou **Detalhes da transação de estoque**. Se você selecionar um recebimento para exibir as saídas relacionadas à transação, o explorador de custos não mostrará os detalhes. Os detalhes serão mostrados somente se você selecionar uma transação de saída.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>Como o relatório de valor de estoque mostra itens que tenham uma quantidade física positiva e um valor financeiro negativo?

O relatório de valor de estoque separa as quantidades e os valores físicos e financeiros em suas próprias colunas. Os valores mostrados são a partir do intervalo de datas selecionado quando você gerou o relatório. O nível de resumo mostrado depende das configurações selecionadas. Se um item tiver transações que foram recebidas fisicamente e emitidas financeiramente, as quantidades e valores serão somados de forma independente. Se você optou por exibir o nível de detalhes como transações, as linhas para cada recebimento e saída serão mostradas separadamente, e as quantidades e os valores físicos e financeiros, respectivamente, serão mostrados. Para obter mais informações, consulte [Exemplos de relatório de valor de estoque e lógica](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>Qual é o impacto dos grupos de dimensões de armazenamento e de rastreamento no relatório de valor de estoque?

Se habilitar a opção **Valor financeiro** para uma dimensão em um grupo de dimensões de armazenamento ou de rastreamento, você poderá selecionar a opção **Exibir** ou **Total** para a dimensão na configuração do relatório de valor de estoque. Se selecionar a opção **Exibir** ou **Total** para uma dimensão em que a opção **Valor financeiro** não esteja selecionada. a coluna ficará em branco na saída do relatório. Se você tiver habilitado a opção **Valor financeiro** para uma dimensão em um grupo de dimensões de armazenamento ou de rastreamento e não selecionar a opção **Exibir** ou **Total** na configuração de relatório de valor de estoque, o sistema resumirá os valores das dimensões selecionadas em que elas são rastreadas financeiramente.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>Posso personalizar os relatórios do Power BI Embedded para os custos?

Sim, os usuários que tiverem as permissões de segurança corretas podem atualizar a tela de design de relatórios de qualquer relatório do Power BI Embedded no Supply Chain Management. Para obter mais informações, consulte [Personalizar relatórios inseridos em espaços de trabalho analíticos](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>Onde posso exibir o demonstrativo de análise de variação?

Você pode acessar o demonstrativo de análise de variação acessando **Gerenciamento de custos \> Consultas e relatórios \> Contabilidade de estoque – relatórios de análise** ou **Gerenciamento de custos \> Consultas e relatórios \> Contabilidade de fabricação – relatórios de análise**. ambas as opções abrem o mesmo relatório, e o relatório tem o mesmo comportamento.

## <a name="item-prices-and-default-costs"></a>Preços do itens e custo padrão

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>Posso manter o custo para cada grade de produto?

Sim. Você pode habilitar a opção **Usar preço de custo por grade** na Guia Rápida **Gerenciar custo** da página **Produto liberado** para habilitar o preço por grade de produto. (Essa opção está disponível somente para produtos mestres.) Em seguida, na página **Preço do item** (que pode ser aberta na página **Versão de custos** ou na página **Produto liberado**), você poderá selecionar **Exibição de dimensões** para especificar se deseja exibir a dimensão **Configuração**, **Tamanho**, **Cor** ou **Estilo**. Para salvar a configuração e usar as dimensões selecionadas sempre que você abrir a página, habilite a opção **Salvar configuração** e selecione **OK**. Você pode inserir as dimensões somente para itens em que as dimensões estejam ativas no grupo de dimensões do produto.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>Posso manter o custo para cada depósito?

Não, você não pode manter o preço do item por depósito. No entanto, você pode manter contratos comerciais para preços de compra ou de venda por depósito. Primeiramente, selecione a opção **Para preços de compra** ou **Para preços de venda** para a dimensão na página **Grupo de dimensões de armazenamento**. Depois, quando criar o diário de contrato comercial e abrir as linhas para as dimensões, selecione **Estoque \> Exibir dimensões** para selecionar quais dimensões devem ser exibidas na grade. Para salvar a configuração e usar as dimensões selecionadas sempre que você abrir a página, habilite a opção **Salvar configuração** e selecione **OK**. Você pode inserir as dimensões somente para itens em que as dimensões estejam ativas no grupo de dimensões do produto.

### <a name="what-are-price-charges"></a>O que são encargos de preço?

Os encargos de preço fornecem uma maneira de adicionar um valor fixo ao preço unitário do preço do item ou do contrato comercial. Ao inserir um valor no campo **Encargos de preço**, você também pode inserir um valor no campo **Quantidade de encargos**. Os encargos de preço são amortizados sobre a quantidade de encargos especificada. Selecione a opção **Incl. no preço unitário** se quiser incluir os encargos de preço no preço unitário do item. Essa opção está sempre habilitada para um custo padrão.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>Como devo configurar preços para itens que são adquiridos em várias moedas?

Se você inserir um preço padrão no campo **Preço de compra** na página **Produto liberado**, presume-se que ele esteja na moeda contábil do razão da entidade legal que você estiver. Da mesma forma, se você inserir um preço de compra em uma versão de custos em que o campo **Tipo de preço** está definido como *Compra*, presume-se que o preço esteja na moeda contábil da sua entidade legal. Ao criar uma ordem de compra para um fornecedor que tenha uma moeda diferente, o sistema converterá automaticamente o valor na moeda contábil na moeda da transação usando a taxa de câmbio especificada no campo **Tipo de taxa de câmbio da moeda contábil** no seu razão.

Ao criar um diário de contrato comercial, você poderá especificar a moeda na qual você está expressando o preço em cada linha. É possível criar contratos comerciais para várias moedas, fornecedores específicos e muitas outras combinações de fatores. Se você criar uma ordem de compra em que exista um contrato comercial para a moeda selecionada, o sistema usará o contrato comercial que tenha a moeda correspondente. Ao lançar transações, como recebimentos ou faturas de produtos, o valor será convertido na moeda contábil do razão usando a taxa de câmbio especificada no razão.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>Como devo configurar custos para itens que são adquiridos em várias moedas?

Não é possível configurar custos em mais de uma moeda. O custo que você especificar para o preço do item ou os custos padrão que você inserir no campo **Preço** na Guia Rápida **Gerenciar custo** na página **Produto liberado** são sempre expressos na moeda contábil do razão da entidade legal selecionada.

Se a sua organização usar custos padrão, você deverá ter uma estratégia para definir os custos quando houver várias moedas. Você também deve ter um processo para atualizar regularmente o custo para a ajudar a reduzir o número de variações que são lançadas.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>Posso usar a Definição de lucro na página Grupo de custos para calcular os preços de venda?

Sim, é possível usar a **Definição de lucro** na página **Grupo de custos** para adicionar uma porcentagem quando os preços de venda são calculados usando um cálculo de custo. Para obter informações, consulte [Cálculos de BOM](bom-calculations.md).

## <a name="marking"></a>Marcação

### <a name="how-does-marking-affect-periodic-costing-models"></a>Como a marcação afeta os modelos de custos periódicos?

Se você usar um modelo de custos periódicos, como PEPS, UEPS ou média ponderada, e tiver marcado uma transação de recebimento em relação a uma transação de saída, o modelo heurístico do item será ignorado durante o processo de fechamento de estoque. Em vez disso, os sistema usará o custo real do recebimento para o custo da saída.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>O que acontece durante o fechamento de estoque quando uso a marcação?

Quando você marca recebimentos e saídas, o fechamento de estoque liquidará as transações que foram marcadas juntas. Quando a marcação é usada para criar uma liquidação, o campo **Princípio** na página **Liquidação** será definido como *Marcação*. Se uma transação for marcada antes de ser atualizada fisicamente ou financeiramente, a saída usará o custo do recebimento marcado em vez do custo médio. Se as transações forem marcadas depois da atualização financeira, o processo de fechamento e ajuste de estoque corrigirá o custo da saída para que ele corresponda ao custo do recebimento.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>Posso marcar manualmente as transações quando usar o custo padrão ou a média móvel?

Não, você não pode marcar manualmente os recebimentos ou as saída quando usar o custo padrão ou a média móvel. Se as transações (por exemplo, entrega direta ou ordem intercompanhia) forem marcadas automaticamente, o registro de marcação permanecerá e atuará como uma reserva fixa. No entanto, quando você usa o custo padrão ou a média móvel, a marcação dos registros não têm efeito sobre o custo dos itens.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>Como a marcação afeta o demonstrativo de lucros e perdas?

Quando você marca uma transação de saída em relação a um recebimento, o custo da saída corresponderá ao recebimento selecionado. Quando você lança a saída fisicamente ou financeiramente, o lançamento afetará as contas **Custo dos produtos vendidos, entregues** e **Custo dos produtos vendidos, faturados** que você especificar no perfil de lançamento de estoque. Se uma transação for marcada após a a atualização física ou financeira, o processo *Fechamento e ajuste de estoque* criará um ajuste que tenha um comprovante correspondente que ajusta a conta **Custo dos produtos vendidos, faturados** e faz a contrapartida na conta que você especificar para **Custo de unidades, faturadas** (estoque).

### <a name="how-does-marking-affect-master-planning"></a>Como a marcação afeta o planejamento mestre?

A guia **Atualização padrão** na página **Parâmetros do planejamento mestre** inclui um campo chamado **Atualizar marcação**. A opção que você selecionar nele será usada quando você confirmar uma ordem planejada que é gerada pelo planejamento mestre. As opções a seguir estão disponíveis:

- *Não* – O sistema não realiza nenhuma marcação.
- *Padrão* – O sistema marca os recebimentos em relação às saídas acordo com a vinculação. Uma ordem de requisito é marcada em relação a uma ordem de atendimento. Se uma quantidade permanecer no processamento, a ordem de processamento não será marcada.
- *Estendido* – O sistema marca as ordens de requisito e as ordens de processamento, independentemente de qualquer quantidade permanecer aberta na ordem de processamento.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Estoque negativo

### <a name="when-should-i-allow-physical-negative-inventory"></a>Quando devo permitir o estoque físico negativo?

Em geral, não é recomendável que você permita estoque físico negativo, porque não é possível ter menos que 0 (zero) de um item tangível em seu depósito. No entanto, os processos empresariais e os cenários de negócios de alguns setores podem restringir as operações que exijam que o estoque tenha permissão para ficar fisicamente negativo. Por exemplo, os varejistas podem mão querer impedir a venda de um item que seja levado para a caixa registradora, mesmo que o sistema indique que não haja nenhum item disponível. Os fabricantes de processo fornecem outro exemplo. Para esses fabricantes, a quantidade consumida pode exceder o que é recomendado na fórmula. Como alternativa, o consumo pode ser estimado em vez de ser preciso, de modo que o consumo exceda a quantidade em um local específico, com um tanque.

Sempre que possível, você deve avaliar seu processo empresarial e tentar aprimorá-lo para garantir que o estoque não fique negativo. Se tiver que permitir o estoque negativo, você deverá ter um processo empresarial claro para corrigir o estoque negativo, pois ele pode afetar os custos desfavoravelmente.

### <a name="when-should-i-allow-financial-negative-inventory"></a>Quando devo permitir o estoque financeiro negativo?

Em geral, recomendamos que a maioria das organizações permitam o estoque financeiro negativo. (Na maioria dos casos, as faturas de ordem de compra não são processadas antes que você possa enviar os itens.) Você deve habilitar essa opção quando tiver processos empresariais específicos que exijam que o preço de venda reflita o custo final de uma ordem de venda. Por exemplo, esse requisito pode ser aplicado em um setor de compra por encomenda ou em regiões específicas onde seja exigido por lei.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>O que acontece com o custo de minhas saídas quando o estoque está negativo?

Quando o estoque de seu item estiver negativo e você usar mais itens do que tiver fisicamente, o sistema usará o preço padrão do item para calcular a média se você usar um modelo de custos periódicos, como PEPS, UEPS ou média ponderada. Se nenhum preço padrão for especificado para o item, o sistema emitirá o estoque com um valor 0 (zero). Esse comportamento pode fazer com que os cálculos de sua média ou a média móvel sejam incorretos.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>Posso impedir que itens sejam separados, embalados ou vendidos em ordens de venda ou em ordens de produção se não houver estoque disponível o suficiente?

Sim. Recomendamos que você desabilite a opção **Físico negativo** para o grupo de modelos de item para impedir que itens sejam separados, embalados ou vendidos em ordens de venda ou em ordens de produção.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>Posso impedir que itens sejam faturados em uma ordem de venda se nenhuma ordem de compra tiver sido faturada para o mesmo item?

Sim. Recomendamos que você desabilite a opção **Financeiro negativo** para o grupo de modelos de item para impedir que itens sejam faturados em uma ordem de venda se nenhuma ordem de compra tiver sido faturada para o mesmo item.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>Como o estoque negativo afeta as proporções financeiras, como a margem de lucro bruto?

Quando você permite que seu estoque fique negativo, o valor do estoque em seu balanço patrimonial e o custo dos produtos vendidos em seu demonstrativo de lucros e perdas pode ser atenuado, especialmente se nenhum preço padrão for configurado para os itens. Portanto, os relatórios financeiros e as proporções, como a margem de lucro bruto, podem ser superestimados, porque o custo está incorreto. Se você usar um modelo de custos periódicos, como PEPS, UEPS ou média ponderada, o valor das saídas pode ser ajustado quando você executar o processo de fechamento e ajuste de estoque depois que as quantidades negativas tiverem sido corrigidas. No entanto, se você usar a média móvel, não há nenhuma maneira de reavaliar as transações individuais.

### <a name="how-should-i-correct-negative-inventory"></a>Como devo corrigir o estoque negativo?

Recomendamos que você monitore frequentemente e corrija o estoque negativo quando sua organização ou seus requisitos comerciais exigirem que você permita que o estoque fique negativo. É possível corrigir os valores do estoque realizando uma contagem cíclica, lançando um ajuste ou lançando um diário de movimento. Se tiver que reconhecer ganhos inesperados no estoque em uma conta contábil específica, você deverá planejar o uso de um diário de movimento. Caso contrário, quando você usar a contagem cíclica ou o processo de ajuste de estoque, o sistema lançará o ajuste de estoque na conta **Recebimento de estoque** e fará a contrapartida nas contas **Despesas de estoque, lucro** que você especificar no perfil de lançamento de estoque.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>Tenho que criar um item se meu estoque ficar negativo e usar a média móvel?

Não. Se a sua organização permitir que o estoque fique fisicamente negativo e você estiver usando a média móvel como seu modelo de estoque, o sistema usará a sequência de custos de fallback atribuída na página **Parâmetros de gerenciamento de estoque e depósito** para determinar como o custo será atribuído às suas saídas. Em geral, recomendamos que você evite permitir que seu estoque fique fisicamente negativo. Para obter mais informações, consulte outras perguntas na seção [Estoque negativo](#negative-inventory) deste tópico.

## <a name="not-stocked-products"></a>Produtos não estocados

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>Posso lançar listas de separação da ordem de venda para produtos não estocados?

Ao gerar uma lista de separação para uma ordem de venda que inclui itens que estejam em um grupo de modelos de item que não esteja estocado, você não verá nenhuma linha para esse itens não estocados. Não é possível usar o aplicativo móvel Warehouse Management para processar itens não estocados.

Ao gerar uma guia de remessa para uma ordem de venda que inclui itens que estejam em um grupo de modelos de item que não esteja estocado, defina o campo **Quantidade** como *Quantidade separada e produtos não estocados* para incluir os itens não estocados na geração do documento. Se você selecionar *Tudo*, somente os itens estocados serão incluídos na guia de remessa.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>Devo usar um produto não estocado ou uma categoria (categoria de vendas ou categoria de compras)?

A escolha entre um produto não estocado e uma categoria depende dos seus requisitos comerciais específicos. Produtos não estocados geralmente oferecem mais controle sobre os valores padrão, como as quantidades e os preços nas ordens de compra e venda. Portanto, prefere-se produtos não estocados em cenários em que o mesmo produto ou serviço seja comprado ou vendido mais de uma vez. Categorias são úteis em cenários em que o preço, os itens, as descrições, etc., sejam inconsistentes de transação para transação. As categorias também podem ser usadas em qualquer produto para ajudar a classificar o tipo de produto que está sendo vendido ou comprado.

## <a name="service-items"></a>Itens de serviço

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>Qual é a diferença entre um item de serviço e um produto não estocado?

Um item de serviço é um tipo de produto. Ao criar um produto liberado recentemente, você pode definir o campo **Tipo de produto** como *Item* ou *Serviço*. *Item* geralmente é selecionado para indicar que o item é tangível, enquanto *Serviço* geralmente é selecionado para indicar que o item é intangível

Qualquer produto liberado recentemente, independentemente de ser um item ou serviço, pode ser estocado ou não estocado A configuração de estocado ou não estocado é controlada pelo grupo de modelos de item selecionado para o produto liberado. Quando você seleciona um grupo de itens que não estão estocados, o sistema não cria as transações de estoque para a ordem de compra ou de venda relacionada, por exemplo.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>Posso incluir itens não estocados em uma BOM?

Não, você não pode incluir um produto liberado que esteja vinculado a um grupo de modelos de item em que a opção **Em estoque** esteja desabilitada em uma BOM ou fórmula. Não importa se o campo **Tipo de produto** estiver definido como *Item* ou *Serviço*. Somente os itens que estejam estocados podem ser incluídos nas linhas da BOM ou da fórmula.

## <a name="costing-modelspecific-questions"></a>Perguntas específicas sobre o modelo de custos

### <a name="which-costing-model-should-i-use"></a>Qual modelo de custos devo usar?

Os modelos de custos que você deve selecionar dependem dos seus requisitos comerciais. Antes de selecionar um modelo de custos para uso no Supply Chain Management, você deve validar que o modelo seja permitido pelos regulamentos locais. Recomendamos que você valide sua seleção com um contador certificado em sua região.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>Posso usar mais de um modelo de custos em minha organização?

Sim. Não há limite para o número de grupos de modelos de item ou de modelos de custos que podem ser selecionados no Supply Chain Management.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>Posso usar mais de um modelo de custos para cada item?

Não. Você pode selecionar somente uma modelo de custos para cada produto liberado. Esse comportamento é controlado pelo grupo de modelos de item. Se usar mais de um modelo de custos para relatórios sobre valores de estoque, você deverá considerar o uso do suplemento Contabilidade de Estoque Global.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>Quando uso a execução de fabricação, qual metodologia de custos devo usar?

Os modelos de custos que você deve selecionar dependem dos seus requisitos comerciais. Não nenhuma vantagem ou desvantagem específica ao usar qualquer modelo de custos quando sua organização também usa a execução de fabricação.

### <a name="when-is-fefo-used"></a>Quando o método FEFO é usado?

O método FEFO (Primeiro a expirar, primeiro a sair) não é uma metodologia de custos. Ele é uma técnica de reserva que geralmente é usada nas organizações de fabricação. Você pode habilitar reservas de FEFO para um grupo de modelos de item habilitando a opção **Controlado por data FEFO** e selecionando um valor no campo **Critérios de separação**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>Há benefícios de desempenho ao selecionar um modelo de custos em vez de outro?

Em geral, o modelo de custos que você selecionar para um item tem um impacto mínimo no desempenho geral do sistema. No entanto, a quantidade de tempo exigida para executar o processo de fechamento de estoque ou de recálculo pode ser afetado pelo modelo de custos do estoque selecionado. Por exemplo, se você usar custo padrão ou média móvel, o processo de fechamento de estoque causa um impacto mínimo no sistema porque ele não atualiza cada transação de estoque e nem cria liquidações. No entanto, um modelo de custos periódicos, como PEPS, UEPS ou média ponderada, pode aumentar a quantidade de tempo exigida para concluir o processo de fechamento de estoque. Especificamente, o processo de fechamento pode ser mais longo se você inserir um número alto no campo **Número máximo de iterações permitidas por item** ou um número baixo no campo **Valor mínimo permitido** para o processo *Fechar estoque*.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>Quando devo usar a opção Preço de recebimento fixo?

Quando você marca a caixa de seleção **Preço de recebimento fixo** para um item na página **Grupo de modelos de item**, o sistema usará o preço de recebimentos como o custo padrão para o recebimento de estoque. Se houver uma diferença entre o preço de compra e o preço de custo padrão do item que está configurado para um produto, a diferença será lançada na conta **Lucro sobre preço de recebimento fixo** ou **Perda sobre preço de recebimento fixo**, e a contrapartida na conta **Compensação do preço de recebimento fixo**. (Todas essas contas estão especificadas na página **Lançamentos**.)

Marque a caixa de seleção **Preço de recebimento fixo** quando usar um modelo de custos periódicos, como PEPS, UEPS ou média ponderada, e você precise que a variação do preço de compra seja rastreada no razão se o preço de um recebimento for diferente do custo padrão do item.

### <a name="moving-average"></a>Média móvel

### <a name="is-moving-average-the-same-as-a-floating-average"></a>Média móvel é a mesma coisa que média flutuante?

Os termos média móvel, média flutuante e média são frequentemente usados como sinônimos. Desses termos, média móvel é o único modelo de custos que está disponível no Supply Chain Management. Embora e média não seja um modelo de custos oficial, é a técnica que é usada quando você usa um modelo de custos periódicos, como PEPS, UEPS ou média ponderada. O termo média flutuante não é usado no Supply Chain Management e talvez tenha conotações diferentes em outros sistemas.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>Como posso acomodar a diferença entre o preço de recebimento do produto e o preço da fatura quando uso a média móvel?

Quando você usa a média móvel, o custo físico (preço de recebimento) é usado para calcular a média móvel de todas as transações de saída. Se houver uma diferença entre o custo físico (preço de recebimento) e o custo financeiro (preço de fatura), o sistema lançará automaticamente a diferença na conta principal especificada para o tipo de lançamento **Diferença de preço da média móvel** na guia **Estoque** da página **Perfil de lançamento de estoque**.

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>Onde está a diferença de preço da média móvel apresentada na contabilidade?

Se houver uma diferença de preço entre o lançamento de uma atualização física e de uma atualização financeira para um recebimento, a diferença será lançada na conta principal especificada para o tipo de lançamento **Diferença de preço da média móvel** na guia **Estoque** da página **Perfil de lançamento de estoque**. Para obter informações, consulte [Média móvel](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>Quando uso a média móvel, o que acontecerá se houver uma saída antes do recebimento?

Normalmente, talvez haja uma saída antes do recebimento porque você permite que o estoque fique negativo para o grupo de modelos de item ou porque a saída tem data retroativa. Para obter mais informações, consulte a seção [Estoque negativo](#negative-inventory) deste tópico.

Se você está fazendo transações com data retroativa, recomendamos que você considere cuidadosamente seu processo empresarial e suas operações para determinar se há uma maneira de evitar esse cenário. Se você fizer uma transação com data retroativa para um item que usa média móvel, o sistema atribuirá a média móvel atual à transação. As saídas posteriores não serão ajustadas. Para obter mais informações sobre média móvel com transações com data retroativa, consulte [Média móvel](moving-average.md).

### <a name="standard-costing"></a>Custo padrão

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>Qual é a diferença entre custo padrão e preço de recebimento fixo?

Custo padrão requer que você defina o preço de um item e ative o custo na versão de custos. Esse custo é usado em todos os recebimentos e saídas. Variações para os recebimentos do estoque são registradas na contabilidade usando as contas de variação que você especifica na guia **Custo padrão** da página **Perfil de lançamento de estoque**.

No entanto, quando você usa o preço de recebimento fixo, somente os custo dos recebimentos é fixo, e o sistema usa o custo que você especificar na Guia Rápida **Gerenciar custos** da página **Produto liberado**. As diferenças entre o custo padrão e o preço da ordem de compra fará com que a variação de preço da ordem de compra seja lançada nas contas de de lucros e perdas do preço de recebimento fixo. As saídas não preço de recebimento fixo. Em vez disso, as saídas serão avaliadas na média no momento do lançamento (a não ser que você use a marcação) e elas serão reavaliadas no modelo heurístico selecionado quando você executou o fechamento do estoque.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>Posso usar reservas de FEFO com custos padrão?

Sim, você pode usar reservas de FEFO em um grupo de modelos de item quando selecionar custos padrão. As reservas de FEFO controlam a lógica de reserva que é usada para o manuseio físico dos itens, enquanto os custos padrão controlam o custo físico e financeiro de um item.

### <a name="can-i-upload-pending-prices"></a>Posso carregar preços pendentes?

Sim, você pode usar o suplemento do Excel na Estrutura de Gerenciamento de Dados para carregar um preço pendente. Recomendamos que você use as seguintes entidades:

- Preços de item pendentes (V2)
- Custos unitários de categoria de custo de roteiro pendentes
- Fatores de cálculo do nó de planilha de custos (V2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>Com que frequência posso atualizar o custo padrão de um item?

Não há limite para a frequência com que você pode ativar um novo custo padrão. Se você ativar um novo custo para um item no mesmo dia que o último custo foi ativado, o sistema usará o custo ativado mais recentemente nas novas transações ou atualizações (como updates de transações existentes).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>Posso desativar ou excluir um custo ativado?

Não, você não pode desativar ou excluir um custo ativado. Se ativou um custo incorretamente, você poderá ativar um novo custo que tenha o valor correto.

### <a name="are-calculation-groups-used-with-standard-costing"></a>Os grupos de cálculos são usados com custos padrão?

Os grupos de cálculos podem ser usados com qualquer item, independentemente do grupo de modelos de item que você escolher. Os grupos de cálculo são usados durante o acúmulo de custo ou no processo de cálculo de custo para determinar as configurações que devem ser usadas para os itens para os quais você está executando o cálculo. Para obter mais informações sobre grupos de cálculo, consulte [Grupos de cálculo da BOM](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>Quando devo usar uma versão custo planejado?

As versões de custos podem ter um tipo de *Custo padrão* ou *Custo planejado*. O tipo de *Custo padrão* é usado para os custos que estão ativos no sistema e que serão lançados nas transações. O tipo de *Custo planejado* é usado para a execução de simulações nos custos e não afeta o custo das transações.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>O custo total de um entidade pode ser transferido para outra entidade como o custo de venda?

Não há nenhuma maneira automatizada de copiar custos de uma empresa para outra. Além disso, não há nenhuma maneira automatizada de copiar custos de um preço de compra para um preço de venda. Se a sua organização tiver que concluir uma dessas tarefas, considere se é possível usar a Estrutura de Gerenciamento de Dados para exportar os dados para fora da versão de custos e carregá-los em uma empresa diferente, como um preço de venda na versão de custos ou como um contrato comercial. A manipulação manual dos arquivos pode ser necessária.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>Qual é a melhor maneira de copiar custos planejados para uma versão de custos padrão?

Você pode usar o botão **Copiar** na página **Versões de custos** para copiar preços de itens, preços de categoria de custo ou custos indiretos de uma versão de custos para outra.
