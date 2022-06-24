---
title: Liberar estruturas de produtos
description: Este artigo explica como você pode liberar estruturas de produtos completas além de lançar produtos juntamente com suas versões de engenharia. Dessa forma, você pode garantir que os dados de produtos relevantes da engenharia possam ser facilmente reutilizados em diferentes entidades legais.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c8359f86e5123ee40e9673971de626e1b327ac95
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875471"
---
# <a name="release-product-structures"></a>Liberar estruturas de produtos

[!include [banner](../includes/banner.md)]

Para garantir que os dados de produtos relevantes da engenharia possam ser facilmente reutilizados em diferentes entidades legais, você pode liberar estruturas de produtos completas além de lançar os produtos juntamente com suas versões de engenharia. Portanto, você pode liberar estruturas de lista de materiais (BOM) de vários níveis juntamente com o pai em uma única ação de liberação. Neste caso, a BOM e os produtos de nível inferior também são liberados.

Os produtos de engenharia são criados e mantidos por sua empresa de engenharia da forma que atendem aos requisitos de qualidade à medida que são criados. Cada empresa operacional que fabrica um produto precisa do mesmo produto e da BOM subjacente. Dependendo do recurso de produção, o roteiro pode ser criado localmente. Nesse caso, você não liberará um roteiro junto com o produto. No caso de entidades legais que vendem os produtos mas não as fabricam, a BOM pode não ser necessária.

Para tornar o processo mais eficiente, todos os dados relevantes para a engenharia podem ser liberados para outras empresas operacionais ao mesmo tempo. Esses dados incluem a estrutura de produtos. Durante o processo de liberação, você pode escolher a parte dos dados do produto que deve ser liberada.

Para obter mais informações sobre empresas de engenharia e empresas operacionais, consulte [Empresas de engenharia e regras de propriedade de dados](engineering-org-data-ownership-rules.md).

Observe que você pode liberar produtos e produtos padrão juntamente com a estrutura de produto do lançamento. Durante esse processo, toda a estrutura de produto será liberada, até mesmo a BOM e o roteiro da empresa em que os produtos estão sendo lançados.

