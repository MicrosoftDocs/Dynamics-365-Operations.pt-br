---
title: Atualizações automáticas de remessas
description: Este artigo fornece uma visão geral da funcionalidade que permite atualizações automáticas de remessas.
author: Mirzaab
ms.date: 11/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable,SalesTableListPage,SalesTable,WHSWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e5816a7cddf509260511368b74655a9fd5bfc485
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067871"
---
# <a name="shipment-auto-updates"></a>Atualizações automáticas de remessas

[!include [banner](../includes/banner.md)]

A funcionalidade de atualização automática de remessas atualiza automaticamente quantidades (aumentos e reduções) em uma linha de carga que esteja associada a uma remessa depois que a carga foi liberada para um depósito. Essa funcionalidade continua ativada até que linha de carga na remessa ou carga seja processada em uma onda. Quando usada, as atualizações de ordens podem passar automaticamente para o depósito, sem precisar de intervenção manual, até que o trabalho do depósito seja criado.

Quando a funcionalidade de atualização automática de remessas não é usada, apenas as reduções de quantidade fluem automaticamente até que o trabalho do depósito seja criado. Os usuários devem atualizar ou excluir linhas manualmente e depois precisam liberar as linhas novamente, caso as quantidades da ordem aumentem ou sejam adicionadas novas linhas na ordem. Ao usar a funcionalidade de atualização automática de remessas, as empresas podem fornecer atualizações para o depósito continuamente, sem precisar se preocupar que as remessas e cargas relacionadas não refletirão as atualizações da linhas das ordens.

A funcionalidade de atualização automática de remessas aplica-se a linhas de ordens de venda e a linhas de ordens de transferência, e é ativada para um depósito específico. Portanto, as empresas podem aplicar políticas de atualização automática de remessas diferentes nos vários depósitos conforme necessário. Por padrão, a política de atualização automática de remessas para reduções de quantidade é aplicada a todos os depósitos que usam processos de gerenciamento de depósito (WMS). Quando essa configuração de política padrão é usada, apenas as reduções de quantidade fluem automaticamente até uma remessa e carga até que o trabalho do depósito seja criado. Esse comportamento é semelhante ao usado antes da introdução da funcionalidade de atualização automática de remessas.

## <a name="main-elements-of-the-functionality"></a>Principais elementos da funcionalidade

A funcionalidade de atualização automática de remessas recorre principalmente ao status da remessa para determinar se a quantidade em uma linha de carga deve ser alterada quando ocorre uma mudança em uma linha da ordem de venda ou da ordem de transferência. Ela também depende principalmente do status da remessa para determinar quando uma nova linha de carga deve ser adicionada automaticamente a uma carga existente. Quando o status da remessa **Na Onda** ou superior, não ocorre nenhuma atualização automática.

O status Na Onda também é considerado para atualizações automáticas. Quando a onda relacionada à linha de carga tem o status **Mantido**, **Executando**, **Liberado**, **Separado** ou **Remetido**, se um usuário tentar reduzir a quantidade em uma linha de carga (por meio de uma redução de quantidade na linha da ordem de venda ou na linha da ordem de transferência), a seguinte mensagem de erro será exibida: "As reservas não podem ser removidas porque há um trabalho criado com base nas reservas". Além disso, quando a onda tem um dos status de onda mencionados, se um usuário tentar aumentar indiretamente a quantidade da linha de carga aumentando a quantidade na linha da ordem de venda ou na linha da ordem de transferência, a quantidade na linha de carga não será aumentada automaticamente. Nesse caso, a linha de carga deverá ser atualizada manualmente.

## <a name="scenarios"></a>Cenários

A funcionalidade de atualização automática de remessas dá suporte a quatro cenários: adicionar uma nova linha da ordem, aumentar a quantidade em uma linha da ordem, reduzir a quantidade em uma linha da ordem e remover uma linha da ordem.

