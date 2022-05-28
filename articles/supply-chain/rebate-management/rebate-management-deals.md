---
title: Acordos de gerenciamento de reembolso
description: Este tópico descreve como criar acordos de gerenciamento de reembolso. Os acordos são usados para controlar diferentes métodos e bases para calcular reembolsos e royalties. Eles incluem regras para inclusões e exclusões.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 76cdbf21cfbc0db7b363d0fbf60a1ecd0046efc1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689653"
---
# <a name="rebate-management-deals"></a>Acordos de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]

Os acordos de gerenciamento de reembolso são usados para controlar diferentes métodos e bases para calcular reembolsos e royalties. Eles incluem regras para inclusões e exclusões. Há três tipos de acordos de gerenciamento de reembolso: reembolsos de clientes, royalties de clientes e reembolsos de fornecedores. Os três tipos usam configurações semelhantes. Este tópico indica onde há diferenças.

## <a name="create-a-deal"></a>Crie um acordo

1. Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Todos os acordos de gerenciamento de reembolso**. Na página **Todos os acordos de gerenciamento de reembolso**, você pode criar e trabalhar com acordos dos três tipos.

    Outra alternativa é seguir uma destas etapas. Em cada caso, a página de listagem exibida fornece as mesmas configurações da página de listagem **Todos os acordos de gerenciamento de reembolso**, mas é filtrada para mostrar acordos de apenas um tipo.

    - Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Acordos de reembolso de clientes** para criar somente acordos de reembolso de clientes.
    - Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Acordos de royalty de clientes** para criar somente acordos de royalty de clientes.
    - Acesse **Gerenciamento de reembolso \> Acordos de gerenciamento de reembolso \> Acordos de reembolso de fornecedor** para criar somente acordos de reembolso de fornecedores.

1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar novo acordo**, defina os seguintes campos:

    - **Acordo de gerenciamento de reembolso** – Se você tiver [configurado uma sequência numérica](rebate-management-parameters.md) para acordos de reembolso, este campo será automaticamente definido como uma ID exclusiva, gerada pelo sistema. Caso contrário, insira uma ID exclusiva.
    - **Descrição** – insira uma descrição do acordo.
    - **Módulo** – Selecione o tipo de parceiro ao qual o acordo se aplica (*Cliente* ou *Fornecedor*). Dependendo da página inicial, este campo pode ser definido automaticamente com base no tipo de acordo selecionado. Nesse caso, o campo é somente leitura.
    - **Tipo** – Selecione o tipo de acordo (*Reembolso* ou *Royalty*). Dependendo da página inicial, este campo pode ser definido automaticamente com base no tipo de acordo selecionado. Nesse caso, o campo é somente leitura.
    - **Reconciliar por** – Selecione como o acordo deve ser calculado e reconciliado:

        - *Acordo* – um único reembolso deve ser processado para todos os reembolsos e deduções no acordo.
        - *Linha* – os reembolsos devem ser processados para cada linha em um acordo.

    - **Perfil de lançamento** – selecione o [perfil de lançamento](rebate-management-posting.md) a ser usado para transações em que o acordo se aplica. Este campo está disponível somente quando o campo **Reconciliar por** está definido como *Acordo*. Se ele estiver definido como *Linha*, você atribuirá o perfil mais tarde para cada linha adicionada ao acordo.
    - **Perfil de lançamento para garantia** – selecione o [perfil de lançamento](rebate-management-posting.md) a ser usado para transações de garantia. Os perfis de lançamento serão necessários somente para transações de garantia se a garantia se aplicar a um royalty. Caso contrário, embora um perfil de lançamento não seja obrigatório, se nenhum perfil de lançamento for especificado, será exibido um erro quando as garantias forem lançadas. Este campo está disponível somente quando o campo **Tipo** está definido como *Royalty*. 
    - **Saída de reembolso** – Selecione como o reembolso ou royalty deve ser pago:

        - *Financeiro* – gera uma nota de crédito de texto livre ou uma nota de débito de contas a pagar, de forma que quantias possam ser pagas ou recebidas posteriormente. Observe que as provisões **podem** ser usadas com reembolsos em que esta opção está selecionada. Esta opção é a única disponível quando o campo **Tipo** está definido como *Royalty*.
        - *Item* – gera uma ordem de venda para os itens de acordo com a configuração do acordo. Nessa ordem de venda, um preço igual a 0 (zero) é atribuído a cada item. Observe que as provisões **não podem** ser usadas com reembolsos em que esta opção está selecionada.

    - **Moeda do reembolso** – Selecione a moeda a ser usada quando o reembolso, a dedução ou o royalty é pago.
    - **Notas do documento** – insira notas sobre o acordo, conforme necessário.
    - **Garantia cumulativa** – você só poderá definir esta opção como *Sim* se o campo **Tipo** estiver definido como *Royalty*. Esta opção afeta o cálculo de pagamentos de dedução garantidos. Este é um exemplo:

        - A garantia do acordo é vender um valor que resultará em um pagamento de USD 10.000 por trimestre.
        - A organização que está vendendo as mercadorias vende um valor que causa um pagamento de dedução de USD 12.000 no primeiro trimestre. O resultado é um royalty de USD 12.000 que é pago, menos a garantia de USD 10.000.
        - Se a opção **Garantia cumulativa** estiver definida como *Sim*, o valor adicional de USD 2.000 em royalties pagos no primeiro trimestre se aplicarão ao segundo trimestre. Portanto, são garantidos USD 8.000 para o cliente (a garantia de USD 10.000 menos o pagamento adicional de USD 2.000).
        - No segundo trimestre, você registra vendas que disparam um royalty de USD 5.000.
        - O sistema identifica um pagamento de USD 3.000 (a garantia de USD 8.000 menos USD 5.000 de royalties pagos).
        - Se a opção **Garantia cumulativa** estiver definida como *Não*, haverá uma garantia total de USD 10.000 por trimestre. Essa garantia corresponde a um pagamento sugerido de USD 5.000 no segundo trimestre (a garantia de USD 10.000 menos USD 5.000 de royalties pagos).

