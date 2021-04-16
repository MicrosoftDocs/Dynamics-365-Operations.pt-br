---
title: Configuração de gerenciamento de crédito
description: Este tópico descreve a configuração necessária para o Gerenciamento de crédito.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 640d81920dad391a77b58942972660b01f11b003
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830631"
---
# <a name="credit-management-setup"></a>Configuração de gerenciamento de crédito 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Fluxos de trabalho de gerenciamento de crédito

Vá para **Crédito e cobranças \> Configuração \> Fluxos de trabalho de gerenciamento de crédito** para definir os fluxos de trabalho usados para gerenciar ajustes de limite de crédito.

- Você pode criar um fluxo de trabalho que permita aprovar um lote de ajustes de limites de crédito com uma única aprovação.
- Você pode adicionar um fluxo de trabalho no nível da linha para que os ajustes de limite de crédito possam ser aprovados individualmente.
- Você pode criar um fluxo de trabalho de liberação que encaminhe os bloqueios automaticamente para um processo de fluxo de trabalho.

## <a name="blocking-rules"></a>Regras de bloqueio

### <a name="ranking-payment-terms"></a>Classificando condições de pagamento

Você pode colocar uma ordem de venda em espera se as condições de pagamento na ordem não corresponderem às condições de pagamento padrão do cliente. No entanto, às vezes as condições de pagamento são diferentes, mas parecidas o bastante a ponto de você não querer colocar a ordem em espera. Você pode classificar as condições de pagamento para que algumas delas tenham a mesma classificação, enquanto outras têm uma classificação mais alta ou mais baixa.

Se as classificações das condições de pagamento estiverem ativas, e as condições de pagamento na ordem tiverem uma classificação superior à das condições de pagamento padrão do cliente, as ordens de venda serão mantidas em espera.

Para configurar as classificações de condições de pagamento, acesse **Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Classificar condições de pagamento**  

### <a name="ranking-settlement-discounts"></a>Classificando descontos de liquidação

Você pode colocar uma ordem de venda em espera se o desconto à vista na ordem não corresponder ao desconto à vista padrão do cliente. No entanto, às vezes os descontos à vista são diferentes, mas parecidos o bastante a ponto de você não querer colocar a ordem em espera. Você pode classificar os descontos à vista para que alguns deles tenham a mesma classificação, enquanto outros têm uma classificação mais alta ou mais baixa.

Se as classificações dos descontos à vista estiverem ativas e os descontos à vista na ordem tiverem uma classificação superior à do desconto à vista padrão do cliente, as ordens de venda serão mantidas em espera.

Para configurar as classificações de condições de pagamento, acesse **Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Classificar descontos de liquidação**  

## <a name="reasons"></a>Motivos

Vários tipos de motivos são usados no Gerenciamento de crédito:

- Os motivos de bloqueio indicam por que uma ordem de venda foi colocada em espera.
- Os motivos de liberação são atribuídos a uma ordem quando ela é liberada do bloqueio.
- Os motivos de status indicam por que um status de conta foi atribuído a um cliente.

Você pode configurar motivos na página **Motivos de gerenciamento de crédito** (**Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Motivos de gerenciamento de crédito**).

1. No campo **Tipo do motivo**, selecione o tipo de motivo: **Bloqueio**, **Liberação** ou **Status**.
2. No campo **Motivo**, insira um nome para o motivo.
3. No campo **Descrição**, insira uma descrição do código de motivo.

## <a name="credit-management-groups"></a>Grupos de gerenciamento de crédito

Os grupos de gerenciamento de crédito são usados para identificar clientes ou grupos de clientes que têm as mesmas propriedades de gerenciamento de crédito. Por exemplo, grupos de gerenciamento de crédito podem ser usados para determinar as regras de gerenciamento de crédito de bloqueio e exclusão para clientes.

Você pode criar grupos de gerenciamento de crédito na página **Grupos de gerenciamento de crédito** (**Crédito e cobranças \> Configuração > Configuração de gerenciamento de crédito \> Grupos de gerenciamento de crédito**).

1. Selecione **Novo** para criar uma linha.
2. Insira uma ID para o grupo. A ID pode ter até 10 caracteres.
3. No campo **Descrição**, insira um nome para o grupo. O nome pode ter até 60 caracteres.

O grupo de gerenciamento de crédito é atribuído a um cliente na FastTab **Crédito e cobranças** da página **Todos os clientes** (**Contas a receber \> Clientes \> Todos os clientes**).

## <a name="account-statuses"></a>Status da conta

Você pode criar status de conta para identificar a posição de crédito de uma conta de cliente. Você pode definir um status e seu efeito sobre os processos em espera de faturamento e entrega. Os status de conta também podem ser usados para determinar regras de bloqueio para um cliente.

Você pode criar status de conta na página **Status da conta** (**Crédito e cobranças \> Configuração > Configuração de gerenciamento de crédito \> Status da conta**).

1. Adicione um status de conta e insira uma descrição que represente a posição de crédito de um cliente. Por exemplo, use **Normal** para indicar que um cliente tem uma boa posição e as ordens em aberto estão sujeitas ao processamento padrão de gerenciamento de crédito.
2. Nos campos **Faturamento** e **Entrega em Espera**, selecione o tipo de bloqueio que deve ocorrer para os clientes que têm esse status de conta. Você pode bloquear todo o processamento, bloquear somente o processamento de faturas ou pode bloquear nenhum processamento quando as regras de limite de crédito forem aplicadas.

## <a name="scoring-groups"></a>Grupos de pontuação

