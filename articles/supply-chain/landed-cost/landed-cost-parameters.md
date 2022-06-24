---
title: Configuração de parâmetros de custo de entrega
description: Este artigo descreve como configurar informações gerais e definições de configuração que são usadas no módulo de custo de entrega para lançamento, atualizações de status, sequências numéricas e comportamento.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 99dbe17d4e83c2c75d52ca3fd22a1772d8045355
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871968"
---
# <a name="landed-cost-parameters-setup"></a>Configuração de parâmetros de custo de entrega

[!include [banner](../../includes/banner.md)]

Você usa a página **Parâmetros de custo de entrega** para configurar informações gerais e definições de configuração que são usadas no módulo **Custo de entrega** para lançamento, atualizações de status, sequências numéricas e comportamento. A configuração de parâmetros é compartilhada em entidades legais e pode ser modificada por um administrador.

## <a name="open-the-landed-cost-parameters-page"></a>Abra a página Parâmetros de custo de entrega

Para trabalhar com os parâmetros, acesse **Custo de entrega \> Configuração \> Parâmetros de custo de entrega** e defina os campos conforme descrito nas subseções a seguir.

![Página Parâmetros de custo de entrega.](media/landed-cost-parameters.png "Página Parâmetros de custo de entrega")

## <a name="general-tab"></a>Guia Geral

### <a name="general-fasttab"></a>FastTab Geral

A tabela a seguir descreve os campos disponíveis na FastTab **Geral** da guia **Geral** da página **Parâmetros de custo de entrega**.

| Configuração | descrição |
|---|---|
| Usar taxa de remessa | Uma taxa de remessa é definida para um período definido e é usada para custos estimados de mercadorias que usam várias moedas. Defina esta opção como *Sim* para usar uma taxa de remessa. |
| Tipo de taxa de câmbio | A coleção padrão de taxas de câmbio usada para cálculos de várias moedas para uma viagem e custos de viagem. |
| Atualizar quantidade da ordem de compra | Selecione o que ocorrerá se um usuário alterar a quantidade em uma linha da ordem de compra:<ul><li>**Aceitar** – a quantidade de viagens é ajustada automaticamente.</li><li>**Aviso** – se a linha estiver associada a uma viagem, um aviso será exibido, mas a quantidade de viagens será atualizada.</li><li>**Erro** – se a linha estiver anexada a uma viagem, uma mensagem de erro será mostrada e a ordem de compra não poderá ser atualizada. Portanto, a linha da ordem deve primeiro ser removida da viagem.</li></ul> |
| Atualizar automaticamente o número de caixas | Quando esta opção é definida como *Sim*, todas as embalagens são adicionadas juntas e exibidas nos níveis de viagem e contêiner. Quando ele está definido como *Não*, o número de caixas é inicialmente definido como 0 (zero) e pode ser editado manualmente, conforme necessário. |

### <a name="costing-fasttab"></a>FastTab Avaliação de custo

A tabela a seguir descreve os campos disponíveis na FastTab **Avaliação de custo** da guia **Geral** da página **Parâmetros de custo de entrega**.

