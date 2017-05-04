---
title: Fechamento anual
description: "Este tópico descreve a configuração e as etapas necessárias para executar o processo de fechamento anual da contabilidade."
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

[!include[banner](../includes/banner.md)]


Este tópico descreve a configuração e as etapas necessárias para executar o processo de fechamento anual da contabilidade. 

Ao final de um ano fiscal, é necessário executar o processo de fechamento anual para transferir saldos de abertura para o próximo ano. A maioria das organizações executarão o processo de fechamento anual diversas vezes. A primeira vez serve para mover os saldos para o novo ano fiscal. O fechamento anual pode então ser executado novamente, quantas vezes forem necessárias, para mover os saldos de entradas de ajuste para o novo ano fiscal. 

Durante o processo de fechamento anual, existem dois tipos de transações possíveis criadas. Uma transação de Abertura sempre é gerada e é usada para criar os saldos iniciais do novo ano fiscal. A transação de Abertura mostra os saldos da conta contábil de balanço no novo ano fiscal e saldos dos balanços de conta contábil de lucros e perdas na conta contábil de rendimentos retidos no novo ano fiscal. A transação de Fechamento é criada opcionalmente para trazer os saldos das contas de lucros e perdas para zero quando o ano fiscal estiver sendo fechado.

## <a name="prepare-to-run-the-year-end-close"></a>Preparação para executar o fechamento anual
Antes de executar o processo de fechamento anual, confirme as configurações para: 

Na página **Conta principal**:

-   Confirme se o **Tipo de conta principal** está definido corretamente para cada conta principal. O Tipo de conta principal é usado para determinar se o saldo da conta principal será levado a diante como um saldo inicial ou fechado nos rendimentos retidos na transação de Abertura.
-   O campo **Conta de abertura** pode ser usado para transferir o saldo da conta principal para a nova conta principal durante o fechamento anual. A nova conta principal é inserida no campo **Conta de abertura**. Tipicamente isso será usado para contas principais de balanço quando a conta principal é inativada e uma nova conta principal é usada para o novo ano fiscal.

Na página **Parâmetros da contabilidade** em **Fechamento do ano fiscal**:

-   A opção **Excluir transações de fechamento anual** é usada para especificar se a transação de Abertura de um fechamento anual anterior gerada pelo sistema deve ser excluída quando o fechamento anual for executado novamente. Se essa opção estiver definida como **Sim**, a transação de Abertura anterior é excluída e uma nova transação de Abertura é criada com base nos saldos atuais. Se essa opção estiver definida como **Não**, a transação de Abertura anterior é mantida e uma transação de Abertura adicional é criada para mover os saldos em diante de transações de ajuste enviadas após o fechamento anual anterior.
-   A opção **Criar transações de fechamento durante a transferência** é usada para criar transações de Fechamento durante o fechamento anual para zerar os saldos das contas de lucros e perdas. Se essa opção estiver definida como **Sim**, ambas as transações de Abertura e Fechamento são criadas. Se essa opção estiver definida como **Não**, apenas a transação de Abertura é criada no próximo ano fiscal para transferir os saldos. Os saldos das contas de lucros e perdas continuam no final do ano fiscal.
-   A opção **Mudar o status do ano fiscal para permanentemente fechado** é usada para mudar o ano fiscal para o status de permanentemente fechado. Use essa configuração com cautela, pois todos os períodos com status de permanentemente fechado não podem ser reabertos, impedindo que ajustes ao ano fiscal sejam lançados. É uma prática recomendada definir essa opção como **Não**.
-   A opção **Número de comprovante deve ser preenchido** é usada para definir se um número de comprovante é necessário durante a execução do processo de fechamento anual. É uma prática recomendada exigir um número de comprovante para identificar facilmente a transação de Abertura.

Na página **Calendário fiscal**:

-   O próximo ano fiscal deve existir antes de executar o fechamento anual. O próximo ano fiscal é necessário para criar os saldos iniciais do período de abertura.

Na página **Calendário contábil**:

-   Opcional: Cada período fiscal do ano fiscal que está sendo fechado pode ser definido como **Em espera** para prevenir que novas transações sejam inseridas. Quando as entradas de ajuste são identificadas, os períodos Em espera podem ser reabertos para lançar entradas de ajuste, mesmo que o processo de fechamento anual já tenha sido executado.

## <a name="define-year-end-close-templates"></a>Definir modelos de fechamento anual
Depois que o sistema está configurado, o processo de fechamento anual pode ser executado. Na página **Fechamento anual**, um modelo pode ser definido para o grupo de entidades legais para a qual o processo de fechamento anual será executado. O modelo será reutilizado a cada fechamento anual, mas pode ser modificado caso ocorra alteração na organização. 

Primeiro, defina o **Nome do grupo** para o modelo, e selecione o calendário fiscal. O nome do grupo deve identificar o grupo de entidades legais inclusas.  Por exemplo, os modelos podem ser configurados com base na geografia, com grupos separados criados para entidades legais norte-americanas, entidades legais da EMEA e entidades legais da APAC. 

Em seguida, as entidades legais podem ser adicionadas ao modelo. As entidades legais podem ser adicionadas selecionando uma hierarquia da organização ou selecionando as entidades legais. Se uma hierarquia da organização é selecionada, apenas as entidades legais que utilizam o calendário fiscal selecionado dentro da hierarquia serão adicionadas ao modelo. Se você usar entidades legais para adicionar ao modelo, apenas as entidades legais com o mesmo calendário fiscal podem ser adicionadas. O mesmo calendário fiscal é necessário porque o fechamento anual é executado através da seleção de um ano fiscal, o que pode variar de calendário para calendário. 