Para obter um exemplo de como liberar um produto, consulte [Liberar um produto de engenharia para uma empresa local](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>Dados liberados para um produto quando a estrutura de produtos de lançamento é usada

Os dados a seguir estão incluídos na liberação de produtos de engenharia:

- **Dados do produto** – Um novo produto liberado é criado.
- **Dados da versão de engenharia** – A versão de engenharia e seus dados são criados ou atualizados. Observe que se você liberar a mesma versão de engenharia novamente para uma empresa operacional, os dados de engenharia serão substituídos.
- **Atributos de engenharia** – Os atributos de engenharia e seus valores são criados ou atualizados.
- **Lista de materiais de engenharia** – A BOM de engenharia e suas linhas podem ser criadas ou atualizadas. Para obter mais informações sobre a propriedade de dados, consulte [Proprietários de produtos](product-owner.md).
- **Rotas de engenharia** – As rotas de engenharia e suas operações são criadas ou atualizadas. Para obter mais informações sobre a propriedade de dados, consulte [Proprietários de produtos](product-owner.md).
- **Documentos de engenharia** – Os documentos de engenharia que estão conectados à versão de engenharia são criados ou atualizados.

Quando você ativar o gerenciamento de alterações de engenharia no sistema, a estrutura de produto de lançamento estará disponível. Além disso, os produtos padrão incluirão suas BOMs e roteiros quando eles forem liberados.

## <a name="product-acceptance"></a>Aceitação do produto

**Aceitação do produto** é um parâmetro chave que influencia o processo de liberação. Você pode definir esse parâmetro para cada empresa, acessando **Gerenciamento de alteração de engenharia \> Configuração \> Parâmetros de gerenciamento de alteração de engenharia**. Para obter mais informações, consulte [Parâmetros do gerenciamento de alteração de engenharia](engineering-parameters.md).

### <a name="automatic-product-acceptance"></a>Aceitação automática de produtos

Cada liberação de produtos de engenharia começa quando alguém da empresa de engenharia seleciona um produto a ser lançado. Quando o parâmetro **Aceitação do produto** é definido como *Automático*, o usuário na empresa de engenharia decide quais dados do produto devem ser liberados automaticamente para as empresas operacionais. O produto será liberado automaticamente para as empresas selecionadas no assistente de liberação.

### <a name="manual-product-acceptance"></a>Aceitação manual de produtos

Cada liberação de produtos de engenharia começa quando alguém da empresa de engenharia seleciona um produto a ser lançado. Quando o parâmetro **Aceitação do produto** é definido como *Manual*, o usuário na empresa de engenharia decide quais dados do produto devem ser liberados para as empresas operacionais. Um usuário de cada empresa operacional revisa os dados do produto e decide se a liberação deve ser aceita. O usuário na empresa operacional pode definir as seguintes opções quando os dados são recebidos:

- Se os produtos (atualizações) não forem relevantes para a empresa operacional, o usuário poderá optar por não aceitar a liberação.
- O usuário pode alterar o modelo de item para novos produtos.
- O usuário pode escolher se o produto deve ser liberado junto com suas BOMs e/ou roteiros e se eles devem ser liberados como aprovados e ativos.
- O usuário pode alterar as datas de efetivação dos produtos.

Para obter um exemplo de como aceitar um produto, consulte [Revisar e aceitar o produto antes de liberá-lo na empresa local](engineering-scenarios.md#accept).

> [!NOTE]
> Para produtos padrão, você pode liberar de qualquer entidade legal para qualquer outra entidade legal. Para produtos de engenharia, a única entidade legal da qual você pode liberar é a empresa de engenharia.

## <a name="release-policies"></a>Políticas de liberação

Nem todas as empresas operacionais precisam dos mesmos dados de produtos. Em geral, as empresas operacionais que fabricam produtos de engenharia exigem uma BOM, enquanto a empresa operacional que apenas vende produtos de engenharia não exigem uma BOM. Você pode usar as diretivas de liberação para estabelecer os parâmetros usados para a liberação de produtos.

Para obter mais informações sobre categorias de produto de engenharia, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).

Durante o processo de liberação, você pode influenciar as configurações.

## <a name="create-and-manage-product-release-policies"></a>Criar e gerenciar políticas de preparação do produto

Para trabalhar com diretivas de liberação de produtos, Acesse **Gerenciamento de alteração de engenharia \> Configuração \> Políticas de liberação de produtos**. Siga uma destas etapas.

- Para criar uma nova política, selecione **Novo** no Painel de ações e defina os campos conforme descrito nas subseções a seguir.
- Para editar uma política existente, selecione-o no painel de listas, selecione **Editar** no Painel de ações e defina os campos conforme descrito nas subseções a seguir.
- Para excluir uma diretiva existente, selecione-a no painel de lista, selecione **Editar** no Painel de ações e, na Guia rápida **Geral**, verifique se a opção **Ativo** está definida como *Não*. Em seguida, selecione **Excluir** no Painel de ações.

### <a name="header"></a>Cabeçalho

Defina os campos a seguir no cabeçalho de uma política de versão do produto.

| Campo | descrição |
|---|---|
| Organização | Digite um nome para a política. |
| descrição | Insira uma descrição para a política. |

### <a name="general-fasttab"></a>Guia Rápida Geral

Defina os campos a seguir na Guia rápida **Geral** de uma política de versão do produto.

| Campo | descrição |
|---|---|
| Tipo de Produto | Selecione se a diretiva se aplica a produtos do tipo *Item* ou *Serviço*. Não é possível alterar essa configuração após salvar o registro. |
| Tipo de produção | Este campo é exibido somente quando você habilita [gerenciamento de alterações de fórmula](manage-formula-changes.md) em seu sistema. Selecione o tipo de produção ao qual essa política de liberação se aplica:<ul><li>**Coproduto**: use esta política de liberação para gerenciar coprodutos. Os coprodutos são produzidos durante o processo de fabricação e não são produtos com versão ou de engenharia. As políticas de liberação para coprodutos podem ajudar a garantir que configurações importantes, como **Grupo de dimensões de armazenamento** e **Grupo de dimensões de rastreamento**, sejam configuradas usando um modelo de produto liberado antes de serem liberadas para uma empresa.</li><li>**Subproduto**: use esta política de liberação para gerenciar subprodutos. Os subprodutos são produzidos durante o processo de fabricação e não são produtos com versão ou de engenharia. As políticas de liberação para subprodutos podem ajudar a garantir que configurações importantes, como **Grupo de dimensões de armazenamento** e **Grupo de dimensões de rastreamento**, sejam configuradas usando um modelo de produto liberado antes de serem liberadas para uma empresa.</li><li>**Nenhum**: use esta política para gerenciar produtos padrão que não tenham controle de versão ou produtos de engenharia, ou coprodutos ou subprodutos.</li><li>**Item de planejamento**: use esta política de liberação para gerenciar itens de planejamento que são produzidos usando a fabricação de processos. Os itens de planejamento usam fórmulas. Eles se parecem com itens de fórmula, mas são usados para produzir apenas coprodutos e subprodutos, não produtos acabados.</li><li>**BOM**: use esta política de liberação para gerenciar produtos de engenharia, que não usam fórmulas e geralmente (mas não necessariamente) incluem BOMs.</li><li>**Fórmula**: use esta política de liberação para gerenciar itens acabados que são produzidos usando a fabricação de processos. Esses itens terão uma fórmula, mas não uma BOM.</li></ul> |
| Aplicar modelos | Selecione uma das opções a seguir para especificar se e como os modelos de liberação de produto devem ser aplicados quando a diretiva for usada:<ul><li>**Sempre** – Um produto de modelo liberado deve sempre ser usado para lançamentos. Se você selecionar esta opção, use a Guia rápida **Todos os produtos** para especificar o modelo usado para cada empresa para a qual você libera. Se você não especificar um modelo para cada empresa listada na guia **Todos os produtos**, receberá um erro quando tentar salvar a diretiva.</li><li>**Opcional** – Se um produto de modelo liberado for especificado para uma empresa listada na guia **Todos os produtos**, esse modelo será usado quando você liberar para essa empresa. Caso contrário, nenhum modelo será usado. Se você selecionar esta opção, poderá salvar a diretiva sem atribuir modelos a todas as empresas. (Nenhum aviso será exibido.)</li><li>**Nunca** – Nenhum produto de modelo liberado será usado para quaisquer empresas para as quais você libera os produtos, mesmo se um modelo for especificado para empresas que estão listadas na Guia rápida **Todos os produtos**. As colunas do modelo não estarão disponíveis.</li></ul> |
| Com atividade | Use esta opção para ajudar a manter as políticas de versão. Defina como *Sim* para todas as diretivas de versão que você usa. Defina como *Não* para marcar uma política de liberação como inativa quando ela não for usada. Observe que não é possível desativar uma diretiva de versão atribuída a uma categoria de produto de engenharia, e você pode excluir somente as diretivas de liberação inativas. |

### <a name="all-products-fasttab"></a>Guia rápida de todos os produtos

Na guia **Todos os produtos**, adicione uma linha para cada empresa operacional para a qual você deseja usar esta diretiva para liberar. Use os botões na Guia rápida **Todos os produtos** para adicionar e remover linhas conforme necessário. Para cada linha adicionada, defina os campos a seguir.

> [!NOTE]
> As configurações na guia **Todos os produtos** aplicam-se aos produtos de engenharia e aos produtos padrão.

| Campo | descrição |
|---|---|
| ID de contas da empresa | Selecione a empresa à qual a linha se aplica. Os parâmetros na linha serão aplicados quando os produtos forem liberados para essa empresa. |
| Produto liberado de modelo | Adicionar um modelo ao produto. |
| Copiar aprovação da BOM | Marque esta caixa de seleção para copiar o status de aprovação da BOM para a empresa de destino. |
| Copiar ativação da BOM | Marque esta caixa de seleção para copiar o status de ativação da BOM para a empresa de destino. |
| Copiar aprovação de roteiro | Marque esta caixa de seleção para copiar o status de aprovação da rota para a empresa de destino.|
| Copiar ativação de roteiro | Marque esta caixa de seleção para copiar o status de ativação da rota para a empresa de destino. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Parâmetros de opção da Guia rápida de produtos de engenharia

Toda vez que você adiciona uma linha na Guia rápida **Todos os produtos**, uma linha que tem um valor **ID de contas da empresa** correspondente também é criada na Guia rápida **Parâmetros de opção para produtos de engenharia**. Em seguida, se você remover uma linha da Guia rápida **Todos os produtos**, a linha que tem o valor **ID de contas da empresa** correspondente também é removida da Guia rápida **Parâmetros de opção para produtos de engenharia**.

Para cada linha mostrada na guia rápida **Parâmetros de opção de produtos de engenharia**, defina os campos a seguir.

> [!NOTE]
> As configurações na Guia rápida **Parâmetros de opção para produtos de engenharia** aplicam-se apenas aos produtos de engenharia.

| Campo | descrição |
|---|---|
| BOM de modelo | Quando um produto com uma BOM é liberado, as linhas da BOM de modelo especificada serão adicionadas. Este campo é útil para adicionar componentes locais, como embalagem ou instruções no idioma local. |
| Roteiro de modelo | Quando um produto com uma rota é liberado, as linhas de modelo especificadas serão adicionadas. |
| Efetividade de cópia | Selecione se as datas de efetividade usadas devem ser copiadas da empresa de engenharia para a empresa operacional durante a liberação de produtos. |
| Adicionar automaticamente à proposta de liberação | Marque esta caixa de seleção para produtos que devem ser lançados automaticamente na ordem de alteração de engenharia. Dessa forma, os produtos que pertencem a categorias de produtos de engenharia que usam essa diretiva de versão podem ser liberados automaticamente para empresas operacionais nas quais essa opção é configurada. (Para obter mais informações, consulte [Gerenciar alterações de produtos de engenharia](engineering-change-management.md).)

### <a name="review-each-product-when-you-release-it"></a>Revisar cada produto ao liberá-lo

Quando produtos de engenharia que têm BOMs ou roteiros são liberados, os parâmetros são definidos para os valores padrão, conforme indicado na política de liberação. Como um usuário, você pode influenciar esse comportamento no lado da liberação ao usar a estrutura de produto de lançamento.

Para liberar produtos de engenharia, na página **Produtos liberados**, selecione os produtos a serem liberados e selecione **Liberar a estrutura de produtos** para abrir o assistente de liberação. A página **Selecionar produtos de engenharia a serem liberados** mostra os produtos. Selecione um único produto e, em seguida, selecione **Liberar detalhes** para revisar os detalhes da versão do produto.

Na página **Detalhes da versão**, você pode mudar o valor dos campos **Receber BOM**, **Copiar aprovação de BOM**, **Copiar ativação de BOM**, **Receber BOM**, **Copiar aprovação de rota** e **Copiar ativação de rota**. No cenário push-pull, você pode alterar o valor dos mesmos campos no lado de recebimento, desde que a BOM e o roteiro sejam liberados.

## <a name="product-owners-and-product-releases"></a>Proprietários de produtos e liberações de produtos

Como os proprietários de produtos sabem quais entidades legais precisam de seus produtos, um produto pode ser liberado somente pelos membros do grupo do proprietário do produto do produto. Outros usuários não podem liberar produtos que não são de sua propriedade.

Esse comportamento se aplica somente quando um produto é selecionado diretamente para liberação. Os produtos que fazem parte da estrutura de outro produto por meio de uma BOM *podem* ser liberados por usuários não proprietários ao liberar o produto pai, desde que eles tenham o produto pai.

Por exemplo, o produto X é atribuído ao grupo de proprietários de produtos *Projetar gabinetes*. O produto X também faz parte da BOM do produto Y, que é atribuída ao grupo de proprietários de produtos de *Design de alto-falantes*. Se um usuário do grupo de proprietários de produtos *Design de alto-falantes* lançar o produto Y e sua BOM, o produto X será liberado junto com o produto Y.

Para obter mais informações, consulte [Proprietários do produto](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
