---
title: Fechamento anual
description: "Este tópico descreve da instalação e pisa necessário executar o processo de fechamento de fim de ano contabilidade."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Fechamento anual

Este tópico descreve da instalação e pisa necessário executar o processo de fechamento de fim de ano contabilidade. 

No final de um ano fiscal, você deve executar o recálculo do ano final dos saldos iniciais de transferência para o novo ano. A maioria de organizações executarão o processo de fechamento de fim de ano várias vezes. A primeira vez é obter os saldos movidos no novo ano fiscal. O prazo final de ano poderá ser executado novamente, quantas vezes for necessário, para mover os saldos das entradas de ajuste do novo ano fiscal. 

Durante o processo o final do ano, há dois tipos de transações criadas possíveis. Uma transação de abertura sempre é gerada e usada para criar os saldos iniciais do novo ano fiscal. A transação de abertura mostra os saldos da conta contábil de balanço no novo ano fiscal e os saldos dos saldos de contas contábeis de lucros e perdas na conta contábil no salário retido novo ano fiscal. A transação de fechamento é criada para derrubar opcionalmente os saldos de contas de lucros e perdas para zerar no ano fiscal que está sendo fechado.

## <a name="prepare-to-run-the-year-end-close"></a>Preparar-se executar o fechamento de fim de ano
Antes de executar o recálculo do final do ano, valide as configurações para: 

Na página **Conta principal**:

-   Valide ** tipo de conta principal ** corretamente é definido para cada conta principal. O tipo de conta principal é usado para determinar se o saldo de conta principal será trazido adiantar como o saldo inicial ou fechado ganhos retidos na transação de abertura.
-   ** Conta de abertura ** o campo pode ser usado para transferir o saldo de conta principal para uma nova conta principal durante o fechamento de fim de ano. A nova conta principal é inserido ** conta de abertura ** o campo. Isso será usado normalmente para contas de balanço principais quando a conta está desativada principal e uma nova conta principal é usada para o novo ano fiscal.

** Parâmetros de contabilidade na página ** abaixo ** ano fiscal seguinte **:

-   ** Excluir transações de fechamento de ano ** a opção é usada especifique se a transação de abertura gerada pelo de um fechamento anterior de final de ano deve ser excluída quando o fechamento de fim de ano é executado novamente. Se essa opção está definida ** Sim **, a transação de abertura anterior será excluída e uma nova transação de abertura é criada com base nos saldos atuais. Se essa opção está definida ** nenhum **, as transações anteriores de sobras de abertura e uma transação de abertura adicional é criada para mover o próximo de saldos de ajustar as transações lançadas após o fechamento anterior de fim de ano.
-   ** Criar transações de fechamento durante a transferência ** a opção é usada para criar transações de fechamento no ano fiscal que está sendo fechado para exibir os saldos de contas de lucros e perdas a zero. Se essa opção está definida ** Sim **, as transações de abertura e a transação de fechamento são criadas. Se essa opção está definida ** nenhum **, somente as transações de abertura é criada em próximo ano fiscal para transferir os saldos. Os saldos da conta de lucros e perdas permanecem no final do ano fiscal.
-   ** Status ajustado do ano fiscal fechado permanentemente ** a opção é usada definir o ano fiscal a um status fechado permanentemente. Use essa configuração com cautela, pois os períodos com status permanentemente fechado não podem ser reabertas, impedindo os ajustes sejam lançadas ao ano fiscal. É uma prática recomendada definir isso ** ** nenhum.
-   ** O número de comprovante deverá ser preenchido ** a opção será usada se definir um número de comprovante será necessário executar o recálculo do final do ano. É uma prática recomendada exigir um número de comprovante para identificar facilmente a transação de abertura.

** O calendário fiscal ** página em:

-   O próximo ano fiscal deve estar antes de executar o fechamento de fim de ano. O próximo ano fiscal é necessário para criar os saldos inicial do período de abertura.

** Calendário contábeis ** página em:

-   Opcional: Cada período fiscal por ano fiscal que é inserido pode ser definido ** ** em espera para impedir que as novas transações foram inseridas. Quando as entradas de ajuste são identificadas, períodos Em que podem ser reabertas lançar entradas de ajuste, se o processo de fechamento de fim de ano já foi executado.

## <a name="define-year-end-close-templates"></a>Defina modelos próximos de final de ano
Depois que o sistema está configurado, o próximo ano final de processo pode ser executado. ** Final do ano seguinte ** na página, modelo pode ser definido para o grupo de entidades legais para que o processo de fechamento de fim de ano será executado. O modelo serão reutilizadas no final de cada ano, mas pode ser alterado se a organização se altera. 

Primeiro, defina ** ** nome de grupo para o modelo, e selecione o calendário fiscal. O nome do grupo deverá identificar o grupo de entidades legais incluídas.  Por exemplo, modelos podem ser configurados com a região, a grupos separados criados para entidades legais norte-americanas, legais de entidades, e EMEA entidades legais de APAC. 

Em seguida, as entidades legais pode ser adicionado ao modelo. As entidades legais podem ser adicionadas quando uma hierarquia organizacional ou selecionando entidades legais. Se uma hierarquia organizacional for selecionada, apenas as entidades legais na hierarquia que usam o calendário fiscal selecionado serão incluídas no modelo. Se usar entidades legais para adicionar ao modelo, apenas as entidades legais com o mesmo calendário fiscal podem ser adicionadas. O mesmo calendário fiscal é necessário porque o prazo final de ano é executado em um ano fiscal, que pode variar de calendário ao calendário. 

