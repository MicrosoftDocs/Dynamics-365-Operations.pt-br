---
title: Configuração do reconhecimento de receita
description: Este artigo descreve as opções de configuração para o reconhecimento de receita e as implicações referentes a elas.
author: bking
ms.date: 04/28/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 00acb795b05d01136cc154f697e7c955b0c6b620
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348400"
---
# <a name="revenue-recognition-setup"></a>Configuração do reconhecimento de receita
[!include [banner](../includes/banner.md)]

Um novo módulo **Reconhecimento de receita** foi adicionado e inclui itens de menu para todas as configurações necessárias. Este artigo descreve as opções de configuração e as implicações referentes a elas.

> [!NOTE]
> O recurso Reconhecimento de receita agora está habilitado por padrão pelo Gerenciamento de recursos. Se a sua organização não usar esse recurso, você poderá desativá-lo no espaço de trabalho **Gerenciamento de recursos**.
>
> O reconhecimento de receita, incluindo a funcionalidade de pacote, não é compatível com o uso em canais do Commerce (comércio eletrônico, PDV e call center). Os itens que são configurados para o reconhecimento de receita não devem ser adicionados a ordens ou transações que foram criadas nos canais do Commerce.

O módulo **Reconhecimento de receita** apresenta as seguintes opções de configuração:

- Diários de reconhecimento de receita
- Parâmetros para o reconhecimento de receita
- Agendas de receita 
- Configuração do estoque

    - Grupos de itens e produtos lançados
    - Definindo a agenda de receita
    - Definindo o preço de receita
    - Configuração do estoque

        - Definindo a agenda de receita
        - Definindo o preço de receita

    - Perfis de lançamentos
    - Pacotes

        - Componentes de pacote
        - Item de pacote

- Configuração de projeto

## <a name="revenue-recognition-journals"></a>Diários de reconhecimento de receita

Um novo tipo de diário foi introduzido para o reconhecimento de receita. O diário é necessário e usado em dois casos.

O primeiro ocorre após todas as obrigações contratuais terem sido atendidas, quando a receita adiada é reconhecida ao criar-se um diário de reconhecimento de receita baseado nos detalhes da agenda de receita. O diário contém uma entrada contábil que move o saldo da conta contábil da receita adiada para a conta contábil da receita.

O segundo cenário ocorre quando um diário é criado após a realocação. A realocação ocorre quando uma linha da ordem de venda é adicionada a uma ordem de venda faturada anteriormente, ou quando uma nova ordem de venda é criada e inclui uma linha que faça parte do contrato original. Se uma fatura for lançada antes que a nova linha de ordem de venda seja adicionada, uma entrada contábil de correção deve ser criada para a fatura de cliente lançada.

O diário é configurado na página **Nomes de diários** (**Reconhecimento de receita \> Configuração \> Nomes de diários**). O tipo de diário deve ser definido como **Reconhecimento de receita**. 

## <a name="parameters-for-revenue-recognition"></a>Parâmetros para o reconhecimento de receita

As configurações de reconhecimento de receita são definidas na guia **Reconhecimento de receita** da página **Parâmetros de contabilidade** (**Reconhecimento de receita \> Configuração \> Parâmetros de contabilidade**). As seguintes configurações estão disponíveis:

