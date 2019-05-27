---
title: Calendários e planejamento mestre
description: Este tópico fornece uma visão geral de calendários de cadeia de suprimentos e como afetam o planejamento mestre.
author: t-benebo
manager: AnnBe
ms.date: 05/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: t-benebo
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 266eec2bb870be270b7796b35903a402e014c67c
ms.sourcegitcommit: 1f211ac6bd384fd8a2b5352104baf264d88f39b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538717"
---
# <a name="calendars-and-master-planning"></a>Calendários e planejamento mestre

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral de calendários de cadeia de suprimentos e como afetam o planejamento mestre.  Os calendários diferentes usados no mecanismo de planejamento mestre são explicados, incluindo como afetam a remessa e o recebimento de datas em ordens planejadas. Finalmente, são fornecidas recomendações referentes à atribuição, ao uso e à atualização dos calendários.

## <a name="definition-of-a-calendar"></a>Definição de um calendário.

Você pode definir um calendário para usar em sua organização na página **Administração da organização > Configuração > Calendários > Calendários**. 

Cada entrada de data em um calendário pode ser **aberta** ou **fechada** ou **calendário base**. Isso é especificado na coluna **Controle** na página **Horários de trabalho** . Para cada data: 
- **Aberta** - Indica que o trabalho é executado no dia selecionado. O calendário será atualizado de acordo com o modelo de horário de trabalho.
- **Fechada** - Indica que o trabalho não é executado durante o dia. 
- **Calendário base** - Indica que a data específica herdará os horários de trabalho e datas abertas/fechadas do calendário base. Assim , quando o calendário base é atualizado, o calendário selecionado herda os tempos de operação dele. 

Para todas as datas fechadas, a caixa de seleção **Fechado para retirada** será atribuída automaticamente. Para datas abertas, você pode selecionar manualmente a opção **Fechado para retirada** . Isso indica que o trabalho é executado na data, mas a remessa não é executada. 

## <a name="calendars-that-affect-master-planning"></a>Calendários que afetam o planejamento mestre

### <a name="calendar-for-a-coverage-group"></a>Calendário para um grupo de cobertura
Um grupo de cobertura indica um conjunto comum de parâmetros usados para o reabastecimento de itens pertencentes ao grupo de cobertura determinado. 

Para adicionar um calendário a um grupo de cobertura, vá para **Planejamento mestre > Configuração > Cobertura > Grupos de cobertura**. Encontre o grupo de cobertura a que deseja atribuir o calendário e o selecione no campo **Calendário** .

O grupo de cobertura pode ser atribuído em páginas diferentes: 
    - Na página **Detalhes do produto liberado** de um item. Para ver o grupo de cobertura de um item, vá para **Gerenciamento de informações do produto > Produtos > Produtos liberados** e selecione o item para ir para a página **Detalhes de produtos liberados**. Você pode ver o grupo de cobertura de item na FasTab **Plano**.
    - Na página **Cobertura de item**. Na página de detalhes de produtos lançados, clique em **Cobertura de item** para ir para a respectiva página. Na guia visão geral é possível ver diferentes parâmetros para o reabastecimento dependendo de site, depósito e dimensões do produto. O grupo de cobertura para cada item será herdado do grupo de cobertura na página **Detalhes do produto liberado** . Isso pode ser substituído usando **Use configurações específicas** ou **Substituir a configuração de grupo** na guia **Geral** .
    - Na página **Parâmetros de planejamento mestre**. Se um item não tiver um grupo de cobertura definido nas páginas anteriores, o planejamento mestre assumirá a definição geral do grupo de cobertura nos parâmetros de planejamento mestre. Isso é configurado em **Planejamento mestre > Configuração > Parâmetros de planejamento mestre** no campo **Grupo de cobertura geral** . 

### <a name="calendar-for-a-vendor"></a>Calendário para um fornecedor
Para indicar os dias úteis de um fornecedor, você pode atribuir um calendário de compra ao fornecedor na página **Padrões de ordem de compra** para um fornecedor. 

Para definir um calendário para um fornecedor, você deve criar o calendário em **Administração da organização > Calendários > Calendários**. Quando o calendário é criado, você precisa atribuí-lo ao fornecedor. Vá para **Contas a pagar > Fornecedores > Todos os fornecedores** e selecione o fornecedor para o qual deseja atribuir o calendário. Em seguida, na página do fornecedor na FastTab **Padrões da ordem de compra** atribua o novo calendário de compra usando o menu suspenso. 

O calendário de um fornecedor indica os dias em que ele aceita a apresentação de uma ordem de compra e as datas nas quais ele pode entregar ordens a sua empresa. Portanto, as datas de ordem para ordens de compra do fornecedor com um calendário de compra serão datas definidas como abertas no calendário. As datas de entrega para essas ordens também serão em dias abertos e, portanto, afetarão o prazo de entrega do item comprado. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Defina o prazo de entrega para um item comprado