| Configuração | Descrição |
|---|---|
| Especificação de lançamento | Selecione o ajuste de valor no razão:<ul><li>**Total** – um valor total é lançado no razão.</li><li>**Grupo de itens** – o ajuste é especificado por grupo de itens.</li><li>**Número de itens** – o ajuste é especificado por item. Esse valor fornece mais detalhes.</li></ul> |
| Permitir custo zero | Defina esta opção como *Não* para mostrar um erro se um usuário tentar lançar uma estimativa de custo para uma fatura de viagem ou uma ordem de compra que não inclua um valor para o custo de viagem esperado. A mensagem de erro informa que um custo 0 (zero) não pode ser alocado e o lançamento da fatura falhará. Nesse caso, o usuário pode atualizar manualmente a estimativa (ou reconfigurar o custo automático) e, em seguida, extrair o valor atualizado ou excluir o custo caso ele não se aplique.<p>Defina esta opção como *Sim* para permitir que o custo de viagem seja deixado em branco. Nesse caso, o preço 0 (zero) será alocado de acordo com a área de custo. Uma fatura de custo do fornecedor pode ser processada em relação ao custo de preço zero quando a viagem é recebida.</p><p>É recomendável configurar a estimativa no registro de custo automático para evitar que um custo de preço zero apareça. Embora essa estimativa não seja totalmente precisa, ela ainda será mais precisa do que um custo zero presumido.</p> |
| Data de lançamento de ajuste | Quando você lança uma fatura de custo de uma viagem de Contas a pagar, a tabela de liquidações (ajustes de estoque) também é atualizada. Selecione a data definida por padrão na página **Selecionar custos de viagem** enquanto estiver no diário de fatura:<ul><li>**Data da transação** – use a data do diário (data de lançamento).</li><li>**Data da fatura da ordem de compra** – use a data de lançamento financeiro da fatura de estoque (ordem de compra).</li><li>**Data selecionada** – o usuário pode especificar uma data de lançamento. Embora a data possa ficar em branco, se ela ainda estiver em branco quando a fatura de custo for lançada, o usuário receberá uma mensagem de erro.</li></ul> |
| Usar comprovante de fatura de compra | Quando esta opção for definida como *Sim*, as transações de acumulação de custo usarão o mesmo número de comprovante usado para a fatura de compra. Quando estiver definido como *Não*, o sistema usará o próximo número disponível para a sequência numérica do **Comprovante de acúmulo de custos** configurada na guia **Sequências numéricas** da página **Parâmetros de custo de entrega**.<p>Esta opção só tem efeito quando a opção **Lançar na conta de encargos do razão** está definida como *Sim* na guia **Fatura** da página **Parâmetros de contas a pagar**.</p> |
| Bloquear lançamento manual para limpar conta | Defina esta opção como *Sim* para impedir o lançamento em contas de compensação nas quais a transação não está vinculada a uma viagem, selecionando **Funções \> Selecionar custos de viagem** no Painel de Ações do diário de faturas do fornecedor. É recomendável definir esta opção como *Sim* para que a conta de viagem e de compensação possa ser liquidada corretamente. |
| Usar conta de acúmulo de encargo do tipo de custo | Quando esta opção for definida como *Sim*, a conta de competência de encargo configurada para o código de tipo de custo relevante na página **Códigos de tipo de custo** será usada para acumular custos como uma despesa.<p>Esta opção só tem efeito quando a opção **Lançar na conta de encargos do razão** está definida como *Sim* na guia **Fatura** da página **Parâmetros de contas a pagar**. |
| Lançar ajustes como variação | Quando esta opção é definida como *Sim*, a funcionalidade padrão é substituída e obriga as transações de ajuste de estoque relacionadas a variações entre os custos estimados e os custos reais a serem lançadas em uma conta de variação.<p>Quando esta opção é definida como *Não*, as transações de ajuste de estoque relacionadas a variações são tratadas com base na configuração do método de avaliação de custo e do código de tipo de custo. Para custo padrão, as variações ainda serão lançadas na conta de variação. Para a média ponderada móvel (WMA), as variações serão lançadas na conta de variação ou no estoque.</p><p>Esta opção só tem efeito quando a opção **Lançar na conta de encargos do razão** está definida como *Sim* na guia **Fatura** da página **Parâmetros de contas a pagar**.</p> |

### <a name="validation-fasttab"></a>FastTab Validação

A tabela a seguir descreve os campos disponíveis na FastTab **Validação** da guia **Geral** da página **Parâmetros de custo de entrega**.

| Configuração | Descrição |
|---|---|
| Várias faturas de custo | Selecione o que ocorre se mais de uma fatura for processada em relação a uma viagem, fólio ou contêiner para o mesmo encargo diverso.<ul><li>**Aceitar** – o sistema deve permitir várias faturas de custo.</li><li>**Aviso** – um aviso é exibido.</li><li>**Erro** - uma mensagem de erro é mostrada.</li></ul> |
| Vários fornecedores por fólio | Selecione o que ocorrerá se mais de uma ordem de compra do fornecedor for adicionada a um fólio.<ul><li>**Aceitar** – o sistema deve permitir a ação.</li><li>**Aviso** – um aviso é exibido, mas a ação ainda pode ser executada.</li><li>**Erro** – uma mensagem de erro é mostrada e a ação é impedida.</li></ul><p>Seu corretor alfandegário ou as legislações locais podem obrigar um valor específico para este campo.</p> |
| Modo múltiplo de tolerância de entrega | Selecione o que ocorrerá se as mercadorias de uma ordem de compra que utiliza um modo de entrega diferente daquele da viagem forem adicionadas a essa viagem.<ul><li>**Aceitar** – o sistema deve permitir a ação.</li><li>**Aviso** – um aviso é exibido, mas a ação ainda pode ser executada.</li><li>**Erro** – uma mensagem de erro é mostrada e a ação é impedida.</li></ul> |
| Tolerância de vários depósitos | Selecione o que ocorrerá se uma viagem incluir várias linhas da ordem que devam ser entregues a depósitos diferentes. Essas linhas de ordem podem ser espalhadas por uma ou mais ordens de compra.<ul><li>**Aceitar** – o sistema deve permitir a ação.</li><li>**Aviso** – um aviso é exibido.</li><li>**Erro** - uma mensagem de erro é mostrada.</li></ul> |
| Volume ausente | Selecione o que ocorrerá se um usuário adicionar um item sem volume a uma viagem.<ul><li>**Aceitar** – o sistema deve aceitar o item.</li><li>**Aviso** – um aviso é exibido.</li><li>**Erro** - uma mensagem de erro é mostrada.</li></ul><p>Se os volumes forem usados para calcular e distribuir os custos, recomendamos que você selecione *Aviso* ou *Erro*.</p> |
| Provedor de serviços sem custo de viagem | Selecione o que ocorrerá se um usuário tentar processar uma fatura para um provedor de serviços que não tenha sido vinculado a uma viagem. <ul><li>**Aceitar** – o sistema deve permitir a ação.</li><li>**Aviso** – um aviso é exibido.</li><li>**Erro** - uma mensagem de erro é mostrada.</li></ul><p>É recomendável selecionar *Aviso*.</p> |

