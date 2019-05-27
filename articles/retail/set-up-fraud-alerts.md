---
title: Configurar e trabalhar com alertas de fraude de call center
description: Este tópico explica como configurar regras para alertar representantes de atendimento ao cliente sobre informações potencialmente fraudulentas quando as ordens são processadas. Você também pode especificar os códigos que são usados para colocar ordens suspeitas automaticamente ou manualmente em espera.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 13b6a18750e79a17c7f6034780922c64b12390e2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546331"
---
# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Configurar e trabalhar com alertas de fraude de call center

[!include [banner](includes/banner.md)]

Este tópico explica como configurar critérios e regras para colocar ordens de venda potencialmente fraudulentas em espera para revisão adicional. O recurso de verificação de fraude é usado para determinar a validade das informações em uma ordem de venda. Se as informações na ordem de venda parecem ser questionáveis, com base em critérios e regras de fraude de uma organização, a ordem pode ser colocada em espera para revisão adicional. Nesse caso, não é possível liberar a ordem para o depósito para o processamento até que o bloqueio seja liberado.

> [!NOTE]
> Esse recurso pode ser usado somente com o processamento de ordens de vendas para o canal de call center do Retail.

## <a name="turning-on-the-fraud-check-feature"></a>Ativação do recurso de verificação de fraude

Para usar o recurso de verificação de fraude, você deverá definir a opção **Habilitar a conclusão de ordem** do canal como **Sim** quando o canal de call center estiver [definido](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-order-processing-options). Quando a conclusão de ordem estiver ativada, os usuários do call center deverão selecionar **Concluir** na página da ordem de venda para todas as ordens de venda criadas. A ação Concluir faz com que a página **Resumo da ordem de venda** seja aberta. Depois de inserir os dados de pagamento necessários na página **Resumo da ordem de venda**, os usuários deverão selecionar **Enviar** para finalizar a ordem. Quando a ordem for enviada, o recurso de verificação de fraude será disparado e todas as regras que estiverem ativas no sistema serão automaticamente validadas.

Os usuários do call center também podem ser inserir manualmente as ordens de venda em espera para a revisão de fraude antes de selecionar **Enviar**. Para colocar uma ordem de venda em espera manualmente, na página **Resumo da ordem de venda** , selecione **Esperar** \> **Bloqueio manual por fraude**. Será solicitado que você insira um comentário para explicar o motivo por colocar a ordem em espera. Esse comentário aparecerá na bancada de [bloqueios de ordens](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) para fornecer contexto ao usuário que revisar as ordens que estão em espera para determinar se a ordem deve ser liberada.

Além da configuração da opção **Habilitar conclusão de ordem** no canal, você deve configurar o recurso de verificação de fraude nos parâmetros do Call center. Vá para **Varejo** \> **Configuração de canal** \> **Configuração de call center** \> **Parâmetros de call center**. Na página **Parâmetros de call center**, na guia **Bloqueios** , defina a opção **Verificação de fraude** como **Sim**.

Na guia **Bloqueios**, você também deve definir os [códigos de bloqueio](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds) que serão aplicados a uma ordem que for colocada em espera manualmente ou automaticamente para a revisão de fraude. Defina os códigos de bloqueio nos campos **Código de bloqueio manual por fraude** e **Código de bloqueio por fraude** . Pode ser útil criar dois códigos exclusivos de bloqueio para que os usuários que trabalham na bancada de bloqueios possam facilmente filtrar e distinguir os bloqueios automáticos dos bloqueios manuais.

Para que o recurso de verificação de fraude funcione com eficiência, você também deve definir o campo **Pontuação mínima** . Cada critério e regra de fraude definidos no sistema têm uma pontuação. Quando uma ordem de venda é verificada quanto a correspondências de fraude, se houver uma ou mais correspondências, as pontuações serão somadas para dar à ordem uma pontuação total de fraude. Se a pontuação total de fraude de uma ordem exceder o valor do campo **Pontuação mínima**, a ordem será colocada automaticamente em espera. Opcionalmente, você pode usar os outros campos relacionados à pontuação na guia **Bloqueios** para definir a pontuação do email, do número de telefone, do CEP e do CEP estendido. Se você não especificar uma pontuação para algum desses critérios de fraude estáticos quando defini-los na página **Dados de fraude estáticos**, o sistema dará uma pontuação a eles usando as pontuações padrão especificadas na guia **Bloqueios** da página **Parâmetros de call center** .

Por fim, use o campo **Tipo de comentário sobre fraude** para especificar o tipo de documento que deve ser usado quando os usuários colocarem uma ordem manualmente em espera para a revisão de fraude. Normalmente, este campo é definido como **Anotação**.

## <a name="defining-fraud-criteria-and-rules"></a>Definição de critérios e regras de fraude

O sistema faz referência a dois tipos de critérios de fraude para determinar se uma ordem deve ser colocada em espera para a revisão de fraude:

