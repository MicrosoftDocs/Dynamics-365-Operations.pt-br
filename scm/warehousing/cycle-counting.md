---
title: "Contagem cíclica"
description: "Este artigo descreve como você pode usar a contagem cíclica com a solução de armazenamento disponível no Gerenciamento de depósito. Este artigo não se aplica à solução de armazenamento disponível no Gerenciamento de estoque."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 387d114936567fc471cdcafcb2e93c1704db7ead
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="cycle-counting"></a>Contagem cíclica

[!include[banner](../includes/banner.md)]


Este artigo descreve como você pode usar a contagem cíclica com a solução de armazenamento disponível no Gerenciamento de depósito. Este artigo não se aplica à solução de armazenamento disponível no Gerenciamento de estoque.

A contagem cíclica é um processo de depósito que você pode usar para auditar itens de estoque disponíveis. O processo de contagem cíclica pode ser descrito em três etapas:

1.  **Criar o trabalho de contagem cíclica** ─ o trabalho de contagem cíclica pode ser criado automaticamente com base nos parâmetros de limite para itens ou usando um plano de contagem cíclica. Como alternativa, você pode criar o trabalho de contagem cíclica manualmente usando os parâmetros do item ou do depósito na página **Trabalho de contagem cíclica por item** ou na página **Trabalho de contagem cíclica por local**.
2.  **Processar contagem cíclica** ─ após a criação do trabalho de contagem cíclica, você executa o trabalho de contagem cíclica contando os itens em um local de depósito e depois usando um dispositivo móvel para inserir o resultado no Microsoft Dynamics 365 for Operations. Como alternativa, você pode contar itens em um local de depósito sem criar o trabalho de contagem cíclica. Esse processo é conhecido como *contagem cíclica de ponto*.
3.  **Resolver uma diferença no valor contado do ciclo** ─ após uma contagem cíclica, todos os itens que possuem diferenças no valor contado terão um status do trabalho **Revisão pendente** na página **Todos os trabalhos**. Você pode resolver essas diferenças na página **Revisão de trabalho restante do ciclo de contagem**.

A ilustração a seguir mostra o processo de contagem cíclica. ![Fluxo de processo para contagem cíclica](./media/performcyclecountinginawarehouselocation.jpg)

## <a name="cycle-counting-prerequisites"></a>Pré-requisitos da contagem cíclica
A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes que você possa usar a contagem cíclica.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pré-requisito</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Item</td>
<td>O item deve ser habilitado para os processos de gerenciamento de depósito.</td>
</tr>
<tr class="even">
<td>Depósito</td>
<td>O depósito deve ser habilitado para os processos de gerenciamento de depósito. Para habilitar o depósito para processos de gerenciamento de depósito, na página <strong>Depósitos</strong>, selecione o depósito e selecione a opção <strong>Usar processos de gerenciamento de depósito</strong>. Para permitir que os funcionários movam paletes durante a contagem cíclica, na Guia Rápida <strong>Gerenciamento de depósito</strong>, marque a caixa de seleção <strong>Permitir movimentações de palete durante a contagem cíclica</strong>.</td>
</tr>
<tr class="odd">
<td>Pools de trabalho</td>
<td>Opcional: crie um grupo de trabalho para segregar o trabalho de depósito com base no tipo de trabalho (nesse caso, trabalho de contagem cíclica).</td>
</tr>
<tr class="even">
<td>Locais</td>
<td>Habilitar a contagem cíclica para localizações. Para habilitar a contagem cíclica para um local de depósito, na página <strong>Perfis de local</strong>, selecione a opção <strong>Permitir contagem cíclica</strong>.</td>
</tr>
<tr class="odd">
<td>Parâmetros de gerenciamento de depósito</td>
<td>Configurar parâmetros de contagem cíclica. Na página <strong>Parâmetros de gerenciamento de depósito</strong>, especifique o código padrão do tipo de ajuste, ID da classe de trabalho e a prioridade de trabalho da contagem cíclica.</td>
</tr>
<tr class="even">
<td>Dispositivo móvel</td>
<td><ul>
<li>Crie um item de menu para um dos seguintes métodos no formulário <strong>Itens de menu de dispositivo móvel</strong>:
<ul>
<li>Contagem cíclica direcionada ao usuário</li>
<li>Contagem cíclica direcionada ao sistema</li>
<li>Agrupamento de contagens cíclicas</li>
<li>Contagem cíclica pontual</li>
</ul>
</li>
<li>Configurar um menu para o dispositivo móvel.</li>
<li>Crie uma conta de usuário de trabalho e atribua um menu do dispositivo móvel para a ID do usuário de trabalho.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tarefa de configuração relacionada</td>
<td>Configure um plano de contagem cíclica para um local de depósito.</td>
</tr>
</tbody>
</table>

## <a name="automatically-create-cycle-counting-work"></a>Criar trabalho de contagem cíclica automaticamente
Há duas maneiras de agendar a criação recorrente de um trabalho de contagem cíclica: configurar limites de contagem cíclica ou configurar planos de contagem cíclica.

-   Um limite de contagem cíclica indica a quantidade ou o limite da porcentagem de itens de estoque. O trabalho de contagem cíclica é criado automaticamente quando o limite é atingido.
-   Um plano de contagem cíclica cria um trabalho de contagem cíclica de forma imediata ou periodicamente por meio de um trabalho em lotes. Quando o trabalho de contagem é criado, a linha de trabalho de contagem inclui informações sobre o local a ser contado. O estoque disponível associado a esse local não está bloqueado e, portanto, está disponível para a reserva e o processamento de saída mesmo que exista um trabalho de contagem aberto.