- **Adicionar uma nova linha da ordem** – Quando o campo **Atualização automática de remessas** na Guia Rápida **Depósito** da página **Depósitos** (**Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**) está definido como **Sempre**, se houver uma remessa para a ordem e for adicionada uma nova linha da ordem a uma ordem de venda ou ordem de transferência depois que já foi criada uma carga para a ordem de venda, a carga existente não será atualizada. Uma nova linha de carga que não tem nenhuma referência à carga existente é criada e associada à remessa existente. A nova linha é adicionada à carga e liberada.
- **Aumentar a quantidade em uma linha da ordem** – Quando o campo **Atualização automática de remessas** é definido como **Sempre**, se houver uma remessa para a ordem e a quantidade em uma linha da ordem de venda ou uma linha da ordem de transferência existente for aumentada depois que já foi criada uma carga para a ordem de venda, a linha de carga será aumentada com a mesma quantidade que a linha da ordem. Se a carga foi liberada, mas nenhum trabalho foi criado, a linha de carga é aumentada com a mesma quantidade da linha da ordem.
- **Reduzir a quantidade em um linha da ordem** – Quando o campo **Atualização automática de remessas** está definido como **Sempre** ou **Em redução de quantidade**, se houver uma remessa para a ordem e a quantidade em uma linha da ordem de venda ou uma linha da ordem de transferência existente for reduzida depois que já foi criada uma carga para a ordem de venda, a quantidade na linha de carga associada será atualizada de modo correspondente, a menos que a quantidade naquela linha de carga já seja igual ou menor que a nova quantidade na linha da ordem. Nesse caso, a linha de carga não é afetada. Se a carga foi liberada, mas nenhum trabalho foi criado, a quantidade na linha de carga associada é atualizada de modo correspondente, a menos que a quantidade na linha de carga já seja igual ou menor que a nova quantidade na linha da ordem. Nesse caso, a linha de carga é afetada.
- **Remover uma linha da ordem** – Quando o campo **Atualização automática de remessas** está definido como **Sempre** ou **Em redução de quantidade**, se o usuário tentar remover uma linha da ordem para a qual existe uma linha de carga, será mostrada uma mensagem de erro.

## <a name="example-scenario"></a>Cenário de exemplo

Para este cenário, você deve ter os dados de demonstração instalados e deve usar a empresa de dados de demonstração **USMF**.

### <a name="turn-on-the-auto-update-shipment-functionality"></a>Ativar a funcionalidade de atualização automática de remessas

Para ativar a funcionalidade de atualização automática de remessas, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
2. Selecione o depósito **24**.
3. Na Guia Rápida **Depósito**, no campo **Atualização automática de remessas**, altere o valor de **Em redução de quantidade** para **Sempre**.

Depois de alterar o valor para **Sempre**, qualquer aumento ou redução nas quantidades das linhas da ordem de venda e das linhas da ordem de transferência, assim como todas as adições de novas linhas, refletem-se nas remessas e cargas do depósito selecionado, considerando as restrições de atualização mencionadas anteriormente.

### <a name="change-the-wave-template-so-that-load-lines-arent-automatically-processed"></a>Alterar o modelo de onda de forma que as linhas de carga não sejam processadas automaticamente

Para configurar o modelo da onda de modo que ele não processe as linhas de carga automaticamente, siga essas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
2. Selecione o modelo de onda **Padrão de remessa 24**.
3. Selecione **Editar**.
4. Na Guia Rápida **Geral**, defina a opção **Automatizar criação da onda** como **Sim** e verifique se todas as outras opções estão definidas como **Não**.

É importante que nenhum trabalho seja criado e liberada automaticamente como parte do processo de criação da onda. Depois que é criado o trabalho relacionada à linha de carga que foi criada para a linha da ordem de venda, a linha de carga não será mais atualizada automaticamente se a quantidade na linha da ordem de venda for alterada.

### <a name="create-a-sales-order"></a>Criar uma ordem de venda

Para criar uma ordem de venda, siga estas etapas.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
2. Selecione o cliente **US-003**.
3. Crie uma linha para o número de item **A0001**.
4. Insira a quantidade **10**. (Verifique se você está usando o depósito **24**.)
5. Selecione **Salvar**.
6. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**. Uma remessa e uma onda são criadas.

Como você alterou o modelo de onda no procedimento anterior, nenhuma carga ou trabalho são criados. O status da remessa é **Aberta**, e o status da onda é **Criado**.

