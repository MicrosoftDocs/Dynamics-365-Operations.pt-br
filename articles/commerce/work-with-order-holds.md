---
title: Configurar e trabalhar com bloqueios de ordem do call center
description: Este tópico descreve como trabalhar com bloqueios em ordens usando o Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 08c0eda418af1aa56c6cc71ca1f7f10460651bc9
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021581"
---
# <a name="configure-and-work-with-call-center-order-holds"></a>Configurar e trabalhar com bloqueios de ordem do call center

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos de bloqueio de ordem do Dynamics 365 Commerce para ordens do call center.

## <a name="configuring-call-center-order-holds"></a>Como configurar bloqueios de ordem do call center

Para usar os recursos de bloqueio de ordem do call center, primeiro defina códigos de bloqueio. Para criar um conjunto de códigos de bloqueio definidos pelo usuário, com base nas suas necessidades comerciais, vá para **Vendas e marketing** \> **Configuração** \> **Ordens de venda** \> **Códigos de bloqueio de ordem**. Opcionalmente, você pode sinalizar um dos códigos de bloqueio como o código de retenção padrão, definindo a opção **Padrão da ordem de venda** como **Sim** para ele. Esse código de bloqueio será usado a qualquer momento em que uma ordem de venda for colocada em espera. Se uma ordem de venda tiver reservado o estoque e as reservas precisarem ser removidas automaticamente se a ordem for colocada em espera por um motivo específico, defina a opção **Remover reservas de estoque** como **Sim** para os códigos de motivo.

Para especificar o tipo de nota que será capturado quando usuários que colocam uma ordem de venda em espera inserirem notas opcionais, vá para **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber** e, na Guia Rápida **Configuração de vendas**, na guia **Geral**, defina o campo **Tipo de nota**. Use o campo **Status da ordem de venda Em Espera** para definir a cor que será usada para realçar ordens de venda que estão em espera quando são exibidas na página **Atendimento ao cliente**.

Para criar um conjunto opcional de códigos de motivo de bloqueio, vá para **Varejo e Comércio** \> **Configuração de canal** \> **Códigos informativos**. Esses códigos informativos podem ser usados como um código de motivo secundário para definir mais o código de bloqueio principal. Selecione **Novo** para criar um conjunto de códigos de motivo e selecione **Subcódigos** para definir a lista de motivos adicionais. Para vincular os códigos informativos que você definir para o canal de call center, vá para **Varejo e Comércio** \> **Canais** \> **Call centers** \> **Todos os call centers**. Na Guia Rápida **Geral**, defina o campo **Código de bloqueio**.

## <a name="putting-orders-on-hold"></a>Como colocar ordens em espera

As ordens criadas por usuários de call center no back office do Commerce podem ser colocadas em espera, de forma manual ou automática, em situações específicas.

Durante a entrada da ordem, mas antes do envio e da confirmação da ordem, os usuários de call center podem colocar manualmente uma ordem em espera para impedir que ela seja liberada para o depósito para processamento. Por exemplo, o cliente que está inserindo a ordem pode não estar pronto para confirmá-la. Ou podem estar faltando dados críticos necessários na ordem para processá-la.

Na página de entrada da ordem, o usuário de call center pode colocar uma ordem em espera usando a opção **Bloqueios de ordem** na guia **Ordem de venda** do menu de entrada da ordem. Outra opção é o usuário selecionar o item de menu **Bloqueio** na página **Resumo da ordem de venda** que aparece quando ele seleciona **Concluir** em uma ordem de venda de call center.

Em ambos os casos, a página **Bloqueios da ordem** aparecerá. O usuário pode selecionar **Novo** para criar um bloqueio para a ordem. No campo **Código de bloqueio**, o usuário deve selecionar o código que melhor descreva o motivo do bloqueio. No campo **Código de motivo**, o usuário também pode selecionar um código adicional para fornecer um segundo nível de descrição do bloqueio.

Na Guia Rápida **Notas**, no campo **Notas de bloqueio**, o usuário pode inserir notas adicionais, livres para fornecer o contexto ou informações adicionais sobre o bloqueio. Essas notas podem ajudar outros usuários que examinarão ou trabalharão com a ordem de bloqueio posteriormente.

Depois que as informações de bloqueio forem inseridas e salvas, o usuário poderá fechar a página **Bloqueios de ordem**. O usuário será retornado à página de entrada da ordem de venda. Se nenhuma ação adicional for necessária na ordem de venda, o usuário poderá fechar a página de entrada da ordem de venda.

Se o sinalizador **Habilitar conclusão de ordem** for ativado no canal de call center, o pagamento não precisará ser aplicado a uma ordem que foi colocada em espera. Em contraste, para uma ordem de venda que não esteja em espera, os usuários não poderão sair da página de entrada de ordem de venda até que o pagamento seja aplicado. É claro que o pagamento deverá ser efetuado antes da liberação do bloqueio da ordem.