Você pode configurar grupos de pontuação para definir fatores de risco e os critérios usados para mensurá-los. Quando as informações sobre um cliente são aplicadas a um grupo de pontuação, uma pontuação é calculada para cada fator de risco e usada para colocar o cliente em um grupo de risco. O grupo de risco pode ser usado para identificar a confiabilidade de crédito e calcular limites de crédito automáticos.

Você pode criar grupos de pontuação na página **Grupos de pontuação** (**Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Risco \> Grupos de pontuação**).

1. Crie um grupo de pontuação e insira um nome para ele.
2. Insira uma descrição para descrever melhor o grupo de pontuação.
3. Selecione um tipo de grupo. Existem oito tipos predefinidos. Você também pode selecionar **Definido pelo usuário** para definir um tipo de grupo mais adequado para sua organização.
4. Selecione um tipo de pontuação para definir como o grupo de pontuação calcula a pontuação de risco. As opções a seguir estão disponíveis:

    - **Intervalo** – Use esta opção para definir um intervalo de valores a serem usados para calcular uma pontuação.
    - **Definido pelo usuário** – Use esta opção para definir manualmente uma lista de valores a serem usados para a pontuação.

5. Se você selecionou **Intervalo** como o tipo de pontuação, adicione linhas para definir o intervalo de valores e as pontuações correspondentes.

    1. No campo **Do valor**, especifique o valor mais baixo do intervalo.
    2. No campo **Ao valor**, especifique o valor mais alto do intervalo.
    3. No campo **Pontuação**, insira a pontuação que deve ser atribuída quando o valor fornecido está no intervalo "de"/"até".

    Se você selecionou **Definido pelo usuário** como o tipo de pontuação, adicione linhas para especificar os valores definidos pelo usuário e as pontuações correspondentes.

    1. No campo **Valor**, insira o valor definido pelo usuário que deve ser fornecido das informações do cliente.
    2. No campo **Pontuação**, insira a pontuação que deve ser atribuída quando o valor fornecido está no intervalo "de"/"até".

## <a name="risk-classification"></a>Classificação de risco

É possível definir avaliações de risco que podem ser atribuídas a clientes com base na pontuação de risco deles. Uma pontuação de risco é calculada comparando as informações do cliente com cada grupo de pontuação. As pontuações são somados, e a pontuação total é comparada com os valores na configuração do grupo de risco para identificar o grupo de risco ao qual o cliente pertence. A pontuação do grupo de risco é usada para definir as regras de exclusão e bloqueio de gerenciamento de crédito para o cliente.

Você pode configurar grupos de risco na página **Avaliações de risco** (**Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Risco \> Avaliações de risco**).

1. Insira uma ID de grupo de risco.
2. Insira uma descrição para explicar melhor o grupo de risco.
3. Insira um intervalo de pontuações usado para determinar quais clientes pertencem ao grupo de risco.
4. Selecione um indicador de grupo de risco para especificar o símbolo que representa o grupo de risco.

## <a name="guaranteeinsurance-types"></a>Tipos de garantia/seguro

Você pode configurar tipos de garantia/seguro na página **Tipos de garantia/seguro** (**Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Seguros e garantias \> Tipos de seguro e garantia**).

1. Insira um tipo de garantia ou de seguro que identifique o nome do fiador ou do corretor de seguro.
2. Insira uma descrição para descrever o fiador/corretor de seguro.

## <a name="coverage-types"></a>Tipos de cobertura

Tipos de cobertura podem ser usados para classificar melhor as apólices de seguro. Eles não podem ser usados com garantias.

Você pode adicionar tipos de cobertura na página **Tipos de cobertura** (**Crédito e cobranças \> Configuração \> Configuração de de gerenciamento de crédito \> Seguro e garantias \> Tipos de cobertura**).

1. Insira um tipo de cobertura para identificar o tipo de cobertura que deve ser adicionado como seguro ou garantia.
2. Insira uma descrição para descrever o tipo de cobertura.

## <a name="automatic-credit-limits"></a>Limites de crédito automático

Você pode criar critérios para limites de crédito automáticos na página **Limites de crédito automáticos** (**Crédito e cobranças \> Configuração \> Configuração de gerenciamento de crédito \> Risco \> Limites de crédito automáticos**).

1. Selecione um grupo de risco ao qual o limite de crédito automático deve ser atribuído.
2. Selecione a moeda para o limite de crédito automático. É possível criar vários limites de crédito automáticos em diferentes moedas para o mesmo grupo de risco.
3. Insira o valor da receita que representa a receita máxima da empresa que pode ser usada para esse limite de crédito automático. Quando os limites de crédito são criados, o valor da receita é comparado a um valor de receita encontrado na página **Finanças** (**Contas a receber \> Todos os clientes \> Selecionar um cliente \> Geral \> Estatísticas \> Finanças**). O sistema usa o valor mais recente na seção **Visão geral**.

Siga estas etapas para adicionar linhas que representem o limite de crédito a ser gerado com base nos critérios selecionados.

1. Selecione o grupo de pontuação que define as informações do cliente que devem ser usadas para calcular o limite de crédito.
2. Selecione o operador de comparação que define como as informações do grupo de pontuação devem ser avaliadas.
3. Insira o valor que deve ser comparado ao valor especificado para o grupo de pontuação.
4. Insira o limite de crédito que deverá ser atribuído se as informações do cliente corresponderem ao valor especificado para o grupo de pontuação. Por exemplo, você cria um limite de crédito automático para o grupo de pontuação **Baixa**. Se anos na empresa é um dos grupos de pontuação, você pode definir uma linha que atribua um limite de crédito de 100.000 se o cliente estiver no negócio há cinco anos e outra linha que atribua um limite de crédito de 200.000 se o cliente estiver no negócio há 10 anos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]