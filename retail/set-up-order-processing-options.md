---
title: "Configurar opções de processamento da ordem"
description: "Este tópico fornece informações sobre como processar ordens referentes call center usando o Microsoft Dynamics 365 para operações de varejo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: eb62073fdfa50576d2c613594f3d85cbc0b322f6
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-order-processing-options"></a>Configurar opções de processamento da ordem

Este tópico fornece informações sobre como processar ordens referentes call center usando o Microsoft Dynamics 365 para operações de varejo. 

Varejo e comércio em dynamics 365 para canais de varejo de operações oferece suporte, como lojas online, armazenamentos físicas e almofariz, call center. Em call centers, os trabalhadores pegam ordens de cliente pelo telefone e criam ordens de venda. Este tópico descreve como criar um call center e configurar opções de call center. Cada call center pode ter seus próprios usuários, métodos de pagamento, grupos de preços, dimensões financeiras e modos de entrega. Você pode configurar essas opções ao criar o call center. **Importante:** para que os fluxos de trabalho do call center sejam usados quando o usuário atual do Dynamics AX criar ordens de venda, o usuário deverá ser atribuído ao call center como um usuário de call center. Você pode usar a página **Call center** para habilitar ou desabilitar grupos de recursos exclusivos de call centers. Os seguintes grupos de recursos podem ser habilitados:

-   **Conclusão da ordem** – Este grupo inclui recursos relativos a pagamentos e conclusão de ordens na página **Ordem de venda**.
-   **Venda direta** – Este grupo inclui recursos relativos aos códigos fonte, scripts e solicitações de catálogo.

Quando você habilitar esses recursos nas configurações do call center, eles serão disponibilizados na página **Ordem de venda** dos usuários associados ao call center. A maioria desses recursos exige configuração adicional antes que eles possam ser usados. As imagens e os scripts são habilitados como parte da configuração de venda direcionada do call center específico. Se esse recurso estiver habilitado, os scripts e as imagens de produto serão exibidos no painel Quadro de Fatos da página **Ordem de venda**. A imagem padrão que é definida para um produto é exibida. Os scripts podem ser configurados para um item, um catálogo, um cliente ou um item no contexto de um catálogo. As ordens do call center podem mostrar detalhes adicionais sobre como o preço de uma linha de ordem específica foi derivado. Por exemplo, as ordens mostram quais descontos foram aplicados. Habilite essa funcionalidade ** contas a receber em ** &gt; ** de instalação ** &gt; ** parâmetros de contas a receber ** &gt; ** preços ** &gt; ** ** detalhes de preço. Você pode acessar a página **Detalhes de preço** na lista suspensa **Linha da ordem de venda**. Você pode usar o rastreamento de evento de ordem para fins de auditoria, a fim de analisar as ações tomadas em uma ordem durante o ciclo de vida da ordem ou rastrear as ações de um usuário específico. Por exemplo, você pode registrar a ação todas as vezes que um usuário criar uma ordem de venda, colocar uma ordem em espera, substituir um encargo ou atualizar uma linha de ordem. Você pode configurar eventos de ordem para rastrear ações de usuários específicos, de grupos de usuários ou de todos os usuários durante um período. Você pode exibir as ações que foram executadas em um documento abrindo a página **Eventos da ordem** no Painel de Ação da página desse documento. Você pode configurar eventos ** ordem de vendas e marketing ** &gt; ** em de instalação ** &gt; ** eventos ** &gt; ** eventos ** de ordem. Quando a ordem de um cliente não pode ser enviada em tempo, uma empresa pode enviar automaticamente mensagens de email de notificação ao cliente para explicar o status da ordem e dar ao cliente a oportunidade de cancelar a ordem. Se o atraso se estender além de um limite especificado, a ordem pode ser cancelada automaticamente. Até três mensagens de email poderão ser enviadas em intervalos especificados:

1.  **Primeiro aviso de cancelamento** – o cliente pode decidir cancelar a ordem.
2.  **Segundo aviso de cancelamento** – O cliente pode cancelar a ordem.
3.  **Aviso final de cancelamento** – O sistema cancela a ordem e o cliente é informado do cancelamento.

Você pode isentar clientes individuais e produtos do processo de notificação automática e cancelamento. Um alerta de margem é acionado ao adicionar um item a uma ordem. O alerta contém informações importantes sobre o item, como lucratividade do item e margem de preço. Você pode usar essas informações para decidir se uma definição de preço é recomendável ao adicionar um item à ordem de venda. Por exemplo, você pode configurar limites para as margens comerciais a fim de especificar que um limite de 40% ou mais acima do custo é aceitável para um item, mas um limite de 20% a 39% acima do custo é questionável. Nesse caso, qualquer item com um limite entre 20% e 39% dispara um aviso. Qualquer item com um limite inferior a 20% acima do custo não pode ser vendido, e o preço do item não pode ser ajustado. Você pode configurar alertas margem ** contas a receber em ** &gt; ** de instalação ** &gt; ** parâmetros de contas a receber ** &gt; ** alertas margem **. Quando você configura a atribuição de imposto com base nas regras padrão, é possível determinar uma prioridade correspondente para os elementos do endereço. Por exemplo, é possível especificar que a correspondência de um grupo de impostos por código postal ou CEP tenha uma prioridade mais alta do que a correspondência de um grupo de impostos por estado. À medida que você insere novos registros de endereço de cliente, o grupo de impostos é atribuído automaticamente, com base em como o endereço do cliente corresponde às regras padrão e à prioridade definida. Você pode configurar essa funcionalidade na página **Parâmetros da contabilidade**.