Depois que as entidades legais são adicionadas, defina as contas principais de rendimentos retidos para cada entidade legal. O campo **Data do último fechamento anual** será atualizado cada vez que o fechamento anual for executado para a entidade legal. 

A guia **Dimensão financeira** é usada para definir quais dimensões financeiras serão usadas na transação de Abertura. Observe que as configurações que você está definindo são relevantes apenas à entidade legal selecionada na tabela **Entidades legais**. Você repetirá a configuração para cada entidade legal na tabela. 

**Transferir dimensões de balanço** é usado para definir se as dimensões financeiras em transações lançadas em contas de balanço devem ser mantidas na transação de Abertura. É uma prática recomendada definir essa opção como **Sim**. **Transferir dimensões de lucros e perdas** é usado para definir quais dimensões financeiras em transações lançadas em contas de lucros e perdas serão transferidas para a conta principal de rendimentos retidos. Primeiro, identifique as dimensões financeiras relevantes para a entidade legal selecionada. Isso inclui qualquer dimensão financeira lançada durante o ano, mesmo que a dimensão financeira não faça parte de uma estrutura de conta ativa. Em seguida, defina cada dimensão como **Fechar individual** ou **Fechar todas**.  O padrão é **Fechar todas**, o que mantém os valores originais da dimensão financeira de transações lançadas e as utiliza para criar os saldos iniciais para a conta de rendimentos retidos. Saldos iniciais de rendimentos retidos separados serão criados para cada combinação única de valores da dimensão financeira. Se **Fechar individual** é selecionado, todas as transações lançadas com aquela dimensão financeira será resumida em um saldo inicial de rendimentos retidos para o valor da dimensão inserido no campo seguinte ao **Fechar individual**. Por exemplo, suponha que todas as transações do ano fiscal foram lançadas com a estrutura de conta Conta principal - Departamento. Na dimensão financeira do Departamento no modelo, **Fechar individual** é selecionado e 100 é o valor inserido. Se a receita total de todas as transações lançadas aos departamentos 200, 300 e 400 é $100,000, um saldo inicial será criado para Rendimentos retidos - 100. Se você selecionar **Fechar individual** e deixar o valor da dimensão financeira em branco, todas as transações irão lançar em rendimentos retidos com o valor da dimensão em branco. 

O processo de fechamento anual não segue as estruturas de conta. Isso porque as estruturas de conta podem mudar ao longo do ano fiscal e nem sempre é possível identificar a estrutura de conta relevante devido a todas essas alterações.  Quando as transações de abertura forem criadas, os saldos serão trazidos a diante com dimensões financeiras, como definido no modelo do fechamento anual. As entradas dos saldos iniciais podem incluir dimensões financeiras que já não estão na estrutura de conta atual e combinações de segmento que não são mais válidas na estrutura de conta atual. Se a sua organização deseja excluir uma dimensão financeira para o saldo inicial de rendimento retido, defina a dimensão financeira como **Fechar individual** e deixe o valor da dimensão vazio.

## <a name="run-the-year-end-close-process"></a>Executar o processo de fechamento anual
Depois que os modelos de fechamento anual são criados, o processo de fechamento anual é iniciado selecionando **Executar ano fiscal** no Painel de Ação. Selecione todas ou um subconjunto de entidades no modelo sobre o qual será executado o fechamento anual. Ao executar o fechamento anual pela primeira vez em um ano fiscal, você provavelmente irá escolher todas as entidades para criar saldos iniciais para todas as entidades legais. Se você estiver executando o fechamento anual novamente, você pode escolher executar o processo apenas para as entidades legais para as quais entradas de ajuste foram lançadas. 

Selecione o ano fiscal sobre o qual você gostaria de executar o processo de fechamento anual. Caso exista mais de um período de fechamento para o último período do ano fiscal, o campo **Nome do período** ficará disponível para que você possa selecionar em qual período de fechamento lançar a transação de Fechamento, se a configuração está definida para criar a transação de Fechamento. 

Insira um número de comprovante, que pode ou não ser necessário, dependendo da configuração em Parâmetros da contabilidade. O mesmo número de comprovante será usado para todas as entidades legais selecionadas para o processo de fechamento anual. O número de comprovante não é gerado utilizando uma sequência numérica. É uma prática recomendada inserir um número de comprovante, mesmo que não seja necessário. Inserir um número de comprovante facilita encontrar a transação de Abertura no novo ano fiscal. Se um número de comprovante não for inserido, o comprovante ficará em branco para a transação de Abertura. 

Se deseja reverter um fechamento anual anterior, do ano fiscal selecionado, defina **Desfazer fechamento anterior** como **Sim**. O fechamento anual será revertido, mas o processo pode ser executado novamente a qualquer momento. Se você reverter um fechamento anual, a **Data do último fechamento anual** ficará indisponível. 

O processo de fechamento anual é executado, por padrão, no modo de lote. É uma prática recomendada executar o processo no modo de lote, para permitir que o usuário retorne às outras atividades. Após a conclusão do processo de fechamento anual, a **Data do último fechamento anual** será atualizada com a data da sessão.

Para obter mais informações, consulte [Fechar a contabilidade ao final do período](close-general-ledger-at-period-end.md).