- Os **dados de fraude estáticos** usam um valor específico, como um número de telefone que seja colocado em uma lista de telefones bloqueados ou um endereço de email que seja sinalizado porque sabe-se que ele foi usado em transações fraudulentas anteriores. Para configurar os dados de fraude estáticos, vá para **Varejo** \> **Configuração de canal** \> **Configuração de call center** \> **Fraude** \> **Dados de fraude estáticos**. Na página **Dados de fraude estáticos** , você pode adicionar os critérios de fraude manualmente ou por meio da importação de dados. As pontuações são anexadas às informações fraudulentas. Se o recurso de verificação de fraude estiver ativado, cada ordem de venda inserida será comparada aos dados estáticos. Se os dados forem encontrados no endereço de cobrança do cliente ou no endereço de entrega que esteja vinculado ao cabeçalho da ordem, ou se os dados forem encontrados em endereços de entrega que estejam vinculados a alguma das linhas nessa ordem de venda, as pontuações de todas as correspondências exclusivas serão somadas e comparadas com o valor **Pontuação mínima** para determinar se a ordem deve ser colocada em espera.
- As **regras de fraude** consistem nas variáveis definidas pelo usuário e nas condições definidas para essas variáveis. Para criar regras, vá para **Varejo** \> **Configuração de canal** \> **Configuração de call center** \> **Fraude** \> **Regras**. As regras de fraude permitem que uma empresa configure um conjunto de regras mais complexo que pode incluir instruções **E** ou **OU** para avaliar várias condições. Por exemplo, um usuário deseja que todas as ordens para os clientes que pertencem a um determinado grupo de clientes e que encomendaram um produto específico seja colocada em espera para a revisão de fraude. Nesse caso, as condições para validar o cliente e os produtos são definidas na página **Regras** e uma condição E é usada. Uma ordem será então colocada em espera somente se as duas condições forem verdadeiras e se o valor da pontuação atribuído a essa regra mais o valor da pontuação de quaisquer outras regras que correspondam à ordem exceder o valor da **Pontuação mínima** definido na página **Parâmetros de call center**.

> [!NOTE]
> Várias regras ou regras muito complexas afetarão o desempenho do sistema quando as ordens de venda forem enviadas. O recurso de verificação de fraude não foi otimizado para lidar com um grande volume de entradas de dados de fraude estáticos e muitas regras ativas. Lembre-se de que cada regra será avaliada quando os usuários do call center selecionarem **Enviar** durante a entrada de ordens de venda. As regras são avaliadas no cabeçalho de ordem de venda e em todas as linhas da ordem. Quanto mais regras e mais complexas forem as instruções das regras, mais demorado será o tempo de processamento. Se houver muitas linhas de item em uma ordem e muitas regras ativas e entradas de dados estáticos, o processo automático de revisar e validar todos os dados e calcular uma pontuação de fraude pode sofrer um sério impacto no desempenho. As organizações que usam esse recurso devem sempre testar e confirmar que o tempo de processamento para o envio de ordem é aceitável antes de aplicar alterações às regras ou critérios de fraude estáticos ao ambiente de produção.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Identificação de ordens que estão em espera para a revisão de fraude

Quando os usuários do call center enviam uma ordem de venda, se a ordem corresponder aos critérios ou regras de fraude, e se a pontuação exceder o mínimo, os usuários receberão uma mensagem de aviso informando que a ordem foi colocada em espera. Os usuários podem fechar a mensagem, pois ela é meramente informativa. Os usuários podem, opcionalmente, comunicar essas informações ao cliente. A empresa deve determinar o protocolo a ser seguido pelos usuários nessa situação.

A ordem foi salva, mas o sinalizador **Não processar** está definido nela. Esse sinalizador ajuda a garantir que a ordem não poderá ser liberada para o depósito. A qualquer momento, os usuários poderão visualizar o sinalizador **Não processar** para qualquer ordem de venda na página **Status detalhado** . Esse link pode ser aberto a partir das páginas **Todas as ordens de venda** e **Atendimento ao cliente** . O sistema também atualiza o valor do campo **Status detalhado** da ordem para **Bloqueio por fraude**.

Para exibir e gerenciar as ordens que estão em espera para a revisão de fraude, vá para **Varejo** \> **Clientes** \> **Bloqueios da ordem**. Na página **Bloqueios da ordem**, selecione uma entrada na lista e clique em **Bloqueio da ordem** para ver uma exibição mais detalhada que inclui informações sobre o motivo do bloqueio. No FastTab **Detalhes da fraude**, você pode visualizar os critérios sistemáticos de fraude que foram considerados uma correspondência com a ordem e as pontuações aplicadas. Se a ordem foi colocada em bloqueio manual, você poderá revisar os comentários inseridos pelo usuário que colocou a ordem em espera consultando a seção **Anotações de fraude** no FastTab **Anotações** .

Para obter mais informações sobre como trabalhar com o bloqueio de ordens, consulte [Bloqueios da ordem](https://docs.microsoft.com/dynamics365/unified-operations/retail/work-with-order-holds).
