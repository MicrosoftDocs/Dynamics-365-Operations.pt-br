---
title: Gerenciamento de turnos e gaveta de dinheiro
description: "Este tópico explica como configurar e utilizar turnos no ponto de venda (PDV) de varejo."
author: jblucher
manager: AnnBe
ms.date: 05/10/2018
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
ms.sourcegitcommit: da5519eb0746347905e3b3d3d81161850c429f57
ms.openlocfilehash: f0856a3a36ff97773c0fadbe94fe680762c5206b
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2018

---

# <a name="shift-and-cash-drawer-management"></a>Gerenciamento de turnos e gaveta de dinheiro

[!include [banner](includes/banner.md)]

Este tópico explica como configurar e utilizar turnos no ponto de venda (PDV) de varejo. 

No Microsoft Dynamics 365 for Retail, o termo *turno* descreve o conjunto de dados transacionais e atividades de PDV entre dois momentos. Para cada turno, o valor em dinheiro esperado é comparado ao valor que foi contado e declarado.

Normalmente, os turnos são abertos no início do dia útil. Nesse momento, um usuário declara o valor inicial que a gaveta de dinheiro contém. As transações de vendas são realizadas ao longo do dia. Por fim, ao final do dia, a gaveta é contada e os valores finais são declarados. O turno é fechado e uma redução Z é gerada. A redução Z indica se há excedente ou escassez.

## <a name="typical-shift-scenarios"></a>Cenários típicos de turnos
O Retail fornece várias opções de configuração e operações de PDV para oferecer suporte a uma grande variedade de processos comerciais de fechamento do dia para o PDV. Esta seção descreve alguns cenários típicos de turnos.

### <a name="fixed-till"></a>Gaveta do caixa fixa
Tradicionalmente, esse cenário tem sido usado com mais frequência. Ainda é usado extensivamente. Em um turno de "gaveta do caixa fixa", o turno e a gaveta do caixa são associados a uma caixa registradora específica. Eles não são movidos de uma caixa registradora à outra. Um turno de "gaveta do caixa fixa" pode ser usado por um único usuário ou compartilhado entre vários usuários. Turnos de "gaveta do caixa fixa" não exigem nenhuma configuração especial.

### <a name="floating-till"></a>Gaveta do caixa flutuante
Em um turno de "gaveta do caixa flutuante", o turno e a gaveta de dinheiro podem ser movidos de uma caixa registradora à outra. Embora uma caixa registradora possa ter apenas um turno ativo por gaveta de dinheiro, os turnos podem ser suspensos e retomados posteriormente ou em uma caixa registradora diferente.

Por exemplo, uma loja tem duas caixas registradoras. Cada caixa registradora é aberta no início do dia quando o caixa abre um novo turno e fornece o valor inicial. Quando um caixa estiver pronto para fazer uma interrupção, ele suspenderá seu turno e removerá a gaveta do caixa da gaveta de dinheiro. Essa caixa registradora então ficará disponível para outros caixas. Outro caixa pode entrar e abrir seu próprio turno na caixa registradora. Depois do término da interrupção do primeiro caixa, este poderá retomar seu turno quando uma das outras caixas registradoras ficar disponível. Turnos de "gaveta do caixa flutuante" não exigem nenhuma configuração ou permissão especial.

### <a name="single-user"></a>Usuário único
Muitos varejistas preferem permitir apenas um usuário por turno, para ajudar a garantir o nível mais alto de responsabilidade pelo dinheiro na gaveta de dinheiro. Se apenas um usuário tiver permissão para usar a gaveta do caixa associada a um turno, esse usuário poderá ser unicamente responsabilizado por quaisquer discrepâncias. Se um turno é usado por mais de um usuário, é difícil determinar quem cometeu um erro ou quem pode estar tentando roubar da gaveta do caixa.

### <a name="multiple-users"></a>Vários usuários
Alguns varejistas estão dispostos a sacrificar o nível de responsabilidade que os turnos de usuário único fornecem e permitir mais de um usuário por turno. Essa abordagem é comum quando há mais usuários do que caixas registradoras disponíveis, e a necessidade de flexibilidade e velocidade supera o potencial de perdas. Ela também é comum quando os gerentes de loja não têm seus próprios turnos, mas podem, conforme necessário, usar os turnos de qualquer um dos seus caixas. Para entrar e usar um turno aberto por outro usuário, é necessário ter a permissão de PDV **Permitir vários logons de turno**.