### <a name="defaults-fasttab"></a>FastTab Padrões

A tabela a seguir descreve os campos disponíveis na FastTab **Padões** da guia **Geral** da página **Parâmetros de custo de entrega**.

| Configuração | Descrição |
|---|---|
| Nome do diário | Selecione o diário padrão que a função *Criar diário de entrada* deve usar. |
| Status da viagem | Selecione o status que uma viagem deve ter para que os usuários possam configurar um contêiner de remessa de aluguel para ele no sistema. Normalmente, essa ação ocorre quando as mercadorias estão em trânsito ou na doca. |
| Modelo de diário | Selecione o modelo de percurso padrão a ser usado para novos contêineres de remessa de aluguel. Em geral, você seleciona um modelo de percurso que inclui custos de aluguel. |
| Movimentação | Se a quantidade excedente/insuficiente de uma entrega estiver dentro da tolerância definida, um diário de movimentação será automaticamente processado. Selecione o diário de movimentação padrão a ser usado. O campo **Contrapartida** para o nome do diário de movimentação selecionado deve ter um valor. |
| Transferir | Quando uma entrega insuficiente é processada, a quantidade de recebimento breve é transferida para um depósito de entrega insuficiente. Selecione o diário de transferência padrão a ser usado. |
| Desabilitar ordens de compra sem viagem | Desative a funcionalidade de entrega excedente/insuficiente de Custo de entrega para ordens de compra não anexadas a uma viagem. |
| Desabilitar ordens de compra sem mercadorias em trânsito | Desative a funcionalidade de entrega excedente/insuficiente de Custo de entrega para ordens de compra que não utilizam mercadorias na funcionalidade em trânsito. |
| Mercadorias em trânsito em período de carência de recebimento | Especifique o número de dias após o primeiro recebimento de um contêiner de remessa para o qual ainda é possível concluir recebimentos excedentes adicionais para esse contêiner de remessa. |

## <a name="status-updates-tab"></a>Guia Atualizações do status

O sistema usa valores de status para indicar o status de cada viagem. Os valores de status da viagem podem ser aplicados automaticamente a viagens via acompanhamento de viagem ou trabalhos em lotes periódicos. Como alternativa, você pode aplicá-las manualmente abrindo a viagem e selecionando um status no grupo **Atualização de viagens** na guia **Gerenciar** do Painel de Ações. 

Você poderá criar quantos valores de status de viagem desejar. No entanto, quatro deles devem ser definidos como usados para uma finalidade especial na guia **Atualizações de status** da página **Parâmetros de custo de entrega**. A tabela a seguir descreve os campos disponíveis.

| Configuração | Descrição |
|---|---|
| Orçado | Selecione o status de viagem que identifica que uma viagem foi finalizada. |
| Em trânsito | Selecione o status de viagem que identifica que uma viagem está em trânsito. |
| Pronto para avaliação de custo | Selecione o status de viagem que identifica que uma viagem está pronta para avaliação de custo. Esse status é usado quando todas as faturas de compra de estoque e de custo viagem, em que o campo **Crédito no custo da viagem** está definido como *Fornecedor*, foram processadas para a viagem. As viagens que falham no processo de custo terão o status de *Pronto para avaliação de custo*.|
| Pré-orçar | Selecione o status de viagem que identifica que uma viagem está sendo pré-orçada. Este status é usado quando uma nova transação de custo é adicionada a uma viagem após ela ser orçada. Novas transações de custo podem ser adicionadas a uma viagem pré-custeada quando uma segunda fatura de frete ou um encargo de imobilização inesperado é recebido. Esse status é aplicado automaticamente quando um novo custo de viagem é adicionado a uma viagem orçada. |

