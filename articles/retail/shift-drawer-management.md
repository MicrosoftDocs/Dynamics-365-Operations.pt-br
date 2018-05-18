---
title: "Gerenciamento de gaveta de pagamento e à vista"
description: "Este artigo explica como configurar e usar os dois tipos de ponto de varejo de turnos de venda (POS): compartilhado e autônomo. Turnos compartilhados podem ser usados por vários usuários em vários locais, enquanto os turnos autônomos podem ser usados por somente um trabalhador por vez."
author: rubencdelgado
manager: AnnBe
ms.date: 02/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8a24f8adc4f7886a1f942d83f7a4eb12e7034fcd
ms.openlocfilehash: c1483d3240d266845cea7789b70c038cb98fdfcc
ms.contentlocale: pt-br
ms.lasthandoff: 03/22/2018

---

# <a name="shift-and-cash-drawer-management"></a>Gerenciamento de gaveta de pagamento e à vista

[!include [banner](includes/banner.md)]

Este artigo explica como configurar e usar os dois tipos de ponto de varejo de turnos de venda (POS): compartilhado e autônomo. Turnos compartilhados podem ser usados por vários usuários em vários locais, enquanto os turnos autônomos podem ser usados por somente um trabalhador por vez.

Há dois tipos de ponto de varejo de turnos de venda (POS): independente e compartilhado. Turnos autônomos podem ser usados por somente um trabalhador por vez. Turnos compartilhados podem ser usados por vários usuários em vários locais. Portanto, eles efetivamente criam um turno único para vários trabalhadores em uma loja.

## <a name="standalone-shifts"></a>Turnos autônomos
Turnos autônomos são usados em um cenário de POS tradicional, fixo, onde o dinheiro é reconciliado independente de cada registradora de POS. Por exemplo, em uma configuração de supermercado, normalmente existem diversos terminais de PDV fixos, e um caixa é atribuído a cada terminal. Nesse caso, cada registradora provavelmente usará um turno autônomo e o caixa é responsável pela gaveta ou físico à vista no registrador. Um turno autônomo engloba todas as atividades na registradora durante o turno de trabalho da caixa. Atividades podem incluir o valor de abertura depositado da gaveta do caixa, toda remoção e adição de pagamento à vista por meio de operações como descartes de banco e entrada de flutuação e a declaração de meio de pagamento no fim do turno.

### <a name="set-up-a-stand-alone-shift"></a>Configurar um turno autônomo

Um turno autônomo é designado no nível da gaveta de dinheiro. Este procedimento explica como configurar um turno autônomo em uma registradora de POS.

1.  Clique em **Varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Selecione o perfil de hardware a ser usado para o turno autônomo.
3.  Na Guia Rápida **Caixa**, confirme que a opção **Caixa registradora de turno compartilhado** está definida para **Não**.
4.  Clique em **Salvar**.
5.  Clique em **Varejo** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **Registros**.
6.  Selecione o registro que exige uma mudança autônoma e, em seguida, clique em **Editar**.
7.  No campo **Perfil de Hardware**, selecione o perfil de hardware que você selecionou na etapa 2.
8.  Clique em **Salvar**.
9.  Clique em **Varejo** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
10. Selecione a agenda de distribuição **1090** e clique **Executar agora** para sincronizar as alterações para o PDV.

### <a name="use-a-stand-alone-shift"></a>Usar um turno autônomo

1.  Entrar no PDV.
2.  Se nenhuma mudança for aberta, selecione **Abrir um novo turno**.
3.  Vá para a operação **Declarar valor inicial** e especifique a quantidade de dinheiro que está sendo adicionado à gaveta ao iniciar o dia de trabalho.
4.  Realizar algumas transações.
5.  No final do dia, selecione **Declarar meio de pagamento** para declarar o valor do dinheiro que permanece na caixa registradora.
6.  Insira o valor em dinheiro, e em seguida clique em **Salvar** para salvar a declaração de meios de pagamento.
7.  Selecione **Fechar turno** para fechar o turno.