Para especificar o prazo de entrega da compra (e se somente os dias úteis devem ser considerados) de um item, é preciso ir para a página de configurações de ordem padrão do produto, em **Gerenciamento de informações do produto > Produtos > Produtos liberados** e selecionar **Configurações de ordem padrão**. 

> [!Note]
> Os **Dias úteis** no prazo de entrega da compra indicam os dias úteis do fornecedor. Por exemplo, um calendário de entrega apenas às terças com um prazo de entrega de 10 dias e a caixa de seleção de dias úteis selecionada indica que levará 10 semanas (10 terças-feiras) para que o item seja entregue.
Assim, na maioria dos casos não é recomendado selecionar dias úteis para os prazos de entrega de ordens de compra.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Defina os prazos de entrega na página de contratos comerciais

O planejamento mestre pode ser configurado para incluir todos os contratos comerciais de fornecedores. Os contratos comerciais são preços fixos ou descontos acordados que são definidos para um ou mais clientes ou fornecedores para a venda ou a compra de produtos individuais ou de vários produtos. Vá para **Planejamento mestre > Configuração > Parâmetros de planejamento mestre** e, na guia **Ordens Planejadas**, selecione **Localizar contratos comerciais** para incluir os contratos comerciais durante o planejamento. O planejamento mestre pode selecionar o fornecedor com o **Prazo de entrega mínimo** ou com o **Menor preço unitário**.

### <a name="calendar-for-a-warehouse"></a>Calendário para um depósito
Você pode atribuir um calendário a um depósito para indicar as datas abertas para remessa e recebimento. Se nenhum calendário foi atribuído a um depósito, pressupõe-se que está aberto todos os dias. 

> [!Note]
> Atribuir um calendário a um depósito de trânsito não tem impacto. Depósitos de trânsito são usados para respaldar ordens de transferência. As datas de remessa ou recebimento aplicáveis para as ordens são definidas pelos dias abertos no depósito de "Origem"e no de "Destino" e pelo modo do calendário de entrega.

#### <a name="closed-for-pickup-policy"></a>Fechado para política de retirada
Para indicar que um depósito está aberto para recebimento mas a retirada não é possível, você pode usar **Fechado para política de retirada** no calendário do depósito. Isso também se aplica a retiradas pelo cliente. 

### <a name="transport-calendar"></a>Calendário de transporte 
Para indicar as datas disponíveis para remessa de ordens de transferência **Do depósito**, você pode atribuir um **Calendário de transporte**. Você pode definir um calendário de transporte por modo de entrega, ou por modo de entrega e do depósito. O calendário de transporte é configurado em **Vendas e marketing > Configuração > Distribuição > Modos de entrega**. Selecione um modo de entrega e clique no botão **Calendário de transporte**.

Uma linha pode ser criada para cada depósito e modo de entrega, em que o calendário é adicionado à coluna **Calendário de transporte**. Ela especificará o calendário de transporte que será aplicado quando as mercadorias forem enviadas do depósito usando o modo de entrega determinado. Para aplicar um calendário de transporte para todas as remessas com um modo de entrega determinado, uma linha pode ser criada sem especificar o depósito.  Isso afetará todas as remessas que usam o modo de entrega determinado, independentemente do depósito. 

Se nenhum calendário de transporte tiver sido atribuído, pressupõe-se que está aberto para transporte todos os dias.

### <a name="calendar-for-a-customer"></a>Calendário para um cliente
Para indicar as datas quando um cliente poderá aceitar entregas, você pode atribuir ao cliente um calendário de recebimento. Se nenhum calendário foi atribuído a um cliente, presume-se que o cliente possa receber ordens todos os dias. Isso afetará a data de recebimento nas linhas da ordem de venda. Se você selecionar uma data nas linhas de ordem de venda que não está "aberta" no calendário cliente, o sistema indicará que a data de recebimento é inválida. 

Observe que só é possível incluir um calendário por cliente. Caso precise incluir um calendário para cada endereço diferente de um cliente, você pode criar um cliente por endereço e depois atribuir seu respectivo calendário. 

A data de recebimento solicitada nas linhas da ordem de venda é afetada pelo calendário do cliente e pelo método de controle de data de entrega. Você pode ler mais sobre como a primeira data de entrega é calculada em [Promessa de ordem.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations).

### <a name="shipping-calendar-for-a-legal-entity"></a>Calendário de remessa para uma entidade legal
Para indicar as datas em que uma entidade legal pode fazer remessa de mercadorias, você pode definir um calendário de remessa em **Administração da organização > Organizações > Entidades legais**. Selecione a entidade legal e adicione o calendário na guia **Comércio exterior e logística** no campo **Calendário de remessa**. O calendário de remessa atua como uma fonte de padrões para todos os calendários de depósito na entidade legal. 

## <a name="how-calendars-affect-dates-in-planning"></a>Como os calendários afetam as datas no planejamento

