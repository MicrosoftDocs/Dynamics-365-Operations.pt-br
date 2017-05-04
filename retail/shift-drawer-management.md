---
title: "Gerenciamento de gaveta de pagamento e à vista"
description: "Este artigo explica como configurar e usar os dois tipos de ponto de varejo de turnos de venda (POS): compartilhado e autônomo. Turnos compartilhados podem ser usados por vários usuários em vários locais, enquanto os turnos autônomos podem ser usados por somente um trabalhador por vez."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 09c7fce1fa83d6a8d6391db667b7260d2a199390
ms.lasthandoff: 03/31/2017


---

# <a name="shift-and-cash-drawer-management"></a>Gerenciamento de gaveta de pagamento e à vista

[!include[banner](includes/banner.md)]


Este artigo explica como configurar e usar os dois tipos de ponto de varejo de turnos de venda (POS): compartilhado e autônomo. Turnos compartilhados podem ser usados por vários usuários em vários locais, enquanto os turnos autônomos podem ser usados por somente um trabalhador por vez.

Há dois tipos de ponto de varejo de turnos de venda (POS): independente e compartilhado. Turnos autônomos podem ser usados por somente um trabalhador por vez. Turnos compartilhados podem ser usados por vários usuários em vários locais. Portanto, eles efetivamente criam um turno único para vários trabalhadores em uma loja.

## <a name="standalone-shifts"></a>Turnos autônomos
Turnos autônomos são usados em um cenário de POS tradicional, fixo, onde o dinheiro é reconciliado independente de cada registradora de POS. Por exemplo, em uma configuração de supermercado, normalmente existem diversos terminais de PDV fixos, e um caixa é atribuído a cada terminal. Nesse caso, cada registradora provavelmente usará um turno autônomo e o caixa é responsável pela gaveta ou físico à vista no registrador. Um turno autônomo engloba todas as atividades na registradora durante o turno de trabalho da caixa. Atividades podem incluir o valor de abertura depositado da gaveta do caixa, toda remoção e adição de pagamento à vista por meio de operações como descartes de banco e entrada de flutuação e a declaração de meio de pagamento no fim do turno.

### <a name="set-up-a-stand-alone-shift"></a>Configurar um turno autônomo

Um turno autônomo é designado no nível da gaveta de dinheiro. Este procedimento explica como configurar um turno autônomo em uma registradora de POS.

1.  Clique em **Varejo e comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Selecione o perfil de hardware a ser usado para o turno autônomo.
3.  Na Guia Rápida **Caixa**, confirme que a opção **Caixa registradora de turno compartilhado** está definida para **Não**.
4.  Clique em **Salvar**.
5.  Clique em **Varejo e comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Registradoras**.
6.  Selecione o registro que exige uma mudança autônoma e, em seguida, clique em **Editar**.
7.  No campo **Perfil de Hardware**, selecione o perfil de hardware que você selecionou na etapa 2.
8.  Clique em **Salvar**.
9.  Clique em **Varejo e comércio** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
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

1.  Clique em **Varejo e comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de hardware**.
2.  Selecione o perfil de hardware a ser usado para o turno compartilhado.
3.  Na Guia Rápida **Caixa**, confirme que a opção **Caixa registradora de turno compartilhado** está definida para **Sim**.
4.  Clique em **Salvar**.
5.  Clique em **Varejo e comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Registradoras**.
6.  Selecione o registro que exige uma mudança compartilhada e, em seguida, clique em **Editar**.
7.  No campo **Perfil de Hardware**, selecione o perfil de hardware que você selecionou na etapa 2.
8.  Clique em **Salvar**.
9.  Clique em **Varejo e comércio** &gt; **TI de varejo** &gt; **Agenda de distribuição**.
10. Selecione a agenda de distribuição **1090** e clique **Executar agora** para sincronizar as alterações para o PDV.

### <a name="use-a-shared-shift"></a>Use um turno compartilhado

1.  Entrar no PDV.
2.  Caso ainda não esteja conectado a uma estação de hardware do POS, selecione **Operação não sacadora** e, em seguida, selecione a operação **Selecionar a estação de hardware** para ativar uma estação de hardware para a mudança compartilhada. Essa etapa é necessária somente na primeira vez que um registro é adicionado a um ambiente de turno compartilhado.
3.  Saia do POS e entre novamente.
4.  Selecione **Criar um novo turno**.
5.  Selecione **Declarar Valor Inicial**.
6.  Insira o valor inicial de todas as registradoras na loja que fazem parte do turno compartilhado e, em seguida, clique em **Salvar**.
    -   Para adicionar a parte do valor inicial para cada registradora subsequente, use a operação **Selecionar estação de hardware **para ativar a estação de hardware.
    -   Para adicionar uma gaveta a uma registradora específica, use a operação **Abrir gaveta**.
    -   Continue até que todas as registradoras em mudança compartilhada tenham sua parte do valor inicial.

7.  No final do dia, abra cada registradora e remova o dinheiro.
8.  Depois que você remover o dinheiro da última caixa registradora, conte o dinheiro de todas as gavetas de dinheiro.
9.  Use a operação **Declarar meio de pagamento** para declarar a quantidade total de dinheiro de todas as as registradoras que são incluídos durante a mudança compartilhada.
10. Use a operação **Fechar turno** para fechar o turno compartilhado.