**Observação:** outras operações estão disponíveis durante o turno, dependendo de processos de negócios que estão em vigor. As operações **Depósito no Cofre**, **Depósito Bancário** e **Remoção de meio de pagamento** podem ser usadas para remover o dinheiro da gaveta do caixa durante o dia ou antes do turno ser encerrado. Se uma gaveta fica insuficiente de dinheiro, a operação **Entrada de flutuação** pode ser usada para adicionar dinheiro à gaveta.

## <a name="shared-shifts"></a>Turnos compartilhados
Uma mudança compartilhada é usada em um ambiente onde vários caixas compartilham uma registradora ou um conjunto de registradoras durante o dia de trabalho. Normalmente, uma mudança compartilhada é usada em ambientes móveis de POS. Em um ambiente móvel, cada caixa não é responsável por uma única caixa registradora. Em vez disso, todas as caixas devem ser capazes de uma venda de meio de pagamento e adicionar dinheiro a qualquer caixa registradora aos quais assemelham-se. Nesse cenário, as registradoras são compartilhadas entre os caixas que estão incluídas em um turno compartilhado. Todas as registradoras em um turno compartilhado estão incluídas no mesmo turno para atividades que estão relacionadas ao gerenciamento de pagamento à vista para essa mudança. Portanto, o valor inicial para a mudança deve incluir a soma de todo dinheiro em todos os as registradoras que são incluídas durante a mudança compartilhada. Da mesma forma, a declaração de meios de pagamento será a soma de todo dinheiro em todos os as registradoras que são incluídas durante a mudança compartilhada. **Observação:** Apenas um turno compartilhado pode ser aberto por vez em cada loja. Turnos compartilhados e autônomos podem ser usados no mesmo armazenamento.

### <a name="set-up-a-shared-shift"></a>Definir um turno compartilhado

1.  Clique em **Varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Selecione o perfil de hardware a ser usado para o turno compartilhado.
3.  Na Guia Rápida **Caixa**, confirme que a opção **Caixa registradora de turno compartilhado** está definida para **Sim**.
4.  Clique em **Salvar**.
5.  Clique em **Varejo** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **Registros**.
6.  Selecione o registro que exige uma mudança compartilhada e, em seguida, clique em **Editar**.
7.  No campo **Perfil de Hardware**, selecione o perfil de hardware que você selecionou na etapa 2.
8.  Clique em **Salvar**.
9.  Clique em **Varejo** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
10. Selecione a agenda de distribuição **1090** e clique **Executar agora** para sincronizar as alterações para o PDV.

### <a name="use-a-shared-shift"></a>Use um turno compartilhado

1.  Entrar no PDV.
2.  Caso ainda não esteja conectado a uma estação de hardware do POS, selecione **Operação não sacadora** e, em seguida, selecione a operação **Selecionar a estação de hardware** para ativar uma estação de hardware para a mudança compartilhada. Essa etapa é necessária somente na primeira vez que um registro é adicionado a um ambiente de turno compartilhado.
3.  Saia do POS e entre novamente.
4.  Selecione **Criar um novo turno**.
5.  Selecione **Declarar Valor Inicial**.
6.  Insira o valor inicial de todas as registradoras na loja que fazem parte do turno compartilhado e, em seguida, clique em **Salvar**.
    -   Para adicionar a parte do valor inicial para cada registradora subsequente, use a operação **Selecionar estação de hardware** para ativar a estação de hardware.
    -   Para adicionar uma gaveta a uma registradora específica, use a operação **Abrir gaveta**.
    -   Continue até que todas as registradoras em mudança compartilhada tenham sua parte do valor inicial.

7.  No final do dia, abra cada registradora e remova o dinheiro.
8.  Depois que você remover o dinheiro da última caixa registradora, conte o dinheiro de todas as gavetas de dinheiro.
9.  Use a operação **Declarar meio de pagamento** para declarar a quantidade total de dinheiro de todas as as registradoras que são incluídos durante a mudança compartilhada.
10. Use a operação **Fechar turno** para fechar o turno compartilhado.

## <a name="shift-operations"></a>Operações de turnos
Várias ações podem ser tomadas para alterar o status de um turno ou para aumentar ou diminuir a quantidade de dinheiro na gaveta. A seção a seguir descreve essas operações de turnos para Modern POS e Cloud POS do Dynamics 365 for Retail.

**Turno aberto**