Após as entidades legais são adicionadas, defina o que o salário retido principais para cada entidade legal. ** Data final do ano passado ** o campo será atualizado sempre que o fechamento e anos é executado para a entidade legal. 

** Dimensão financeira ** o guia é usada para definir quais dimensões financeiras serão usadas na transação de abertura. Observe que as configurações que você está definindo são relevantes apenas à entidade legal selecionada ** entidades legais ** na grade. Você repetirá o de instalação para cada entidade legal na grade. 

** Dimensões do balanço de transferência ** é usado para definir se as dimensões financeiras das transações lançadas em contas de balanço devem ser atualizadas na transação de abertura. É uma prática recomendada definir esta opção ** Sim **. ** Transferir dimensões de lucros e perdas ** é usado para definir quais dimensões financeiras em transações lançadas na conta de lucros e perdas será transferido para a conta principal ganhos retidos. Primeiro, identifique as dimensões financeiras relevantes a entidade legal selecionada. Isso incluiria as dimensões financeiras lançadas contra durante o ano, se a dimensão financeira não fizer parte de uma estrutura conta de ativo. Em seguida, defina como cada dimensão ou ** próximo ou escolha ** ** fechar tudo **.  O padrão é ** fechar tudo **, que mantém os valores de dimensões financeiras das transações originais lançadas e as usa criando os saldos iniciais para conta de ganhos retidos. Separate lucros retidos começando saldos será criado para cada combinação exclusivo de valores de dimensões financeiras. Se ** próximo único ** for selecionado, as transações lançadas nessa dimensão serão resumidas financeiramente no salário retido começando o saldo do valor da dimensão inserido no campo próximo após ** ** opção. Por exemplo, suponha que todas as transações por ano fiscal foram lançadas com a estrutura da conta principal - departamento. A dimensão financeira do departamento no modelo, ** próximo único ** é selecionado e 100 é o valor inserido. Se a receita total de todas as transações lançadas departamentos 200, 300, e 400 será $100,000, um saldo inicial serão criados para trabalho Retained - 100. Se você selecionar a opção ** ** e deixar o valor de dimensão financeira, todas as transações postarão a ganhos retidos com esse valor de dimensão que está em branco. 

O final do ano adere não as estruturas de conta. Isso porque as estruturas de conta podem alterar ao longo de um ano fiscal e não é sempre possível identificar a estrutura da conta relevante devido 2 essas alterações.  Quando as transações abertas forem criadas, os saldos serão trazidos o próximo com dimensões financeiras como definido no modelo e anos. As entradas dos saldos inicial podem incluir dimensões financeiras não nas combinações de estrutura e dos segmentos de conta atual que não são válidas na estrutura da conta atual. A organização se deseja excluir uma dimensão financeira ao saldo de ganho retido inicial para definir, a dimensão financeira a ser ** próximo escolha e deixe ** o valor de dimensão em branco.

## <a name="run-the-year-end-close-process"></a>Execute o processo o final do ano
Após os seguintes modelos final de ano é criado, o processo de fechamento de fim de ano é iniciado escolhendo ** ano fiscal de execução ** no painel de ações. Selecione todas as regras ou um subconjunto entidades legais de modelo em que executa o fechamento de fim de ano. Ao executar o fechamento de fim de ano pela primeira vez em um ano fiscal, escolherá você provavelmente legais todas as entidades para criar os saldos inicial para todas as entidades legais. Se você estiver executando o fechamento de fim de ano novamente, poderá optar para executar o processo para apenas as entidades legais para as entradas de ajuste foram lançadas. 

Selecione o ano fiscal que você gostaria de executar o fechamento e anos em processo. Se mais de um período fechado se existe para o período do ano fiscal, ** nome do período tornar-se-á ** o campo disponível para que você possa selecionar o período de fechamento para lançar a transação de fechamento, se a configuração definida para criar a transação de fechamento. 

Insira um número de comprovante, ou que não seja necessário, do de instalação em parâmetros de contabilidade. O mesmo número de comprovante será usado para todas as entidades legais selecionadas para o próximo processo e anos. O número de comprovante for gerado com uma sequência numérica. É uma prática recomendada inserir um número de comprovante, mesmo que não se necessário. Inserir um número de comprovante facilita encontrar a transação de abertura no novo ano fiscal. Se um número de comprovante for inserido, o comprovante será em branco para a transação de abertura. 

Se deseja reverter um final do ano anterior fechamento para o ano fiscal selecionado, definido ** desfazer fechamento anterior ** ** Sim **. O prazo final do ano serão revertidos, mas o processo pode ser executado novamente a qualquer momento. Se você reverter um fechamento de fim de ano, ** data final do ano passado ** não está disponível. 

O final do ano padrão para executar no modo de lote. Uma prática recomendada é executar o processo em lote, de forma a permitir que o usuário retorne às outras. Depois que o próximo processo e anos será concluída, ** data final do ano passado ** será atualizado com a data da sessão.

Para obter mais informações, consulte fechando [a contabilidade na extremidade] do período (close-general-ledger-at-period-end.md).