1. Selecione **OK** para criar o acordo e fechar a caixa de diálogo.

Esse procedimento cria o nível de cabeçalho do novo acordo. Em seguida, você adicionará linhas ao acordo.

## <a name="add-lines-to-a-deal"></a>Adicionar linhas a um acordo

Depois de criar um acordo conforme descrito na seção anterior, você poderá abri-lo na página de listagem. Em seguida, você pode adicionar linhas para identificar os clientes ou fornecedores, itens, períodos, uma base e métodos de cálculo para o acordo. Um acordo pode ter uma ou várias linhas. Se um acordo tiver várias linhas, elas em geral serão do mesmo tipo, ou os mesmos parâmetros serão associados a elas. Até você adicionar linhas a um acordo, ele não fará nada.

1. Abra a página de listagem de acordos de reembolso apropriada, conforme descrito na seção anterior.
1. Encontre e abra o acordo com o qual deseja trabalhar.
1. Na FastTab **Gerenciamento de reembolso**, selecione um dos seguintes botões para adicionar uma linha de negócios à grade:

    - **Adicionar linha** – adicione uma nova linha de negócios, em branco.
    - **Copiar linha** – se uma linha de negócios existente for semelhante à linha de negócios que você deseja adicionar, você poderá selecionar este botão para adicionar uma cópia dela. A nova linha de negócios incluirá todas as configurações relativas a Detalhes de gerenciamento de reembolso. Você pode editar as configurações. Por exemplo, você geralmente atualizará a relação de item e a porcentagem de reembolso.