O PDV requer que um usuário tenha um turno ativo e aberto para executar qualquer operação que resulte em uma transação financeira como uma venda, uma devolução ou uma ordem de cliente.  

Ao fazer logon no PDV, o sistema primeiramente verifica se o usuário tem um turno ativo disponível na caixa registradora atual. Se não tiver, o usuário poderá optar por abrir um novo turno, retomar um turno existente ou continuar para fazer logon no modo "sem gaveta”, dependendo da configuração do sistema e de suas permissões.

**Declarar Valor Inicial**

Essa operação geralmente é a primeira ação executada na abertura de um novo turno. O usuário especifica o valor inicial em dinheiro na gaveta para o turno. Isso é importante porque o cálculo a mais/a menos que ocorre no fechamento de um turno é feito com base nesse valor.

**Entrada de flutuação**

As entradas de flutuação não são transações de vendas, são executadas em um turno ativo e aumentam a quantidade de dinheiro na gaveta. Um exemplo comum de uma entrada de flutuação seria adicionar mais troco à gaveta quando ele estiver acabando.

**Remoção de Meio de Pagamento**

As remoções de meios de pagamento não são transações de vendas, são executadas em um turno ativo para reduzir a quantidade de dinheiro na gaveta. Elas são mais comumente usadas em conjunto com uma entrada de flutuação em um turno diferente. Por exemplo, a Caixa registradora 1 está ficando sem troco, então o usuário na Caixa registradora 2 executa uma remoção de meios de pagamento para reduzir a quantia na gaveta. Em seguida, o usuário na Caixa registradora 1 executaria uma entrada de flutuação para aumentar sua quantia.

**Suspender turno**

Os usuários podem suspender seus turnos ativos para liberar a caixa registradora atual para outro usuário, ou para mover o turno para uma caixa registradora diferente (isso é normalmente chamado de "gaveta do caixa flutuante"). 

A suspensão do turno impede novas transações ou alterações no turno até que ele seja retomado.

**Retomar turno**

Essa operação permite que um usuário retome um turno suspenso anteriormente em uma caixa registradora que ainda não tenha um turno ativo.

**Declaração de meios de pagamento**

A declaração de meios de pagamento é uma ação que o usuário executa para especificar a quantidade total de dinheiro na gaveta, principalmente antes de fechar o turno. Essa é a quantidade que é comparada com o turno esperado para calcular o valor a mais/a menos.

**Sangria para cofre**

As sangrias para cofre podem ser executadas a qualquer momento em um turno ativo. Essa operação remove dinheiro da gaveta, para que possa ser transferido para um local mais seguro como um cofre na sala reservada. O valor total registrado para sangrias para cofre ainda é incluído nos totais do turno, mas não precisa ser contabilizado como parte da declaração de meios de pagamento.

**Sangria para banco**

Como as sangrias para cofre, as sangrias para banco também são executadas em turnos ativos. Essa operação remove dinheiro do turno para preparar para o depósito bancário.

**Turno com fechamento cego**

Um turno com fechamento cego é um turno que não está mais ativo, mas que não foi totalmente fechado. Turnos com fechamento cego não podem ser retomados como um turno suspenso, mas procedimentos como a declaração de valores iniciais e de meios de pagamento podem ser executados posteriormente ou a partir de uma caixa registradora diferente.

Turnos com fechamento cego são frequentemente usados para liberar uma caixa registradora para um novo usuário ou turno, sem precisar contar, reconciliar e fechar totalmente esse turno. 

**Fechar turno**

Essa operação calcula os totais do turno, valores a mais/a menos e fecha um turno ativo ou com fechamento cego. Turnos fechados não podem ser retomados ou modificados.  

**Gerenciar turnos**

Essa operação permite que os usuários visualizem todos os turnos ativos, suspensos e com fechamento cego da loja. Dependendo das suas permissões, os usuários poderão realizar os procedimentos finais de fechamento como declaração de meios de pagamento e encerramento de turnos com fechamento cego. Essa operação também permitirá que os usuários visualizem e excluam turnos inválidos no evento raro de um turno ser deixado em um estado incorreto após alternar entre os modos offline e online. Esses turnos inválidos não contêm as informações financeiras ou os dados transacionais necessários para a reconciliação. 