### <a name="shared-shift"></a>Turno compartilhado
Uma configuração de "turno compartilhado” permite que os varejistas tenham um único turno entre várias caixas registradoras, gavetas de dinheiro e usuários. Um turno compartilhado tem um único valor inicial e um único valor de fechamento que são resumidos em todas as gavetas de dinheiro. Turnos compartilhados são mais comuns quando dispositivos móveis são usados. Nesse cenário, uma gaveta de dinheiro separada não é reservada para cada caixa registradora. Em vez disso, todas as caixas registradoras podem compartilhar uma única gaveta de dinheiro.

Para que os turnos compartilhados sejam usados em uma loja, a gaveta de dinheiro deve ser configurada como uma "gaveta de turno compartilhado" em **Retail \> Configuração de canal \> Configuração de PDV \> Perfis de PDV \> Perfis de hardware \> Gaveta**. Além disso, os usuários devem ter uma ou ambas as permissões de turno compartilhado (Permitir gerenciar turno compartilhado e Permitir usar turno compartilhado).

> [!NOTE]
> Apenas um turno compartilhado pode ser aberto por vez em cada loja. Turnos compartilhados e autônomos podem ser usados no mesmo armazenamento.

## <a name="shift-and-drawer-operations"></a>Operações de turno e de gaveta
Várias operações podem ser realizadas para alterar o estado de um turno, ou para aumentar ou diminuir a quantidade de dinheiro na gaveta. Esta seção descreve essas operações de turno para PDV Moderno e PDV em Nuvem do Microsoft Dynamics 365 for Retail.

### <a name="open-shift"></a>Turno aberto
O PDV requer que os usuários tenham um turno ativo e aberto para executar qualquer operação que produza uma transação financeira, como uma venda, uma devolução ou uma ordem de cliente.

Quando um usuário entra no PDV, o sistema verifica primeiro se um turno ativo está disponível para esse usuário na caixa registradora atual. Se não houver um turno ativo disponível, o usuário poderá abrir um novo turno, retomar um turno existente ou entrar no modo "sem gaveta”, dependendo da configuração do sistema e das permissões do usuário.

### <a name="declare-start-amount"></a>Declarar Valor Inicial
Essa operação geralmente é a primeira a ser executada na abertura de um novo turno. Nessa operação, os usuários especificam o valor inicial em dinheiro na gaveta para o turno. Essa operação é importante porque o cálculo de excedente/escassez que ocorre quando um turno é fechado considera o valor inicial.

### <a name="float-entry"></a>Entrada de flutuação
As *Entradas de flutuação* não são transações de vendas, são executadas em um turno ativo para aumentar a quantidade de dinheiro na gaveta. Um exemplo comum de uma entrada de flutuação é uma transação para adicionar mais troco à gaveta quando ele estiver acabando.

### <a name="tender-removal"></a>Remoção de Meio de Pagamento
As *Remoções de meios de pagamento* não são transações de vendas, são executadas em um turno ativo para reduzir a quantidade de dinheiro na gaveta. Essa operação geralmente é usada em conjunto com uma operação de Entrada de flutuação em um turno diferente. Por exemplo, como a caixa registradora 1 está ficando sem troco, o usuário na caixa registradora 2 realiza uma remoção de meios de pagamento para reduzir a quantia na sua gaveta de dinheiro. Em seguida, o usuário na caixa registradora 1 realiza uma entrada de flutuação para aumentar a quantia na sua gaveta de dinheiro.

### <a name="suspend-shift"></a>Suspender turno
Os usuários podem suspender seus turnos ativos para liberar a caixa registradora atual para outro usuário, ou para mover o turno para uma caixa registradora diferente (nesse caso, o turno normalmente é chamado de turno de "gaveta do caixa flutuante").

A suspensão de um turno impede novas transações ou alterações no turno até que ele seja retomado.

### <a name="resume-shift"></a>Retomar turno
Essa operação permite que os usuários retomem um turno suspenso anteriormente em qualquer caixa registradora que ainda não tenha um turno ativo.

### <a name="tender-declaration"></a>Declaração de meios de pagamento
Essa operação é executada para especificar a quantidade total de dinheiro contida atualmente na gaveta. Os usuários costumam executar essa operação antes de fechar um turno. O valor especificado é comparado ao valor esperado do turno para calcular o valor de excedente/escassez.

### <a name="safe-drop"></a>Sangria para cofre
As sangrias para cofre podem ser realizadas em um turno ativo a qualquer momento. Essa operação remove dinheiro da gaveta, para que possa ser transferido para um local mais seguro, como um cofre na sala reservada. O valor total registrado para sangrias para cofre é incluído nos totais do turno, mas não precisa ser contabilizado como parte da declaração de meios de pagamento.

