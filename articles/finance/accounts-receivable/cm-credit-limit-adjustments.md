---
title: Ajustes do limite de crédito
description: Este tópico explica como configurar e adicionar ajustes de limite de crédito.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9b236f489fa2045bdff05f76fadbeacc2f9ed2f4
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124199"
---
# <a name="credit-limit-adjustments"></a>Ajustes do limite de crédito 

[!include [banner](../includes/banner.md)]

Os ajustes de limite de crédito permitem que os gerentes de crédito atualizem os limites de crédito e as datas de vencimento de um único cliente, de um grupo de clientes ou de todos os clientes por meio de um processo de lançamento. Você pode adicionar entradas de ajuste de limite de crédito para atualizar clientes e grupos de crédito de clientes ou pode usá-las para calcular limites de crédito automáticos. As entradas podem ser revisadas, enviadas para aprovação por meio de um fluxo de trabalho e lançadas em contas de cliente.

## <a name="set-up-credit-limit-adjustments"></a>Configurar ajustes de limite de crédito

Você pode criar entradas no diário de ajustes de limite de crédito na página **Ajustes de limite de crédito** (**Gerenciamento de crédito \> Ajustes de limite de crédito \> Ajustes de limite de crédito**).

1. Selecione **Novo**. É criado um novo grupo de entradas que tem um número de ajuste de limite de crédito.
2. Selecione o tipo de ajuste de limite de crédito:

    - Selecione **Limite de crédito** para alterar o limite de crédito do cliente.
    - Selecione **Limite de crédito temporário** para criar um limite de crédito temporário em vez de alterar o limite atual de crédito do cliente. Os limites de crédito temporários substituem o limite de crédito de um cliente por um período definido. Depois que o período terminar, o limite de crédito do cliente será usado de novo.
3. Insira uma descrição. 

Se a caixa de seleção **Lançado** estiver marcada, os limites de crédito foram aplicados. O campo **Status de aprovação** indica o status do fluxo de trabalho do diário. Um fluxo de trabalho é opcional.

### <a name="add-credit-limit-adjustments"></a>Adicionar ajustes de limite de crédito

Para adicionar ajustes de limite de crédito manualmente, selecione **Linhas** e siga estas etapas.

1. Para adicionar um ajuste de limite de crédito para um cliente, use o menu **Ajustes do cliente**. Para adicionar um limite de crédito a um grupo de crédito de cliente, selecione **Ajustes de grupo de crédito de cliente**.
2. Insira uma conta de cliente para a conta do cliente da fatura que deve ser atualizada com o novo limite de crédito. Se você selecionou **Ajustes de grupo de crédito de cliente** na etapa 1, insira o grupo de crédito de cliente. Não é possível inserir uma conta de cliente e uma ID de grupo de crédito de cliente na mesma linha do diário.

    O limite de crédito atual é mostrado, e o nome é exibido automaticamente.

3. Insira o novo limite de crédito que deverá substituir o atual quando a entrada de limite de crédito for lançada.
4. Insira uma data para definir a nova data de vencimento do limite de crédito do cliente. Você deve inserir uma data de vencimento de limite de crédito ao criar um ajuste de limite de crédito.

O campo **Status de aprovação** indica o status do fluxo de trabalho da linha do diário.

Se quiser que os ajustes de limite de crédito sejam gerados automaticamente, você pode usar o menu **Gerar** no Painel de Ação.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Adicionar ajustes de limite de crédito temporários

Para adicionar ajustes de limite de crédito temporários manualmente, siga estas etapas para as linhas de diário.

1. Para adicionar um ajuste de limite de crédito para um cliente, use o menu **Ajustes do cliente**. Para adicionar um limite de crédito a um grupo de crédito de cliente, selecione **Ajustes de grupo de crédito de cliente**.
2. Insira uma conta de cliente para a conta do cliente da fatura que deve ser atualizada com o novo limite de crédito. Se você selecionou **Ajustes de grupo de crédito de cliente** na etapa 1, insira o grupo de crédito de cliente. Não é possível inserir uma conta de cliente e uma ID de grupo de crédito de cliente na mesma linha do diário.

    Se já existir um limite de crédito temporário ativo ou futuro, serão exibidos o limite de crédito temporário atual e os intervalos de datas de cada limite de crédito temporário. O nome é exibido automaticamente.

3. Insira o novo limite de crédito que deve substituir o atual.
4. Nos campos **Nova data inicial** e **Nova data final**, defina o período em que o limite de crédito avançado é válido. Você deve inserir as datas de vencimento do limite de crédito ao criar um diário de ajuste de limite de crédito.

O campo **Status de aprovação** indica o status do fluxo de trabalho da linha do diário.

## <a name="generate-credit-limit-adjustments"></a>Gerar ajustes do limite de crédito

Os limites de crédito também podem ser ajustados de maneira automática. No Painel de Ação, selecione **Gerar** e, depois, escolha uma das seguintes opções:

- De cliente existente
- De grupo de crédito de cliente existente
- Limites de crédito automático

### <a name="from-existing-customer"></a>De cliente existente

Você pode criar linhas de diário a partir de clientes existentes. Quando você seleciona **Gerar \> De cliente existente**, é exibida uma caixa de diálogo onde é possível especificar critérios para selecionar clientes e calcular os novos limites.

1. Insira um valor de ajuste para adicionar ou subtrair um valor do limite de crédito. Insira um valor negativo para diminuir o limite de crédito atual ou um valor positivo para aumentá-lo.
2. No campo **Tipo de valor**, selecione como o valor inserido na etapa 1 deve ser usado para calcular o novo limite de crédito:

    - Selecione **Valor Fixo** para alterar o limite de crédito por um valor.
    - Selecione **Porcentagem** para alterar o limite de crédito por uma porcentagem.

3. Insira um valor usado para arredondar o limite de crédito calculado. Por exemplo, insira **10,00** para arredondar o limite de crédito para as unidades monetárias mais próximas de 10,00.
4. Defina o campo **Forma de arredondamento** para especificar se o restante deve ser arredondado para cima ou para baixo.
5. Selecione o método usado para ajustar datas.

    - Se você selecionar **Absoluto**, poderá inserir datas que definam o intervalo de datas para os limites de crédito.
    - Se selecionar **Relativo**, poderá inserir datas de compensação para o intervalo. O intervalo de datas atual do limite de crédito será ajustado pela compensação.

6. Use a FastTab **Registros a serem incluídos** para filtrar a lista de clientes incluídos. Se você não incluir filtros, entradas de limite de crédito serão geradas para todos os clientes.
7. Selecione **OK** para criar as entradas de ajuste de limite de crédito.

### <a name="from-existing-customer-credit-group"></a>De grupo de crédito de cliente existente

Você pode criar linhas de diário a partir de grupos de crédito de cliente existentes. Quando você seleciona **Gerar \> De grupo de crédito de cliente existente**, é exibida uma caixa de diálogo onde é possível especificar critérios para selecionar grupos de crédito de cliente e calcular os novos limites. Os critérios são os mesmos usados para criar linhas de diário a partir de clientes existentes. Consulte as etapas da seção anterior.

### <a name="automatic-credit-limits"></a>Limites de crédito automático

Você pode criar limites de crédito automáticos para definir e atualizar limites de crédito do cliente. Os limites de crédito automáticos são criados para um grupo de risco e são baseados em valores específicos usados nos grupos de pontuação. Você pode usar esses limites de crédito automáticos para gerar entradas de limite de crédito. Se um cliente tiver sido atribuído a um grupo de risco específico, e as informações de crédito do cliente corresponderem aos critérios de um limite de crédito automático, será criada uma entrada de ajuste de limite de crédito.

#### <a name="create-automatic-credit-limits"></a>Criar limites de crédito automáticos

Você cria limites de crédito automáticos usando ajustes de limite de crédito. Quando você seleciona **Gerar \> Limites de crédito automáticos**, é exibida uma caixa de diálogo onde é possível definir uma data de vencimento para os novos limites de crédito que serão criados com base nos grupos de risco aos quais os clientes estão atribuídos. Quando terminar, selecione **OK** para criar as linhas de ajuste de limite de crédito.

### <a name="post-adjustments"></a>Lançar ajustes

Depois de criar linhas de ajuste de limite de crédito, você pode usar o botão **Lançar** do Painel de Ação para lançar as entradas e atualizar os limites de crédito do cliente. No entanto, se tiver configurado um fluxo de trabalho, você deverá selecionar **Fluxo de Trabalho \> Enviar** no Painel de Ação para enviar o diário para aprovação.

### <a name="credit-limit-adjustments-workflows"></a>Fluxos de trabalho de ajustes de limite de crédito

Os fluxos de trabalho **Ajustes de limite de crédito** podem ser usados para enviar ajustes de limite de crédito através de um processo de aprovação de fluxo de trabalho. É possível criar dois fluxos de trabalho na página **Fluxo de trabalho de gerenciamento de crédito** (**Gerenciamento de crédito \> Configuração \> Fluxo de trabalho de gerenciamento de crédito**):

- **Ajustes de limite de crédito** – Este fluxo de trabalho pode ser usado para aprovar entradas no nível de cabeçalho.
- **Linha de ajustes de limite de crédito** – Este fluxo de trabalho pode ser usado para aprovar as entradas de ajuste para que possam ser aprovadas por pessoas diferentes com base nos critérios do fluxo de trabalho.

> [!NOTE]
> Ao criar o fluxo de trabalho **Ajustes de limite de crédito**, você pode configurá-lo para que os ajustes sejam lançados automaticamente depois que as linhas forem aprovadas. Basta incluir a tarefa **Lançar Diário automaticamente** no fluxo de trabalho.