### <a name="decrease-the-quantity-on-a-sales-order-line"></a>Reduzir a quantidade em uma linha da ordem de venda

Para reduzir a quantidade em uma linha da ordem de venda, siga estas etapas.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
2. Selecione a ordem de venda que você acabou de liberar para o depósito.
3. Selecione a linha da ordem de venda. No campo **Quantidade**, altere o valor de **10** para **8**.
4. Na linha da ordem de venda, selecione **Depósito \> Detalhes da remessa**. Na página **Detalhes da remessa**, na Guia Rápida **Linhas de carga**, a quantidade reflete a alteração na linha da ordem de venda.

### <a name="increase-the-quantity-on-a-sales-order-line"></a>Aumentar a quantidade em uma linha da ordem de venda

Para aumentar a quantidade em uma linha da ordem de venda, siga estas etapas.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
2. Selecione a ordem de venda que você já liberou para o depósito.
3. Altere a quantidade da linha de **8** para **12**.
4. Selecione **Salvar**.
5. Volte à página **Todas as ordens de venda** e selecione a ordem de venda novamente.
5. No Painel de Ação, na guia **Depósito**, no grupo **Informações relacionadas**, selecione **Detalhes da remessa**. Na página **Detalhes da remessa**, na Guia Rápida **Linhas de carga**, a quantidade reflete a alteração na linha da ordem de venda.

Embora a quantidade na linha de carga tenha aumentado de 8 para 12, apenas oito itens permanecem reservados, a menos que a reserva automática seja ativada. Como a quantidade que foi adicionada à remessa existente não foi reservada, se a onda for processada neste momento, sem reserva, o trabalho será criado somente para a quantidade que já foi reservada.

> [!NOTE]
> Quando a quantidade em uma linha da ordem é reduzida, a quantidade na linha de carga não será afetada, se ele já for igual ou menor que a nova quantidade na linha da ordem. Quando a quantidade em uma linha da ordem é aumentada, a linha de carga aumenta com a mesma quantidade que a linha da ordem. Se a quantidade na linha da ordem for diferente da quantidade na linha de carga, a diferença permanecerá.

### <a name="add-a-sales-order-line"></a>Adicionar uma linha da ordem de venda

Para adicionar uma linha da ordem de venda, siga estas etapas.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
2. Selecione a ordem de venda que você já liberou para o depósito.
3. Crie uma linha para o número de item **A0002**.
4. No campo **Quantidade**, insira **10**. (Verifique se você está usando o depósito **24**.) A nova linha é adicionada automaticamente à remessa existente.
5. Selecione **Salvar**.
6. Volte à página **Todas as ordens de venda** e selecione a ordem de venda novamente.
7. No Painel de Ação, na guia **Depósito**, no grupo **Informações relacionadas**, selecione **Detalhes da remessa**. Na página **Detalhes da remessa**, na Guia Rápida **Linhas de carga**, observe a segunda linha de carga.

Como a linha da ordem de venda que você acabou de adicionar à remessa existente não foi reservada, se a onda for processada neste momento, o trabalho será criado apenas para a quantidade na primeira linha da ordem de venda e na primeira linha de carga.

### <a name="process-a-wave"></a>Processar uma onda

Para processar a onda, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
2. Selecione a onda que você já criou.
3. No Painel de Ação, na guia **Onda**, no grupo **Onda**, selecione **Processar**.

A onda é processada e cria o trabalho para as quantidades reservadas nas linhas de carga. O status da remessa é atualizado de **Aberto** para **Na Onda**. Conforme o status da remessa é atualizado para **Na Onda**, todas as alterações que ocorrerem, como reduções ou aumentos nas quantidades das linhas ou adições de novas linhas à ordem de venda, não afetam as linhas de carga existentes associadas à remessa na onda.

Se uma remessa tem o status **Na Onda** ou superior, as atualizações de quantidade em uma linha da ordem de venda não se refletem nem são confirmadas em uma linha de carga associada à remessa. As alterações de quantidade em uma linha de carga devem ser feitas diretamente na linha de carga.

A validação é realizada depois que o trabalho para a linha de carga é criado e uma reserva é feita. Uma redução da quantidade na linha da ordem de venda é então confirmada na reserva de linha de trabalho.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]