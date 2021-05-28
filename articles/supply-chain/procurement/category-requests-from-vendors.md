---
title: Solicitações de categoria de fornecedores
description: Este tópico descreve como os fornecedores podem solicitar categorias de compras para sua conta. Também descreve o processo de aprovação que é preenchido pelos agentes de compras.
author: kamaybac
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1951f85f84c3b8b2d42f49d5f464d90d410ebfa2
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6015942"
---
# <a name="category-requests-from-vendors"></a>Solicitações de categoria de fornecedores

[!include [banner](../includes/banner.md)]

O processo de solicitação de categoria permite que os fornecedores que solicitam novas categorias de compras sejam associadas a sua conta. Essas categorias de compras podem então ser usadas pelos processos de compras e de fornecimento relacionados. (Para obter mais informações, consulte [Visão geral dos catálogos de compra](procurement-catalogs.md).)

As solicitações de categoria são iniciadas por fornecedores no espaço de trabalho **Informações do fornecedor**. Em seguida, eles são enviados para a agência para revisão e aprovação. As categorias aprovadas são adicionadas à lista de categorias de compras para a conta do fornecedor.

## <a name="turn-on-the-feature-in-your-system"></a>Ative o recurso no seu sistema

Se o sistema ainda não incluir o recurso descrito neste tópico, vá para [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Permitir que os fornecedores se apliquem às categorias de compras por meio da colaboração do fornecedor*.

Depois que o recurso for ativado, você ainda poderá adicionar categorias de compras manualmente a contas de fornecedor. Para obter mais informações, consulte [Aprovar fornecedores para categorias específicas da compras](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Requisitos de colaboração do fornecedor

Antes que um fornecedor possa interagir com solicitações de categoria, ele deve ser configurado para colaboração de fornecedor.

O fornecedor deve ter pelo menos um usuário de colaboração de fornecedor. Somente os usuários fornecedores com a função de segurança *Administrador do fornecedor (externo)* podem criar e enviar solicitações de categoria.

Para obter mais informações, consulte [Configurar e manter colaboração de fornecedor](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Configurar o fluxo de trabalho da solicitação de categoria do fornecedor

O fluxo de trabalho *Solicitação de categoria de fornecedor* deve ser configurado nos fluxos de trabalho de compras e fornecimento. Os fornecedores enviarão novas solicitações de categoria que podem ser revisadas e aprovadas. As categorias de compras solicitadas são adicionadas a uma conta de fornecedor após a aprovação de uma solicitação de categoria.

O exemplo a seguir mostra como configurar um fluxo de trabalho de *Solicitação de categoria de fornecedor* simples que tenha um único aprovador. Você deve revisar seus processos internos para determinar a configuração de fluxo de trabalho apropriada para a sua agência.

1. Vá para **Compras e fornecimento \> Configuração \> Fluxos de trabalho de compras e fornecimento**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo, selecione **Fluxo de trabalho de solicitação de categoria de fornecedor** para abrir o editor de fluxo de trabalho.
1. Efetue login no editor de fluxo de trabalho.
1. No Painel de Ações, selecione **Propriedades**.
1. Na página **Propriedades** do fluxo de trabalho, no campo **Instruções de envio**, insira o texto de instrução. As instruções estarão visíveis para fornecedores quando eles enviarem uma solicitação de categoria.
1. Feche a página **Propriedades**.
1. Arraste o elemento do fluxo de trabalho **Aprovar nova solicitação de categoria** para a tela.
1. Arraste um link do elemento do fluxo de trabalho **Iniciar** para o elemento do fluxo de trabalho **Aprovar nova solicitação de categoria**.
1. Arraste um link do elemento do fluxo de trabalho **Aprovar nova solicitação de categoria** para o elemento do fluxo de trabalho **Finalizar**.
1. Toque duas vezes (ou clique duas vezes) no elemento de fluxo de trabalho **Aprovar nova solicitação de categoria**.
1. Selecione e segure (ou clique com o botão direito do mouse) no elemento do fluxo de trabalho **Etapa 1** e selecione **Propriedades**.
1. Na página **Propriedades** do elemento do fluxo de trabalho, no campo **Assunto do item de trabalho**, insira o texto do assunto. Esse texto será mostrado como o valor do campo **Assunto** na página **Itens de trabalho atribuídos a mim**.
1. No campo **Instruções do item de trabalho**, insira o texto da instrução. As instruções estarão visíveis para os aprovadores quando selecionarem **Fluxo de trabalho** no Painel de Ações de uma solicitação de categoria.
1. No painel esquerdo, selecione **Atribuição**.
1. Na guia **Tipo de atribuição**, defina **Atribuir usuários a este elemento de fluxo de trabalho** para *Usuário*.
1. Na guia **Usuário**, na lista de **Usuários disponíveis**, selecione um aprovador. Por exemplo, selecione um usuário no departamento de Compras.
1. Selecione o botão Seta para a direita (**\>**) para mover o aprovador para a lista de **Usuários selecionados**.
1. Feche a página **Propriedades**.
1. Selecione **Salvar e fechar**.
1. No campo **Notas da versão**, insira notas sobre o fluxo de trabalho.
1. Selecione **OK** para salvar o fluxo de trabalho.
1. Se você estiver pronto para começar a testar o fluxo de trabalho, selecione **Ativar a nova versão**. Caso contrário, selecione **Não ativar a nova versão**.
1. Selecione **OK** para concluir a configuração do fluxo de trabalho.

> [!TIP]
> Se a sua agência não exigir aprovação de solicitações de categoria, configure o fluxo de trabalho para aprovação automática.

Para obter mais informações sobre como configurar fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Crie e envie uma solicitação de categoria

Esta seção descreve como os fornecedores podem usar o espaço de trabalho **Informações do fornecedor** para criar, editar, exibir e enviar solicitações de categoria.

### <a name="start-a-new-request"></a>Iniciar uma solicitação

Para iniciar uma nova solicitação de categoria, siga estas etapas.

1. No espaço de trabalho **Informações do fornecedor**, selecione o bloco **Solicitações de categoria**.
1. Na página **Solicitações de categoria**, no Painel de Ações, selecione **Nova solicitação de categoria**.
1. Na caixa de diálogo **Nova solicitação de categoria**, localize a categoria que deseja aplicar navegando na árvore e/ou usando o filtro na parte superior da lista. Marque a caixa de seleção de cada categoria relevante.

    Observe os seguintes pontos:

    - As categorias atualmente ativas na sua conta de fornecedor são mostradas como selecionadas e não podem ser removidas.
    - Você pode solicitar várias categorias de compras em uma única solicitação de categoria.

1. Selecione **OK** para criar a solicitação de rascunho.

    A nova solicitação de rascunho aparecerá agora na página **Solicitações de categoria**.

1. Abra a nova solicitação de rascunho para revisá-la e editá-la, conforme necessário.

    - Para exibir a lista de categorias que estão incluídas no momento na solicitação, selecione a FastTab **Categorias solicitadas**.
    - Para exibir suas categorias ativas, abra o Quadro de Fatos **Categorias ativas** no lado direito da página.
    - Para adicionar uma categoria à solicitação, selecione **Adicionar** na barra de ferramentas da FastTab **Categorias solicitadas**.
    - Para remover uma categoria da solicitação, selecione a categoria na FastTab **Categorias solicitadas** e selecione **Remover** na barra de ferramentas.
    - Para anexar um documento à solicitação, selecione **Anexos** no Painel de Ações. Os documentos anexados estarão disponíveis para os aprovadores quando examinarem a solicitação de categoria.
    - Para remover um documento anexado da solicitação, selecione **Anexos** no Painel de Ações. Selecione o documento para remover e, depois, selecione **Excluir** no Painel de Ações.

1. Se você estiver pronto para enviar a solicitação, selecione **Enviar** no Painel de Ações. Caso contrário, basta fechar a página e ignorar as etapas restantes deste procedimento. Você poderá retornar à solicitação posteriormente.
1. Leia as instruções de envio exibidas e selecione **Enviar**.
1. Na caixa **Comentário**, especifique as informações adicionais necessárias. Depois, selecione **Enviar** para concluir a solicitação.

### <a name="edit-a-draft-or-recalled-request"></a>Editar um rascunho ou solicitação cancelada

Para editar uma solicitação de rascunho ou de categoria cancelada, siga estas etapas.

1. No espaço de trabalho **Informações do fornecedor**, selecione o bloco **Solicitações de categoria**.
1. Selecione a solicitação de rascunho ou cancelada para abri-la.
1. Edite a solicitação, conforme necessário, e feche-a ou envie-a, conforme descrito no procedimento anterior.

### <a name="submit-a-draft-or-recalled-request"></a>Enviar um rascunho ou solicitação cancelada

Para enviar uma solicitação de rascunho ou de categoria cancelada, siga estas etapas.

1. No espaço de trabalho **Informações do fornecedor**, selecione o bloco **Solicitações de categoria**.
1. Selecione a solicitação de rascunho ou cancelada que deseja enviar.
1. No Painel de Ações, selecione **Enviar**.
1. Leia as instruções de envio exibidas e selecione **Enviar**.
1. Na caixa **Comentário**, especifique as informações adicionais necessárias. Depois, selecione **Enviar** para concluir a solicitação.

    O status da solicitação de categoria é alterado para um dos seguintes valores:

    - _Revisão pendente_ – a solicitação está no fluxo de trabalho.
    - _Aprovação pendente_ – a aprovação é necessária.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Cancelar uma solicitação enviada que ainda não foi aprovada

Para cancelar uma solicitação de categoria que foi enviada mas ainda não foi aprovada, siga estas etapas.

1. No espaço de trabalho **Informações do fornecedor**, selecione o bloco **Solicitações de categoria**.
1. Selecione a solicitação pendente que deseja recuperar.
1. No Painel de Ações, selecione **Cancelar**.
1. Na caixa **Inserir um comentário**, especifique as informações adicionais necessárias. Depois, selecione **Enviar** para concluir a solicitação.

    O status da solicitação de categoria é alterado para _Cancelado_. A solicitação permanecerá neste status até que você a exclua ou reenvie.

### <a name="delete-a-draft-or-recalled-request"></a>Excluir um rascunho ou solicitação cancelada

Para excluir uma solicitação de rascunho ou de categoria cancelada, siga estas etapas.

1. No espaço de trabalho **Informações do fornecedor**, selecione o bloco **Solicitações de categoria**.
1. Selecione a solicitação de rascunho ou cancelada que deseja excluir.
1. No Painel de Ações, selecione **Excluir**.
1. Selecione **Sim** para confirmar a exclusão.

### <a name="view-completed-requests"></a>Exibir solicitações concluídas

Para exibir solicitações concluídas, abra o espaço de trabalho **Informações do fornecedor** e selecione o bloco **Solicitações de categoria**. As solicitações de categoria que tiverem sido concluídas terão um dos seguintes status:

- _Aprovado_ - a solicitação foi aprovada. Para exibir as categorias adicionadas recentemente, volte ao espaço de trabalho **Informações do fornecedor**, abra a lista suspensa **Mais detalhes** no painel esquerdo e selecione **Categorias**.
- _Rejeitada_ – a solicitação foi rejeitada. Você pode criar uma nova solicitação de categoria, conforme necessário.

## <a name="review-category-requests"></a>Revisar solicitações de categoria

Esta seção explica como aprovar, rejeitar e delegar solicitações de categoria que os fornecedores enviaram e como exibir solicitações concluídas. Essas ações de fluxo de trabalho são para a solicitação de categoria inteira.

### <a name="view-category-requests"></a>Exibir solicitações de categoria

Para exibir solicitações de categoria, siga estas etapas.

1. Vá para **Compras e fornecimento \> Fornecedores \> Solicitações de colaboração do fornecedor \> Solicitações de categoria**.

    A página **Solicitações de categoria** será exibida. A exibição de página padrão mostra solicitações de categoria que têm um status de *Ação Pendente*.

1. Para exibir todas as solicitações, selecione *Tudo* no campo **Mostrar solicitações**.
1. Abra uma solicitação para revisá-la e editá-la, conforme necessário.

    - Para exibir a lista de categorias que estão incluídas no momento na solicitação, selecione a FastTab **Categorias solicitadas**.
    - Para exibir as categorias ativas, abra o Quadro de Fatos **Categorias ativas** no lado direito da página.
    - Se os documentos foram enviados, o botão  **Anexos** (clipe de papel) no Painel de Ações mostra uma contagem dos documentos anexados. Para exibir documentos anexados, selecione o botão **Anexos**. Em seguida, selecione o documento a ser exibido e selecione **Abrir** para exibi-lo.
    - Para anexar um documento à solicitação, selecione **Anexos** no Painel de Ações. Os documentos anexados estarão disponíveis para os aprovadores quando examinarem a solicitação de categoria.
    - Para remover um documento anexado da solicitação, selecione **Anexos** no Painel de Ações. Selecione o documento para remover e, depois, selecione **Excluir** no Painel de Ações.
    - Para exibir o histórico do fluxo de trabalho, selecione **Fluxo de trabalho** no Painel de Ações. Nas opções de fluxo de trabalho, selecione **Mais** e depois **Histórico do fluxo de trabalho**. A página **Histórico do fluxo de trabalho** será exibida.

### <a name="approve-a-pending-category-request"></a>Aprovar uma solicitação de categoria pendente

Para aprovar uma solicitação de categoria pendente, siga estas etapas.

1. Vá para **Compras e fornecimento \> Fornecedores \> Solicitações de colaboração do fornecedor \> Solicitações de categoria**.
1. Selecione a solicitação pendente a ser aprovada.
1. Revise a solicitação de categoria.
1. Opcional: na FastTab **Geral**, no campo **Código de motivo**, selecione um código de motivo. Em seguida, no campo **Comentário do motivo**, insira um comentário sobre o código de motivo.
1. No Painel de Ações, selecione **Fluxo de Trabalho**.
1. Nas opções de fluxo de trabalho, selecione **Aprovar**.
1. No campo **Comentário**, especifique as informações adicionais necessárias. Depois, selecione **Aprovar** para concluir a solicitação.

    O status da solicitação de categoria é alterado para _Aprovado_, e as categorias de compras são adicionadas à conta do fornecedor.

### <a name="reject-a-pending-category-request"></a>Rejeitar uma solicitação de categoria pendente

Para rejeitar uma solicitação de categoria pendente, siga estas etapas.

1. Vá para **Compras e fornecimento \> Fornecedores \> Solicitações de colaboração do fornecedor \> Solicitações de categoria**.
1. Selecione a solicitação pendente a ser rejeitada.
1. Revise a solicitação de categoria.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Geral**, no campo **Código de motivo**, selecione um código de motivo. Em seguida, no campo **Comentário do motivo**, insira um comentário sobre o código de motivo.
1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, selecione **Fluxo de Trabalho**.
1. Nas opções de fluxo de trabalho, selecione **Mais** e depois **Rejeitar**.
1. No campo **Comentário**, especifique as informações adicionais necessárias. Depois, selecione **Rejeitar** para concluir a solicitação.

    O status da solicitação de categoria é alterado para _Rejeitado_. Neste ponto, o fornecedor pode criar uma nova solicitação de categoria, conforme necessário.

### <a name="delegate-a-pending-category-request"></a>Delegar uma solicitação de categoria pendente

Para delegar uma solicitação de categoria pendente a outro usuário, siga estas etapas.

1. Vá para **Compras e fornecimento \> Fornecedores \> Solicitações de colaboração do fornecedor \> Solicitações de categoria**.
1. Selecione a solicitação pendente que deseja aprovar.
1. No Painel de Ações, selecione **Fluxo de Trabalho**.
1. Nas opções de fluxo de trabalho, selecione **Mais** e depois **Delegar**.
1. No campo **Usuário**, selecione o usuário ao qual atribuir a solicitação de categoria para revisão.
1. No campo **Comentário**, especifique as informações adicionais necessárias.
1. Selecione **Delegar** para concluir a delegação. O usuário selecionado agora pode revisar a solicitação de categoria.

### <a name="view-procurement-categories-for-a-vendor"></a>Exibir categorias de compras para um fornecedor

Para exibir as categorias de compras de um fornecedor após a aprovação de uma solicitação de categoria, siga estas etapas.

1. Vá para **Aquisição e fornecimento \> Fornecedores \> Todos os fornecedores**.
1. Na página **Todos os fornecedores**, selecione o fornecedor para o qual você deseja exibir as categorias de compras.
1. No Painel de Ações, abra a guia **Geral** e, no grupo **Configurar**, selecione **Categorias**.

    A página **Categorias** será exibida. A FastTab **Compras** mostra as categorias de compras que foram adicionadas por meio da solicitação de categoria.

1. Na FastTab **Compras**, você pode fazer alterações, se necessário. Por exemplo, você pode definir o campo **Status da categoria de fornecedor** como _Preferencial_.