### <a name="create-cycle-counting-work-based-on-threshold-parameters-for-items"></a>Crie o trabalho de contagem cíclica com base nos parâmetros de limite para os itens

O trabalho de contagem cíclica pode ser criado quando o número de itens cai abaixo de um valor limite específico em um local. Por exemplo, há 60 itens em um local com um limite de contagem cíclica de 40. Durante uma transação de ordem de venda, 25 itens serão separados no local e colocados no local de preparo. Como a nova contagem de itens de 35 é menor do que a quantidade limite, o trabalho de contagem cíclica é criado automaticamente para o local.

### <a name="schedule-cycle-counting-work"></a>Agendar trabalho de contagem cíclica

Você pode agendar planos de contagem cíclica para criar um trabalho de contagem cíclica de forma imediata ou periódica. Ao configurar planos de contagem cíclica, você pode controlar o pool de trabalho para o qual o trabalho de contagem cíclica é criado, o número máximo de contagens de ciclos criados para itens em locais diferentes e o número de dias antes que um local de depósito seja contado novamente. Por exemplo, um item estará disponível em três locais no depósito, e o número máximo de contagens do ciclo é definido como **2**. Nesse caso, quando você executa o plano de contagem cíclica, duas contagens cíclicas são criadas para os dois locais onde o item está presente. Como outro exemplo, você define o número de dias entre as contagens cíclicas como **5**. Nesse caso, o trabalho de contagem cíclica é criado a cada cinco dias. No entanto, se o trabalho de contagem cíclica for processado no dia três, o trabalho seguinte de contagem cíclica será criado cinco dias após a última contagem cíclica tiver sido processada, no dia oito.

## <a name="create-cycle-counting-work-manually"></a>Criar o trabalho de contagem cíclica manualmente
Para criar manualmente o trabalho de contagem cíclica, você poderá usar a página **Trabalho de contagem cíclica por item** ou a **Trabalho de contagem cíclica por local**. Você pode especificar o número máximo de contagens cíclicas a serem criadas. Por exemplo, se o gerente de depósito especificar um valor **5**, o trabalho de contagem cíclica será criado para cinco locais mesmo que o item esteja presente em 10 locais. Você também pode selecionar uma ID de grupo de trabalho à qual as IDs de trabalho de contagem cíclica criadas são atribuídas. Quando uma ID de grupo de trabalho é processada para a contagem cíclica, as IDs de trabalho de contagem cíclicas atribuídas ao grupo de trabalho são processadas como um grupo.

## <a name="perform-a-cycle-count-by-using-a-mobile-device"></a>Executar uma contagem cíclica usando um dispositivo móvel
Há vários métodos para processar o trabalho de contagem cíclica usando o Dynamics 365 for Operations em um dispositivo móvel:

-   **Direcionado ao usuário** ─ o funcionário pode especificar uma ID de trabalho de contagem cíclica com o status **Aberto**.
-   **Direcionado ao sistema** ─ o Dynamics 365 for Operations atribui uma ID de trabalho de contagem cíclica ao trabalhador.
-   **Agrupamento de contagem cíclica** ─ o trabalhador pode agrupar as IDs de trabalho de contagem cíclica que são específicas de um local, zona, ou grupo de trabalho específico.
-   **Contagem cíclica de ponto** ─ o trabalhador pode contar itens em um local de depósito a qualquer momento, sem criar o trabalho de contagem cíclica. Para executar a contagem cíclica de ponto em um local, o trabalhador insere a ID do local.

O exemplo a seguir mostra como você pode executar a contagem cíclica de ponto usando um dispositivo móvel. As instruções que o trabalhador vê no dispositivo variam, dependendo da configuração do item de menu para a contagem cíclica de ponto.

1.  No dispositivo móvel, selecione o item de menu para processar o trabalho de contagem cíclica de ponto.
2.  Registre o local para o qual será executada a contagem cíclica de ponto.
3.  Registre e confirme o número do item e a quantidade contada do item. **Observação:** o status do trabalho de contagem cíclica é atualizado para **Revisão pendente** ou **Fechado** na página **Todos os trabalhos**, dependendo dos parâmetros definidos na página **Trabalhador**.
4.  Opcional: repita a etapa 3 para os outros itens no local e confirme se não há itens adicionais disponíveis para a contagem.

## <a name="resolve-cycle-counting-differences"></a>Resolver diferenças de contagem cíclica
Uma diferença de contagem cíclica ocorrerá nos cenários a seguir se a opção **É um supervisor de contagem cíclica** estiver definida como **Não** para uma ID de usuário de trabalho:

-   O valor contado não está nos limites de desvio especificados nos campos **Limite máximo da porcentagem** ou **Limite máximo da quantidade** na página **Usuários de trabalho**. Por exemplo, a quantidade de estoque disponível em um local é 50 e o limite de desvio para o usuário de trabalho é 10. Se o usuário de trabalho inserir um valor que não esteja entre 40 e 60, uma diferença ocorre.
-   O valor contado difere da quantidade de estoque disponível e não há limites de desvio definidos.

Você pode ajustar as diferenças no valor contado e aceitar o valor contado na página **Revisão de contagem de ciclo pendente** na página. Você pode verificar a contagem modificada da quantidade do item na página **Disponível por local**. O valor contado será rejeitado se a diferença não puder ser aprovada.

# <a name="see-also"></a>Consulte também
[Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md)