1. Na nova linha de negócios, defina os seguintes campos:

    - **Número de gerenciamento de reembolso** – Se você tiver [configurado uma sequência numérica](rebate-management-parameters.md) para números de gerenciamento de reembolso, este campo será automaticamente definido como uma ID exclusiva, gerada pelo sistema. Caso contrário, insira uma ID exclusiva.
    - **Tipo** – o tipo de acordo ao qual a linha se aplica (*Reembolso* ou *Royalty*). O valor é copiado do cabeçalho e não pode ser alterado.
    - **Descrição** – insira uma descrição da linha do acordo.
    - **Empresa** – Selecione a empresa (entidade legal) à qual a linha do acordo se aplica. Durante o processamento, os usuários podem processar somente as linhas de acordos atribuídas à empresa que estão usando no momento. A página de listagem **Acordos de reembolsos do cliente** fornece uma exibição de várias empresas, com base no acesso de segurança do usuário. No entanto, você só pode editar e processar reembolsos para a empresa que está usando no momento.
    - **Código da conta** – selecione o escopo de clientes ou fornecedores ao qual a linha de negócios se aplica:

        - *Tabela* – a linha de negócios se aplica a um cliente ou fornecedor específico.
        - *Grupo* – a linha de negócios se aplica a um grupo de clientes ou fornecedores. Para obter mais informações sobre como configurar grupos, consulte [Grupos de gerenciamento de reembolso](rebate-management-groups.md).
        - *Todos* – a linha de negócios se aplica a todos os clientes ou fornecedores.

    - **Relação da conta** – Se você selecionou *Tabela* no campo **Código de conta**, selecione o cliente ou fornecedor ao qual o acordo se aplica. Se você tiver selecionado *Grupo*, selecione o grupo de clientes ou fornecedores. Se você selecionou *Tudo*, este campo ficará indisponível.
    - **Código da item** – selecione o escopo de itens ao qual a linha de negócios se aplica:

        - *Tabela* – a linha de negócios se aplica a um item específico.
        - *Grupo* – a linha de negócios se aplica a um grupo de itens. Para obter mais informações sobre como configurar grupos, consulte [Grupos de gerenciamento de reembolso](rebate-management-groups.md).
        - *Todos* — a linha de negócios se aplica a todos os itens.

    - **Relação de itens** – Se você selecionou *Tabela* no campo **Código do item**, selecione o item ao qual a linha de negócios se aplica. Se você tiver selecionado *Grupo*, escolha o grupo de itens. Se você selecionou *Tudo*, este campo ficará indisponível.
    - **Tipo de unidade** – Selecione o tipo de unidade que se aplica à linha de negócio (*Unidade de estoque* ou *Unidade de peso variável*). Observe que este campo pode estar em branco em registros mais antigos. Nesse caso, pressupõe-se o valor da *Unidade de estoque*.
    - **(Parâmetros de gerenciamento de estoque)** – Nos campos restantes da linha de negócios, especifique valores para os parâmetros de gerenciamento de estoque que serão usados para definir os itens incluídos no acordo (como o tamanho, a cor, o estilo, o site e o depósito do item). Para adicionar ou remover as dimensões, selecione **Exibir dimensões** no Painel de Ações.

1. No Painel de ações, selecione **Salvar**.
1. Se desejar limitar ainda mais o conjunto de itens ao qual uma linha de negócios se aplica, selecione a linha e, depois, na guia **Gerenciamento de reembolso**, selecione **Filtrar** para abrir uma caixa de diálogo **Consulta** padrão.
1. Para cada linha de negócios adicionada, configure os detalhes de cálculo e outros detalhes na FastTab **Detalhes do gerenciamento de reembolso**, conforme descrito na próxima seção.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Adicionar detalhes de gerenciamento de reembolso a uma linha de negócios

Para cada linha de negócios, configure detalhes na FastTab **Detalhes de gerenciamento de reembolso**. Primeiro, selecione a linha de negócios na FastTab **Gerenciamento de reembolso**. Defina valores para essa linha de negócios usando as várias guias na FastTab **Detalhes de gerenciamento de reembolso**. As subseções a seguir descrevem como usar cada guia.

### <a name="settings-on-the-general-tab"></a>Configurações na guia Geral

A guia **Geral** na FastTab **Detalhes de gerenciamento de reembolso** permite configurar o método de cálculo e a base para a linha de negócios selecionada. Essa configuração controla se uma compra mínima é necessária, os perfis de lançamento associados à linha de negócios e os detalhes do cálculo. A tabela a seguir descreve os campos disponíveis.

