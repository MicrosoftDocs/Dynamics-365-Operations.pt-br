---
title: Ordens de qualidade
description: Este tópico descreve como criar ordens de qualidade de forma manual ou automática e como trabalhar com elas para realizar inspeções e registrar resultados de testes no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c951716a456101ba753e5c567c80deb4ee7e764f
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956556"
---
# <a name="quality-orders"></a>Ordens de qualidade

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar ordens de qualidade de forma manual ou automática e como trabalhar com elas para realizar inspeções e registrar resultados de testes no Microsoft Dynamics 365 Supply Chain Management.

## <a name="automatically-created-quality-orders"></a>Ordens de qualidade criadas automaticamente

Você pode configurar o sistema para que ele crie ordens de qualidade automaticamente com base em regras de amostragem de item. Para obter mais informações, consulte [Amostragem de item de gerenciamento de qualidade](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Criar ordens de qualidade manualmente

Para criar uma ordem de qualidade manualmente, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Ordens de qualidade**, no campo **Tipo de referência**, selecione a referência de estoque à qual sua ordem de qualidade será relacionada. Para obter uma descrição dos tipos de referência disponíveis para seleção, consulte a seção [Tipos de referência de ordem de qualidade](#ref-types) posteriormente neste tópico.

    > [!NOTE]
    > O estoque relacionado à referência selecionada deve estar disponível. Se não houver estoque disponível para a combinação do tipo de referência, da quantidade e das dimensões de estoque selecionados, você receberá uma mensagem de erro.

1. Siga uma destas etapas, dependendo do valor selecionado no campo **Tipo de referência**:

    - Se você selecionou **Estoque**, informações de referência adicionais não serão necessárias.
    - Se você selecionou **Venda** ou **Compra**, especifique as seguintes informações:

        - **Seleção de conta** – Faça referência ao número do cliente ou do fornecedor.
        - **Número de referência** – Faça referência ao número da ordem de venda ou da ordem de compra.
        - **Lote de referência** – Faça referência à linha da ordem de venda ou à linha da ordem de compra específica.

    - Se você selecionou **Produção**, **Quarentena** ou **Produção de coprodutos**, no campo **Número de referência**, faça referência ao número da ordem de produção, da ordem de lote ou da ordem de quarentena.
    - Se você selecionou **Operação de roteiro**, especifique as seguintes informações:

        - **Número de referência** – Faça referência ao número da ordem de produção ou da ordem de lote.
        - **Nº da Oper.** – Faça referência ao número da operação de roteiro específica.
        - **Operação** – Faça referência à operação de roteiro específica.
        - **Recurso** – Faça referência ao recurso específico que deve ser usado com a operação de roteiro.

1. No campo **Grupo de teste**, selecione o grupo de testes que devem ser realizados.
1. No campo **Quantidade**, insira a quantidade de itens que devem ser testados.
1. Na seção **Dimensões de estoque**, insira as dimensões de estoque adicionais necessárias para o item selecionado.
1. Selecione **OK**.

Após a criação de uma ordem de qualidade, você poderá começar a inspecionar o estoque e registrar os resultados do teste. Para obter mais informações sobre como registrar e validar os resultados do teste, consulte [Inspecionar a qualidade das mercadorias](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Tipos de referência das ordens de qualidade

As ordens de qualidade são usadas para rastrear os detalhes sobre inspeções e resultados de teste para um estoque específico no seu depósito. Uma ordem de qualidade deve incluir uma referência que represente a origem do estoque que está sendo testado. As ordens de qualidade podem ser relacionadas aos seguintes tipos de referência:

- **Estoque** – Este tipo de referência indica que você está inspecionando o estoque disponível. As inspeções desse tipo normalmente são aleatórias ou não planejadas, e são feitas quando um trabalhador do depósito identifica um problema.
- **Venda** – Este tipo de referência indica que você está inspecionando o estoque relacionado a uma ordem de venda específica. As inspeções desse tipo normalmente estão relacionadas às especificações do cliente ou à geração de um certificado de análise (CoA) que deve ser fornecido a um cliente como parte de uma remessa. (Às vezes, um CoA também é chamado de certificado de conformidade \[CoC\] .)
- **Compra** – Este tipo de referência indica que você está inspecionando o estoque relacionado a uma ordem de compra. As inspeções desse tipo costumam ser usadas para inspecionar bens de entrada antes de serem colocados em estoque ou consumidos em processos de produção.
- **Produção** – Este tipo de referência indica que você está inspecionando o estoque relacionado a uma ordem de produção. As inspeções desse tipo costumam ser usadas para inspecionar bens acabados antes de serem colocados em estoque.
- **Quarentena** – Este tipo de referência indica que você está inspecionando o estoque relacionado a uma ordem de quarentena. As ordens de quarentena são um tipo especial de ordem que rastreia o estoque em um depósito segregado ou uma área segregada no seu depósito. As inspeções desse tipo costumam ser usadas para inspecionar bens que um cliente devolveu ou que foram colocados em quarentena para análise adicional. As ordens de quarentena podem ser geradas com base em ordens de qualidade. Como alternativa, elas podem ser geradas com base em outras fontes, em seguida, as ordens de qualidade podem ser relacionadas às ordens de quarentena.
- **Operação de roteiro** – Este tipo de referência indica que você está inspecionando o estoque relacionado a uma etapa específica do roteiro de uma ordem de produção. As inspeções desse tipo normalmente são usadas para analisar o trabalho em andamento (WIP) de um produto antes que ele passe para a próxima etapa no processo de produção.
- **Produção de coprodutos** – Este tipo de referência indica que você está inspecionando o estoque relacionado a um coproduto de uma ordem de produção. As inspeções desse tipo normalmente são usadas para inspecionar o coproduto de uma ordem de lote antes que ele seja adicionado ao estoque.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Exibir e criar ordens de qualidade em várias partes do sistema

As ordens de qualidade podem ser criadas manualmente. Como alternativa, elas podem ser criadas automaticamente com base nas associações de qualidade definidas por você. Para obter mais informações sobre como criar e gerenciar a criação automática de ordens de qualidade, consulte [Associações de qualidade](quality-associations.md).

Você pode usar a página de ordens de qualidade para criar manualmente uma nova ordem de qualidade ou exibir o status de uma ordem de qualidade relacionada a outro registro. Há várias maneiras de acessar a página de ordens de qualidade.

### <a name="from-the-quality-orders-page"></a>Na página Ordens de qualidade

Para criar ordens de qualidade manualmente e exibir todas as ordens de qualidade existentes, vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**. As seções restantes deste tópico fornecem mais informações sobre como trabalhar com a página **Ordens de qualidade**.

### <a name="from-sales-orders"></a>Nas ordens de venda

Para trabalhar com ordens de qualidade relacionadas às suas ordens de venda, vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda** e siga qualquer uma destas etapas:

- Abra uma ordem de venda ou selecione-a na grade. Em seguida, no Painel de Ações, na guia **Separar e empacotar**, no grupo **Gerenciamento de qualidade**, selecione **Ordens de qualidade** para abrir a página **Ordens de qualidade**. Nela, você poderá exibir, criar ou atualizar ordens de qualidade relacionadas à ordem de venda.
- Abra uma ordem de venda e, na guia **Cabeçalho**, selecione a FastTab **Geral**. O campo **Status da ordem de qualidade** mostra o status geral de todas as ordens de qualidade relacionadas à ordem de venda.
- Abra uma ordem de venda e, na guia **Linhas**, selecione a FastTab **Linhas da ordem de venda**. A coluna **Status da ordem de qualidade** mostra o status de cada linha da ordem de venda.

### <a name="from-purchase-orders"></a>Nas ordens de compra

Para trabalhar com ordens de qualidade relacionadas às suas ordens de compra, vá para **Compras e fornecimento \> Ordens de compra \> Todas as ordens de compra** e siga qualquer uma destas etapas:

- Abra uma ordem de compra ou selecione-a na grade. Em seguida, no Painel de Ações, na guia **Receber**, no grupo **Gerenciamento de qualidade**, selecione **Ordens de qualidade** para abrir a página **Ordens de qualidade**. Nela, você poderá exibir, criar ou atualizar ordens de qualidade relacionadas à ordem de compra.
- Abra uma ordem de compra e, na guia **Cabeçalho**, selecione a FastTab **Geral**. O campo **Status da ordem de qualidade** mostra o status geral de todas as ordens de qualidade relacionadas à ordem de compra.
- Abra uma ordem de compra e, na guia **Linhas**, selecione a FastTab **Linhas da ordem de compra**. A coluna **Status da ordem de qualidade** mostra o status de cada linha da ordem de compra.

### <a name="from-production-orders"></a>Nas ordens de produção

Para trabalhar com ordens de qualidade relacionadas às suas ordens de produção, vá para **Controle de produção \> Ordens de produção \> Todas as ordens de produção** e siga qualquer uma destas etapas:

- Abra uma ordem de produção ou selecione-a na grade. Em seguida, no Painel de Ações, na guia **Exibir**, no grupo **Gerenciar qualidade**, selecione **Ordens de qualidade** para abrir a página **Ordens de qualidade**. Nela, você poderá exibir, criar ou atualizar ordens de qualidade relacionadas à ordem de produção.
- Abra uma ordem de produção ou selecione-a na grade. Em seguida, no Painel de Ações, na guia **Ordem de produção**, no grupo **Detalhes da produção**, selecione **Roteiro** para abrir a página **Roteiro de produção**. Para exibir as ordens de qualidade relacionadas a uma operação de roteiro, siga uma destas etapas:

    - Selecione a operação de roteiro de destino na grade. Em seguida, no Painel de Ações, selecione **Consultas \> Ordens de qualidade**.
    - Selecione o valor no campo **Oper. Nº** para a operação de roteiro de destino para abrir a página de detalhes **Roteiro de produção**. Na FastTab **Geral**, o campo **Status da ordem de qualidade** mostra o status das ordens de qualidade relacionadas à operação de roteiro.

- Abra uma ordem de produção e selecione a FastTab **Geral**. O campo **Status da ordem de qualidade** mostra o status das ordens de qualidade relacionadas à ordem de produção.

### <a name="from-quarantine-orders"></a>Nas ordens de quarentena

Para trabalhar com ordens de qualidade relacionadas às suas ordens de quarentena, vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de quarentena** e siga qualquer uma destas etapas:

- Revise os valores na coluna **Status da ordem de qualidade**. Dessa forma, você pode conhecer o status geral de todas as ordens de qualidade relacionadas a cada ordem de quarentena na grade.
- Selecione uma ordem de quarentena na grade e, no Painel de Ações, selecione **Ordens de qualidade** para exibir, criar ou atualizar ordens de qualidade relacionadas à ordem de quarentena.

## <a name="advanced-actions-for-quality-orders"></a>Ações avançadas para ordens de qualidade

Você pode realizar várias ações em ordens de qualidade para gerenciar o status, gerar documentos e consultar detalhes adicionais.

### <a name="reopen-a-quality-order"></a>Reabrir uma ordem de qualidade

Por padrão, não é mais possível editar ou atualizar uma ordem de qualidade depois de ela ter sido validada e os testes terem sido aprovados. No entanto, em alguns casos, talvez seja necessário reabrir uma ordem de qualidade depois de ela ter sido concluída.

Para reabrir uma ordem de qualidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Abra a ordem de qualidade validada ou selecione-a na grade.
1. No Painel de Ações, selecione **Reabrir ordem de qualidade**.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Criar um certificado de análise para uma ordem de qualidade

Um CoA é um relatório gerado pela equipe de controle de qualidade de uma organização. Ele valida que um produto atende a regulamentações ou requisitos específicos. Os clientes ou estabelecimentos regulatórios na sua localização geopolítica podem exigir CoAs. Eles também podem ser exigidos com base no seu setor e no tipo de produtos que você manipula, compra, produz ou vende.

O Supply Chain Management permite gerar um CoA com base em uma ordem de qualidade. O relatório incluirá os resultados de todos os testes na ordem de qualidade em que a opção **Certificado de relatório de análise** estiver definida como *Sim*. Essa opção pode ser definida por padrão, com base no teste definido na página **Testes**. No entanto, você pode substituir a configuração em testes específicos para uma ordem de qualidade específica.

Para gerar um CoA para uma ordem de qualidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Selecione a ordem de qualidade para a qual você deseja criar um CoA.
1. No Painel de Ações, selecione **Consultas \> Certificado de análise**.
1. Na página **Certificado de análise**, no Painel de Ações, selecione **Novo**.
1. Opcional: no campo **Contato**, selecione a pessoa de contato à qual o certificado deve ser endereçado.
1. No Painel de Ações, selecione **Imprimir**.
1. Na caixa de diálogo **Certificado de análise**, defina como o relatório deve ser impresso. Em seguida, selecione **OK** para imprimir o relatório em uma impressora, na tela, em um arquivo ou em um email.
1. Feche as páginas.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Bloquear ou desbloquear estoque para uma ordem de qualidade

Quando uma ordem de qualidade é gerada automaticamente com base em uma associação de qualidade, a amostragem de item atribuída à associação de qualidade pode ser configurada para bloquear a quantidade de estoque total da referência que está sendo testada. Para obter mais informações sobre amostragens de item, consulte [Amostragem de item de gerenciamento de qualidade](quality-item-sampling.md).

Se você não estiver usando o bloqueio total ou se estiver criando uma ordem de qualidade manualmente, o sistema criará de forma automática um registro de bloqueio de estoque para a quantidade do item que está sendo testado na ordem de qualidade. No registro criado na página **Bloqueio de estoque**, o campo **Tipo de bloqueio de estoque** é definido como *Ordem de qualidade*.

Para exibir e editar o bloqueio de estoque de uma ordem de qualidade selecionada na página **Bloqueio de estoque**, selecione **Consultas \> Bloqueio de estoque** no Painel de Ações. Para obter mais informações, consulte [Bloqueio de estoque](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Consultar os detalhes de uma ordem de qualidade

Use os botões a seguir no Painel de Ações da página **Ordens de qualidade** para exibir mais informações sobre ou relacionadas a uma ordem de qualidade:

- **Consultas \> Detalhes do trabalho** – Abra uma página na qual você possa exibir trabalho de depósito relacionado à ordem de qualidade.
- **Consultas \> Não conformidades** – Abra uma página na qual você possa exibir as não conformidades relacionadas à ordem de qualidade.
- **Estoque** – Os comandos neste menu são comuns em todas as transações de estoque. Você pode usá-los para exibir ou atualizar detalhes, como transações, estoque disponível, reservas e marcação.

### <a name="create-cases-related-to-quality-orders"></a>Criar casos relacionados a ordens de qualidade

Você pode criar casos relacionados a ordens de qualidade. Dessa forma, é possível rastrear detalhes sobre problemas e trabalhar para uma resolução. Em seguida, você poderá usar os recursos de fluxo de trabalho do gerenciamento de casos para encaminhar um caso por meio de um processo empresarial predefinido para obter aprovações adicionais ou mais informações sobre um problema específico. Você também pode usar o recurso de artigos de conhecimento para criar uma base de dados de conhecimento de resoluções para problemas comuns.

## <a name="case-management-examples-for-quality-management"></a>Exemplos de gerenciamento de casos para gerenciamento de qualidade

### <a name="example-1"></a>Exemplo 1

Você trabalha para uma empresa de fabricação que deve seguir regulamentações rigorosas relacionadas à produção de produtos regulamentados, como alimentos. As ordens de qualidade são usadas para registrar e rastrear detalhes sobre a qualidade dos itens durante todo o processo de produção. Se uma ordem de qualidade for reprovada em testes específicos, talvez haja um problema com o equipamento. Os casos são usados para acompanhar um processo empresarial e escalonar o problema para os engenheiros corretos, de forma que a causa raiz possa ser determinada. Para facilitar o acompanhamento dos processos empresariais, a empresa mantém uma base de dados de conhecimento com problemas comuns relacionados a ordens de qualidade e problemas em equipamentos.

### <a name="example-2"></a>Exemplo 2

Você trabalha para uma empresa de distribuição que envia produtos que podem ser personalizados para vários países e regiões. Alguns clientes têm especificações estritas que devem ser seguidas. Caso contrário, taxas e devoluções ou estornos podem ser incorridos. Você usa ordens de qualidade para rastrear os detalhes sobre cada teste e os resultados que correspondem aos requisitos do cliente. Os casos são usados para revisar e aprovar os detalhes do CoA antes de o documento ser gerado e anexado a outras papeladas de remessa.

## <a name="additional-resources"></a>Recursos adicionais

- [Processos de gerenciamento de qualidade](quality-management-processes.md)
- [Teste de qualidade](quality-tests.md)
- [Grupos de teste de qualidade](quality-test-groups.md)
- [Associações de qualidade](quality-associations.md)
- [Processos de gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