## <a name="voyage-creator-tab"></a>Guia Criador da viagem

A tabela a seguir descreve as seções na **Criador da viagem** da página **Parâmetros de custo de entrega**.

| Seção | descrição |
|---|---|
| Tolerâncias | Os campos **Tolerância de volume externo** e **Tolerância de peso externo** definem limites acima dos quais mercadorias são considerados com volume e peso excessivos. Quando um usuário adicionar mercadorias na página **Editor de viagens**, se o volume ou o peso exceder o valor definido aqui, o sistema mostrará um aviso. O valor de cada campo é expresso como uma porcentagem do volume ou peso máximo definido para o tipo de contêiner de remessa relevante. Recomendamos que o valor seja entre 5% e 10% do volume ou peso máximo. |
| Configuração de criação do fólio | O sistema pode criar vários fólios durante o processo de criação de viagens. Use esta seção para definir quando um novo fólio deve ser criado. Para cada linha desta seção, o sistema verificará a tabela e o campo especificados e criará um fólio para cada valor de campo exclusivo. |

## <a name="cost-estimates-tab"></a>Guia Estimativas de custo

A guia **Estimativas de custo** da página **Parâmetros de custo de entrega** fornece apenas um campo: **Versão de avaliação de custo padrão**. Este campo se aplica somente quando o método de avaliação de custo é *Avaliação de custo padrão*. Selecione a versão de avaliação de custo padrão a ser usada para a tarefa periódica *Atualização de preço de custo do item*. Talvez seja necessário alterar essa configuração toda vez que um novo ano financeiro começar.

## <a name="inventory-dimensions-tab"></a>Guia Dimensões de estoque

Use a guia **Dimensões de estoque** da página **Parâmetros de custo de entrega** para controlar as dimensões de estoque disponíveis que devem ser mostradas por padrão em cada página Custo de entrega em que dimensões são usadas.

Selecione uma dimensão e, em seguida, defina a opção **Linhas de viagem**, **Mercadorias em trânsito** e/ou **Estimativas de custo** como *Sim* para cada página em que a dimensão deve ser mostrada por padrão. Repita essa etapa para outras dimensões, conforme necessário.

As configurações desta guia estabelecem as dimensões padrão para cada página designada em entidades legais. No entanto, os usuários que estão trabalhando em uma das páginas designadas podem substituir as dimensões padrão selecionando **Inventário \> Exibir dimensões** no Painel de Ações.

## <a name="number-sequences-tab"></a>Guia Sequências numéricas

A guia **Sequências numéricas** da página **Parâmetros de custo de entrega** lista cada tipo de sequência numérica de referência exigido pelo Custo de entrega, mas que não é compartilhado entre entidades legais. Para cada referência na lista, selecione um código de sequência numérica.

> [!NOTE]
> Em uma configuração de várias empresas, diferentes sequências numéricas devem ser criadas para cada empresa (entidade legal).

## <a name="shared-number-sequences-tab"></a>Guia Sequências numéricas compartilhadas

A guia **Sequências numéricas compartilhadas** da página **Parâmetros de custo de entrega** lista cada tipo de sequência numérica de referência que é compartilhado entre entidades legais para o Custo de entrega. No momento, há apenas uma sequência numérica na lista. Essa sequência numérica é usada para a ID da viagem.

Na página **Todas as viagens**, os usuários podem exibir todas as viagens em todas as entidades legais. No entanto, para editar e processar uma viagem, os usuários devem estar na entidade legal do registro selecionado.

## <a name="feature-visibility-tab"></a>Guia Visibilidade de recursos

O custo de entrega adiciona recursos (campos e funções) a várias páginas usadas com frequência no Microsoft Dynamics 365 Supply Chain Management. Essas páginas incluem páginas relacionadas a dados mestre de fornecedor, produtos liberados, ordens de compra, ordens de transferência e configuração de depósito. Se você estiver usando o Custo de entrega, torne esses recursos visíveis em qualquer lugar antes de aproveitá-los. Se você não estiver usando o Custo de entrega, poderá ocultar os recursos para mantê-los fora do caminho.

Na guia **Visibilidade de recursos** da página **Parâmetros de custo de entrega**, defina a opção **Ativar** como *Sim* para tornar recursos de Custo de entrega visíveis sempre que estiverem disponíveis. Defina-a como *Não* para ocultar os recursos em páginas comuns fora do Custo de entrega. No entanto, mesmo quando a opção estiver definida como *Não*, o próprio módulo, incluindo a página **Parâmetros de custo de entrega**, permanecerá disponível para os usuários com as permissões corretas para acessá-lo.