### <a name="bank-drop"></a>Sangria para banco
Como as sangrias para cofre, as sangrias para banco são realizadas em turnos ativos. Essa operação remove dinheiro do turno para preparar para o depósito bancário.

### <a name="blind-close-shift"></a>Turno com fechamento cego
*Turnos com fechamento cego* não estão mais ativos, mas não foram totalmente fechados. Diferentemente dos turnos suspensos, os turnos com fechamento cego não podem ser retomados. No entanto, operações como Declarar valor inicial e Declaração de meios de pagamento podem ser executadas neles posteriormente ou de uma caixa registradora diferente.

Turnos com fechamento cego são frequentemente usados para liberar uma caixa registradora para um novo usuário ou turno, sem precisar contar, reconciliar e fechar totalmente o turno.

### <a name="close-shift"></a>Fechar turno
Essa operação calcula os totais do turno e os valores de excedente/escassez, e fecha um turno ativo ou com fechamento cego. Dependendo das permissões do usuário, uma redução Z também é impressa para o turno. Turnos fechados não podem ser retomados ou modificados.

### <a name="print-x"></a>Imprimir X
Essa operação gera e imprime um relatório X para o turno ativo atual.

### <a name="reprint-z"></a>Reimprimir Z
Essa operação reimprime a redução Z mais recente gerada pelo sistema quando um turno foi fechado.

### <a name="manage-shifts"></a>Gerenciar turnos
Essa operação permite que os usuários visualizem todos os turnos ativos, suspensos e com fechamento cego da loja. Dependendo das suas permissões, os usuários poderão realizar os procedimentos finais de fechamento, como Declaração de meios de pagamento e Operações de fechamento de turno para turnos com fechamento cego. Essa operação também permite que os usuários visualizem e excluam turnos inválidos, no evento raro de um turno ser deixado em um estado incorreto após uma alternação entre os modos offline e online. Esses turnos inválidos não contêm as informações financeiras nem os dados transacionais necessários para a reconciliação.

## <a name="shift-and-drawer-permissions"></a>Permissões de turno e de gaveta
As seguintes permissões de PDV afetam o que um usuário pode ou não fazer em vários cenários:

- **Permitir fechamento cego**
- **Permitir impressão do leitura X**
- **Permitir impressão da redução Z**
- **Permitir declaração de meios de pagamento**
- **Permitir sangria/suprimento**
- **Abrir gaveta sem venda**
- **Permitir vários logons de turno** – Permite que o usuário entre e use um turno que foi aberto por outro usuário. Os usuários que não tiverem essa permissão poderão entrar e usar apenas os turnos que abriram.
- **Permitir gerenciar turno compartilhado** – Os usuários devem ter essa permissão para abrir ou fechar um turno compartilhado.
- **Permitir usar turno compartilhado** – Os usuários devem ter essa permissão para entrar e usar um turno compartilhado.

## <a name="back-office-end-of-day-considerations"></a>Considerações de fechamento do dia do back office
A maneira como os turnos e a reconciliação de gavetas de dinheiro são usados no PDV é diferente da maneira como os dados de transação são resumidos durante o cálculo de demonstrativos. É importante que você entenda essa diferença. Dependendo da configuração e dos processos comerciais, os dados do turno no PDV (a redução Z) e um demonstrativo calculado no back office podem fornecer resultados diferentes. Essa diferença não significa necessariamente que os dados do turno ou o demonstrativo calculado estejam incorretos, ou que haja um problema com os dados. Isso significa apenas que os parâmetros fornecidos podem incluir transações adicionais ou menos transações, ou que as transações foram resumidas de forma diferente.

Embora cada varejista tenha necessidades comerciais diferentes, recomendamos configurar o sistema da seguinte maneira para evitar situações em que diferenças desse tipo ocorram:

Vá para **Retail \> Canais \> Lojas de varejo \> Todas as lojas de varejo \> Demonstrativo/fechamento** e, para cada loja, defina os campos **Método do demonstrativo** e **Método de fechamento** como **Turno**.

Essa configuração ajuda a garantir que os demonstrativos do back office incluam as mesmas transações que os turnos no PDV, e que os dados sejam resumidos por esse turno.

Para obter mais informações sobre métodos de demonstrativo e de fechamento, consulte [Configurações de loja para obter demonstrativo do Retail](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).