### <a name="order-date-of-a-planned-purchase-order"></a>A data da ordem de uma ordem de compra planejada 
A data da ordem em uma ordem de compra planejada indica a data em que a ordem é apresentada. Será uma data aberta no calendário do fornecedor e no calendário do grupo de cobertura. Por vezes os fornecedores precisam de alguns dias de margem entre o momento que recebem a ordem de compra e o momento em que conseguem fazer a remessa da mercadoria. Essas datas são indicadas nos dias da margem do fornecedor. Entretanto, se o item comprado for atribuído a um grupo de cobertura com dias de margem, esses dias de margem substituirão os dias de margem do fornecedor.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Data de entrega de uma ordem de compra planejada
A data de recebimento de uma compra indica a data em que você receberá as mercadorias. Será uma data aberta no calendário. O calendário que será levado em conta para indicar quais dias as ordens de compra podem ser recebidas são estes, em ordem de prioridade, da maior para a menor: 
    1. Calendário do fornecedor
    2. Calendário do grupo de cobertura
    3. Calendário do depósito para o depósito de recebimento

Observe que o calendário do grupo de cobertura pode ser definido em páginas diferentes e assumirá a prioridade na seguinte ordem:
    1. Grupo de cobertura de item na página **Detalhes dos produtos liberados**
    2. Grupo de cobertura de item na página **Cobertura de item**
    3. Grupo de cobertura de item padrão em **Parâmetros de planejamento mestre**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Data de remessa de uma ordem de transferência planejada
Quando você cria uma ordem de transferência entre dois depósitos, a data de remessa e a data de recebimento serão incluídas no cabeçalho da ordem de transferência, juntamente com o depósito "De" e do depósito "Para". A diferença entre essas duas datas é o tempo esperado de transporte (em dias) entre os depósitos.

A data de remessa de uma ordem de transferência planejada indica a data em que as mercadorias são enviadas do depósito "De". Os calendários usados especificando a data de remessa disponível são listados por prioridade: 
    1. O calendário do depósito do depósito "De"
    2. Calendário do grupo de cobertura (consulte a ordem de fallback para este calendário acima) Se houver um calendário do depósito definido, a data de remessa será uma data aberta no calendário. Se não houver calendário do depósito definido, será usado o calendário do grupo de cobertura. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Data de recebimento de uma ordem de transferência planejada
A data de recebimento de uma ordem de transferência indica a data em que as mercadorias são recebidas no depósito "Para".

Os calendários usados para especificar a data de recebimento são os listados por prioridade: 
    1. Calendário do grupo de cobertura 
    2. Calendário de depósito do depósito "Para" Se houver um calendário de cobertura definido, a data de recebimento será uma data aberta no calendário. Se não houver calendário do grupo de cobertura definido, será usado o calendário do depósito. 

Ao localizar as datas de remessa e recebimento de transferência planejada, as margens definidas pelo usuário para remessa e recebimento também serão consideradas. 

## <a name="using-calendars-in-master-planning"></a>Usando calendários no planejamento mestre

### <a name="assignment-of-scm-calendars"></a>Atribuição de calendários SCM
É importante definir os calendários para identificar os dias úteis da empresa. A melhor implementação é definir um calendário para cada elemento com dias úteis diferentes. Ou seja, todos os calendários externos (cliente, fornecedor) e todos os internos (depósito, grupo de cobertura e modo de entrega) relacionados à empresa.

### <a name="recommendation-on-warehouse-calendars"></a>Recomendação sobre calendários de depósito
Recomenda-se usar um calendário por depósito para incluir alterações específicas que afetam apenas o depósito. Por exemplo, dois ou mais depósitos podem ter os mesmos dias úteis mas uma política de retirada diferente. Nesse caso, um calendário para cada um dos depósitos com a respectiva política de retirada é a melhor implementação para que o sistema inclua as melhores datas para ordens planejadas de compra, de transferência e de produção. Se nenhum calendário de depósito estiver definido, o calendário da entidade legal poderá ser usado como fonte de padrões para o calendário do depósito. 

### <a name="recommendation-of-coverage-group-calendars"></a>Recomendação de calendários do grupo de cobertura
Em relação ao calendário do grupo de cobertura, é importante lembrar que ele tem um comportamento de substituição em relação às datas de recebimento no planejamento mestre. Por isso, recomenda-se usá-lo com cuidado. Particularmente, ele é útil nos casos em que é necessário fazer o reabastecimento em dias específicos na semana. 

### <a name="updating-scm-related-calendars"></a>Atualizando os calendários de SCM relacionados
Embora seja importante que os calendários relevantes sejam atribuídos em seus locais respectivos (fornecedor, cliente, modo de entrega ou grupo de cobertura), atualizá-los também é importante para que reflitam as alterações. O sistema definirá as datas das ordens de produção, transferência, compra e venda dependendo da combinação dos calendários atribuídos. É uma prática recomendada esclarecer quem é responsável por atribuir e atualizar os calendários nas áreas correspondentes. No caso de uma eventualidade ou qualquer outra mudança incomum em dias úteis, é essencial atualizar os calendários adequadamente. Todas as tarefas que dependem de calendários, como planejamento mestre e planos de produção, devem ser executadas novamente quando os calendários são atualizados. 
