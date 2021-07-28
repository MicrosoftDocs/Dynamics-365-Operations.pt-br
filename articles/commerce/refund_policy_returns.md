---
title: Criar e atualizar uma política de devolução e reembolso para um canal
description: Este tópico explica como configurar uma política de devoluções e reembolsos para um canal.
author: ShalabhjainMSFT
ms.date: 07/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 6cb2bb77a62ee9fc2ea6115949e30496bf3365c4
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345099"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Criar e atualizar uma política de devolução e reembolso para um canal

[!include [banner](includes/banner.md)]

A política de devolução de canal no Dynamics 365 Commerce permite que os varejistas definam os encargos nos quais os meios de pagamento possam ser permitidos para processar uma devolução em um dispositivo de ponto de venda (PDV).  

Este tópico descreve as etapas para configurar uma política de devoluções e reembolsos para um canal.

No momento, o escopo da política está limitado à definição de meios de pagamento que possam ser permitidos para um canal. A lista "permitido" baseia-se nos métodos de pagamento usados para fazer a compra. Por exemplo:

- Se uma compra tiver sido feita com o uso de um vale-presente, a política da loja será processar os reembolsos apenas para um novo vale-presente ou para conceder crédito da loja. 
- Se uma venda é feita em dinheiro, as opções permitidas para reembolso são dinheiro, vale-presente e conta do cliente, mas não cartão de crédito. 

## <a name="enable-return-policy"></a>Habilitar política de devolução

Para habilitar a funcionalidade de política de devolução de canais, faça o seguinte:

1. Vá para o espaço de trabalho **Gerenciamento de Recursos** no Dynamics 365 Commerce.
1. Procure o recurso **Habilitar políticas de devolução de canal** na lista de nomes de recursos.
1. Selecione **Habilitar agora**.
1. Na página **Agendamento de distribuição**, execute o trabalho de **1110** (configuração global) para distribuir a alteração do recurso. 

## <a name="configure-return-policy"></a>Configurar política de devolução

Siga estas etapas para configurar uma política de devolução para uma loja de varejo ou canal de varejo online.

1. Vá para **Retail e Commerce** \> **Configuração do Canal** \> **Devoluções** \> **Política de devolução de canais**.

1. Selecionar **Novo** para criar um novo modelo de política de devolução. Para usar um modelo existente, selecione o modelo no painel esquerdo. Para novos modelos, adicione um nome e uma descrição que o ajudarão a identificar a política quando ela estiver sendo aplicada ao canal.

   ![Adicionar nova política de devolução.](media/Return-policy-page1.png)
     
   
1. Na seção **Métodos de pagamento de reembolso permitidos**, defina meios de pagamento de devolução **Permitidos** que sejam específicos de cada método de pagamento.
   ![Definir métodos de pagamento permitidos por tipo de pagamento.](media/Return-policy-page2.png)
   
    > [!IMPORTANT]
    > - Os métodos de pagamento derivam dos métodos de pagamento definidos para a organização.
    > - Adicionar um tipo de meio de pagamento de devolução permitido para cada método de pagamento listado garantirá que as devoluções possam ser feitas no tipo de meio de pagamento de devolução permitido.
    
1. Associe o modelo de política de devolução com as lojas em que ele será usado. Selecione **Adicionar** na guia **Canais de varejo** e associe os canais disponíveis. 

    - Na caixa de diálogo **Escolher nós organizacionais**, selecione os armazenamentos, regiões e organizações aos quais o modelo será associado.
    - Apenas um modelo de política de devolução pode ser associado a cada loja.
    - Use os botões de seta para selecionar lojas, regiões ou organizações.
    - A data de efetivação na política será a data na qual as políticas são aplicadas aos canais e os trabalhos do canal são executados. 

    ![Escolha a caixa de diálogo dos nós da organização.](media/Return-policy-page3.png)

1. Na página **Agenda de distribuição**, execute o trabalho **1070** para disponibilizar a política de devolução do canal para o PDV.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Visualize a política de devolução de canal no PDV.

Siga as etapas em um dos exemplos a seguir para exibir os tipos de meio de pagamento de devolução permitidos no PDV.

1. Entre no PDV como um caixa ou gerente.
1. Em **Turno e gaveta**, selecione **Mostrar diário**.
1. Selecione a transação que faz parte da devolução. 
1. Selecione os itens a serem reembolsados e escolha o método de pagamento.  
    - Se o meio de pagamento selecionado estiver na lista permitida de tipos de meio de pagamento de devolução, o caixa poderá concluir a transação.
    - Se o meio de pagamento selecionado não for permitido, uma mensagem de erro será exibida.
    - Selecione **Valor Devido** para exibir uma lista de todos os tipos de meio de pagamento de devolução permitidos.

- ou -

1. Entre no PDV como um caixa ou gerente.
1. Selecione **Transação de Devolução** e insira a ID de recibo usando uma verificação de código de barras ou por entrada manual. 
1. Selecione a transação que faz parte da devolução. 
1. Selecione os itens a serem reembolsados e escolha o método de pagamento.  
    - Se o meio de pagamento selecionado estiver na lista permitida de tipos de meio de pagamento de devolução, o caixa poderá concluir a transação.
    - Se o meio de pagamento selecionado não for permitido, uma mensagem de erro será exibida.
    - Selecione **Valor Devido** para exibir uma lista de todos os tipos de meio de pagamento de devolução permitidos.

![Tipo de reembolso não permitido.](media/Return-policy-page6.png)



![Tipos de reembolso não permitidos.](media/Return-policy-page5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