- **Nome do diário de reconhecimento de receita** — Selecione o diário que foi criado para o reconhecimento de receita. O diário é necessário quando a receita é reconhecida na agenda de receita, ou quando você faz a realocação para uma ordem de venda que foi faturada anteriormente.
- **Habilitar o método de alocação de desconto** — Defina essa opção como **Sim** para determinar o preço de receita através da alocação do valor de mercado justo definido no preço de receita para cada produto liberado. Essa alocação inclui a alocação das linhas de descontos para os itens. Se essa opção for definida como **Não**, o sistema usará o preço médio definido no preço de receita para cada produto liberado. Se essa opção estiver definida como **Não**, mas nenhum preço médio estiver configurado para os produtos lançados, a alocação do preço de receita não ocorre.
- **Incluir descontos de cabeçalho** — Defina essa opção como **Sim** para determinar o preço da receita ao alocar descontos para os produtos. Se essa opção estiver definida como **Não**, o desconto de cabeçalho não será incluído na alocação de preço da receita.
- **Desabilitar os termos de contrato** — Defina essa opção como **Sim** se os produtos com um tipo de receita de **Suporte pós-contrato** puderem ser liberados mesmo se as datas de início e término do contrato não estiverem definidas para eles. Normalmente, as datas de início e término do contrato são requeridas para o tipo de receita **Suporte pós-contrato**. Quando as datas de início e término do contrato não forem definidas, os detalhes da agenda de receita no lançamento serão calculados usando o número de ocorrências e a data da fatura.
- **Lançar correções de fatura para Contas a receber ao realocar** — Ao realocar faturas já lançadas, a entrada contábil da fatura lançada deve ser corrigida. Use essa opção para especificar como a correção é feita.

    - Defina essa opção como **Não** para limitar o lançamento da transação de correção na Contabilidade. Quando essa opção é definida como **Não**, nenhum documento adicional é criado em Contas a receber para a correção de contabilidade interna. Quando a fatura é paga, o processo de pagamento usa a entrada contábil anterior para lançar todos os descontos à vista ou lucros realizados ou perdas.
    - Defina essa opção como **Sim** para criar automaticamente um documento do estorno e uma nova fatura para a transação de correção em Contas a receber. Como a correção será uma correção de contábil interna, os novos documentos não serão enviados ou não serão mencionados para o cliente. O documento de estorno é liquidado na fatura original, e a nova fatura corrigida é paga pelo cliente. Observe que os três documentos são exibidos em relatórios, como o demonstrativo de cliente.