Além disso, os usuários de call center podem bloquear manualmente ordens suspeitas de fraude por algum motivo. As ordens também podem ser colocadas em espera automaticamente quando correspondem a critérios e regras de fraude. Para saber mais sobre esse tipo de bloqueio de ordem, consulte [Configurar alertas de fraude](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Como exibir e gerenciar ordens que estão em espera

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Como exibir informações de bloqueio para uma única ordem de venda

Na página **Atendimento ao cliente**, os usuários podem identificar visualmente ordens que estão em espera, pois as linhas de ordem são realçadas em uma cor específica. Essa cor é definida pelo campo **Status da ordem de venda Em Espera** na página **Parâmetros de contas a receber** .

> [!NOTE]
> Se a linha for selecionada na página, a cor de destaque não estará visível.

Os usuários também podem exibir informações detalhadas de status de uma ordem de venda para saber se a ordem está em espera. As informações detalhadas de status podem ser acessadas na página **Todas as ordens de venda** ou **Atendimento ao cliente**. Se uma ordem estiver em espera, o sinalizador **Não processar** será definido para ela e o campo **Status detalhado** mostrará um status **Em Espera** ou **Bloqueio de fraude**, dependendo do cenário.

Para exibir os detalhes de um bloqueio de ordem individual, os usuários podem abrir uma exibição detalhada da página **Bloqueio da ordem** na página **Atendimento ao cliente**, usando o menu **Opções** da ordem selecionada. Os usuários também podem acessar essa exibição na página **Todas as ordens de venda**, selecionando o item de menu **Bloqueios de ordem** na guia **Ordem de venda**.

### <a name="viewing-all-orders-that-are-on-hold"></a>Como exibir todas ordens que estão em espera

Para exibir todas as ordens que foram colocadas em espera de forma manual ou automática, vá para **Varejo e Comércio** \> **Clientes** \> **Bloqueios de ordem**.

A bancada **Bloqueios de ordem** fornece uma exibição de lista de todas as ordens que estão em espera devido a ações de bloqueio manual ou relativo a fraudes. Aproveitando as opções padrão de filtragem e classificação na página, os usuários podem criar exibições que permitam gerenciar ou trabalhar com códigos de bloqueio específicos cuja revisão esteja sob sua responsabilidade. A bancada **Bloqueios de ordem** também indica o número de dias em que uma ordem está em espera. Essas informações podem ajudar os usuários a priorizarem a fila.

Para obter uma exibição mais detalhada das ordens que estão em espera, os usuários podem clicar na opção **Bloqueio de ordem** no menu. Essa exibição que fornece informações sobre o cliente, notas que foram aplicadas à ordem, o cliente ou a ação de bloqueio. A exibição também fornece detalhes sobre o motivo de um bloqueio automático, se a ordem foi colocada em espera pois correspondia a uma regra de fraude.

Nos modos de exibição de lista e detalhado da página **Bloqueios de ordem**, os usuários podem exibir ou editar informações adicionais relativas à ordem, como pagamentos, totais e notas.

As opções na guia **Bloquear finalização da compra** podem ser úteis se vários usuários da empresa trabalham na fila de bloqueio ao mesmo tempo. Ao selecionarem a opção **Check-out**, os usuários podem indicar que estão trabalhando para examinar e investigar o bloqueio da ordem. Assim, outros usuários não perdem tempo tentando executar o mesmo trabalho. Na exibição detalhada da página **Bloqueios de ordem**, os usuários podem exibir informações sobre a data e a hora de check-out e sobre o usuário que efetuou o check-out do registro de bloqueio.

Após o check-out de um registro de bloqueio, somente o usuário que efetuou o check-out poderá desmarcar o check-out. Essa restrição visa prevenir que usuários utilizem registros em que outros usuários já estejam trabalhando. Para liberar uma ordem para retornar à fila para que outros usuários possam trabalhar nela, o usuário que efetuou o check-out do registro seleciona a opção **Liberar check-out**.

> [!NOTE]
> O bloqueio não é liberado quando o check-out é desmarcado.

Em algumas situações, por exemplo, quando um usuário fica doente ou sai da empresa, os registros com check-out para esse usuário talvez precisem ser reatribuídos a outro usuário. Um gerente pode reatribuir registros usando a opção **Substituir check-out**.

## <a name="releasing-orders-that-are-on-hold"></a>Como liberar ordens que estão em espera

Nas exibições de lista e detalhada na exibição da página **Bloqueios de ordem**, a guia **Liberar bloqueio** contém as opções usadas para liberar um bloqueio de ordem. Use a opção **Liberar bloqueios** para liberar uma ordem do código de bloqueio selecionado.

As ordens de call center exigem o pagamento. Portanto, um bloqueio não poderá ser totalmente liberado se o pagamento não tiver sido aplicado à ordem. Na página **Parâmetros de call center**, na guia **Bloqueios**, verifique se o parâmetro **Enviar quando liberado** está ativado. Essa configuração ajuda a garantir que uma ordem de bloqueio liberado passe pela lógica correta de envio da ordem para validar e autorizar pagamentos. Se houver pagamentos ausentes, o usuário receberá um erro e o código de bloqueio não será limpo.

Se o parâmetro **Enviar quando liberado** não estiver definido, os usuários deverão selecionar a opção **Liberar e enviar** no menu **Liberar bloqueio** para ajudar a garantir que a ordem passe por todas as validações de pagamento necessárias. Se houver falha no envio da ordem quando o sinalizador **Habilitar conclusão de ordem** for ativado no canal de call center, a ordem será liberada do status de bloqueio, mas o sinalizador **Não processar** permanecerá definido. Então, a ordem não será liberada para o depósito até que os pagamentos corretos sejam aplicados e validados.

Se os usuários quiserem liberar um bloqueio, mas fazer alterações adicionais na ordem antes de liberá-la para processamento, eles poderão selecionar a opção **Liberar e modificar**. Essa opção remove o código de bloqueio e abre detalhes da ordem de venda para que os usuários possam fazer alterações adicionais na ordem. Os usuários também poderão aplicar o pagamento e enviar a ordem de venda por meio da lógica de validação do pagamento quando o sinalizador **Habilitar conclusão de ordem** estiver ativado no canal de call center.

## <a name="reporting-options"></a>Opções de relatório

Vá para **Varejo e Comércio** \> **Consultas e relatórios** \> **Relatórios de call center** \> **Relatório de bloqueios de ordem** para executar um relatório sobre os bloqueios de ordem por intervalo de datas, código de bloqueio ou outros critérios relacionados.
