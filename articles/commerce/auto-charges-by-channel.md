---
title: Habilitar e configurar encargos automáticos por canal
description: Este tópico explica como habilitar e configurar encargos automáticos por canal no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: c38717ca9c57913ea22f2dd7712b49f39d2e556e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349689"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a>Habilitar e configurar encargos automáticos por canal

Este tópico explica como habilitar e configurar encargos automáticos por canal no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Você pode ter situações nas quais as taxas de reciclagem ou outras taxas devem ser aplicadas a um grupo de produtos vendidos em todas ou em algumas lojas em um estado específico (por exemplo, Califórnia). O recurso **Habilitar os encargos automáticos de filtro por canal** no Commerce permite que você especifique encargos automáticos por canal (por exemplo, um canal físico específico). Este recurso está disponível no Dynamics 365 Commerce versões 10.0.10 e posterior.

Para habilitar e configurar encargos automáticos por canal, você deve concluir as seguintes tarefas:

- Ative o recurso **Habilitar encargos automáticos de filtro por canal**.
- Configurar a finalidade da hierarquia da organização.
- Definir encargos automáticos por canal.

> [!NOTE]
> O recurso **Habilitar encargos automáticos de filtro por canal** funciona somente se o recurso de encargos automáticos avançados também estiver ativado. Para obter informações sobre como ativar o recurso de encargos automáticos avançados, consulte os [Encargos automáticos avançados do Omnicanal](omni-auto-charges.md).

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a>Ative o recurso Habilitar encargos automáticos de filtro por canal

Para habilitar os encargos automáticos por canal no Commerce, siga estas etapas.

1. Vá para **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recurso**.
1. Na guia **Não habilitado**, na lista **Nome do recurso**, localize e selecione **Habilitar encargos automáticos do filtro por canal**.
1. No canto inferior direito, selecione **Habilitar agora**. Depois que o recurso for ativado, ele será exibido na lista da guia **Tudo**.
1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. No painel esquerdo, localize e selecione o trabalho **1110** (**Configuração global**).
1. No painel de ações, selecione **Executar agora** para propagar as alterações de configuração.

> [!WARNING]
> Se você desativar o recurso **Habilitar encargos automáticos de filtro por canal** depois de tê-lo usado, o campo **Relação de canal de varejo** em **Encargos automáticos** não será mais exibido e você perderá todas as configurações existentes. Se a remoção das configurações de **Relação de canal de varejo** fizer com que as regras de encargos automáticos sejam duplicadas, uma tentativa de desativar o recurso falhará. Antes de desativar o recurso, verifique se todas as regras de encargos automáticos foram revisadas e faça as alterações necessárias.

## <a name="configure-the-organization-hierarchy-purpose"></a>Configurar a finalidade da hierarquia da organização

Uma nova finalidade de hierarquia da organização chamada **Encargo automático de varejo** foi criada para gerenciar a hierarquia de encargos automáticos por canal.

Para atribuir uma hierarquia padrão a uma finalidade da hierarquia organizacional no Commerce, siga estas etapas.
        
1. Vá para **Administração da organização \> Organizações \> Finalidades de hierarquias de organização**.
1. No painel esquerdo, selecione **Encargo automático de varejo**.
1. Em **Hierarquias atribuídas**, selecione **Adicionar**.
1. Na caixa de diálogo **Hierarquias da organização**, selecione uma hierarquia da organização (por exemple, **Lojas de varejo por região**), e selecione **OK**.
1. Em **Hierarquias atribuídas**, selecione **Definir como padrão**.
1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. No painel esquerdo, localize e selecione o trabalho **1040** (**Produtos**).
1. No painel de ação, selecione **Executar Agora**.
1. Repita as duas etapas anteriores para executar os trabalhos **1070** (**Configuração de canal**) e **1110** (**Configuração global**).

![Configuração da organização de encargo automático de varejo finalidade da hierarquia.](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a>Definir encargos automáticos por canal

Depois que você ativou o recurso **Habilitar o filtro de encargos automáticos por canal** e configurou a finalidade da hierarquia da organização **Encargo automático de varejo**, os encargos automáticos por canal podem ser definidos no nível do cabeçalho da ordem ou no nível da linha da ordem.

Para definir os encargos automáticos por canal no Commerce, siga estas etapas.

1. Vá para **Contas a receber \> Configuração de encargos \> Encargos automáticos**.
1. No painel à esquerda, no campo **Nível**, selecione **Cabeçalho** ou **Linha**, dependendo de seus requisitos empresariais.
1. No campo **Código de canal de varejo**, selecione o código de canal apropriado (por exemplo **Tabela** ou **Grupo**). Se a configuração padrão, **Tudo** for usada, as regras de encargos serão aplicadas a todos os canais.

    - Se você selecionar **Grupo**, certifique-se de que o grupo de encargos de canal de varejo foi criado em **Varejo e Commerce \> Configuração do canal \> Encargos \> Grupos de encargo de canal de varejo**.
    - Se você selecionar **Tabela** poderá selecionar um canal específico (por exemplo, **San Francisco**) no campo **Relação de canal de varejo**.

1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. No painel esquerdo, localize e selecione o trabalho **1040** (**Produtos**).
1. No painel de ação, selecione **Executar Agora**.
1. Repita as duas etapas anteriores para executar os trabalhos **1070** (**Configuração de canal**) e **1110** (**Configuração global**).
    
![Encargos automáticos definidos por canal.](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a>Cenário de exemplo

O exemplo a seguir destaca as etapas necessárias para configurar um produto, de forma que as taxas de reciclagem sejam cobradas quando o produto é vendido por meio de um canal físico e de San Francisco. O exemplo também mostra como os encargos automáticos aparecem no aplicativo de ponto de venda (POS) comercial.

A organização define um código de encargos denominado **RECICLAR**, conforme mostrado na ilustração a seguir.

![Código de encargos RECICLAR.](media/Auto-charges-charge-code.png)

Um encargo automático é criado no nível da linha. Tem as seguintes configurações:

- O campo **Código de conta** está definido como **Tudo**.
- O campo **Item de conta** está definido como **Tabela**.
- O campo **Relação de itens** está definido como ID do produto **91001**.
- O campo **Modo de código de entrega** está definido como **Tudo**.
- O campo **Código de canal de varejo** está definido como **Tabela**.
- O campo **Relação de canal de varejo** está definido como a loja **San Francisco**.

Uma linha de encargos automáticos é criada. Tem as seguintes configurações:

- O campo **Moeda** é definido como **USD**.
- O campo **Código de encargos** está definido como **RECICLAR**.
- O campo **Categoria** é definido como **Fixo**.
- O campo **Encargos** é definido como **$6,25**.

![Configuração do encargo automático de nível de linha e linha de encargos automáticos.](media/Auto-charges-recyclingfee-line-fee.png)

No aplicativo POS, uma ordem de venda é criada no canal de armazenamento **San Francisco**. A linha **Encargos** mostra a taxa de reciclagem de **$6,25**.

Ao selecionar **Opções de transação \> Encargos \> Gerenciar encargos** no aplicativo PDV, você pode visualizar o código de encargos e descrição da taxa de reciclagem.

![Taxa de reciclagem no aplicativo PDV.](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a>Recursos adicionais

[Encargos automáticos avançados de omnicanal](omni-auto-charges.md)

[Ratear encargos do cabeçalho para as linhas de vendas correspondentes](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]