| Campo | Descrição |
|---|---|
| Método de cálculo | Selecione o método a ser usado quando a linha de negócio selecionada for combinada com outras linhas de negócio (*Em etapas*, *Cumulativa*, *Contínua* ou *Total*). O valor deste campo pode afetar drasticamente o resultado dos cálculos de reembolso. Para obter uma descrição completa de cada método e exemplos que mostrem como ele afeta o cálculo do reembolso, consulte a seção [Métodos de cálculo para linhas de negócio](#calc-methods) mais adiante neste tópico. |
| Base | Selecione se o reembolso é aplicado com base na quantidade (ou seja, o número total de unidades que são compradas ou vendidas) ou no valor (ou seja, o preço total dos mercadorias compradas ou vendidas). |
| Tipo de transação | <p>Selecione o ponto no processo quando o cálculo deverá ocorrer:</p><ul><li>*Ordem* – use a quantidade ou o valor encomendado como a base do cálculo.</li><li>*Entregues* – use a quantidade ou o valor entregue como a base do cálculo.</li><li>*Fatura* – use a quantidade ou o valor faturado como a base do cálculo.</li></ul> |
| Unidade | Se você selecionou *Quantidade* no campo **Base**, selecione a unidade na qual a quantidade deve ser especificada. |
| Valor mínimo | Insira o valor mínimo que deve ser pago por período. Você poderá inserir um valor negativo para permitir valores de reembolso negativos se notas de crédito excederem vendas para o período. |
| Princípio de redução de reembolso | Selecione o [princípio de redução de reembolso](rebate-reduction-principle.md) que se aplica à linha de negócio. |
| Número da grade | Se a linha de negócio se aplicar a um item com grades, selecione a grade à qual a linha de negócio se aplica. |
| Base de reembolso de fornecedor | <p>Este campo é mostrado somente para reembolsos de fornecedores (ou seja, acordos em que o campo **Módulo** está definido como *Fornecedor*). Selecione a base de reembolso do fornecedor:</p><ul><li>*Ordem de compra* – o reembolso que o fornecedor recebe se baseia na quantidade ou no valor da ordem de compra.</li><li>*Ordem de venda* – o fornecedor só receberá um reembolso após a venda das mercadorias. O reembolso se baseia na quantidade ou no valor da ordem de venda.</li></ul> |
| Base de preço | <p>Este campo é mostrado somente para reembolsos de fornecedores (acordos em que o campo **Módulo** está definido como *Fornecedor*). Se você selecionou *Ordem de venda* no campo **Base de reembolso de fornecedor**, selecione a base de preço aplicável:</p><ul><li><p>*PEPS* – a tarefa periódica **Calcular preço de compra PEPS** deve ser executada para calcular o reembolso. (Para executar a tarefa, acesse **Gerenciamento de reembolso \> Tarefas periódicas \> Calcular preço de compra PEPS**.) Uma regra PEPS (primeiro a entrar, primeiro a sair) será usada para calcular o valor do estoque vendido. Esse valor será usado para calcular os reembolsos do fornecedor. Este é um exemplo:</p><ul><li>**Estoque vendido:** 1.000 unidades a USD 3,00 cada = USD 3.000</li><li>**Preço de compra atual, com base no PEPS:** USD 2,00</li><li>**Cálculo de trabalho:** *Unidades vendidas* × *Preço de compra atual* = 1.000 × USD 2,00 = USD 2.000</li></ul></li><li><p>*Último preço de compra* – o valor da última transação de compra será usado para calcular os reembolsos do fornecedor. Este é um exemplo:</p><ul><li>**Estoque vendido:** 1.000 unidades a USD 3,00 cada = USD 3.000</li><li>**Último preço de compra:** USD 2,00</li><li>**Cálculo de trabalho:** *Unidades vendidas* × *Último preço de compra* = 1.000 × USD 2,00 = USD 2.000</li></ul></li><li><p>*Preço médio de compra* – o valor médio ponderado dos últimos *X* meses será usado para calcular os descontos do fornecedor. Se você selecionar esta opção, deverá inserir o número de meses no campo **Número de meses** (que está disponível somente quando o campo **Base de preço** é definido como *Preço médio de compra*). Este é um exemplo:</p><ul><li>**Estoque vendido:** 1.000 unidades a USD 3,00 cada = USD 3.000</li><li>**Preço médio de compra:** USD 2,00</li><li>**Cálculo de trabalho:** *Unidades vendidas* × *Preço médio de compra* = 1.000 × USD 2,00 = USD 2.000</li></ul></li><li><p>*Preço de venda* – o preço de venda será usado para calcular os reembolsos do fornecedor. Este é um exemplo:</p><ul><li>**Estoque vendido:** 1.000 unidades a USD 3,00 cada = USD 3.000</li><li>**Preço médio de compra:** USD 2,00</li><li>**Cálculo de trabalho:** *Unidades vendidas* × *Preço de venda* = 1.000 × USD 3,00 = USD 3.000</li></ul></li></ul> |
| Número de meses | Este campo é mostrado somente para reembolsos de fornecedores (acordos em que o campo **Módulo** está definido como *Fornecedor*). Se você selecionou *Preço médio de compra* no campo **Base de preço**, insira o número de meses que deve ser usado. |
| Perfil de lançamento | Selecione [perfil de lançamento](rebate-management-posting.md) que se aplica à linha de negócio selecionada. Esse perfil é usado somente quando o campo **Reconciliar por** no cabeçalho de negócio é definido como *Linha*. Se o campo **Reconciliar por** estiver definido como *Negócio*, o perfil de lançamento definido no cabeçalho de negócio será sempre usado. Se nenhum perfil de lançamento estiver definido na linha de negócio, o perfil de lançamento definido no cabeçalho de negócio será usado. |
| Perfil de lançamento para garantia | Este campo funciona como o campo **Perfil de lançamento**, mas se aplica somente a royalties. |
| Tipo de Pagamento | O tipo de pagamento para o perfil de lançamento selecionado para o negócio. |
| Imposto inclusivo | Selecione se a transação tem imposto incluído. A inclusividade do imposto é relevante apenas quando o campo **Base** é definido como *Valor*. O valor da fatura será usado como o valor de imposto incluído. Se o cálculo do reembolso for baseado em uma porcentagem, o sistema multiplicará a porcentagem do reembolso pelo valor de imposto incluído. Observe que o cálculo usa o valor do imposto da linha de negócio. |
| Incluir notas de crédito | <p>Defina esta opção como *Sim* para incluir notas de crédito no cálculo de reembolso.</p><p>Se você definir esta opção como *Sim*, o efeito variará de acordo com o valor do campo **Tipo de transação**:</p><ul><li>Se o campo **Tipo de transação** estiver definido como *Fatura*, o cálculo será fatorado em notas de crédito. Essa configuração é a configuração usual.</li><li>Se o campo **Tipo de transação** estiver definido como *Ordem*, o cálculo será fatorado nas duas ordens de venda que têm valores negativos e ordens devolvidas abertas.</li></ul> |
| Valor descontado | Defina esta opção como *Sim* para basear o cálculo no valor descontado do item ou dos itens em casos em que os descontos de linha de negócio são fornecidos. |
| Faturas pagas somente | Defina esta opção como *Sim* se o cálculo dever considerar somente as faturas totalmente pagas. (Em outras palavras, os reembolsos não serão calculados para faturas parcialmente pagas). Esta opção está disponível somente quando o campo **Tipo de transação** é definido como *Fatura*. |
| Incluir texto livre | Defina esta opção como *Sim* para incluir faturas de texto livre no cálculo. As faturas de texto livre podem ser incluídas somente para linhas de negócio em que o campo **Código do item** está definido como *Todos*. |
| Incluir desconto de liquidação | Defina esta opção como *Sim* para reduzir o reembolso pelo primeiro desconto de liquidação. Presume-se que a organização terá o primeiro desconto de liquidação. Defina esta opção como *Não* para habilitar o desconto de liquidação a ser usado posteriormente. |
| Notas do documento | Insira notas que devam ser usadas como texto da transação em linhas do diário de transações de reembolso. |

### <a name="settings-on-the-dates-tab"></a>Configurações na guia Datas

As configurações na guia **Datas** da FastTab **Detalhes do gerenciamento de reembolso** definem a frequência e o tempo dos cálculos especificados na guia **Geral** . Elas determinam como os cálculos ocorrem no tempo de processamento.

Esta guia permite que você especifique o intervalo de datas no qual a linha de negócio selecionada é válida e a frequência de cálculo. Você também pode especificar se a garantia deve ser lançada e quando.

Você pode usar os botões da barra de ferramentas para adicionar linhas de datas à grade ou removê-las. Se houver várias linhas de datas, os intervalos de datas válidos não deverão se sobrepor. Caso contrário, você receberá uma mensagem de erro ao tentar salvar o negócio.

A tabela a seguir descreve os campos disponíveis para cada linha de datas.

| Campo | Descrição |
|---|---|
| Data Inicial | Insira a primeira data na qual a linha de data se aplica. Se as datas "de" e "até" forem especificadas no cabeçalho do negócio, elas serão usadas como valores padrão para cada nova linha de data. |
| Data final | Insira a última data na qual a linha de data se aplica. Se as datas "de" e "até" forem especificadas no cabeçalho do negócio, elas serão usadas como valores padrão para cada nova linha de data. |
| Por | Especifique com que frequência a linha de negócio deve ser calculada. Insira um inteiro aqui e selecione uma unidade no campo **Acumular por**. Por exemplo, para calcular semanas alternadas, defina o campo **Por** como *2* e o campo **Acumular por** como *Semanas*. |
| Acumular por | Selecione a unidade que se aplica à configuração **Por**. Selecione *Vida útil* para calcular toda a vida útil da linha de negócio. Selecione *Período personalizado* para selecionar um período definido na contabilidade. Nesse caso, você também deve definir o campo **Tipo de período**. |
| Tipo de período | Este campo está disponível somente quando o campo **Acumular por** está definido como *Período personalizado*. Os valores disponíveis para a seleção são obtidos dos tipos de período definidos na contabilidade. |
| Primeiro dia da semana | Especifique como as semanas são identificadas para o período. Este campo está disponível somente quando o campo **Acumular por** está definido como *Semanas*. |
| Reivindicar por | Especifique com que frequência as quantias de reembolso podem ser reivindicadas para a linha de negócio. Insira um inteiro aqui e selecione uma unidade no campo **Reivindicar por**. |
| Reivindicar por | Selecione a unidade que se aplica à configuração **Reivindicar por**. Selecione *Vida útil* para permitir reivindicações únicas durante a vida útil da linha de negócio. Selecione *Período personalizado* para selecionar um período definido na contabilidade. Nesse caso, você também deve definir o campo **Reivindicar tipo de período**. |
| Reivindicar tipo de período | Este campo está disponível somente quando o campo **Reivindicar por** está definido como *Período personalizado*. Os valores disponíveis para a seleção são obtidos dos tipos de período definidos na contabilidade. |
| Processar no lançamento | Marque esta caixa de seleção se a linha de declaração dever ser processada na hora de lançamento. Esta opção está disponível apenas para linhas de negócio em que o campo **Tipo de transação** na guia **Geral** está definido como *Entregue* ou *Fatura*. Para provisões, a provisão será lançada quando a nota de entrega ou fatura for gerada. |
| Garantia por | Este campo se aplica somente ao negócios de royalty. Especifique com que frequência a garantia do royalty deve ser calculada durante o período definido pela configuração  **Acumular por**. Insira um inteiro aqui e selecione uma hora de pagamento no campo **Garantia paga**. |
| Garantia paga | <p>Este campo se aplica somente ao negócios de royalty. Ele trabalha em conjunto com o campo **Garantia por** para definir a frequência do cálculo da garantia. Selecione um dos seguintes valores:</p><ul><li><p>*Início do período* – a garantia é paga no início do período do contrato definido para a linha de dados. A garantia total é processada primeiro. Somente o valor de royalties que excedem o valor garantido é lançado como um royalty. Este é um exemplo:</p><ul><li>**Garantia mínima:** USD 10.000 por dois meses.</li><li>**Mês 1:** USD 10.000 lançados como garantia e USD 0 lançados em royalties.</li><li>**Mês 2:** USD 2.000 lançados para royalties e USD 0 lançados em garantias.</li><li>**Cálculo de trabalho:** *Garantia restante* – *Royalties lançados* = USD 0 – USD 2.000 =-USD 2.000.</li></ul><p>Como é necessário um pagamento de royalty de USD 2.000, um diário é criado para USD 2.000.</p><p>**Observação:** a garantia deve ser calculada e lançada junto com a provisão de deduções para o primeiro período.</p></li><li><p>*Fim do período* – a garantia não é paga até o final do contrato de deduções, conforme definido na linha de data. Este é um exemplo:</p><ul><li>**Garantia mínima:** USD 10.000 por dois meses.</li><li>**Mês 1:** USD 5.000 foram lançadas como royalty e um diário foi criado.</li><li>**Mês 2:** USD 7.000 foram lançadas como royalty e um diário foi criado.</li><li>**Cálculo de trabalho:** como os royalties excedem o valor da garantia, USD 0 são lançados na garantia.</li></ul><p>**Observação:** a garantia deve ser calculada e lançada apenas junto com a transação de deduções e reembolsos para o período final.</p></li></ul> |
| Garantia mínima | Este campo se aplica somente ao negócios de royalty. Insira o valor mínimo da garantia de um royalty, na moeda definida no cabeçalho do negócio. |

### <a name="settings-on-the-lines-tab"></a>Configurações na guia Linhas

A guia **Linhas** da FastTab **Detalhes de gerenciamento de reembolso** permite definir linhas de cálculo para a linha de negócios selecionada. Cada linha de cálculo estabelece uma quantidade ou um limite de valor e um valor de remuneração ou itens relacionados. O campo **Base** em **Geral** especifica se cada linha de cálculo se baseia em uma quantidade ou um valor.

Você pode usar os botões da barra de ferramentas para adicionar linhas de cálculo à grade ou removê-las. Você pode ter qualquer número de linhas de cálculo. No entanto, se houver várias linhas de cálculo, a quantidade de "até" e "de" ou os intervalos de valores não deverão ser sobrepostos.

A tabela a seguir descreve os campos disponíveis para cada linha de cálculo.

| Campo | Descrição |
|---|---|
| Qtd./valor de origem | Insira a quantidade ou o valor mínimo ao qual a linha de cálculo se aplica. |
| Qtd./valor de destino | Insira a quantidade ou o valor máximo ao qual a linha de cálculo se aplica. |
| Método de gerenciamento de reembolso | <p>Este campo está disponível apenas para negócios em que o campo **Saída do reembolso** no cabeçalho é definido como *Financeiro*. Selecione o método a ser usado para calcular o reembolso.</p><ul><li>*Fixo* – um valor de preço fixo é usado para a linha.</li><li>*Porcentagem* – uma porcentagem do valor de venda é usada.</li><li>*Taxa* – é usado um valor de preço fixo por ordem.</li></ul><p>**Importante:** É recomendável utilizar o mesmo método para cada linha de cálculo na guia **Linhas**. Se um novo método for necessário, crie uma nova linha de negócio. Lembre-se de que você pode usar o botão **Copiar linha** na FastTab **Gerenciamento de reembolso** para criar uma nova linha de negócio a partir de uma linha de negócio existente.</p><p>**Observação:** se o campo **Saída do reembolso** for definido como *Item*, esse campo será sempre definido como *Fixo*. Para obter mais informações sobre como especificar os itens, consulte o texto após esta tabela. |
| Valor de gerenciamento de reembolso | Este campo está disponível apenas para negócios em que **Saída do reembolso** no cabeçalho é definido como *Financeiro*. Insira o valor que deve ser usado para calcular o reembolso, com base no método selecionado no campo **Método de gerenciamento de reembolso**. |

Como foi mencionado na tabela anterior, para negócios em que o campo **Saída do reembolso** no cabeçalho está definido como *Item*, você deve especificar os itens que serão fornecidos para cada linha de cálculo na guia **Linhas** . Para especificar os itens, siga estas etapas.

1. Na guia **Linhas**, crie a linha de cálculo necessária, caso ela não exista, e selecione-a.
1. Se o negócio não tiver sido salvo desde a criação da linha de cálculo, selecione **Salvar** no Painel de Ações.
1. Na guia **Linhas**, selecione **Itens**.
1. Na página **Itens**, use os botões no Painel de Ações para adicionar itens à grade ou remover itens, conforme necessário. Para cada linha, defina os seguintes campos:

    - **Número do item** – selecione o item que será fornecido.
    - **(Outras dimensões)** – Se você precisar usar mais dimensões para definir o item (por exemplo, configuração, tamanho, cor, estilo, site ou depósito do item), especifique-as. Para adicionar ou remover dimensões disponíveis, selecione **Exibir dimensões** no Painel de Ações.
    - **Quantidade** – Insira a quantidade que será fornecida depois que o limite da linha de cálculo selecionada for atingido.
    - **Unidade** – Selecione a unidade em que o valor **Quantidade** é especificado.
    - **Vários** – Este campo funciona junto com o campo **Quantidade**. Por exemplo, em uma linha de item, você define o campo **Quantidade** como *2* e o campo **Vários** como *100*. Se você tiver uma quantidade total da ordem de venda de 150, dois itens ficarão livres (dois por 100).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Configurações na guia Dimensões de estoque

A guia **Dimensões de estoque** na FastTab **Detalhes do gerenciamento de reembolso** mostra todos os valores de dimensão disponíveis para o produto especificado para a linha de negócio selecionada. Ela inclui dimensões que não são mostradas na FastTab **Gerenciamento de reembolso**. Você pode editar valores somente para as dimensões que se aplicam ao produto selecionado.

Você pode adicionar mais dimensões à grade na FastTab **Gerenciamento de reembolso**, selecionando **Exibir dimensões** no Painel de Ações.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Métodos de cálculo para linhas de negócio

Toda vez que você configura detalhes para uma das linhas de negócio, conforme descrito na seção anterior, você deve selecionar o método de cálculo para essa linha. Esta seção explica cada método de cálculo e fornece exemplos que mostram como cada método calcula o reembolso total de ordens e linhas de negócio. Nesses exemplos, as ordens e linhas de negócio são idênticas. Somente os métodos de cálculo são diferentes.

### <a name="stepped-calculation-method"></a>Método de cálculo em etapas

O método de cálculo em etapas calcula passo a passo, em que cada uma linha de negócio contribui de forma incremental para o reembolso até que a quantidade ou o valor de venda seja atingido. As etapas podem se basear na quantidade ou no valor das mercadorias vendidas, dependendo da configuração do campo **Base** na guia **Geral** da FastTab **Detalhes de gerenciamento de reembolso**.

Por exemplo, uma linha de negócio é configurada de forma que o campo **Método de cálculo** seja definido como *Em etapas* e o campo **Base** seja definido como *Valor*. Ele inclui linhas de cálculo que fornecem os seguintes reembolsos:

- **Linha A:** 10% até USD 1.000
- **Linha B:** 25% até USD 2.500

Se o valor das mercadorias compradas ou vendidas for USD 2.000, o reembolso resultante de USD 350 será calculado da seguinte maneira:

- **Reembolso (A):** *Limite (A)* × *Porcentagem (A)* = USD 1.000 × 10% = USD 100
- **Reembolso (B):** (*Valor vendido* – *Limite (A)*) × *Porcentagem (B)* = (USD 2.000 – USD 1.000) × 25% = USD 250
- **Reembolso total:** *Reembolso (A)* + *Reembolso (B)* = USD 100 + USD 250 = USD 350

Se o campo **Base** estiver definido como *Quantidade* em vez de *Valor*, o método de cálculo em etapas funcionará de forma semelhante. A primeira etapa é usada para a quantidade identificada até que a segunda etapa seja atingida. A segunda etapa é usada para todas as quantidades acima da primeira etapa até que a terceira etapa seja atingida. Esse processo prossegue por todas as etapas subsequentes.

### <a name="cumulative-calculation-method"></a>Método de cálculo cumulativo

O método de cálculo cumulativo usa apenas uma linha de cálculo para calcular o reembolso. Se várias linhas de cálculo estiverem disponíveis para a linha de negócio, a linha de cálculo de maior valor ou maior quantidade atingida será usada para toda a quantidade ou valor. Como os outros métodos de cálculo, o método cumulativo usa a configuração do campo **Base** na guia **Geral** da FastTab **Detalhes do gerenciamento de reembolso** para determinar se a quantidade de venda ou o valor de venda é usado para calcular os reembolsos.

Por exemplo, uma linha de negócio é configurada de forma que o campo **Método de cálculo** seja definido como *Cumulativo* e o campo **Base** seja definido como *Valor*. Ele inclui linhas de cálculo que fornecem os seguintes reembolsos:

- **Linha A:** 10% até USD 1.000
- **Linha B:** 25% até USD 2.500

Se o valor das mercadorias compradas ou vendidas for USD 2.000, o cálculo usará apenas a linha B. O reembolso resultante de USD 500 será calculado da seguinte maneira:

- **Reembolso total:** *Valor vendido* × *Reembolso (B)* = USD 2.000 × 25% =USD 500

### <a name="rolling-calculation-method"></a>Método de cálculo contínuo

O método de cálculo contínuo calcula todas as linhas de cálculo possíveis para o negócio. Se houver várias linhas de cálculo, e mais de uma delas for atingida, todas as linhas de cálculo atingidas serão usadas, mas os limites superiores se aplicarão a cada porcentagem. Como os outros métodos de cálculo, o método contínuo usa a configuração do campo **Base** na guia **Geral** da FastTab **Detalhes do gerenciamento de reembolso** para determinar se a quantidade de venda ou o valor de venda é usado para calcular os reembolsos.

Por exemplo, uma linha de negócio é configurada de forma que o campo **Método de cálculo** seja definido como *Contínuo* e o campo **Base** seja definido como *Valor*. Ele inclui linhas de cálculo que fornecem os seguintes reembolsos:

- **Linha A:** 10% até USD 1.000
- **Linha B:** 25% até USD 2.500

Se o valor das mercadorias compradas ou vendidas for USD 2.000, o reembolso resultante de USD 600 será calculado da seguinte maneira:

- **Reembolso (A):** *Limite (A)* × *Porcentagem (A)* = USD 1.000 × 10% = USD 100
- **Reembolso (B):** *Valor vendido* × *Porcentagem (B)* = USD 2.000 × 25% = USD 500
- **Reembolso total:** *Reembolso (A)* + *Reembolso (B)* = USD 100 + USD 500 = USD 600

### <a name="total-calculation-method"></a>Método de cálculo total

O método de cálculo total usa todas as linhas de cálculo para calcular o reembolso. Ele aplica a quantidade total para calcular o reembolso para cada linha de cálculo atingida e cada linha de cálculo aplica sua porcentagem ao valor total. Como os outros métodos de cálculo, o método total usa a configuração do campo **Base** na guia **Geral** da FastTab **Detalhes do gerenciamento de reembolso** para determinar se a quantidade de venda ou o valor de venda é usado para calcular os reembolsos.

Por exemplo, uma linha de negócio é configurada de forma que o campo **Método de cálculo** seja definido como *Total* e o campo **Base** seja definido como *Valor*. Ele inclui linhas de cálculo que fornecem os seguintes reembolsos:

- **Linha A:** 10% até USD 1.000
- **Linha B:** 25% até USD 2.500

Se o valor das mercadorias compradas ou vendidas for USD 2.000, o reembolso resultante de USD 700 será calculado da seguinte maneira:

- **Reembolso (A):** *Valor vendido* × *Porcentagem (A)* = USD 2.000 × 10% = USD 200
- **Reembolso (B):** *Valor vendido* × *Porcentagem (B)* = USD 2.000 × 25% = USD 500
- **Reembolso total:** *Reembolso (A)* + *Reembolso (B)* = USD 200 + USD 500 = USD 700