[![Informações de configuração.](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>Agendas de receita

Uma agenda de receita deve ser criada para cada ocorrência na qual a receita pode ser adiada. Por exemplo, se a sua organização oferecer suporte por períodos de seis meses, 12 meses, 18 meses e 24 meses, você deve criar uma agenda de receita para cada período. A configuração da agenda de receita determina como o preço da receita é alocado de acordo com o número de períodos selecionado. Isto também determina as datas padrão inseridas para a agenda de receita que é criada quando a fatura é lançada.

Se você reconhece a receita por marcos, recomendamos criar uma agenda de reconhecimento de receita para o número de marcos, independentemente das datas de reconhecimento. Após criar as agendas, você pode editá-las para que reflitam as datas previstas para os marcos. Esses registros podem ser colocados em espera até você ser notificado de que o marco foi atingido e a receita puder ser reconhecida.

As agendas de receita são criadas na página **Agendas de receita** (**Reconhecimento de receita \> Configuração \> Agendas de receita**).

[![Agendas de receita.](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

Insira os valores descritivos nos campos **Agenda de receita** e **Descrição**. As seguintes configurações adicionais são usadas para criar a agenda de receita quando a fatura for lançada.

- **Ocorrências** — Insira o número de meses ou de ocorrências em que a receita foi adiada.
- **Bloqueio automático** — Marque essa caixa de seleção se todas as linhas da agenda de receita forem automaticamente colocadas em espera quando a fatura for lançada. O bloqueio deve ser removido manualmente de cada linha da agenda antes que a receita adiada da linha possa ser reconhecida.
- **Termos de contrato automático** — Marque essa caixa de seleção se as datas de início e término do contrato forem definidas automaticamente. Essas datas são definidas automaticamente somente para produtos lançados do tipo receita **Suporte pós-contrato**. A data de início do contrato é definida automaticamente como a data de remessa solicitada da linha da ordem de venda, e a data de término do contrato é configurada automaticamente como a data inicial mais o número de meses ou de ocorrências definido na configuração da agenda da receita. Por exemplo, o produto na linha da ordem de venda é para uma garantia de um ano. A agenda de receita padrão é **12M** (12 meses) e a caixa de seleção **Termos de contrato automático** está marcada para essa agenda de receita. Se a linha da ordem de venda tiver uma data de remessa solicitada de 16 de dezembro de 2019, a data de início padrão do contrato é 16 de dezembro de 2019 e a data de término padrão do contrato é 15 de dezembro de 2020.
- **Base de reconhecimento** — a base de reconhecimento determina como o preço da receita será alocado entre as ocorrências.

    - **Mensalmente por dias** — o valor é alocado com base nos dias de cada mês do calendário.
    - **Mensal** — o valor é alocado igualmente pelo número de meses definido nas ocorrências.
    - **Ocorrências** — o valor é alocado igualmente entre as ocorrências, mas pode incluir um período adicional se você selecionar **Data de início real** como convenção de reconhecimento.
    - **Período fiscal por dias** — o valor é alocado com base nos dias de cada período fiscal. 

         - Os resultados de **Mensais por dias** e **Período fiscal por dias** serão os mesmos quando os períodos fiscais seguirem meses do calendário. A única exceção é quando a convenção de reconhecimento é definida como **Fim do mês/período**, e os campos **Data de início do contrato** e **Data de término** são deixados em branco em uma linha da ordem de venda.

- **Convenção de reconhecimento** — a convenção de reconhecimento determina as datas que são definidas na agenda de receita para a fatura.

    - **Data de início real** — a agenda será criada usando-se a data de início do contrato (para itens de suporte pós-contrato \[PCS\]) ou a data da fatura (para itens essenciais e não essenciais).
    - **Primeiro dia do mês/período** — a data na primeira linha da agenda é a data de início do contrato (ou da fatura). Entretanto, as linhas de agendas subsequentes são criadas para o primeiro dia do mês ou do período fiscal.
    - **Divisão do meio do mês** — a data na primeira linha da agenda depende da data da fatura. Se a fatura for lançada na primeira metade do mês, a agenda de receita será criada usando-se o primeiro dia do mês. Se a fatura for lançada na segunda metade do mês, a agenda de receita será criada usando-se o primeiro dia do mês seguinte.

        - **Divisão do meio do mês** não poderá ser selecionada se a base de reconhecimento for definida como **Período fiscal por dias**.

    - **Primeiro dia do mês/período** — a data na qual agenda começa é o primeiro dia do mês ou do período fiscal seguinte.
    - **Fim do mês/período** — a data na primeira linha da agenda é a data de início do contrato (ou da fatura). Entretanto, todas as linhas de agenda subsequentes são criadas para o último dia do mês ou do período fiscal. 

Selecione o botão **Detalhes da agenda da receita** para exibir os períodos gerais e as porcentagens reconhecidas em cada período. Por padrão, o valor **Reconhecer porcentagem** é dividido igualmente pelo número de períodos. Se a base de reconhecimento for definida como **Mensal**, a porcentagem de reconhecimento poderá ser alterada. Ao alterar a porcentagem de reconhecimento, uma mensagem de aviso informa que o total não equivale a 100%. Se receber essa mensagem, você poderá continuar editando as linhas. No entanto, a porcentagem total deve equivaler a 100 antes de fechar a página.

[![Detalhes da agenda de receita.](./media/revenue-schedule-details-2nd-scrn.png)](./media/revenue-schedule-details-2nd-scrn.png)

## <a name="inventory-setup"></a>Configuração do estoque

Você pode reconhecer a receita de produtos lançados nas ordens de venda, exceto com categorias de vendas nas ordens de venda ou com faturas em texto livre, caso nenhum item seja incluído no documento. As seleções feitas ao configurar produtos lançados determinam como a receita do item é reconhecida. Por exemplo, as seleções determinam se o preço da receita está alocado, e se a receita é adiada usando-se uma agenda de receita.

A configuração pode começar na FastTab **Reconhecimento de receita** da página **Grupo de itens** (**Reconhecimento de receita \> Configuração \> Configuração de estoque e produto \> Grupo de itens**). Essa página inclui vários campos de configuração. Esses campos são usados para definir valores somente para os novos produtos lançados que foram criados no sistema. Conforme os novos produtos forem criados, os valores definidos aqui serão inseridos por padrão para o grupo de itens. Você pode substituir os valores padrão para produtos lançados na página **Produtos liberados** (**Reconhecimento de receita \> De instalação \> Configuração de estoque e produto \> Produtos liberados**). Os valores padrão são definidos para os produtos lançados e transferidos para a ordem de venda.

## <a name="item-groups-and-released-products"></a>Grupos de itens e produtos lançados

### <a name="define-the-revenue-schedule"></a>Definir a agenda de receita

A receita na linha da ordem de venda é adiada se uma agenda de receita for definida para o produto liberado e usado por padrão na linha de ordem de venda. Caso a configuração deva ser usada por padrão para o produto, você pode definir a agenda de receita na FastTab **Reconhecimento de receita** da página **Grupo de itens** (**Reconhecimento de receita \> Configuração \> Configuração de estoque e produto \> Grupo de itens**). Você também pode definir a configuração dos produtos liberados na FastTab **Reconhecimento de receita** da página **Produtos liberados** (**Reconhecimento de receita \> Configuração \> Configuração de estoque \> Produtos liberados**).

No campo **Agenda de receita**, selecione a agenda de receita que representa o período em que a receita deve ser adiada. A agenda de receita é automaticamente inserida na linha da ordem de venda e os detalhes da receita são criados quando a fatura da ordem de venda é lançada.

### <a name="define-the-revenue-price"></a>Definir o preço da receita

Os grupos de itens e os produtos liberados podem ser configurados usando-se o método de preço médio ou o método de alocação de desconto. Os dois métodos precisam de mais configurações na página **Produtos liberados**:

- **A alocação de receita está ativa** — Defina essa opção como **Sim** para incluir o produto liberado no cálculo de alocação da receita. Se essa opção for definida como **Não**, o produto liberado usará o método do preço médio se o mesmo estiver configurado. Se o preço médio não estiver definido, o preço unitário na linha da ordem de vendas será usado para lançar a receita ou adiar a receita.
- **Tipo de receita** — Selecione o tipo da receita que define os produtos liberados:

    - **Essencial** — O item é uma fonte principal da receita de uma organização. Essa é a configuração padrão.
    - **Não essencial** — O item não é uma fonte principal da receita de uma organização. Quando as configurações de preço médio forem usadas, o preço será usado para formar o preço médio e alocado em seguida. Por exemplo, um item essencial tem um preço fixo que deve ser reconhecido para a receita. Se houver um desconto, o desconto pode ser formado usando-se a receita de item essencial, mas **apenas** até o valor de preço fixo. O resto do desconto é extraído da receita para itens não essenciais. Alternativamente, o desconto pode não ser formado pela receita do item essencial.
    - **Suporte pós-contrato** — O item oferece suporte a outros elementos incluídos na venda para o cliente. O preço da receita é distribuído nos produtos essenciais e não essenciais incluídos na venda. Dependendo da configuração, os itens de PCS não podem exigir que as datas de início e término do contrato sejam definidas na linha da ordem de venda.

- **Excluir do formato** — Defina essa opção como **Sim** para indicar que o preço médio do item não pode ser ajustado abaixo da porcentagem mínima definida ou acima de porcentagem máxima. Os preços das receitas serão derivados do preço de receita de outros produtos liberados que foram incluídos na ordem de venda. Se opção for definida como **Não**, o preço médio do item pode ser ajustado ou criado. Observe que se você vender mais de um item que está configurado como preço médio, pelo menos um produto liberado deve ser configurado onde a opção **Excluir do formato** estiver definida como **Não**. Dessa maneira, há pelo menos um item para o qual as diferenças no preço de receita podem ser alocadas.
- **Preço médio** — Defina essa opção como **Sim** para indicar que o preço da receita do item deve ser ajustado até se igualar ao preço médio caso esteja abaixo da tolerância mínima especificada ou acima da tolerância máxima e o valor formado deve ser alocado para as linhas com os produtos onde a opção **Excluir do formato** estiver definida como **Não**.

    - **Tolerância máxima** — Insira a porcentagem acima do preço médio selecionado que é permitida.
    - **Tolerância mínima** — Insira a porcentagem abaixo do preço médio selecionado que é permitida.

Depois que concluir a configuração das definições para produtos liberados, você deverá definir manualmente o preço de receita inserindo o preço justo ou preço médio (se estiver usando o método de preço médio) da página **Preços de receita** (acesse **Reconhecimento de receita \> Configuração \> Configuração de estoque \> Produtos liberados** e, depois, no Painel de Ações, na guia **Vender**, no grupo **Reconhecimento de receita**, selecione **Preços de receita**).

[![Preços de receita.](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

O preço de receita definido manualmente nessa página é usado para determinar a alocação do preço da receita em cada ordem de venda, com base nos critérios definidos. Cada critério corresponde à linha da ordem de venda para determinar o preço da receita que deve ser usado no processo de alocação.

- **Código do item** e **Relação de itens** — O preço de receita pode ser definido para um produto individual ou grupo de produtos. Se selecionar **Tabela** no campo **Código do item**, selecione o produto liberado no campo **Relação de itens**. Se selecionar **Grupo** no campo **Código do item**, selecione o produto liberado no campo **Relação de itens**.
- **Código da conta** e **Número de conta/grupo** — O preço de receita pode ser definido para todos os clientes, um cliente individual, ou um grupo de clientes. Se selecionar **Tudo** no campo **Código da conta**, o preço será usado para todos os clientes. Se selecionar **Tabela** no campo **Código da conta**, selecione o cliente no campo **Número da conta/grupo**. Se selecionar **Grupo** no campo **Código da conta**, selecione o grupo de clientes no campo **Número da conta/grupo**.
- **Moeda** — Você deve inserir um preço de receita separado para cada moeda inserida em uma ordem de venda. Por exemplo, se você vende atualmente em dólares americanos, em dólares canadenses e em euro, deverá definir um preço de receita em todas as três moedas. O preço de receita não é convertido de uma moeda, como moeda contábil, para qualquer outra moeda de transação que estiver você estiver usando.
- **Valor ou percentual da lista** — Especifique se o preço da receita está configurado como um valor ou um percentual do preço de lista. Se você selecionar **Percentual de lista**, os usuários poderão inserir o preço médio como um percentual do preço de lista em vez de um valor. O valor **Percentual de lista** é usado apenas para os produtos liberados que são configurados como itens PCS.
- **Preço de alocação da receita** — Dependendo do valor selecionado no campo **Valor ou percentual de lista**, insira um valor ou um percentual para representar o preço da receita que é usado para alocar a receita nos elementos na ordem de venda.
- **De** e **Até** — Insira o intervalo de datas para o qual o preço da receita está ativo. Esses campos são opcionais.

Se a opção **Habilitar o método de alocação de desconto** na opção **Parâmetros de contabilidade** estiver definida como **Sim**, e se o campo **Tipo de receita** do produto liberado estiver definido como **Suporte pós-contrato**, especifique também os itens que estão recebendo suporte do produto liberado. Essa configuração é feita na página **Base de configuração** (vá para **Reconhecimento de receita \> Configuração \> Configuração de estoque \> Produtos liberados** e, depois, no Painel de Ações, na guia **Vender**, no grupo **Reconhecimento de receita**, selecione **Base de configuração**).

Na página **Base de configuração**, adicione um registro para cada grupo de itens compatível com o item. Quando a alocação de receita ocorrer, o preço de receita será distribuído entre as partes essenciais e não essenciais para o item PCS.

### <a name="posting-profiles"></a>Perfis de lançamentos

Três tipos adicionais de lançamento são compatíveis com o adiamento da receita. Esses tipos de lançamento são configurados na guia **Ordem de venda** da página **Lançamento** (**Reconhecimento de receita \> Configuração \> Configuração de estoque e produto \> Lançamento**).

- **Receita adiada** — Insira a conta principal do preço da receita que é lançado na receita adiada (em vez da receita). O preço da receita é adiado se a linha da ordem de venda tiver uma agenda de receita.
- **Custo dos produtos vendidos diferidos** — Insira a conta principal para o valor do custo dos produtos vendidos para lançar os custo dos produtos vendidos diferidos se a receita também for adiada.
- **Compensação de receita de fatura parcial** — Insira a conta principal da conta de compensação que será usada quando a ordem de venda for parcialmente faturada ou quando a realocação ocorrer. O saldo dessa conta retorna para zero (0) quando as ordens de venda forem faturadas integralmente.

### <a name="bundles"></a>Pacotes

Os itens do pacote são produtos exclusivos liberados que são configurados para incluir componentes. Essa configuração é feita usando-se a funcionalidade de lista de materiais (BOM). Quando um item de pacote é inserido em uma ordem de venda, os componentes individuais são usados para determinar os preços de receita e agendas de receita. No entanto, os documentos impressos para o cliente, como a ordem de venda e a fatura, refletem o item do pacote.

#### <a name="bundle-components"></a>Componentes de pacote

Os componentes incluídos no pacote devem ser configurados em **Produtos liberados** (**Reconhecimento de receita \> Configuração \> Configuração de estoque e produto \> Produtos liberados**). Esses componentes são produtos liberados e devem ser configurados da mesma forma como os produtos que estão incluídos em uma BOM. Por exemplo, um produto liberado pode ser um item de tipo **Item** ou do tipo **Serviço**, mas deve ser atribuído a um grupo de modelo do item quando a opção **Produtos em estoque** estiver definida como **Sim**. Para obter mais informações, consulte a documentação de configuração de itens da BOM.

Os componentes também devem ser configurados também para o reconhecimento de receita, como se fossem produtos que podem ser vendidos individualmente em uma ordem de venda. Por exemplo, certifique-se de que o preço atual da receita esteja definida para cada componente e de que a base de preço esteja configurada para itens PCS.

#### <a name="bundle-items"></a>Itens do pacote

Ao configurar um item do pacote, é necessário configurar dois campos na página **Produtos liberados** (**Reconhecimento de receita \> Configuração \> Configuração de estoque e produto \> Produtos liberados**).

- Na FastTab **Engenharia**, no campo **Tipo de produção**, o item deve ser configurado como um item de BOM.
- Na FastTab **Geral**, no campo **Pacote**, o item deve ser marcado como um item do pacote.

Os componentes devem ser atribuídos ao item principal do pacote/BOM na página **Versões de BOM** (vá para **Reconhecimento de receita \> Configuração \> Configuração de estoque e produto \> Produtos liberados** e, depois, no Painel de Ações, na guia **Engenharia**, no grupo **BOM**, selecione **Versões de BOM**). Para obter mais informações, consulte a documentação de configuração de BOMs.

[![Produtos liberados, agendas de BOM.](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

Se o item principal do pacote e os componentes do pacote forem definidos para serem alocados, o preço de receita do pacote será distribuído aos componentes, com base nas porcentagens de contribuição de receita.

## <a name="project-setup"></a>Configuração de projeto

O reconhecimento de receita pode ser usado para ordens de venda criadas com um projeto por tempo e material. Para ordens de venda que se originam de projetos, você precisa definir apenas as contas principais em perfis de lançamentos do projeto usados para lançar as faturas do projeto. As contas principais são definidas na página **Configuração do lançamento contábil** (**Reconhecimento de receita \> Configuração \> Configuração de projeto \> Configuração do lançamento contábil**).

- **Receita faturada diferida** (em **Contas de receita**) — Insira a conta principal do preço da receita que é lançado na receita adiada (em vez da receita). O preço da receita é adiado se a linha da ordem de venda tiver uma agenda de receita.
- **Custo adiado** (em **Contas de custo**) — Insira a conta principal para o valor do custo dos produtos vendidos para lançar os custo dos produtos vendidos adiados se a receita também for adiada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
